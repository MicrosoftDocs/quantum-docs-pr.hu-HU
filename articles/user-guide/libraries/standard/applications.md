---
title: Alkalmazások a Q# standard könyvtárakban
description: Ismerkedjen meg a Quantum Computing – Hamilton szimuláció és a rövid keresési algoritmusának két alapvető alkalmazásával.
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 115cd65621afd8272887b36163b066a4e6a554d7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835655"
---
# <a name="applications"></a>Alkalmazások #

## <a name="hamiltonian-simulation"></a>Hamilton-szimuláció ##

A kvantum-rendszerek szimulációja a kvantum-számítás legizgalmasabb alkalmazásai közé esik.
A klasszikus számítógépeken a kvantummechanika szimulálása során felmerülő nehézségek általában az állapot-vektoros ábrázolás $N $ dimenzióval méretezhetők.
Mivel ez a képviselet exponenciálisan növekszik a $n $ qubits $N = 2 ^ n $ értékkel, a [dimenzióját átka](xref:microsoft.quantum.concepts.multiple-qubits)néven ismert tulajdonság, a Quantum szimulációs a klasszikus hardveren nem vonható le.

A helyzet azonban nagyon eltérő lehet a kvantum hardveren. A kvantum-szimuláció leggyakoribb változata az idő-független Hamilton-szimulációs probléma. Itt az egyik a System Hamilton $H $, amely egy Hermitian mátrix, és néhány kezdeti Quantum State $ \ket{\psi (0)} $, amelyet a rendszer a kvantum-számítógépeken $n $ qubits alapján kódol. A zárt rendszerekben a kvantum-állapotok a következő Schrödinger-egyenlettel fejlődnek: $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ a cél az, hogy megvalósítsa az egységes idő-evolúciós operátort $U (t) = e ^ {-iHt} $ értéket bizonyos rögzített időpontokban $t $, ahol $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ a Schrödinger-egyenlet feloldása.
Analogously az időfüggő Hamilton-szimulációs probléma ugyanazokat az egyenleteket oldja meg, de a $H (t) $ most már az idő függvénye.

A Hamilton szimuláció a számos más kvantum-szimulációs probléma egyik fő összetevője, és a Hamilton-szimulációs problémák megoldásai olyan algoritmusok, amelyek egy egyszerű kvantum-kapuk sorozatát írják le, amely egy egységes \tilde{U} $ értéket ad meg a következő hibával: $ \\ | \tilde{U}-U (t) \\ | \Le \epsilon $ a [spektrális normában](xref:microsoft.quantum.concepts.matrix-advanced). Ezeknek az algoritmusoknak a bonyolultsága nagyon nagy mértékben függ attól, hogy egy kvantum-számítógép hogyan teszi elérhetővé a Hamilton leírását. Ha például a legrosszabb esetben, ha $H $-t $n $ qubits-ra, a $2 ^ n \times 2 ^ n $ számú listának kell megadnia, az egyiket az egyes mátrix-elemeknél, egyszerűen csak az adatok olvasása már exponenciális idő szükséges. A legjobb esetben feltételezhető, hogy egy olyan fekete dobozhoz fér hozzá, amely $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ triviálisan megoldja a problémát. Ezen bemeneti modellek egyike sem különösen érdekes – az előző, mivel nem jobb, mint a klasszikus megközelítés, és az utóbbi, mint a fekete doboz elrejti a megvalósításának primitívebb kapuit, ami exponenciális lehet a qubits számában.

### <a name="descriptions-of-hamiltonians"></a>A Hamiltonians leírása ###

Ezért a bemenet formátumának további feltételezései szükségesek. Az érdekes Hamiltonians (például reális fizikai rendszerek vagy érdekes számítási problémák) és olyan bemeneti modellek között, amelyek megfelelő mértékben korlátozóak a kvantum-számítógépeken való hatékony megvalósításhoz, olyan bemeneti modellek között kell leküzdeni, amelyek eléggé leíró jellegűek. Számos nem triviális bemeneti modell található az irodalomban, és ezek a kvantumtól a klasszikusig terjedhetnek. 

A Quantum input-modellek példái [alapján a minta-alapú Hamilton-szimulációk](http://www.nature.com/articles/s41534-017-0013-7) feketéket feltételeznek a kvantum-műveletekhez, amelyek a sűrűségi mátrix $ \rho $-es példányait hozzák létre, amelyek a Hamilton $H $. Az [egységes hozzáférési modellben](https://arxiv.org/abs/1202.5822) az egyik azt feltételezi, hogy a Hamilton a unitaries $ $ \begin{align} H & = \sum ^ {d-1} \_ {j = 0} számú összegbe kerül \_ . a j \hat{U} \_ j, \end{align} $ $, ahol $a \_ j>$0, és $ \hat{U} \_ j $ unitaries. Ezt követően a rendszer feltételezi, hogy az egyiknek fekete-Box hozzáférése van az egységes Oracle $V = \sum ^ {d-1} \_ {j = 0} \Ket{j}\bra{j}\otimes \hat{U} \_ j $, amely kiválasztja a kívánt $ \hat{U} \_ j $ értéket. és az Oracle $A \ket {0} = \sum ^ {d-1} \_ {j = 0} \sqrt{a \_ j/\ Sum ^ {d-1} \_ {k = 0} \alpha \_ j} \ket{j} $, amely kvantum-állapotot hoz létre a jelen együtthatók kódolásával. [Ritka Hamilton szimuláció](https://arxiv.org/abs/quant-ph/0301023)esetén az egyik azt feltételezi, hogy a Hamilton egy ritka mátrix, amely csak $d = \mathcal{O} (\Text{polylog} (N)) $ nem nulla értékű elemet tartalmaz minden sorban. Emellett az egyik feltételezi, hogy a hatékony kvantum-áramkörök megléte a nullától eltérő elemek helyét, valamint azok értékeit is kiadja. A Hamilton- [szimulációs algoritmusok](xref:microsoft.quantum.more-information) összetettségét a rendszer a fekete mezőkre vonatkozó lekérdezések száma alapján értékeli ki, és a primitív kapu összetettsége nagy mértékben függ a fekete dobozok megvalósításának nehéz feladataitól.

> [!NOTE]
> A Big-O jelölés általában az algoritmusok összetettségi skálázásának leírására szolgál. A két valós functions $f, g $, The Expression $g (x) = \mathcal{O} (f (x)) $ érték azt jelenti, hogy létezik egy abszolút pozitív konstans $x \_ 0, c>$0, hogy $g (x) \Le c f (x) $ az összes $x \ge x \_ $0. 

A legalkalmasabb alkalmazások a kvantum-számítógépeken történő megvalósításához a fekete dobozok hatékony implementálása szükséges, amely a $ \mathcal{O} (\text{polylog} (N)) $ primitív Quantum Gates. Erősebb, hatékony simulable Hamiltonians kell lennie a klasszikusan ritka leírásnak. Az egyik ilyen megfogalmazás azt feltételezi, hogy a Hamilton a Hermitian-részek összegét összegzi $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $, feltételezi, hogy az egyes részek, egy Hamilton $H \_ j $, könnyen szimulálható. Ez azt jelenti, hogy az egységes $e ^ {-iH \_ j t} $ $t a $ \mathcal{O} (1) $ primitív Quantum Gates használatával pontosan implementálható. Ez például abban az esetben igaz, amikor minden $H \_ j $ a helyi Pauli-operátor, ami azt jelenti, hogy a (z) $ \mathcal{O} (1) $ nem Identity Pauli-operátorok, amelyek térbelien zárt qubits működnek. Ez a modell különösen a kötött és helyi interakcióval rendelkező fizikai rendszerek esetében érvényes, mivel a feltételek száma $d = \mathcal{O} (\text{polylog} (N)) $, és egyértelműen írható le, azaz a "klasszikusan" leírt módon.

> [!TIP]
> Az egyes részekre bontásban lévő Hamiltonians a dinamikus generátor képviseleti könyvtárának használatával lehet leírni. További információ: a dinamikus generátorok ábrázolási szakasza az [adatstruktúrákban](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Szimulációs algoritmusok ###

A kvantum-szimulációs algoritmus egy Hamilton egy adott leírását egy primitív kvantum-kapun alakítja át, amely teljes körű, becsült idő-evolúciót mutat a Hamilton szerint.

Abban a különleges esetben, ha a Hamilton Hermitian-részekből áll, a Trotter-Suzuki dekompozíció egy különösen egyszerű és intuitív algoritmus, amely szimulálja a Hamiltonians, amely a Hermitian-összetevők összegére bomlik le. A család első sorrendű integrátora például a $ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-IH \_ 1 t/r} \cdots e ^ {-IH \_ {d-1} t/r} \right) közelíti meg. ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $ $r d $ feltételt használó termékkel. 

> [!TIP]
> A Trotter-Suzuki szimulációs algoritmus alkalmazásait a minták tartalmazzák.
> Ahhoz, hogy a Ising modell csak az egyes célszámítógépeken elérhető belső műveleteket használja, tekintse meg a [ **SimpleIsing** -mintát](https://github.com/microsoft/Quantum/blob/main/samples/simulation/ising/simple).
> A Trotter-Suzuki Library Ising használó modell esetében tekintse meg a [ **IsingTrotter** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/trotter-evolution).
> A Trotter-Suzuki Library vezérlési struktúrát használó molekuláris hidrogén esetében tekintse meg a [ **H2 szimulációs** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line).

Sok esetben szeretnénk megvalósítani a szimulációs algoritmust, de nem érdeklik a megvalósításának részletei. Például: a második sorrendű integrátor körülbelül $ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/2r} e ^ {-IH \_ 1 t/2r} \cdots e ^ {-IH \_ {d-1} t/2r} e ^ {-IH \_ {d-1} t/2r} \cdots e ^ {-IH \_ 1 t/2r} e ^ {-iH \_ 0 t/2r} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ | H \_ j \\ | ^ 3 t ^ 3/r ^ 2), \end{align} $ $ $2RD $ feltételt használó termékkel. A nagyobb megrendelések esetében még a feltételek és az optimalizált változatok is nagy mértékben nem triviális rendezést igényelhetnek az exponenciálisan. Más speciális algoritmusok is magukban foglalhatják a Ancilla qubits használatát a közbenső lépésekben. Így a szimulációs algoritmusokat a Canonban, felhasználó által definiált típusként csomagoljuk

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

Az első paraméter `Double` a szimuláció időpontja, a második paraméter, amely az `EvolutionGenerator` [adatstruktúrák](xref:microsoft.quantum.libraries.data-structures)dinamikus generátorok ábrázolási szakaszában szerepel, egy időfüggetlen Hamilton klasszikus leírása, amely leírja, hogy a Hamilton egyes használati időszakait hogyan lehet szimulálni. Az űrlap típusai megközelítik a (z) "^ {-iHt} $" egységes $e műveletet a harmadik paraméteren `Qubit[]` , amely a szimulált rendszer kvantum-állapotát tároló regisztráció. Az időfüggő esethez hasonlóan a felhasználó által definiált típust is definiáljuk `EvolutionSchedule` , amely egy időfüggő Hamilton klasszikus leírása.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Például a Trotter-Suzuki dekompozíciót a következő Canon függvények használatával lehet meghívni, és paramétereket kell megadnia `trotterStepSize` a szimuláció időtartamának módosítására az egyes exponenciális értékekben, valamint a `trotterOrder` kívánt integrátor sorrendjét.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> A szimulációs függvénytár alkalmazásait a minták tartalmazzák. A Ising modellben használt fázis-becsléshez `SimulationAlgorithm` tekintse meg a [ **IsingPhaseEstimation** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).
> A adiabatic-állapot előkészítéséhez a Ising-modellben `TimeDependentSimulationAlgorithm` tekintse meg a [ **AdiabaticIsing** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic állapot-előkészítés & fázisának becslése ###

A Hamilton szimuláció egyik gyakori alkalmazása a adiabatic állapotának előkészítése. Itt az egyik a következő két Hamiltonians $H \_ {\text{Start}} $ és $H \_ {\text{End}} $, valamint egy Quantum State $ \ket{\psi (0)} $, amely a start Hamilton $H \_ {\text{Start}} $. A $H \_ {\text{Start}} $ általában úgy van kiválasztva, hogy a $ \ket{\psi (0)} $-es verzió könnyen feldolgozható a számítási alapú állapotból $ \ket{0\cdots 0} $ értékkel. Ezeknek a Hamiltonians az időfüggő szimulációs probléma elég lassan történő interpolációja révén a végén nagy valószínűséggel a végső $H Hamilton \_ ({\text{End}} $) végleges állapotba hozható. Bár a jó közelítések Hamilton a terepi állapotokra, így az időfüggő Hamilton-szimulációs algoritmusok alrutinként is meghívhatók, más, elméletileg eltérő megközelítések, például a variációs Quantum eigensolver.

Egy másik alkalmazás, amely mindenütt a Quantum kémiában található, megbecsüli a kémiai reakció közbenső lépéseit jelképező Hamiltonians. Ilyen séma lehet például, hogy adiabatic állapot-előkészítést használ a terepi állapot létrehozásához, majd időfüggetlen Hamilton szimulációt alkalmaz a fázis-becslési jellemzésben, hogy kinyerje ezt az energiát némi véges hibával és a siker valószínűségével. 

Absztrakt szimulációs algoritmusok felhasználó által definiált típusként, `SimulationAlgorithm` és `TimeDependentSimulationAlgorithm` lehetővé teszik a funkciók kényelmes beépítését kifinomultabb kvantum-algoritmusokban. Ez a gyakran használt alrutinok esetében is motivált.

Így definiáljuk a kényelmes függvényt

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Ez egy egységes műveletet ad vissza, amely megvalósítja a adiabatic-állapot előkészítésének összes lépését. Az első paraméter `interpolatedTime` azt az időpontot határozza meg, amikor lineárisan interpolált a második paraméter által leírt indítási Hamilton `evolutionGeneratorStart` és a harmadik paraméter által leírt záró Hamilton között `evolutionGeneratorEnd` . A negyedik paraméter az `timeDependentSimulationAlgorithm` , ahol a szimulált algoritmus közül választhat. Vegye figyelembe, hogy ha `interpolatedTime` elég hosszú, a kezdeti Alapállapot a Hamilton pillanatnyi állapotában marad az időfüggő szimuláció teljes időtartama alatt, és így végződik a végső Hamilton.

Egy olyan hasznos műveletet is definiálunk, amely egy tipikus kvantum-kémiai kísérlet minden lépését automatikusan végrehajtja. Például a következők állnak rendelkezésre, amely visszaadja az adiabatic állapot-előkészítéssel előállított állapot becslését:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` a kezdeti kvantum-állapot kódolásához használt qubits száma. `statePrepUnitary` előkészíti az indítási állapotot a $ \ket{0\cdots 0} $ számítási alapján. `adiabaticUnitary` a a adiabatic állapot-előkészítést megvalósító egységes művelet, például a függvény által előállított  `InterpolatedEvolution` . `qpeUnitary` az az egységes művelet, amellyel a rendszer a fázisok becslését hajtja végre az eredményül kapott kvantum állapoton. `phaseEstAlgorithm` a fázis becslési algoritmusa közül választhat.

> [!TIP]
> A mintákban a adiabatic-állapot előkészítésének alkalmazásai szerepelnek. A Ising modell adiabatic állapot-előkészítésének manuális megvalósításával és a függvény használatával `AdiabaticEvolution` tekintse meg a [ **AdiabaticIsing** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic).
> A Ising modellben a fázisok becslése és a adiabatic állapotának előkészítéséhez tekintse meg a [ **IsingPhaseEstimation** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).

> [!TIP]
> A [molekuláris hidrogén szimulálása](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) egy érdekes és rövid minta. A [O'Malley et. Al](https://arxiv.org/abs/1512.06860) -ben jelentett modell és kísérleti eredmények. csak a Pauli-mátrixok szükségesek, és az űrlapon a $ \hat H = g \_ {0} I \_ 0i \_ 1 + g \_ 1 {z \_ 0} + g \_ 2 {z \_ 1} + g \_ 3 {z \_ 0} {z \_ 1} + g \_ 4 {y \_ 0} {y \_ 1} + g \_ 5 {x \_ 0} {x \_ 1} $ értéket kell használnia. Ez egy hatékony Hamilton, amely csak a 2 qubits-t igényli, ahol a $g $ konstansokat a két hidrogén atomok közötti távolságból számított $R $ értékre számítjuk. A Canon functions használatával a Paulis átalakítja a unitaries, majd rövid idő alatt kifejlődött a Trotter-Suzuki dekompozíció használatával. A adiabatic-állapot előkészítése nélkül hozható létre jó közelítés a $H _2 $ alapállapothoz, és így a rendszer közvetlenül a Canontól származó fázis-becslés használatával is megtalálhatja a terepi állapotot.

## <a name="shors-algorithm"></a>Shor-algoritmus ##
A rövid algoritmusa továbbra is a kvantum-számítástechnika egyik legjelentősebb folyamata marad, mivel ez azt mutatta, hogy a kvantum-számítógépek a fontos, jelenleg klasszikusan megoldhatatlan problémák megoldására használhatók.
A rövid algoritmusa gyors megoldást kínál a nagy számokra a kvantum-számítógép, a *faktoring*nevű probléma használatával.
A sok mai cryptosystems biztonsága azon a feltételezésen alapul, hogy nem létezik gyors algoritmus a faktoring szolgáltatáshoz.
Ennek megfelelően a rövid algoritmusa olyan hatással volt, hogy miként gondolunk a biztonságra a kvantum utáni világban.

A rövid algoritmusa hibrid algoritmus lehet.
A kvantum-számítógép egy számítási feladatok elvégzésére szolgál.
A rendszer az időszak megkeresésének eredményét a klasszikusan dolgozza fel a tényezők becslése érdekében.
Ezt a két lépést alább tekintjük át.

### <a name="period-finding"></a>Időszak megállapítása ###

Miután megismerte, hogyan működik a Quantum Fourier-transzformáció és a fázis becslése (lásd a [kvantum-algoritmusokat](xref:microsoft.quantum.libraries.standard.algorithms)), ezeket az eszközöket felhasználhatjuk a hagyományosan nehéz számítási probléma megoldásához, amelynek elnevezése az *időszak megállapítása*.  A következő szakaszban bemutatjuk, hogyan alkalmazhatja az időszak megállapítását a faktoring szolgáltatásba.

A két egész szám $a $ és $N $ között, ahol a $a<N $, az időszak megállapításának célját, más néven a sorrend megállapítását is, az a _sorrend_ , amely $r $ $a $ többtényezős $N $, ahol $r $ a legkevésbé pozitív egész számnak felel meg, például $a ^ r \equiv 1 \text{mod} N $.  

Ha kvantum-számítógép használatával szeretné megkeresni a sorrendet, a következő egységes operátorra alkalmazott fázis-becslési algoritmust is használhatja $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \text{mod} N}. $ $ a $U _a $ eigenvectors az egész $s $ és $0 \ LEQ s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum \_ {k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ _eigenstates_ $U _a $.
$U _a $ eigenvalues a $ $ U \_ a \ket{x \_ s} = e ^ {2 \ PI i s/r} \ket{x \_ s}. $$

A fázis becslése így a eigenvalues $e ^ {2 \ PI i s/r} $ értéket jeleníti meg, amelyből a $r $ a $s/r $-ből származó [folyamatos frakciók](https://en.wikipedia.org/wiki/Continued_fraction) használatával hatékonyan megtanult.

A kvantum-időszak megállapításához használt áramköri diagram a következő:

![A kvantum-időszak megkeresésének áramköri diagramja](~/media/QPE.svg)

Itt $2n $ qubits inicializálása $ \ket {0} $-re, a $n $ qubits pedig a $ \ket $-re lett inicializálva {1} .
Az olvasónak újra lehet tudnia, hogy miért lett inicializálva a eigenstates a \ket $ értékre {1} .
Mivel az egyik nem tudja, hogy a rendelés $r $, nem lehet ténylegesen előkészíteni a $ \ket{x_s} $ $ állapotot.
Szerencsére kiderül, hogy a $1/\ SQRT {r} \sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \ket {1} $.
Nem kell ténylegesen előkészíteni a $ \ket{x} $-t!
Most már előkészítheti $n $ qubits kvantum-regisztrációját $ \ket {1} $ állapotban. 

Az áramkör tartalmazza a QFT és a több vezérelt kaput.
A QFT-kaput [korábban](xref:microsoft.quantum.libraries.standard.algorithms)ismertetjük.
A vezérelt $U _a $ Gate Maps $ \ket{x} $ to $ \ket{(AX) \text{mod} N} $, ha a vezérlő qubit $ \ket {1} $, és Maps $ \ket{x} $ to $ \ket{x} $ máskülönben.

Ahhoz, hogy a $ (a ^ NX) \text{mod} N $-t lehessen elérni, egyszerűen alkalmazhatjuk a szabályozott $U _ {a ^ n} $-t, ahol a $a ^ n \text{mod} N $-t a kvantum-áramkörbe való csatlakoztatáshoz.  
Az ilyen Moduláris aritmetika eléréséhez szükséges áramkörök leírását a [Quantum aritmetikai dokumentációja](./algorithms.md#arithmetic)tartalmazza, konkrétan a vezérelt $U \_ {a ^ i} $ műveletek megvalósításához moduláris hatványozására áramkörre van szükségünk.

Míg a fenti kör megfelel a [kvantum fázisok becslésének](xref:microsoft.quantum.characterization.quantumphaseestimation) , és explicit módon lehetővé teszi a megrendelés megtalálását, csökkentheti a szükséges qubits számát. A Beauregard módszerét követve megtekintheti a [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), illetve a Microsoft. Quantum. jellemzésben elérhető fázis-becslési rutinok egyikét. A [robusztus fázis becslése](xref:microsoft.quantum.characterization.robustphaseestimation) például egy extra qubit is használ.
 
### <a name="factoring"></a>Faktoring ###
A faktoring célja, hogy meghatározza a $N $ egész szám két fő tényezőjét, ahol a $N $ egy $n $ bites szám.  
A faktoring az alábbiakban ismertetett lépésekből áll. A lépések három részre oszlanak: a klasszikus előfeldolgozási rutin (1-4); egy kvantum-számítási rutin, amely megkeresi az $a \text{mod} N $ (5); valamint egy klasszikus utófeldolgozó rutin, amely a sorrendből származtatja a legfontosabb tényezőket (6-9).

A klasszikus előfeldolgozási rutin a következő lépésekből áll:
1. Ha a $N $ értéke páros, a $2 $ Prime faktort kell visszaadnia.
2. Ha $N = p ^ q $ $p \geq1 $, $q \geq2 $, a Prime Factor $p $ értéket kell visszaadnia.  Ezt a lépést klasszikusan hajtják végre.
3. Válasszon egy véletlenszerű számot $a $, például $1 < < N-$1.
4. Ha a $ \text{GCD} (a, N) >$1, akkor a \text{GCD} (a, N) $ elsődleges tényezőt kell visszaadnia. Ezt a lépést a Euklidész algoritmusa alapján számítjuk ki.
Ha nem adtak vissza elsődleges tényezőt, folytassa a kvantum-rutin használatával:
5. Hívja meg a kvantum-időszak megkeresésének algoritmusát, hogy kiszámítsa $r $ $a \text{mod} N $ értékének megrendelését. A legfontosabb tényezők megállapításához használja az $r $-t a klasszikus utófeldolgozó rutinban:
6. Ha $r $ páratlan, térjen vissza az előfeldolgozási lépéshez (3).
7. Ha $r $ páros, és $a ^ {r/2} =-1 \ Text {mod} N $, térjen vissza az előfeldolgozási lépéshez (3).
8. Ha a $ \text{GCD} (a ^ {r/2} + 1, N) $ egy nem triviális tényező a $N $ értéknél, a Return $ \text{GCD} (a ^ {r/2} + 1, N) $ értéket kell visszaadnia.
9. Ha a $ \text{GCD} (a ^ {r/2}-1, N) $ nem triviális tényező a $N $ értéknél, a Return $ \text{GCD} (a ^ {r/2}-1, N) $ értéket kell visszaadnia.


A faktoring algoritmus valószínűsége: úgy láthatja, hogy a $r $ értéke legalább az egyik fele lesz, és $a ^ {r/2} \neq-1 \text{mod} N $, ami egy elsődleges tényezőt eredményez.  (További információért lásd a [rövid eredeti dokumentumát](https://doi.org/10.1109/SFCS.1994.365700) , vagy a [További információk](xref:microsoft.quantum.more-information)egyik *alapszintű Quantum Computing* -szövegét).
Ha a rendszer nem ad vissza elsődleges tényezőt, egyszerűen ismételje meg az algoritmust a következő lépésből: (1).  $N $ próbálkozás után a valószínűsége, hogy minden kísérlet meghiúsult, legfeljebb 2 ^ {-n} $.
Így az algoritmus megismétlése után a sikert csak kis számú alkalommal lehet megerősíteni.
