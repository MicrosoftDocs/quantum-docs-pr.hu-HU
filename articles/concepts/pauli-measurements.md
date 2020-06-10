---
title: Pauli-mérések
description: Ismerje meg, hogyan dolgozhat egyetlen és több qubit Pauli-mérési művelettel.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630303"
---
# <a name="pauli-measurements"></a>Pauli-mérések

Az előző megbeszélésekben a számítási szempontok alapján történik a mérés.
Valójában más gyakori mérések történnek a kvantum-számítástechnikaban, amelyek egy adott szempontból megfelelőek a számítási szempontok alapján.
Ahogy dolgozik a Q #-ban, a leggyakoribb mérések valószínűleg *Pauli-mérések*lesznek, ami általánosítja a számítási alapjait, hogy más alapértékekre, valamint a különböző qubits közötti paritásos méréseket is tartalmazzon.
Ilyen esetekben gyakori, hogy megbeszéljük a Pauli-operátorok mérését, általában egy operátort (például $X, Y, Z $ vagy $Z \otimes Z, x \otimes x, x \otimes Y stb $ .).

> [!TIP]
> A Q #-ban a többszörös qubit Pauli-operátorokat általában típusú tömbök jelölik `Pauli[]` .
> Ha például az $X \otimes Z \otimes Y jelölését szeretné $ használni, használhatja a tömböt `[PauliX, PauliZ, PauliY]` .

A kiértékelése a Pauli-operátorok esetében különösen gyakori a kvantum-hibák helyesbítésének almezőjében.
A Q #-ban egy hasonló konvenciót követünk. most a mérések alternatív nézetét magyarázjuk.

A Pauli-mérések részleteinek megismerése előtt érdemes meggondolni, hogy a kvantum-számítógépeken belüli egyetlen qubit hogyan mérhető a kvantum állapot.
Képzelje el, hogy $n $ qubit Quantum állapottal rendelkezik, majd az egyik qubit azonnal kiszámítja a $2 ^ n $ lehetőség felét, amelyet az állapot tartalmazhat.
Ez azt jelenti, hogy a mérték a kvantum-állapotot a két fél szóköz egyikére vetíti.
Általánosíthatja a mérést úgy gondoljuk, hogy ezt az adatelemzést is figyelembe vesszük.

Az alterületek tömör azonosításához szükség van egy nyelvre a leírásához.
A két alterület leírásának egyik módja, ha egy olyan mátrixon keresztül adja meg őket, amely csak két egyedi eigenvalues rendelkezik, az egyezmény szerint pedig $ \pm 1 $ .
Az alterületek ily módon történő leírásának egyszerű példája $Z $ :

$ $ \begin{align}
  Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .
\end{align}
$$

A Pauli-$Z mátrix átlós elemeinek beolvasásával $ láthatjuk, hogy $Z $ két eigenvectors, $ \ket{0 } $ és $ \ket{1 } $ értékű, a megfelelő eigenvalues $ \pm 1 $ .
Így ha mérjük a qubit és a beszerzést `Zero` (amely a $ \ket{0 $ értéknek felel meg } ), tudjuk, hogy a qubit állapota a $Z operátor $ + 1 $ eigenstate $ .
Hasonlóképpen, ha beszerezhetjük `One` , tudjuk, hogy a qubit állapota a $Z $-1 $ eigenstate $ .
Ezt a folyamatot a Pauli-mérések nyelvén nevezzük a "Pauli $Z mérésének" kifejezésnek $ , és teljes mértékben egyenértékűek a számítási alapokra vonatkozó mérések végrehajtásával.

A \times $ $Z egységes átalakítására alkalmas bármely $2 2 mátrix $ megfelel ennek a feltételnek is.
Ez azt is megteheti, hogy használhatunk egy Matrix $A = U ^ \dagger Z U $ -t, ahol a $U $ bármely más egységes mátrix, amely egy olyan mátrixot biztosít, amely meghatározza egy mérték két eredményét a $ \pm 1 $ eigenvectors.
A Pauli-mérések jelölése erre az egységes egyenértékűségre hivatkozik, ha a $X, Y, Z $ méréseket egyenértékű mértékegységként azonosítja, amelyet egy qubit származó információk megszerzéséhez lehet tenni.
Ezek a mérések az alábbiakban láthatók a kényelem érdekében.


|Pauli-mérés  |Egységes átalakítás  |
|-------------------|------------------------|
| $Z$               | \boldone USD$             |
| $X$               | $H$                    |
| $Y$               | $HS ^ {\dagger}$         |

Ez a nyelv használata esetén a "mérték $Y $ " egyenértékű a $HS ^ \dagger alkalmazásával, $ majd a számítási alap mérésével, ahol a [`S`](xref:microsoft.quantum.intrinsic.s) belső kvantum-művelet néha "Phase Gate", és az egységes mátrix szimulálható.

$ $ \begin{align}
    S = \begin{bmatrix}
        1 & 0 \\ \\ 0 & \end{ bmatrix } .
\end{align}
$$

Ezzel egyenértékű a $HS ^ \dagger $ a kvantum-állapot vektorára való alkalmazásával, majd a $Z mérésével is $ , hogy a következő művelet egyenértékű legyen `Measure([PauliY], [q])` :

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

A megfelelő állapotot a rendszer úgy fogja megtalálni, hogy visszaalakítja a számítási alapot, amely a Quantum State Vector $SH alkalmazására vonatkozik $ ; a fenti kódrészletben a blokk használatával automatikusan kezeli az átalakítást a számítási alapra `within … apply` .

A Q #-ban azt mondjuk, hogy az eredmény---az a klasszikus információ, amelyet a rendszer az állapottal való interakcióból kinyert--- `Result` $j \in \\ {\Texttt{Zero } , \texttt{One} $, amely azt jelzi, hogy az eredmény szerepel-e a } \\ Pauli operátor által mért $ (-1) ^ j $ eigenspace.


## <a name="multiple-qubit-measurements"></a>Többszörös qubit mérések

A több-qubit Pauli-operátorok mérései hasonló módon vannak definiálva, ahogy a következőkben is látható:

$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 0&0&0&\\\\ 1 \end { bmatrix } .
$$

Így a kétféle Pauli-$Z-kezelők kétféle, a $ $ + 1 $ és a $-1 eigenvalues tartalmazó mátrixot alkotnak $ .
Az qubit esethez hasonlóan mindkettő fél helyet jelent, ami azt jelenti, hogy az elérhető vektor területének fele a $ + 1 $ eigenspace és a fennmaradó fele a $-1 eigenspace-hez tartozik $ .
Általánosságban elmondható, hogy a kéttényezős termék definíciója alapján a Pauli-$Z $ operátorok és az identitások bármely tenser terméke is engedelmeskedik.
Példa:

$ $ \begin{align}
    Z \otimes \boldone = \begin{bmatrix}
        1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 0 \\ \\ & 0 & 0 &-1 \end{ bmatrix } .
\end{align}
$$

Ahogy korábban is, az ilyen mátrixok egységes átalakítása a $ \pm 1 eigenvalues címkével ellátott két fél szóközt is ismerteti $ .
Például $X \otimes X = h \otimes h (z \otimes z) h h \otimes $ az identitásból, amely $Z = HXH $ .
Az qubit esethez hasonlóan mind a két qubit (Pauli) mérések írhatók, mint $U ^ \dagger (Z \otimes \id) U $ $4 \times 4 $ egységes mátrixokhoz $U $ . A következő táblázatban szereplő transzformációk enumerálása.

> [!NOTE]
> Az alábbi táblázatban a $ \operatorname{SWAP $ értéket használjuk } a Matrix $ $ \begin{align jelzésére}
>     \operatorname{SWAP } & = \left (\begin{Matrix}
>         1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}
> a $ $ a belső művelet szimulálása céljából használatos [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pauli-mérés     |Egységes átalakítás  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $X \otimes \boldone$ | $H \otimes \boldone$ |
| $Y \otimes \boldone$ | $HS ^ \dagger \otimes \boldone$ |
| $ \boldone \otimes Z$ | \operatorname{SWAP USD}$ |
| $ \boldone \otimes X$ | $ (H \otimes \boldone) \operatorname{swap}$ |
| $ \boldone \otimes Y$ | $ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$ |
| $Z \otimes Z$ | $ \operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $ |
| $Y \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (hs ^ \dagger \otimes \boldone) $ |
| $Z \otimes X$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $ |
| $X \otimes X$ | $ \operatorname{CNOT } \_ {10 } (h \otimes h) $ |
| $Y \otimes X$ | $ \operatorname{CNOT } \_ {10 } (hs ^ \dagger \otimes H) $ |
| $Z \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $ |
| $Y \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (hs ^ \dagger \otimes HS ^ \dagger) $ |

Itt a [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) művelet a következő okból jelenik meg.
Minden olyan Pauli-mérés, amely nem tartalmazza a $ \boldone $ mátrixot, egyenértékű a \otimes $ fenti indoklással $Z Z értékkel.
A ( \otimes Z) $Z Z eigenvalues $ csak az egyes számítási alapú vektorokat alkotó qubits paritása függ, és a vezérelt nem műveletek szolgálnak a paritás kiszámításához és az első bites tároláshoz.
Ezután az első bit mérése után helyreállítjuk az eredményül kapott fél terület identitását, amely egyenértékű a Pauli-operátor mérésével.

Egy további Megjegyzés: Ha úgy gondolja, hogy a $Z Z mérése \otimes $ megegyeznek a $Z \otimes \mathbb{1 } $, majd a $ \mathbb{1 \otimes Z értékkel } , akkor $ Ez a feltételezés hamis lenne.
Ennek az az oka, hogy az $Z \otimes Z $ -projekteket a kvantum-állapottal mérjük a $ fenti operátorok $ + 1 vagy $-1 $ eigenstate.
$Z \otimes \mathbb{1 } $, majd a $ \Mathbb{1 } \otimes Z $ projekt mérésével a quantum State Vector először $Z \otimes \mathbb{1 $, majd a } $ \mathbb{1 } \otimes Z egy fél $ területére kerül. Mivel négy számítási alap vektor létezik, mindkét mérés végrehajtása csökkenti az állapotot egy negyedéves területre, és így csökkenti azt egyetlen számítási célú vektorban.

## <a name="correlations-between-qubits"></a>Qubits közötti korrelációk
A Pauli-mátrixok (például $X X vagy $Z Z) tízesebb termékeinek mérésének egy másik módja, \otimes $ \otimes $ hogy ezek a mérések lehetővé teszik a két qubits közötti összefüggésekben tárolt információk megkeresését.
$X \id mérésével \otimes $ megtekintheti az első qubit helyileg tárolt adatokat.
Habár a kvantum-számítástechnika mindkét típusú mérése egyenlően értékes, a korábbi megvilágítja a kvantum-számítástechnika erejét.
Ez azt mutatja, hogy a kvantum-számítástechnikaban gyakran a tanulni kívánt információ nem egyetlen qubit van tárolva, hanem nem helyileg, hanem az összes qubits, és ezért csak egy közös mérésen (pl. $Z \otimes Z) keresztül történik $ .

A hibajavítás során például gyakran szeretnénk megismerni, hogy milyen hibák történtek, miközben a rendszer nem a védelemmel ellátott állapotról tanul.
A [bit-flip Code](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) példa azt szemlélteti, hogyan teheti meg a méréseket, például a $Z \otimes Z \otimes \id $ és a $ \id \Otimes z \otimes z $ .
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Tetszőleges Pauli-operátorok, például $X \otimes Y \Otimes Z \otimes \boldone $ is mérhetők.
A Pauli-operátorok összes ilyen tenser-terméke csak két eigenvalues $ \pm 1 $ , míg mindkét eigenspaces a teljes vektoros terület felét képezi.
Így a fent említett követelmények egybeesnek.

A Q #-ban az ilyen mérések $j, $ Ha a mérés eredménye a eigenspace (-1) ^ j jel eredményét eredményezi $ .
A Q # beépített funkciójaként a Pauli-mérések használata hasznos lehet, mivel az ilyen operátorok mérése hosszú láncú, nem kapukat és átalakításokat igényel, hogy leírja a diagonalizing $U kaput, amely a $ műveletnek a $Z $ és a $ \id tenser-termékként való kifejezéséhez szükséges $ . Az előre definiált mérések egyikének megadásához nem kell aggódnia, hogy hogyan alakíthatja át az adatokat, hogy a számítási alap a szükséges információkat tartalmazza.
A Q # az összes szükséges átalakítást automatikusan kezeli.
További információ: [`Measure`](xref:microsoft.quantum.intrinsic.measure) és [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) műveletek.

## <a name="the-no-cloning-theorem"></a>A klónozás nélküli tétel

A Quantum információi hatékonyak.
Lehetővé teszi, hogy elképesztően olyan dolgokat végezzenek, mint a faktorok száma exponenciálisan, mint a legismertebb klasszikus algoritmusok, vagy hatékonyan szimulálja a korrelált elektron-rendszereket, amelyekkel a klasszikusan exponenciálisan kell szimulálni a pontos műveleteket.
A kvantum-számítástechnika hatékonysága azonban korlátozott.
Az egyik ilyen korlátozást a *nem klónozási tétel*adja meg.

A nem klónozási tétel találó elnevezésű.
Az általános kvantum-állapotok egy kvantum-számítógép általi klónozását nem teszi lehetővé.
A tétel bizonyítása rendkívül egyszerű.
Habár a nem klónozási tétel teljes bizonyítéka egy kicsit túl technikai a vitánk számára, a további kiegészítő qubits hiánya nem a hatókörön belül van (a kiegészítő qubits a számítás során qubits használják, és könnyen használhatók és kezelhetők a Q #-ban, lásd a [kölcsönzött qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

Egy ilyen kvantum-számítógép esetében a klónozási műveletet egy egységes mátrixtal kell ismertetni.
Megtiltjuk a mérést, mivel az sérült a klónozott állapotot.
A klónozási művelet szimulálása érdekében azt szeretnénk, hogy az egységes mátrix a $ $ U \ket { \psi } \ket{0 } = \ket { \psi } { \ket \psi}
$ $ minden állapothoz $ \ket { \psi } $.
A mátrix szorzásának lineáris tulajdonsága azt jelenti, hogy bármely második kvantum-állapothoz $ \ket { \phi } $,

$ $ \begin{align}
    U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}
        \right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).
\end{align}
$$

Ez biztosítja az alapvető intuíciót a nem klónozási tétel mögött: minden olyan eszközön, amely egy ismeretlen kvantum-állapotot másol, a hibákat legalább néhány, az általa használt állapotból kell kiváltani.
Míg a legfontosabb feltételezés, hogy a Cloner lineárisan működik a bemeneti állapoton, megsértheti a kiegészítő qubits hozzáadását és mérését, az ilyen interakciók pedig a mérési statisztikán keresztül a rendszerre vonatkozó információkat is felhasználhatják, és meggátolják az ilyen esetekben történő pontos klónozást is.
A nem klónozási tétel részletesebb igazolását a [További tudnivalókat](xref:microsoft.quantum.more-information)ismertető témakörben talál.

A nem klónozási tétel fontos a kvantum-számítástechnika minőségi megismerése érdekében, mert ha a kvantum-állapotok költséges klónozását, akkor közel varázslatos képességet kap a kvantum-állapotok megismeréséhez.
Valójában megsértheti a Heisenberg hencegő bizonytalansági elvét.
Azt is megteheti, hogy az optimális Cloner használatával egyetlen mintát vesz igénybe egy összetett kvantum-eloszlásból, és megtudhatja, hogy az adott disztribúcióról csak egyetlen mintából lehet tájékozódni.
Ez olyan lenne, mint egy érme tükrözése és a fejek betartása, majd egy barátomnak szól az eredményről, amelyeknek válaszoltak "Ah az érme eloszlásának Bernoulli kell lennie $p = 0.512643 \ ldots $ !"  Egy ilyen utasítás nem sensical, mert egy kis információ (a fejek végeredménye) egyszerűen nem tudja biztosítani az elosztás kódolásához szükséges több bitet a jelentős előzetes információk nélkül.
Hasonlóképpen, az előzetes információk nélkül nem tudjuk tökéletesen klónozott állapotba állítani a kvantum-állapotot, mivel nem tudjuk felkészíteni az ilyen érmék együttesét anélkül, hogy $p tudnánk $ .

Az információk nem ingyenesek a Quantum Computing szolgáltatásban.
A mért qubit egyetlen kis mennyiségű információt biztosítanak, a nem klónozási tétel pedig azt mutatja, hogy nincs olyan hátsó ajtó, amely felhasználható a rendszerről szerzett információk és a meghívott zavarok közötti alapvető kompromisszum megszerzéséhez.
