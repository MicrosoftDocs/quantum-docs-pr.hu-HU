---
title: Pauli-mérések
description: Pauli-mérések
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 300a1ebcfd5d7bca8b025c69adebaad03106433d
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036600"
---
# <a name="pauli-measurements"></a>Pauli-mérések

Az előző megbeszélésekben a számítási szempontok alapján történik a mérés.
Valójában más gyakori mérések történnek a kvantum-számítástechnikaban, amelyek egy adott szempontból megfelelőek a számítási szempontok alapján.
Ahogy dolgozik a Q #-ban, a leggyakoribb mérések valószínűleg *Pauli-mérések*lesznek, ami általánosítja a számítási alapjait, hogy más alapértékekre, valamint a különböző qubits közötti paritásos méréseket is tartalmazzon.
Ilyen esetekben gyakori, hogy megbeszéljük a Pauli-operátorok mérését, általában egy operátort, például $X, Y, Z $ vagy $Z \otimes Z, X\otimes X, X\otimes Y $ és így tovább.

> [!TIP]
> A Q #-ban a többszörös qubit Pauli-operátorokat általában `Pauli[]`típusú tömbök jelölik.
> Ha például az $X \otimes Z \otimes Y $ jelölést szeretné ábrázolni, használhatja a tömböt `[PauliX, PauliZ, PauliY]`.

A kiértékelése a Pauli-operátorok esetében különösen gyakori a kvantum-hibák helyesbítésének almezőjében.
A Q #-ban egy hasonló konvenciót követünk. most a mérések alternatív nézetét magyarázjuk.

A Pauli-mérések részleteinek megismerése előtt érdemes meggondolni, hogy a kvantum-számítógépeken belüli egyetlen qubit hogyan mérhető a kvantum állapot.
Képzelje el, hogy van egy $n qubit kvantum-állapota; Ezután az egyik qubit mérése azonnal kiírja a $2 ^ n $ lehetőség felét, amely az állapot lehet.
Ez azt jelenti, hogy a mérték a kvantum-állapotot a két fél szóköz egyikére vetíti.
Általánosíthatja a mérést úgy gondoljuk, hogy ezt az adatelemzést is figyelembe vesszük.

Az alterületek tömör azonosításához szükség van egy nyelvre a leírásához.
A két alterület leírásának egyik módja, ha egy olyan mátrixon keresztül adja meg őket, amely csak két egyedi eigenvalues rendelkezik, a konvenciók szerint a $1 $ \pm.
Az alterületek ily módon történő leírásának egyszerű példája $Z $:

$ $ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
\end{align} $ $

A Pauli-$Z $ Matrix átlós elemeinek olvasásával láthatjuk, hogy a $Z $ két eigenvectors, $ \ket{0}$ és $ \ket{1}$, a megfelelő eigenvalues $ \pm $1.
Így ha mérjük a qubit, és beszerezzük `Zero` (amely a $ \ket{0}$) állapotnak felel meg, akkor tudjuk, hogy a qubit állapota a $Z $ operátor $ + $1 eigenstate.
Hasonlóképpen, ha `One`beszerzését, tudjuk, hogy a qubit állapota a $Z $ $-$1 eigenstate.
Ezt a folyamatot a Pauli-mérések a "Pauli $Z $" mérésének nyelvén hívják, és teljes mértékben egyenértékűek a számítási alap mérésével.

Minden $2 \ Times $2 mátrix, amely a $Z $ egységes átalakítása, szintén megfelel ennek a feltételnek.
Ez azt is megteheti, hogy használhatunk egy Matrix $A = U ^ \dagger Z U $ értéket, ahol a $U $ bármely más, az egységes mátrix, amely egy mérés két eredményét határozza meg a $ \pm $1 eigenvectors.
A Pauli-mérések jelölése erre az egységes egyenértékűségre hivatkozik, ha a $X, Y, Z
Ezek a mérések az alábbiakban láthatók a kényelem érdekében.


|Pauli-mérés  |Egységes átalakítás  |
|-------------------|------------------------|
| $Z $               | $ \boldone $             |
| $X $               | $H $                    |
| $Y $               | $HS ^ {\dagger} $         |

Ennek a nyelvnek a használata esetén a "mérték $Y $" egyenértékű a $HS ^ \dagger $ és a számítási számítások alapján, ahol a [`S`](xref:microsoft.quantum.intrinsic.s) egy belső kvantum-művelet, amelyet néha "Phase Gate"-nek neveznek, és az egységes mátrix szimulálható

$ $ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.
\end{align} $ $

A $HS ^ \dagger $ értéket is alkalmazza a kvantum állapot vektorára, majd a $Z $ mérésére, hogy a következő művelet egyenértékű legyen `Measure([PauliY], [q]])`:

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

A megfelelő állapotot a rendszer úgy fogja megtalálni, hogy visszaalakítja a számítási alapot, és a $SH $ értéket alkalmazza a kvantum-állapot vektorára; a fenti kódrészletben a `within … apply` blokk használatával automatikusan kezeli az átalakítást a számítási alapra.

A Q #-ban azt mondjuk, hogy az eredmény---az, hogy a---állapottal való interakcióból kinyert klasszikus információ `Result` érték $j \in \\{\texttt{Zero}, \texttt{One}\\} $ értéket, amely azt jelzi, hogy az eredmény a Pauli operátor által mért $ (-1) ^ j $ eigenspace van megadva.


## <a name="multiple-qubit-measurements"></a>Többszörös qubit mérések

A több-qubit Pauli-operátorok mérései hasonló módon vannak definiálva, ahogy a következőkben is látható:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ End {bmatrix}.
$$

Így a két Pauli-$Z $ operátorral rendelkező kétféle, a két szóközből álló mátrix a $ + $1 és a $-$1 eigenvalues áll.
Az qubit esethez hasonlóan mindkettő fél helyet jelent, ami azt jelenti, hogy az elérhető vektor területének fele a $ + $1 eigenspace és a fennmaradó fele a $-$1 eigenspace-hez tartozik.
Általánosságban elmondható, hogy a kéttényezős termék definíciója alapján a Pauli-$Z $ operátorok és az identitás a következőt is betartja.
Például:

$ $ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 &-1 & 0 \\\\ 0 & 0 & 0 &-1 \end{bmatrix}.
\end{align} $ $

Ahogy korábban is, az ilyen mátrixok egységes átalakítása a $ \pm $1 eigenvalues által címkézett két fél szóközt is ismerteti.
Például $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ értéket az identitásból, amely $Z = HXH $.
Az qubit esethez hasonlóan mind a két qubit (Pauli) mérések írhatók $U ^ \dagger (Z\otimes \id) U $ for $4 \ Times $4 egységes mátrixok $U $ használatával. A következő táblázatban szereplő transzformációk enumerálása.

> [!NOTE]
> Az alábbi táblázatban a $ \operatorname{SWAP} $ értéket használjuk, hogy jelezze a következő mátrixot: $ $ \begin{align} \operatorname{SWAP} & = \left (\begin{Matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{Matrix}\right) \end{align} $ $ a belső művelet [`SWAP`](xref:microsoft.quantum.intrinsic)szimulálása céljából.

|Pauli-mérés     |Egységes átalakítás  |
|----------------------|------------------------|
| $Z \otimes \boldone $ | $ \boldone \otimes \boldone $ |
| $Z \otimes \boldone $ | $ \boldone\otimes \boldone $ |
| $X \otimes \boldone $ | $H \otimes \boldone $ |
| $Y \otimes \boldone $ | $HS ^ \dagger\otimes \boldone $ |
| $ \boldone \otimes Z $ | $ \operatorname{SWAP} $ |
| $ \boldone \otimes X $ | $ (H\otimes \boldone) \operatorname{SWAP} $ |
| $ \boldone \otimes Y $ | $ (HS ^ \dagger\otimes \boldone) \operatorname{SWAP} $ |
| $Z \otimes Z $ | $ \operatorname{CNOT}\_{10}$ |
| $X \otimes Z $ | $ \operatorname{CNOT}\_{10}(H\otimes \boldone) $ |
| $Y \otimes Z $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone) $ |
| $Z \otimes X $ | $ \operatorname{CNOT}\_{10}(\boldone\otimes H) $ |
| $X \otimes X $ | $ \operatorname{CNOT}\_{10}(H\otimes H) $ |
| $Y \otimes X $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H) $ |
| $Z \otimes Y $ | $ \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y $ | $ \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger) $ |
| $Y \otimes Y $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger) $ |

Itt a [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) művelet a következő okból jelenik meg.
Minden olyan Pauli-mérés, amely nem tartalmazza a $ \boldone $ mátrixot, egyenértékű a fenti indoklással $Z \otimes Z $ értékkel.
A $Z \otimes Z $ eigenvalues csak a qubits paritása függ az egyes számítási feladatokból álló vektorok méretétől, és a felügyelt nem műveletek a paritás kiszámítására szolgálnak, és az első bit tárolja azt.
Ezután az első bit mérése után helyreállítjuk az eredményül kapott fél terület identitását, amely egyenértékű a Pauli-operátor mérésével.

Egy további Megjegyzés: Ha azt feltételezi, hogy a $Z \otimes Z $ érték mérése megegyeznek a $Z \otimes \mathbb{1}$, majd a $ \mathbb{1} \otimes Z $ értékkel, ez a feltételezés hamis lenne.
Ennek az az oka, hogy a $Z \otimes Z $-projektek a kvantum-állapotot a fenti operátorok $ + $1 vagy $-$1 eigenstate mérik.
$Z \otimes \mathbb{1}$, majd a $ \mathbb{1} \otimes Z $ projektek mérésével a Quantum State Vector először egy fél $Z \otimes \mathbb{1}$-re, majd a $ \mathbb{1} \otimes Z $-ra.
Mivel négy számítási alap vektor létezik, mindkét mérés végrehajtása csökkenti az állapotot egy negyedéves területre, és így csökkenti azt egyetlen számítási célú vektorban.

## <a name="correlations-between-qubits"></a>Qubits közötti korrelációk
A Pauli-mátrixok (például $X \otimes X $ vagy $Z \otimes Z $) mérésének egy másik módja, hogy ezek a méretek lehetővé teszik a két qubits közötti összefüggésekben tárolt információk megtekintését.
$X \otimes \id $ mérésével megtekintheti az első qubit helyileg tárolt információit.
Habár a kvantum-számítástechnika mindkét típusú mérése egyenlően értékes, a korábbi megvilágítja a kvantum-számítástechnika erejét.
Ez azt mutatja, hogy a kvantum-számítástechnikaban gyakran a tanulni kívánt információ egyetlen qubit van tárolva, de nem helyileg, hanem az összes qubits, és így csak egy közös mérésen (például $Z \otimes Z $) keresztül történik. az információk jegyzékbe válnak.

A hibajavítás során például gyakran szeretnénk megismerni, hogy milyen hibák történtek, miközben a rendszer nem a védelemmel ellátott állapotról tanul.
A [bit-flip Code](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) példa azt szemlélteti, hogyan teheti meg a méréseket, például az $Z \otimes Z \otimes \id $ és a $ \Id \otimes Z \otimes z $.
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Az önkényes Pauli-operátorok, például a $X \otimes Y \otimes Z \otimes \boldone $ is mérhetők.
A Pauli-operátorok összes ilyen tenser-terméke csak két eigenvalues $ \pm $1, és mindkét eigenspaces a teljes vektoros terület felét képezi.
Így a fent említett követelmények egybeesnek.

A Q #-ban az ilyen mérések $j $ értéket adnak vissza, ha a mérés eredménye a $ (-1) ^ j $ eigenspace eredményezi.
A Q # beépített funkciójaként a Pauli-mérések használata hasznos lehet, mert az ilyen operátorok méréséhez hosszú láncú vezérelt, nem kapuk és átalakítások szükségesek, hogy leírják a diagonalizing $U $ Gate-t, amely a műveletnek a $Z $ és $ \id $ típusú tenser-termékként való kifejezéséhez szükséges.
Az előre definiált mérések egyikének megadásához nem kell aggódnia, hogy hogyan alakíthatja át az adatokat, hogy a számítási alap a szükséges információkat tartalmazza.
A Q # az összes szükséges átalakítást automatikusan kezeli.
További információ: [`Measure`](xref:microsoft.quantum.intrinsic.measure) és [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) művelet.

## <a name="the-no-cloning-theorem"></a>A klónozás nélküli tétel

A Quantum információi hatékonyak.
Lehetővé teszi, hogy elképesztően olyan dolgokat végezzenek, mint a faktorok száma exponenciálisan, mint a legismertebb klasszikus algoritmusok, vagy hatékonyan szimulálja a korrelált elektron-rendszereket, amelyekkel a klasszikusan exponenciálisan kell szimulálni a pontos műveleteket.
A kvantum-számítástechnika hatékonysága azonban korlátozott.
Az egyik ilyen korlátozást a *nem klónozási tétel*adja meg.

A nem klónozási tétel találó elnevezésű.
Az általános kvantum-állapotok egy kvantum-számítógép általi klónozását nem teszi lehetővé.
A tétel bizonyítása rendkívül egyszerű.
Habár a nem klónozási tétel teljes bizonyítéka egy kicsit túl technikai a vitánk számára, a további kiegészítő qubits nem a hatókörön belül van (a kiegészítő qubits a számítás során qubits használják, és könnyen használhatók és kezelhetők a Q #-ban, lásd: <xref:microsoft.quantum.techniques.qubits>).

Egy ilyen kvantum-számítógép esetében a klónozási műveletet egy egységes mátrixtal kell ismertetni.
Megtiltjuk a mérést, mivel az sérült a klónozott állapotot.
A klónozási művelet szimulálása érdekében azt szeretnénk, hogy az egységes mátrix a következő tulajdonsággal rendelkezzen: $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi} $ $ bármely állapothoz $ \ket{\psi} $.
A mátrix szorzásának lineáris tulajdonsága azt jelenti, hogy bármely második kvantum-állapothoz $ \ket{\phi} $,

$ $ \begin{align} U \left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket {\ Phi} \ ket{0} + \frac{1}{\sqrt{2}} U\ket {\ PSI} \ ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right) \\\\ & \ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right) \otimes \ Left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align} $ $

Ez biztosítja az alapvető intuíciót a nem klónozási tétel mögött: minden olyan eszközön, amely egy ismeretlen kvantum-állapotot másol, a hibákat legalább néhány, az általa használt állapotból kell kiváltani.
Míg a legfontosabb feltételezés, hogy a Cloner lineárisan működik a bemeneti állapoton, megsértheti a kiegészítő qubits hozzáadását és mérését, az ilyen interakciók pedig a mérési statisztikán keresztül a rendszerre vonatkozó információkat is kiszivárgást végeznek, és megelőzik a pontos ilyen esetekben is klónozás.
A nem klónozási tétel részletesebb igazolását a [További tudnivalókat](xref:microsoft.quantum.more-information)ismertető témakörben talál.

A nem klónozási tétel fontos a kvantum-számítástechnika minőségi megismerése érdekében, mert ha a kvantum-állapotok költséges klónozását, akkor közel varázslatos képességet kap a kvantum-állapotok megismeréséhez.
Valójában megsértheti a Heisenberg hencegő bizonytalansági elvét.
Azt is megteheti, hogy az optimális Cloner használatával egyetlen mintát vesz igénybe egy összetett kvantum-eloszlásból, és megtudhatja, hogy az adott disztribúcióról csak egyetlen mintából lehet tájékozódni.
Ez olyan lenne, mint egy érme tükrözése és a fejek betartása, majd egy barátomnak szól az eredményről, amelyeknek válaszoltak "Ah az érme eloszlásának Bernoulli kell lennie $p = 0.512643 \ ldots $!"  Egy ilyen utasítás nem sensical, mert egy kis információ (a fejek végeredménye) egyszerűen nem tudja biztosítani az elosztás kódolásához szükséges több bitet a jelentős előzetes információk nélkül.
Hasonlóképpen, az előzetes információk nélkül nem tudjuk tökéletesen klónozott állapotba állítani a kvantum-állapotot, mivel nem tudjuk előkészíteni az ilyen érmék együttesét anélkül, hogy tudnám $p $-t.

Az információk nem ingyenesek a Quantum Computing szolgáltatásban.
A mért qubit egyetlen kis mennyiségű információt biztosítanak, a nem klónozási tétel pedig azt mutatja, hogy nincs olyan hátsó ajtó, amely felhasználható a rendszerről szerzett információk és a meghívott zavarok közötti alapvető kompromisszum megszerzéséhez.
