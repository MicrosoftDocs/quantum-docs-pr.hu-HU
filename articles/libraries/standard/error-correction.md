---
title: 'Q # standard könyvtárak – hibajavítás | Microsoft Docs'
description: 'Q # standard könyvtárak – hibajavítás'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5aac40686ba9b45a51e0274a1828f2ff7cce6fc3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184440"
---
# <a name="error-correction"></a>Hibajavítás #

## <a name="introduction"></a>Introduction (Bevezetés) ##

A klasszikus számítástechnika esetében, ha egy kicsit a hibák ellen szeretne védeni, az adatbitek megismétlésével általában elég, ha az adott bitet egy *logikai bit* jelzi.
Például hagyja, hogy a $ \overline{0} = $0 legyen az adatmennyiség 0 kódolása, ahol a 0. címkénél nagyobb sort használunk, amely azt jelzi, hogy egy kicsit a 0 állapotú kódolású.
Ha hasonlóan hagyjuk a $ \overline{1} = $111-et, akkor egy egyszerű ismétlődési kód áll rendelkezésére, amely egy kicsit megfricskázó hiba ellen nyújt védelmet.
Azaz ha a három bit bármelyike tükrözött, akkor a logikai bitek állapotát többségi szavazással helyreállítjuk.
Bár a klasszikus hibajavítás sokkal gazdagabb téma, hogy ez az adott példa (azt javasoljuk, hogy tegyük a [kódolási elmélet bevezetését](https://www.springer.com/us/book/9783540641339)), a fenti ismétlődési kód már a kvantum-információk védelmének lehetséges problémájára mutat.
A [nem klónozási tétel](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) azt jelenti, hogy ha az egyes qubit mértékét méri, és a fentiekben a klasszikus kódokhoz hasonló többségi szavazást végez, akkor elveszítettük a védelemmel ellátott pontos információkat.

A kvantum beállításban láthatjuk, hogy a mérték problémás. A fenti kódolás továbbra is megvalósítható.
Hasznos, ha szeretné megtudni, hogyan általánosíthatja a hibajavítást a kvantum-esetre.
Így tehát a $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, és hagyja $ \ket{\overline{1}} = \ket{111}$.
Ezt követően a linearitás alapján meghatározjuk az összes bemenet ismétlődési kódját; például: $ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\sqrt{2} = (\ket{000} + \ket{111})/\sqrt{2}$.
Különösen, ha egy kicsit flip hiba $X _1 $ művelet a középső qubit, azt látjuk, hogy mindkét ág esetében pontosan $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (X_1 \ket{000} + X_1 \ket @no__ t_3_ \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{010} + \ket{101} \right).
\end{align} $ $

Ha szeretné megtudni, hogy miként azonosítható, hogy ez a helyzet a védelemre kerülő állapot mérése nélkül, hasznos, ha leírjuk, hogy milyen módon történik a különböző áttekintő hibák használata a logikai állapotokban:

| Hiba $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ |

Ahhoz, hogy megvédje a kódoláshoz szükséges állapotot, meg kell tudni különböztetni a három hibát egymástól és a $ \boldone $ identitástól a $ \ket{\overline{0}} $ és a $ \ket{\overline{1}} $ érték megkülönböztetése nélkül.
Ha például a $Z _0 $ értéket mérjük, akkor a No-Error esetben a $ \ket{\overline{0}} $ és a $ \ket{\overline{1}} $ értékhez egy másik eredményt kapunk, amely Összecsukja a kódolt állapotot.
Másfelől érdemes megfontolni a $Z _0 Z_1 $ mérését, amely az első két bit paritását adja meg minden számítási alapon.
Ne felejtse el, hogy a Pauli-operátorok minden mérése ellenőrzi, hogy a sajátérték a mért állapot megfelel-e, így a fenti táblázatban szereplő összes \ket{\psi} $ értéknél kiszámítjuk $Z _0 Z_1 \ket{\psi} $ értéket, hogy a $ \pm\ket{\psi} $ lekérése megtörténjen-e.
Vegye figyelembe, hogy $Z _0 Z_1 \ket{000} = \ket{000}$, és a $Z _0 Z_1 \ket{111} = \ket{111}$, így azt a következtetést tartjuk, hogy ez a mérték ugyanaz, mint a kódolt állapotok esetében is.
Másfelől $Z _0 Z_1 \ket{100} =-\ket{100}$ és $Z _0 Z_1 \ket{011} =-\ket{011}$, így a $Z _0 Z_1 $ mérés eredménye azt mutatja, hogy milyen hiba történt.

Ennek kiemeléséhez ismételje meg a fenti táblázatot, de adja hozzá a $Z _0 Z_1 $ és a $Z _1 Z_2 $ mérés eredményét minden egyes sorban.
Az egyes mérések eredményeit a megfigyelt sajátérték ($ + $ vagy $-$) jelöléssel jelöljük, amely megfelel a Q # `Result` `Zero` és `One`értékének.

| Hiba $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | $Z _0 Z_1 $ eredményének eredménye | $Z _1 Z_2 $ eredményének eredménye |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

Így a két mérés eredménye egyedi módon meghatározza, hogy melyik bit-flip hiba történt, de nem tárt fel semmilyen információt arról, hogy melyik állapotot kódoljuk.
Ezeket az eredményeket egy *szindrómát*hívjuk, és a szindrómát visszaképező hibára utalunk, amely a *helyreállítást*okozta.
Különösen hangsúlyozjuk, hogy a helyreállítás egy *klasszikus* következtetési eljárás, amely a bekövetkezett szindrómát veszi át, és az esetlegesen előforduló hibák kijavításának módját adja vissza.

> [!NOTE]
> A fenti bit-flip kód csak egybites tükrözési hibákra képes. Ez egy `X` művelet, amely egyetlen qubit működik.
> A `X` alkalmazása több qubit esetén az $ \ket{\overline{0}} $ és $ \ket{\overline{1}} $ leképezhető a helyreállítás után.
> Hasonlóképpen, egy fázis-tükrözési művelet alkalmazása `Z` leképezi a $ \ket{\overline{1}} $ értéket a $-\ket{\overline{1}} $ értékre, és így a $ \ket{\overline{+}} $ \ket{\overline{-}} $-t fogja leképezni.
> Általánosabban a kódok nagyobb számú hiba kezelésére és $Z $ hibák, valamint $X $ hibák kezelésére használhatók.

A lényege a *stabilizátor formalitása*, amely leírja, hogy leírható a kvantum-hibajavítások olyan mérőszámai, amelyek az összes kód állapotával azonos módon működnek.
A Q # Canon olyan keretrendszert biztosít, amely leírja a stabilizátor-kódok kódolását és dekódolását, valamint leírja, hogyan történik az egyik helyreállítás a hibákból.
Ebben a szakaszban ezt a keretrendszert és annak alkalmazását néhány egyszerű kvantum-hiba – a kódok kijavítani.

> [!TIP]
> A stabilizátorok formális bevezetésének teljes bemutatása meghaladja a jelen szakasz hatókörét.
> A [Gottesman 2009](https://arxiv.org/abs/0904.2557)-re vonatkozó további információkért tekintse meg az olvasók érdeklődését.

## <a name="representing-error-correcting-codes-in-q"></a>Hibakódot jelölő kód kijavítani a Q-ban # ##

A Q # Canon számos különböző, felhasználó által definiált típust biztosít a hibák kijavított kódjának megadásához:

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: azt jelzi, hogy a qubits-regisztrációt egy hibajavítási kód kódjának blokkjának kell értelmezni.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: azt jelzi, hogy a mérési eredmények tömbjét úgy kell értelmezni, mint a kód blokkban mért szindrómát.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: azt jelzi, hogy egy *klasszikus* függvényt kell használni a szindrómák értelmezéséhez, és az alkalmazandó korrekciót kell visszaadnia.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: azt jelzi, hogy egy művelet qubits az adatok ábrázolásával, valamint a friss Ancilla-qubits, hogy egy hibakódot hozzon létre egy hibajavítási kód alapján.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: azt jelzi, hogy egy művelet lebontja a hibakódot az adatok qubits és a Ancilla használt qubits.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: egy olyan műveletet jelöl, amelynek használatával a rendszer egy kód blokkból Kinyeri a szindrómával kapcsolatos információkat anélkül, hogy zavarja a kód által védett állapotot.

Végül a Canon biztosítja a <xref:microsoft.quantum.errorcorrection.qecc> típust a kvantum-hibák meghatározásához szükséges egyéb típusok összegyűjtéséhez. Az egyes stabilizátorok kvantum-kódjához társítva a kód hossza $n $, a logikai qubits száma $k $, valamint a minimális távolság $d $, amely gyakran kényelmesen csoportosítható a ⟦ $n $, $k $, $d $ ⟧. A <xref:microsoft.quantum.errorcorrection.bitflipcode> függvény például a ⟦ 3, 1, 1 ⟧ bitet definiálja:

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

Ha a kód ily módon van definiálva, a hibákból való helyreállításhoz a <xref:microsoft.quantum.errorcorrection.recover> műveletet is használhatja:

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

Ezt részletesebben is megvizsgáljuk a [bit flip Code-mintában](https://github.com/Microsoft/Quantum/tree/master/Samples/src/BitFlipCode).

A bit-flip code-on kívül a Q # Canon az [öt qubit tökéletes kód](https://arxiv.org/abs/1305.08)megvalósításával és a [Seven-qubit kóddal](https://arxiv.org/abs/quant-ph/9705052)van ellátva, amelyek közül mindkettő kiválaszthat egy tetszőleges, egyetlen qubit hibát.
