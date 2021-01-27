---
title: Hibajavítás a Q# standard könyvtárakban
description: Megtudhatja, hogyan használhatja a hibák helyességét a Q# programokban, miközben védi a qubits állapotát.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc8e46aa22cb2575de42cfc3d4f57c43e5d3f7b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857211"
---
# <a name="error-correction"></a>Hibajavítás #

## <a name="introduction"></a>Bevezetés ##

A klasszikus számítástechnika esetében, ha egy kicsit a hibák ellen szeretne védeni, az adatbitek megismétlésével általában elég, ha az adott bitet egy *logikai bit* jelzi.
Például hagyja, hogy a $ \overline {0} = $0 legyen az adatmennyiség 0 kódolása, ahol a 0. címkénél nagyobb sort használunk, jelezve, hogy az egy kicsit a 0 állapotú kódolású.
Ha hasonlóképpen hagyjuk a $ \overline {1} = $111-et, akkor egy egyszerű ismétlődési kód áll rendelkezésére, amely egy kicsit több flip-hibát véd.
Azaz ha a három bit bármelyike tükrözött, akkor a logikai bitek állapotát többségi szavazással helyreállítjuk.
Bár a klasszikus hibajavítás sokkal gazdagabb téma, hogy ez az adott példa (azt javasoljuk, hogy tegyük a [kódolási elmélet bevezetését](https://www.springer.com/us/book/9783540641339)), a fenti ismétlődési kód már a kvantum-információk védelmének lehetséges problémájára mutat.
A [nem klónozási tétel](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) azt jelenti, hogy ha az egyes qubit mértékét méri, és a fentiekben a klasszikus kódokhoz hasonló többségi szavazást végez, akkor elveszítettük a védelemmel ellátott pontos információkat.

A kvantum beállításban láthatjuk, hogy a mérték problémás. A fenti kódolás továbbra is megvalósítható.
Hasznos, ha szeretné megtudni, hogyan általánosíthatja a hibajavítást a kvantum-esetre.
Így a $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket \otimes {0} \ket {0} $, és a $ \ket{\overline {1} } = \ket $ {111} értéket kell hagyni.
Ezt követően a linearitás alapján meghatározjuk az összes bemenet ismétlődési kódját; például: $ \ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} })/\sqrt {2} = (\ket {000} + \ket {111} )/\sqrt {2} $.
Különösen, ha egy kicsit flip hiba $X _1 $ művelet a középső qubit, azt látjuk, hogy mindkét ág esetében pontosan $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left (X_1 \ket {000} + X_1 \ket {111} \right) \\ \\ & = \frac {1} {\sqrt {2} } \left (\ket {010} + \ket {101} \right).
\end{align} $ $

Ha szeretné megtudni, hogy miként azonosítható, hogy ez a helyzet a védelemre kerülő állapot mérése nélkül, hasznos, ha leírjuk, hogy milyen módon történik a különböző áttekintő hibák használata a logikai állapotokban:

| Hiba $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ |
| $X _0 $ | $ \ket {100} $ | $ \ket {011} $ |
| $X _1 $ | $ \ket {010} $ | $ \ket {101} $ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ |

Ahhoz, hogy megvédje a kódoláshoz szükséges állapotot, meg kell tudni különböztetni a három hibát egymástól és a $ \boldone $ identitástól a $ \ket{\overline {0} } $ és a $ \ket{\overline} $ érték megkülönböztetése nélkül {1} .
Ha például az $Z _0 $ értéket mérjük, akkor {0} a No-Error esetben a $ \ket{\overline} $ és a $ \ket{\overline} $ értékhez egy másik eredményt kapunk {1} , amely Összecsukja a kódolt állapotot.
Másfelől érdemes megfontolni $Z _0 Z_1 $ mérését, amely az első két bit paritását adja meg minden számítási alapon.
Ne felejtse el, hogy a Pauli-operátorok minden mérése ellenőrzi, hogy a sajátérték a mért állapot megfelel-e, így a fenti táblázatban szereplő összes \ket{\psi} $ értéknél kiszámítjuk $Z _0 Z_1 \ket{\psi} $ értéket, hogy a $ \pm\ket{\psi} $ beszerzése megtörténjen-e.
Vegye figyelembe, hogy $Z _0 Z_1 \ket {000} = \ket {000} $ és a $Z _0 Z_1 \ket {111} = \ket {111} $, így azt a következtetést tartjuk, hogy ez a mérték ugyanaz, mint a kódolt állapotok esetében is.
Másfelől $Z _0 Z_1 \ket {100} =-\ket {100} $ és $Z _0 Z_1 \ket {011} =-\ket {011} $, így a $Z _0 Z_1 $ mérésének eredménye azt mutatja, hogy milyen hiba történt.

Ennek kihangsúlyozása érdekében ismételje meg a fenti táblázatot, de adja hozzá a $Z _0 Z_1 $ és $Z _1 Z_2 $ mérésének eredményét minden egyes sorban.
Az egyes mérések eredményeit a megfigyelt sajátérték ($ + $ vagy $-$) jelöléssel jelöljük meg, amely a és a Q# `Result` értékének felel meg `Zero` `One` .

| Hiba $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | $Z _0 eredménye Z_1 $ | $Z _1 eredménye Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X _0 $ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X _1 $ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

Így a két mérés eredménye egyedi módon meghatározza, hogy melyik bit-flip hiba történt, de nem tárt fel semmilyen információt arról, hogy melyik állapotot kódoljuk.
Ezeket az eredményeket egy *szindrómát* hívjuk, és a szindrómát visszaképező hibára utalunk, amely a *helyreállítást* okozta.
Különösen hangsúlyozjuk, hogy a helyreállítás egy *klasszikus* következtetési eljárás, amely a bekövetkezett szindrómát veszi át, és az esetlegesen előforduló hibák kijavításának módját adja vissza.

> [!NOTE]
> A fenti bit-flip kód csak egybites tükrözési hibákra képes. Ez egy művelet, amely `X` egyetlen qubit működik.
> `X`Ha egynél több qubit alkalmaz, a {0} helyreállítást követően a $ \ket{\overline} $ \ket{\overline} $-t fogja leképezni {1} .
> Hasonlóképpen, ha egy fázis-tükrözési műveletet alkalmaz a `Z` $ \ket{\overline {1} } $ és a $-\ket{\overline {1} } $ értékre, és így a $ \ket{\overline{+}} $ $ \ket{\overline} $ értékre lesz leképezve {-} .
> Általánosabban a kódok nagyobb számú hiba kezelésére és $Z $ hibák, valamint $X $ hibák kezelésére használhatók.

A *stabilizátorok formalitásának* lényege, hogy betekintést nyerhetünk a kvantum-hibák kijavításának olyan mértékére, amely az összes kód állapotával azonos módon működik.
A Q# Canon olyan keretrendszert biztosít, amely leírja a stabilizátor-kódok kódolását és dekódolását, valamint leírja, hogy az egyes hibák hogyan állíthatók vissza.
Ebben a szakaszban ezt a keretrendszert és annak alkalmazását néhány egyszerű kvantum-hiba – a kódok kijavítani.

> [!TIP]
> A stabilizátorok formális bevezetésének teljes bemutatása meghaladja a jelen szakasz hatókörét.
> A [Gottesman 2009](https://arxiv.org/abs/0904.2557)-re vonatkozó további információkért tekintse meg az olvasók érdeklődését.

## <a name="representing-error-correcting-codes-in-no-locq"></a>Hiba történt a kódok helyesbítésében a következőben: Q# ##

A hibakódok megadásához a Q# Canon számos különböző, felhasználó által definiált típust biztosít:

- <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister>`= Qubit[]`: Azt jelzi, hogy a qubits-regisztrációt egy hibajavítási kód kódjának blokkjának kell értelmezni.
- <xref:Microsoft.Quantum.ErrorCorrection.Syndrome>`= Result[]`: Azt jelzi, hogy a mérési eredmények tömbjét úgy kell értelmezni, mint a kód blokkban mért szindrómát.
- <xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn>`= (Syndrome -> Pauli[])`: Azt jelzi, hogy egy *klasszikus* függvényt kell használni a szindrómák értelmezéséhez, és az alkalmazandó korrekciót vissza kell adni.
- <xref:Microsoft.Quantum.ErrorCorrection.EncodeOp>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Azt jelzi, hogy egy művelet a qubits, valamint a friss Ancilla-qubits együtt az adatok ábrázolását is elvégzi a hibajavítási kód kódjának létrehozása érdekében.
- <xref:Microsoft.Quantum.ErrorCorrection.DecodeOp>`= (LogicalRegister => (Qubit[], Qubit[]))`: Azt jelzi, hogy egy művelet lebontja a hibakódot az adatok qubits, valamint a Ancilla-qubits.
- <xref:Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp>`= (LogicalRegister => Syndrome)`: Egy olyan műveletet jelöl, amelynek használatával a rendszer egy kód blokkból Kinyeri a szindrómát, és nem zavarja a kód által védett állapotot.

Végül a Canon megadja a <xref:Microsoft.Quantum.ErrorCorrection.QECC> típust a kvantum-hiba meghatározásához szükséges egyéb típusok összegyűjtéséhez. Az egyes stabilizátorok kvantum-kódjához társítva a kód hossza $n $, a logikai qubits száma $k $, valamint a minimális távolság $d $, amely gyakran kényelmesen csoportosítható a ⟦ $n $, $k $, $d $ ⟧. A <xref:Microsoft.Quantum.ErrorCorrection.BitFlipCode> függvény például meghatározza a ⟦ 3, 1, 1 ⟧ bit flip code:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Figyelje meg, hogy a `QECC` típus *nem* tartalmaz helyreállítási funkciót.
Ez lehetővé teszi, hogy megváltoztassuk a hibák kijavításához használt helyreállítási funkciót, a kód definíciójának módosítása nélkül. Ez a képesség különösen hasznos, ha a jellemzési mérések származó visszajelzéseket a helyreállítás által feltételezett modellbe foglalja.

Ha a kód ily módon van definiálva, a következő <xref:Microsoft.Quantum.ErrorCorrection.Recover> művelettel állíthatja helyre a hibákat:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Ezt részletesebben is megvizsgáljuk a [bit flip Code-mintában](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code).

A bit-flip kód mellett a Canon az Q# [öt qubit tökéletes kód](https://arxiv.org/abs/quant-ph/9602019)és a [Seven-qubit kód](https://arxiv.org/abs/quant-ph/9705052)megvalósításával érhető el, amelyek közül mindkettő kijavítani egy tetszőleges, egyqubitos hibát.
