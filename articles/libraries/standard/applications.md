---
title: 'Q # standard könyvtárak – alkalmazások | Microsoft Docs'
description: 'Q # standard kódtárak'
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e6eca45dd67b3566340c2a2a4fded0f6e7c3c5c3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185171"
---
# <a name="applications"></a>Alkalmazások #

## <a name="hamiltonian-simulation"></a>Hamilton szimuláció ##

A kvantum-rendszerek szimulációja a kvantum-számítás legizgalmasabb alkalmazásai közé esik.
A klasszikus számítógépeken a kvantummechanika szimulálása során felmerülő nehézségek általában az állapot-vektoros ábrázolás $N $ dimenzióval méretezhetők.
Mivel ez a képviselet exponenciálisan növekszik a $n $ qubits $N = 2 ^ n $ értékkel, a [dimenzióját átka](xref:microsoft.quantum.concepts.multiple-qubits)néven ismert tulajdonság, a Quantum szimulációs a klasszikus hardveren nem vonható le.

A helyzet azonban nagyon eltérő lehet a kvantum hardveren. A kvantum-szimuláció leggyakoribb változata az idő-független Hamilton-szimulációs probléma. Itt az egyik a System Hamilton $H $, amely egy Hermitian mátrix, és néhány kezdeti Quantum State $ \ket{\psi (0)} $, amelyet a rendszer a kvantum-számítógépeken $n $ qubits alapján kódol. Mivel a bezárt rendszerekben a kvantum-állapotok a \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $, a cél az, hogy megvalósítsa az egységes idő-Evolution operátort, $U (t) = e ^ {-iHt} $ egy bizonyos rögzített időpontban $t $ , ahol a $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ megoldja a Schrödinger-egyenletet.
Analogously az időfüggő Hamilton-szimulációs probléma ugyanazokat az egyenleteket oldja meg, de a $H (t) $ most már az idő függvénye.

A Hamilton szimuláció a számos más kvantum-szimulációs probléma fő összetevője, és a Hamilton-szimulációs problémák megoldásai olyan algoritmusok, amelyek egy egyszerű kvantum-kapuk sorozatából álló sorozatot mutatnak be az egységes \tilde{U} $ Hiba: $\\| \tilde{U}-U (t)\\| a \Le \epsilon $ a [spektrális normában](xref:microsoft.quantum.concepts.matrix-advanced). Ezeknek az algoritmusoknak a bonyolultsága nagyon nagy mértékben függ attól, hogy egy kvantum-számítógép hogyan teszi elérhetővé a Hamilton leírását. Ha például a legrosszabb esetben, ha $H $-t $n $ qubits-ra, a $2 ^ n \times 2 ^ n $ számú listának kell megadnia, az egyiket az egyes mátrix-elemeknél, egyszerűen csak az adatok olvasása már exponenciális idő szükséges. A legjobb esetben feltételezhető, hogy egy olyan fekete dobozhoz fér hozzá, amely $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ triviálisan megoldja a problémát. Ezen bemeneti modellek egyike sem különösen érdekes – az előző, mivel nem jobb, mint a klasszikus megközelítés, és az utóbbi, mint a fekete doboz elrejti a megvalósításának primitívebb kapuit, ami exponenciális lehet a qubits számában.

### <a name="descriptions-of-hamiltonians"></a>A Hamiltonians leírása ###

Ezért a bemenet formátumának további feltételezései szükségesek. Az érdekes Hamiltonians, például reális fizikai rendszerekre vagy érdekes számítási problémákra, valamint a kellően korlátozó bemeneti modellekre vonatkozó részletes egyensúlyt kell találni a bemeneti modellek között. a kvantum-számítógépen való hatékony megvalósításhoz. Számos nem triviális bemeneti modell található az irodalomban, és ezek a kvantumtól a klasszikusig terjedhetnek. 

A Quantum input-modellek példái [alapján a minta-alapú Hamilton-szimulációk](http://www.nature.com/articles/s41534-017-0013-7) feketéket feltételeznek a kvantum-műveletekhez, amelyek a sűrűségi mátrix $ \rho $-es példányait hozzák létre, amelyek a Hamilton $H $. Az [egységes hozzáférési modellben](https://arxiv.org/abs/1202.5822) azt feltételezi, hogy a Hamilton a unitaries $ $ \begin{align} H & = \sum ^ {d-1}\_{j = 0} összegét adja vissza, amely egy\_j \hat{U}\_j, \end{align} $ $, ahol $a\_j > 0 $ és $ \hat{U}\_j $ unitaries. Ezt követően a rendszer feltételezi, hogy az egyiknek van fekete dobozhoz való hozzáférése az egységes Oracle $V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $, amely kiválasztja a kívánt $ \hat{U}\_j $, és az Oracle $A \ket{0}= \sum ^ {d-1}\_{ j = 0} \sqrt{a\_j/\ Sum ^ {d-1}\_{k = 0} \alpha\_j} \ket{j} $, amely Quantum State-kódolást hoz létre ezekkel az együtthatókkal. [Ritka Hamilton szimuláció](https://arxiv.org/abs/quant-ph/0301023)esetén az egyik azt feltételezi, hogy a Hamilton egy ritka mátrix, amely csak $d = \mathcal{O} (\Text{polylog} (N)) $ nem nulla értékű elemet tartalmaz minden sorban. Emellett az egyik feltételezi, hogy a hatékony kvantum-áramkörök megléte a nullától eltérő elemek helyét, valamint azok értékeit is kiadja. A Hamilton- [szimulációs algoritmusok](xref:microsoft.quantum.more-information) összetettségét a rendszer a fekete mezőkre vonatkozó lekérdezések száma alapján értékeli ki, és a primitív kapu összetettsége nagy mértékben függ a fekete dobozok megvalósításának nehéz feladataitól.

> [!NOTE]
> A Big-O jelölés általában az algoritmusok összetettségi skálázásának leírására szolgál. Adott két valós functions $f, g $, The Expression $g (x) = \mathcal{O} (f (x)) $ érték azt jelenti, hogy létezik egy abszolút pozitív állandó $x\_0, c > 0 $, hogy $g (x) \Le c f (x) $ az összes $x \ge x\_$0. 

A legalkalmasabb alkalmazások a kvantum-számítógépeken történő megvalósításához a fekete dobozok hatékony implementálása szükséges, amely a $ \mathcal{O} (\text{polylog} (N)) $ primitív Quantum Gates. Erősebb, hatékony simulable Hamiltonians kell lennie a klasszikusan ritka leírásnak. Az egyik ilyen megfogalmazás azt feltételezi, hogy a Hamilton a Hermitian-részek összegét összegzi $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $, feltételezi, hogy az egyes részek, a Hamilton $H\_j $, könnyen szimulálható. Ez azt jelenti, hogy az egységes $e ^ {-iH\_j t} $ minden $t alkalommal, ha a $ \mathcal{O} (1) $ primitív kvantum-kapuk használatával pontosan implementálható. Ez például abban az esetben igaz, amikor az egyes $H\_j $ a helyi Pauli-operátorok, ami azt jelenti, hogy azok a (z) $ \mathcal{O} (1) $ nem Identity Pauli operátorok, amelyek térbelien zárt qubits működnek. Ez a modell különösen a kötött és helyi interakcióval rendelkező fizikai rendszerek esetében érvényes, mivel a feltételek száma $d = \mathcal{O} (\text{polylog} (N)) $, és egyértelműen írható le, azaz a "klasszikusan" leírt módon.

> [!TIP]
> Az egyes részekre bontásban lévő Hamiltonians a dinamikus generátor képviseleti könyvtárának használatával lehet leírni. További információ: a dinamikus generátorok ábrázolási szakasza az [adatstruktúrákban](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Szimulációs algoritmusok ###

A kvantum-szimulációs algoritmus egy Hamilton egy adott leírását egy primitív kvantum-kapun alakítja át, amely teljes körű, becsült idő-evolúciót mutat a Hamilton szerint.

Abban a különleges esetben, ha a Hamilton Hermitian-részekből áll, a Trotter-Suzuki dekompozíció egy különösen egyszerű és intuitív algoritmus, amely szimulálja a Hamiltonians, amely a Hermitian-összetevők összegére bomlik le. A család első sorrendű integrátora például $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \max_j\\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $, $r d $ feltételekkel rendelkező termék használatával. 

> [!TIP]
> A Trotter-Suzuki szimulációs algoritmus alkalmazásait a minták tartalmazzák.
> Ahhoz, hogy a Ising modell csak az egyes célszámítógépeken elérhető belső műveleteket használja, tekintse meg a [ **SimpleIsing** -mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/SimpleIsing).
> A Trotter-Suzuki Library Ising használó modell esetében tekintse meg a [ **IsingTrotter** mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingTrotterEvolution).
> A Trotter-Suzuki Library vezérlési struktúrát használó molekuláris hidrogén esetében tekintse meg a [ **H2 szimulációs** mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine).

Sok esetben szeretnénk megvalósítani a szimulációs algoritmust, de nem érdeklik a megvalósításának részletei. Például: a második sorrendű integrátor körülbelül $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/2r} e ^ {-iH\_1 t/2r} \cdots e ^ {-iH\_{d-1} t/2r} e ^ {-iH\_{d-1} t/2r} \cdots e ^ {-iH\_1 t/2r} e ^ {- iH\_0 t/2r} \right) ^ {r} + \mathcal{O} (d ^ 3 \max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{align} $ $ $2RD $ feltételt használó termékkel. A nagyobb megrendelések esetében még a feltételek és az optimalizált változatok is nagy mértékben nem triviális rendezést igényelhetnek az exponenciálisan. Más speciális algoritmusok is magukban foglalhatják a Ancilla qubits használatát a közbenső lépésekben. Így a szimulációs algoritmusokat a Canonban, felhasználó által definiált típusként csomagoljuk

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

Az első paraméter `Double` a szimuláció időpontja, a második paraméter `EvolutionGenerator`, amely az [adatstruktúrák](xref:microsoft.quantum.libraries.data-structures)dinamikus generátor-ábrázolási szakaszában szerepel, a egy időfüggetlen Hamilton, amely a a Hamilton egyes használati feltételeinek a kvantum-áramkör általi szimulálása. Az űrlap típusai megközelítik a (z) "^ {-iHt} $" egységes műveletet $e a harmadik paraméter `Qubit[]`, amely a szimulált rendszer kvantum-állapotának tárolására szolgáló bejegyzés. Az időfüggő esethez hasonlóan a felhasználó által definiált típust is definiáljuk `EvolutionSchedule` típussal, amely egy időfüggő Hamilton klasszikus leírása.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Például a Trotter-Suzuki dekompozíciót a következő Canon függvények használatával lehet meghívni, a paraméterekkel `trotterStepSize` a szimuláció időtartamának módosítását minden exponenciális értékben, és `trotterOrder` a kívánt integrátor sorrendjére.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : SimulationAlgorithm {
    ...
}
function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> A szimulációs függvénytár alkalmazásait a minták tartalmazzák. A Ising modellben `SimulationAlgorithm`használatával történő fázis-becsléshez tekintse meg a [ **IsingPhaseEstimation** mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation).
> A Ising-modellben a adiabatic-állapot előkészítéséhez `TimeDependentSimulationAlgorithm`használatával tekintse meg a [ **AdiabaticIsing** mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/AdiabaticIsing).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic állapot-előkészítés & fázisának becslése ###

A Hamilton szimuláció egyik gyakori alkalmazása a adiabatic állapotának előkészítése. Itt az egyik a következő két Hamiltonians $H\_{\text{Start}} $ és $H\_{\text{End}} $, valamint egy Quantum State $ \ket{\psi (0)} $, amely a Start Hamilton $H\_{\text{Start}} $. A $H\_{\text{Start}} $ általában úgy van kiválasztva, hogy a $ \ket{\psi (0)} $-es verzió könnyen felkészíthető legyen egy számítási alapú állapotból $ \ket{0\cdots 0} $ értékre. A Hamiltonians között az időfüggő szimulációs probléma lassan való interpolációja miatt az idő függvényében a Befejezés nagy valószínűséggel a végső Hamilton $H\_{\text{End}} $. Bár a jó közelítések Hamilton a terepi állapotokra való felkészülést, így az időfüggő Hamilton szimulációs algoritmusok egy alrutinként, más, elméletileg eltérő megközelítések, például a változó kvantum eigensolver lehetséges.

Egy másik alkalmazás, amely mindenütt a Quantum kémiában található, megbecsüli a kémiai reakció közbenső lépéseit jelképező Hamiltonians. Egy ilyen séma például a adiabatic állapotának előkészítésére támaszkodhat a terepi állapot létrehozásához, majd időfüggetlen Hamilton szimulációt is használhat a fázis-becslési jellemzésben, hogy kinyerje ezt az energiát némi véges hibával, és a siker valószínűsége. 

Az absztrakt szimulációs algoritmusok a felhasználó által definiált típusok `SimulationAlgorithm` és `TimeDependentSimulationAlgorithm` lehetővé teszik a funkciók kényelmes beépítését kifinomultabb kvantum-algoritmusokban. Ez a gyakran használt alrutinok esetében is motivált.

Így definiáljuk a kényelmes függvényt

```qsharp
function InterpolatedEvolution(
        interpolationTime: Double, 
        evolutionGeneratorStart: EvolutionGenerator,
        evolutionGeneratorEnd: EvolutionGenerator,
        timeDependentSimulationAlgorithm: TimeDependentSimulationAlgorithm)
        : (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Ez egy egységes műveletet ad vissza, amely megvalósítja a adiabatic-állapot előkészítésének összes lépését. Az első paraméter `interpolatedTime` azt az időpontot határozza meg, ameddig a lineárisan interpolált a második paraméter által leírt indítási Hamilton, `evolutionGeneratorStart` és a harmadik paraméter `evolutionGeneratorEnd`által leírt záró Hamilton között. A negyedik paraméter `timeDependentSimulationAlgorithm`, ahol a szimulált algoritmus közül választhat. Vegye figyelembe, hogy ha a `interpolatedTime` elég hosszú, a kezdeti Alapállapot a Hamilton pillanatnyi állapotában marad az időfüggő szimuláció teljes időtartama alatt, és így végződik a végső Hamilton.

Egy olyan hasznos műveletet is definiálunk, amely egy tipikus kvantum-kémiai kísérlet minden lépését automatikusan végrehajtja. Például a következők állnak rendelkezésre, amely visszaadja az adiabatic állapot-előkészítéssel előállított állapot becslését:

```qsharp
operation AdiabaticStateEnergyEstimate( 
    nQubits : Int, 
    statePrepUnitary: (Qubit[] => Unit),
    adiabaticUnitary: (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
    : Double {
...
}
```

`nQubits` a kezdeti kvantum-állapot kódolásához használt qubits száma. `statePrepUnitary` előkészíti a kezdő állapotot a $ \ket{0\cdots 0} $ számítási alapból. `adiabaticUnitary` a adiabatic állapot-előkészítést megvalósító egységes művelet, például a `InterpolatedEvolution` függvénnyel előállított. `qpeUnitary` az az egységes művelet, amellyel a rendszer a fázisok becslését hajtja végre az eredményül kapott kvantum-állapot alapján. `phaseEstAlgorithm` a fázis becslési algoritmusa.

> [!TIP]
> A mintákban a adiabatic-állapot előkészítésének alkalmazásai szerepelnek. A Ising modell adiabatic állapot-előkészítésének manuális megvalósításával és az `AdiabaticEvolution` függvény használatával tekintse meg a [ **AdiabaticIsing** mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/AdiabaticIsing).
> A Ising modellben a fázisok becslése és a adiabatic állapotának előkészítéséhez tekintse meg a [ **IsingPhaseEstimation** mintát](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation).

> [!TIP]
> A [molekuláris hidrogén szimulálása](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine) egy érdekes és rövid minta. A [O'Malley et. Al](https://arxiv.org/abs/1512.06860) -ben jelentett modell és kísérleti eredmények. csak a Pauli-mátrixok szükségesek, és a formátum a $ \hat H = g\_{0}I\_0I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Ez egy hatékony Hamilton, amely csak a 2 qubits-t igényli, ahol a $g $ konstansokat a két hidrogén atomok közötti távolságból számított $R $ értékre számítjuk. A Canon functions használatával a Paulis átalakítja a unitaries, majd rövid idő alatt kifejlődött a Trotter-Suzuki dekompozíció használatával. A adiabatic-állapot előkészítése nélkül hozható létre jó közelítés a $H _2 $ alapállapothoz, és így a rendszer közvetlenül a Canontól származó fázis-becslés használatával is megtalálhatja a terepi állapotot.

## <a name="shors-algorithm"></a>Rövid algoritmusa ##
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

A két egész szám $a $ és $N $ között, ahol a $a < N $, az időszak megállapításának célját, más néven a sorrend megállapítását is, az a _sorrend_ , amely $r $ $a $ többtényezős $N $, ahol $r $ a legkevésbé pozitív egész számnak felel meg, például $a ^ r \equiv 1 \text{mod} N $.  

Ha egy kvantum-számítógép használatával szeretné megkeresni a sorrendet, a következő egységes operátorra alkalmazott fázis-becslési algoritmust is használhatja $U _a $: $ $ U_a\ket {x} \equiv \ket{(AX) \text{mod} N}. $ $ a eigenvectors $ $U _a $ egész szám $s $ és $0 \ LEQ s \leq r-$1 , $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ $U eigenstates _$ _a._
$U _a $ eigenvalues a $ $ U\_a \ket{x\_s} = e ^ {2 \ PI i s/r} \ket{x\_s}. $$

A fázis becslése így a eigenvalues $e ^ {2 \ PI i s/r} $ értéket jeleníti meg, amelyből a $r $ a $s/r $-ből származó [folyamatos frakciók](https://en.wikipedia.org/wiki/Continued_fraction) használatával hatékonyan megtanult.

A kvantum-időszak megállapításához használt áramköri diagram a következő:

![](./../../media/QPE.svg)

Itt $2n $ qubits inicializálva van a $ \ket{0}$ és a $n $ qubits értékre, amely a $ \ket{1}$-ra van inicializálva.
Az olvasónak újra lehet tudnia, hogy miért lett inicializálva az eigenstates a (z) $ \ket{1}$ értékre.
Mivel az egyik nem tudja, hogy a megrendelést $r $, nem tudjuk közvetlenül előkészíteni a $ \ket{x_s} $ állapotot.
Szerencsére kiderül, hogy a $1/\ SQRT {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$.
Nem kell ténylegesen előkészíteni a $ \ket{x} $-t!
Most előkészítheti $n $ qubits kvantum-regisztrációját a $ \ket{1}$ állapotban. 

Az áramkör tartalmazza a QFT és a több vezérelt kaput.
A QFT-kaput [korábban](xref:microsoft.quantum.libraries.standard.algorithms)ismertetjük.
A vezérelt $U _a $ Gate Maps $ \ket{x} $ to $ \ket{(AX) \text{mod} N} $, ha a vezérlő qubit $ \ket{1}$, és Maps $ \ket{x} $ to $ \ket{x} $ máskülönben.

Ahhoz, hogy a $ (a ^ NX) \text{mod} N $-t lehessen elérni, egyszerűen alkalmazhatjuk a szabályozott $U _ {a ^ n} $-t, ahol a $a ^ n \text{mod} N $-t a kvantum-áramkörbe való csatlakoztatáshoz.  
Az ilyen Moduláris aritmetika eléréséhez szükséges áramkörök leírását a [Quantum aritmetikai dokumentációja](./algorithms.md#arithmetic)tartalmazza, amely konkrétan egy moduláris hatványozására áramkört igényel az ellenőrzött $U\_{a ^ i} $ művelet megvalósításához.

Míg a fenti kör megfelel a [kvantum fázisok becslésének](xref:microsoft.quantum.characterization.quantumphaseestimation) , és explicit módon lehetővé teszi a megrendelés megtalálását, csökkentheti a szükséges qubits számát. Követheti a Beauregard metódusát, hogy megkeresse a [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), vagy használja a Microsoft. Quantum. Canonban elérhető fázis-becslési rutinok egyikét. A [robusztus fázis becslése](xref:microsoft.quantum.characterization.robustphaseestimation) például egy extra qubit is használ.
 
### <a name="factoring"></a>Faktoring ###
A faktoring célja, hogy meghatározza a $N $ egész szám két fő tényezőjét, ahol a $N $ egy $n $ bites szám.  
A faktoring az alábbiakban ismertetett lépésekből áll. A lépések három részre oszlanak: a klasszikus előfeldolgozási rutin (1-4); egy kvantum-számítási rutin, amely megkeresi az $a \text{mod} N $ (5); valamint egy klasszikus utófeldolgozó rutin, amely a sorrendből származtatja a legfontosabb tényezőket (6-9).

A klasszikus előfeldolgozási rutin a következő lépésekből áll:
1. Ha a $N $ értéke páros, a $2 $ Prime faktort kell visszaadnia.
2. Ha $N = p ^ q $ $p \geq1 $, $q \geq2 $, a Prime Factor $p $ értéket kell visszaadnia.  Ezt a lépést klasszikusan hajtják végre.
3. Válasszon egy véletlenszerű számot $a $, például $1 < < N-$1.
4. Ha a $ \text{GCD} (a, N) > 1 $, a Prime Factor $ \text{GCD} (a, N) $ értéket kell visszaadnia. Ezt a lépést a Euklidész algoritmusa alapján számítjuk ki.
Ha nem adtak vissza elsődleges tényezőt, folytassa a kvantum-rutin használatával:
5. Hívja meg a kvantum-időszak megkeresésének algoritmusát, hogy kiszámítsa $r $ $a \text{mod} N $ értékének megrendelését. A legfontosabb tényezők megállapításához használja az $r $-t a klasszikus utófeldolgozó rutinban:
6. Ha $r $ páratlan, térjen vissza az előfeldolgozási lépéshez (3).
7. Ha $r $ páros, és $a ^ {r/2} =-1 \ Text {mod} N $, térjen vissza az előfeldolgozási lépéshez (3).
8. Ha a $ \text{GCD} (a ^ {r/2} + 1, N) $ egy nem triviális tényező a $N $ értéknél, a Return $ \text{GCD} (a ^ {r/2} + 1, N) $ értéket kell visszaadnia.
9. Ha a $ \text{GCD} (a ^ {r/2}-1, N) $ nem triviális tényező a $N $ értéknél, a Return $ \text{GCD} (a ^ {r/2}-1, N) $ értéket kell visszaadnia.


A faktoring algoritmus valószínűsége: úgy láthatja, hogy a $r $ értéke legalább az egyik fele lesz, és $a ^ {r/2} \neq-1 \text{mod} N $, ami egy elsődleges tényezőt eredményez.  (További információért lásd a [rövid eredeti dokumentumát](https://doi.org/10.1109/SFCS.1994.365700) , vagy a [További információk](xref:microsoft.quantum.more-information)egyik *alapszintű Quantum Computing* -szövegét).
Ha a rendszer nem ad vissza elsődleges tényezőt, egyszerűen ismételje meg az algoritmust a következő lépésből: (1).  $N $ próbálkozás után a valószínűsége, hogy minden kísérlet meghiúsult, legfeljebb 2 ^ {-n} $.
Így az algoritmus megismétlése után a sikert csak kis számú alkalommal lehet megerősíteni.
