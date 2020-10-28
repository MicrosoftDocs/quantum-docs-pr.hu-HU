---
title: Quantum jellemzés és statisztika
description: Ebből a szakaszból megtudhatja, hogyan használhatók a mérési statisztikák a fázis-becslésekben a kvantum-programozás eredményeinek becsléséhez.
author: bradben
uid: microsoft.quantum.libraries.characterization
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51e7b3bcf4402a4d0ba5647643f284e9f10c3bb3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692150"
---
# <a name="quantum-characterization-and-statistics"></a>Quantum jellemzés és statisztika #

Fontos, hogy képes legyen jellemezni a műveletek hatásait a hasznos kvantum-algoritmusok kifejlesztése érdekében.
Ez kihívást jelenthet, mivel a kvantumrendszer minden mérése legfeljebb egy kis mennyiségű adatot eredményez.
Egy sajátérték megismeréséhez, amely lehetővé teszi a kvantum-állapotot, a számos mérés eredményét össze kell keverni, hogy a felhasználó fel tudja venni az ilyen fogalmak ábrázolásához szükséges sok bitet.
A kvantum-állapotok különösen bosszantóak, mert a [nem klónozási tétel](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) azt jelzi, hogy az állapot egyetlen példányáról sem lehet tetszőleges kvantum-állapotot betanulni, mert ezzel az állapot másolatait is lehetővé tenné.
A kvantum-állapotnak a felhasználótól való elhomályosítása abban a tényben tükröződik, amely Q# nem tesz elérhetővé vagy nem határozza meg, hogy milyen állapotban *van* a kvantum-programok.
Így a kvantum-jellemzést úgy közelítjük meg, hogy a műveleteket és az állapotokat fekete dobozként kezeli. Ez a megközelítés gyakran osztozik a kvantum-jellemzés, az ellenőrzés és az érvényesítés (QCVV) kísérleti gyakorlatával.

A jellemzés különbözik a korábban tárgyalt többi könyvtártól.
A cél a rendszerre vonatkozó klasszikus információk megismerése, nem pedig az állapot-vektorok egységes átalakításának elvégzése.
Ezeknek a kódtáraknak ezért a klasszikus és a kvantum-adatok feldolgozását is el kell keverni.


## <a name="iterative-phase-estimation"></a>Iterációs fázis becslése ##

A kvantummechanika a Quantum-jellemzés szempontjából való megtekintése hasznos alternatívát mutat a kvantum fázis becsléséhez.
Ez azt eredményezi, hogy ahelyett, hogy egy $n $-qubit regisztert kellene készítenie, amely a fázis bináris ábrázolását tartalmazza, mint a kvantum fázisok becslésében, megtekintheti a fázisok becslését arra a folyamatra, amellyel a *klasszikus* ügynök a kvantumrendszer tulajdonságait a mérések alapján tanulja meg.
A "visszarúgás" fázis használatával a bejelentési művelet eredményeként a fekete dobozba tartozó műveletek egy ismeretlen szögbe való bekapcsolásához, de az elforgatást közvetlenül követő egyes lépésekben mért Ancilla qubit mérjük.
Ennek az az előnye, hogy csak egyetlen további qubit van szükség a kvantum-esetekben ismertetett visszarúgások végrehajtásához, ahogy ezt követően a mérési eredmények fázisát is megismerheti egy iterációs módon.  
Az alábbiakban javasolt módszerek mindegyike egy másik stratégiát használ a kísérletek tervezéséhez és a különböző adatfeldolgozási módszerekhez a fázis megismerése érdekében.  Ezek mindegyike egyedi előnnyel rendelkezik, és a szigorú hibákra, a képességekre, az előzetes információk bevezetésére, a hibák elmulasztására vagy a limitted klasszikus számítógépeken való futtatására van szükség.

Az iterációs fázisok becslésének megvitatásakor egy egységes $U $ értéket fogunk figyelembe venni, amely egy fekete dobozból álló művelet.
Az [adatstruktúrákban](xref:microsoft.quantum.libraries.data-structures)található Oracle-adatokról szóló szakaszban leírtaknak megfelelően a Q# Canon modelleket a <xref:Microsoft.Quantum.Oracles.DiscreteOracle> felhasználó által definiált típus alapján, a rekord típusa határozza meg `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
Konkrétan, ha `U : DiscreteOracle` , akkor `U(m)` a $U ^ millió $ értéket implementál a következőhöz: `m : Int` .

Ennek a definíciónak a helyén az ismétlődő fázisok becslésének minden lépése a $ \ket{+} $ állapotú kiegészítő qubit előkészítésével jár együtt, a kezdeti állapot pedig az $ \ket{\phi} $, amelyet feltételezzük, [hogy az $U](xref:microsoft.quantum.concepts.matrix-advanced) (m) $, azaz $U (m) \ket{\phi} = e ^ {im\phi} \ ket {\ Phi} $.  
Ekkor a rendszer egy vezérelt alkalmazást `U(m)` használ, amely előkészíti a $ \left (R \_ 1 (m \phi) \ket{+} \right) \ket{\phi} $ állapotot.
Ahogy a Quantum Case esetében, az Oracle ellenőrzött alkalmazásának hatása `U(m)` pontosan ugyanaz, mint a $ \ket{+} $ ismeretlen fázisra vonatkozó $R _1 $ alkalmazásának hatása, így a $U $-re vonatkozó hatásokat ebben az egyszerűbb módon tudjuk leírni.
Szükség esetén az algoritmus elforgatja a vezérlő qubit úgy, hogy $R _1 (-m\theta) $ érték beszerzésére alkalmazza a következő állapotot: $ \ket{\psi} = \left (R \_ 1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
A vezérlőként használt kiegészítő qubit a `U(m)` rendszer a $X $ alapon méri, hogy egyetlen klasszikust szerezzen be `Result` .

Ezen a ponton az `Result` iterációs fázis becslése által beszerzett értékek fázisának újraépítése a klasszikus statisztikai következtetési probléma.
A $m $ értékének megkeresése, amely maximalizálja a szerzett adatokat, mivel a rögzített következtetési módszer miatt egyszerűen probléma van a statisztikában.
Ezt úgy hangsúlyozzuk, hogy röviden leírja az iterációs fázisok becslését elméleti szinten a Bayes-as paraméter alapján, mielőtt a Canonban ismertetjük a Q# klasszikus következtetési probléma megoldásához szükséges statisztikai algoritmusokat.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Iterációs fázis becslése Eigenstates nélkül ###

Ha olyan bemeneti állapotot ad meg, amely nem eigenstate, azaz ha $U (m) \ket{\phi \_ j} = e ^ {im\phi \_ j} $, akkor a fázisok becslésének folyamata nem determinisztikus módon a kvantum-állapotot egyetlen energetikai eigenstate irányába.  A eigenstate végül az a eigenstate, amely a legvalószínűbb, hogy a megfigyelt terméket fogja létrehozni `Result` .

A PE egyetlen lépése a következő, nem egységes átalakítást hajtja végre az állapot \begin{align} \ sum_j \sqrt{\Pr (\phi \_ j)} \ket{\phi \_ j} \mapsto \sum \_ j\frac {\ SQRT {\ PR (\phi \_ j)} \sqrt{\Pr (\text{result} | \phi \_ j)} \Ket{\phi \_ j}} {\sqrt{\Pr (\phi j \_ ) \sum \_ j \Pr (\text{result} | \phi \_ j)}}.
\end{align}, mivel ezt a folyamatot több értékre is megismétlik `Result` , a $ \ prod_k \pr (\text{result} \_ k | \phi j) $ maximális értékkel nem rendelkező eigenstates \_ exponenciálisan lesznek letiltva.
Ennek eredményeképpen a következtetési folyamat általában egyetlen sajátérték rendelkező állapotokra lesz átszervezve, ha a kísérletek megfelelően vannak kiválasztva.

A Bayes "tétel továbbra is azt sugallja, hogy a fázis becslésének eredményét a \begin{align} \frac{\sqrt{\Pr (\phi \_ j)} \sqrt{\Pr (\text{result} | \phi \_ j)} \ket{\phi \_ j}} {\sqrt{\Pr (\phi \_ j) \Sum \_ j \Pr (\text{result} | \phi \_ j)}} = \ sum_j \sqrt{\Pr (\phi \_ j | \text{result})} \ket{\phi \_ j}.
\end{align} itt $ \Pr (\phi \_ j | \text{result}) $ lehet értelmezendő, mert a valószínűsége annak, hogy az egyes hipotézisek az adott eigenstates kapcsolatban szerepelnek:

1. a kvantum állapot ismerete a mérés előtt
2. $U $ és eigenstates ismerete
3. $U $ eigenvalues ismerete.

A három dolog megismerése gyakran exponenciálisan megnehezíti a klasszikus számítógépeket.
A fázisok becslésének segédprogramja nem csupán kis mértékben áll fenn, mert az ilyen típusú kvantum-tanulási feladatot anélkül is elvégezhet, hogy azok ismerete lenne.
Ennek az okának a becslése számos olyan kvantum-algoritmuson belül jelenik meg, amelyek exponenciális sebességeket biztosítanak.

### <a name="bayesian-phase-estimation"></a>A Bayes fázis becslése ###

> [!TIP]
> A következő témakörben talál további információt a Bayes fázis becsléséről a gyakorlatban: [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation) minta.

A Bayes-fázis becslésének ötlete egyszerű.
A fázis-becslési protokollból gyűjti a mérési statisztikát, majd az eredményeket a Bayes-következtetéssel dolgozza fel, és megbecsüli a paramétert.
Ez a feldolgozás a sajátérték, valamint a becsült bizonytalanságot is megadja.
Lehetővé teszi az adaptív kísérletek elvégzését és az előzetes információk felhasználását is.
A metódusok elvi hátránya, hogy számítási feltételként kell megkövetelni.

Ha meg szeretné tudni, hogyan működik ez a Bayes-féle következtetési folyamat, vegye figyelembe az egyetlen eredmény feldolgozásának esetét `Zero` .
Vegye figyelembe, hogy $X = \ket{+} \bra{+}-\ket {-} \bra {-} $, például a $ \ket{+} $ érték az egyetlen pozitív eigenstate, amely a $X $-nek felel meg `Zero` .
Az `Zero` első qubit [ `PauliX` mérésének](xref:microsoft.quantum.concepts.pauli) valószínűsége, ha a bemeneti állapot $ \ket{\psi}\ket{\phi} $, így \begin{Equation} \Pr (\texttt{Zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} az ismétlődő fázisok becslése esetén a $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, például \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \right) \left (\ket {0} + e ^ {i m [\phi-\theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: fázis-est-valószínűség}.
a \end{align} az iterációs fázis becslése egy szinuszos függvény rezgő gyakoriságának megismerését jelenti, amely lehetővé teszi, hogy egy érmet a sinusoid által adott torzítással lehessen átadni.
A hagyományos klasszikus terminológiát követve a $ \eqref{EQ: Phase-est-valószínűség} $ értéket hívjuk az iterációs fázis becslésének *valószínűségi függvényében* .

Miután megfigyelte `Result` , hogy az iterációs fázis kiértékelésének valószínűsége függvényt használja, a Bayes szabály használatával írhatja be, hogy mit higgyünk a megfigyelés követésének fázisában.
Konkrétan, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation}, ahol $d \in \\ {\texttt{Zero}, \texttt{One} \\ } $ a `Result` , és ahol $ \Pr (\phi) $ leírja a $ \phi $-vel kapcsolatos korábbi hiedelmeket.
Ezután az iterációs fázis becslésének iterációs jellegét adja meg explicit módon, mivel a posterior Distribution $ \Pr (\phi | d) $ a következő bevezetését közvetlenül megelőzően ismerteti `Result` .

Ebben az eljárásban a klasszikus vezérlő által a \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \text{Data}] = \int \phi \Pr (\phi | \text{Data}) {\mathrm d} \phi, \end{Equation}, ahol a $ \text{Data} $ a beszerzett értékek teljes rekordját jelenti, \hat{\phi} `Result` .

A Bayes-következtetések pontos megállapítása a gyakorlatban megoldhatatlan.
Ehhez Képzelje el, hogy $n $-bit változót szeretne megtanulni $x $-ra.
A korábbi Distribution $ \Pr (x) $ támogatás több mint $2 ^ n $ feltételezett értéket támogat a $x $ értéknél.
Ez azt jelenti, hogy ha nagyon pontos becslésre van szükségünk, $x $, akkor a Bayes-fázis becslése tiltó memóriát és feldolgozási időt igényel.
Egyes alkalmazások, például a kvantum-szimulációk esetében a limitted pontossága nem zárja ki az ilyen metódusokat, például a rövid algoritmust, a szakasz becslésének lépésein belül nem használhatók a pontos Bayes-következtetések.  Ezért megvalósításokat is biztosítunk a Bayes-as módszerekhez, például a [véletlenszerű RWPE-becslésekhez](xref:Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation) , valamint a nem bayesos megközelítésekhez, például a [robusztus fázisok becsléséhez](xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation).

### <a name="robust-phase-estimation"></a>Robusztus fázis becslése ###

A mérési eredményekből származó fázisok becsült *utólagos* újraépítése exponenciálisan megnehezíti a legrosszabb esetben. Így a gyakorlatban a gyakorlati fázis becslése algoritmusok bizonyos minőségeket feláldoznak a rekonstrukcióban, a klasszikus feldolgozások mennyiségét pedig az elvégzett mérések számával együtt.

Egy ilyen példa egy hatékony klasszikus utólagos feldolgozási lépés a [robusztus fázis-becslési algoritmus](https://arxiv.org/abs/1502.02677), amely a fent említett aláírást és bemeneteket is megjeleníti. Ez azt feltételezi, hogy a bemeneti, $U $ értékű fekete dobozok típusaként vannak becsomagolva `DiscreteOracle` , így csak a vezérelt $U $ egész számú jogosultságot kérdezi le. Ha a regisztráció bemeneti állapota `Qubit[]` eigenstate $U \ket{\psi} = e ^ {i\phi} \ ket {\ psi} $, a robusztus fázis-becslési algoritmus a becslés $ \hat{\phi}\in [-\pi, \pi) $ $ \phi $ értéket adja vissza `Double` .

A robusztus fázisok becslésének legfontosabb funkciója, amelyet a legtöbb más hasznos változatban megosztanak, az, hogy a $ \hat{\phi} $ újraépítési minőség bizonyos értelemben Heisenberg korlátozott. Ez azt jelenti, hogy ha a valódi érték $ \hat{\phi} $ értéke a $ \sigma $, akkor a $ \sigma $ függvény fordítottan arányos – az ellenőrzött $U $-ra, azaz a $ \sigma = \mathcal{O} (1/Q) $ értékű $Q lekérdezések teljes számával arányosan. Az eltérés definíciója most a különböző becslési algoritmusok között változik. Bizonyos esetekben előfordulhat, hogy legalább $ \mathcal{O} (1) $ valószínűséggel, a becslési hiba $ | \hat{\phi}-\phi | \_ \circ\le \sigma $ egy bizonyos körkörös mértéknél $ \circ $. A robusztus fázisok becslése esetében az eltérés pontosan a következő variancia: $ \sigma ^ 2 = \mathbb{E} \_ \hat{\phi} [(\mod \_ {2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $, ha az időszakos fázisokat egyetlen véges intervallumra (-\pi, \pi] $-ra csomagoljuk. Pontosabban, a robusztus fázisok becslésének szórása megfelel a $ $ \begin{align} 2,0 \pi/Q \Le \sigma \Le 2 \ pi/2 ^ {n} \Le 10.7 \ PI/Q, \end{align} $ $, ahol az alsó határ elérte a nagy $Q $ izomorf korlátot, és a felső határ garantált a kis méretű minták esetében is.  Vegye figyelembe, hogy a bemenet által kiválasztott $n $ `bitsPrecision` , amely implicit módon meghatározza a $Q $ értéket.

A további releváns részletek közé tartozik például a $1 $ Ancilla qubit, illetve az eljárás nem adaptív, azaz a kvantum-kísérletek szükséges sorozata független a köztes mérési eredményektől. Ebben a és a közelgő példákban a fázis-becslési algoritmus kiválasztása fontos, az egyiknek a dokumentációra, például @"microsoft.quantum.characterization.robustphaseestimation" a hivatkozott kiadványokra, valamint a megvalósítására kell hivatkoznia.

> [!TIP]
> Számos minta van, ahol robusztus fázis-becslést használunk. A különböző fizikai rendszerek alapvető állapotának kinyeréséhez szükséges fázis-becsléshez tekintse meg a [ **H2-szimulációs** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line), a [ **SimpleIsing** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)és a [ **Hubbard Model** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Folyamatos Oracle- ###

A fentiekben ismertetett Oracle-modell általánosítható is, hogy a folyamatos Oracle-típusok a Canon típus szerint legyenek modellezve <xref:Microsoft.Quantum.Oracles.ContinuousOracle> .
Vegye figyelembe, hogy ahelyett, hogy egyetlen, egységes operátort $U $-t használunk, az egységes operátorok családja $U (t) $, $t \in \mathbb{R} $, hogy $U (t) U (s) $ = $U (t + s) $.
Ez egy gyengébb utasítás, mint a diszkrét esetekben, mivel a kialakítható a <xref:Microsoft.Quantum.Oracles.DiscreteOracle> $t = m \, \delta t $ korlátozásával néhány Fixed $ \delta t $ értékkel.
A [Stone-tétel](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ egyes operátorok esetében $H $, ahol a $ \exp $ a mátrix exponenciális értéke a [speciális mátrixok](xref:microsoft.quantum.concepts.matrix-advanced)részben leírtak szerint.
Egy eigenstate $ \ket{\phi} $ $H $-ból, amely $H \ket{\phi} = \phi \ket{\phi} $-t is eigenstate $U (t) $ az összes $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

A [Bayes fázis becslésének](#bayesian-phase-estimation) pontos elemzése is alkalmazható, és a valószínűségi függvény pontosan ugyanaz ennél az általános Oracle-modellnél: $ $ \Pr (\texttt{Zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]} {2} \right).
$ $ Továbbá, ha $U $ egy dinamikus generátor szimulációja, mint a [Hamilton-szimuláció](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)esetében, akkor a $ \phi $ értéket használjuk energiaként.
Így a folyamatos lekérdezésekkel a fázisok becslése lehetővé teszi, hogy megismerjük a molekulák, [anyagok](https://arxiv.org/abs/1510.03859) vagy [mezők elméletének](https://arxiv.org/abs/1111.3633v2) szimulált [energia-spektrumát](https://arxiv.org/abs/quant-ph/0604193)anélkül, hogy az $t

### <a name="random-walk-phase-estimation"></a>Véletlenszerű séta fázisának becslése ###

Q# hasznos közelítést nyújt a Bayes-fázis becsléséhez, amelyet úgy terveztek, hogy az olyan kvantum-eszközökhöz közelítse a használatot, amelyek az iterációs fázis becslése alapján kapott adatrekordon véletlenszerű sétával működnek.
Ez a módszer egyaránt adaptív és teljes mértékben determinisztikus, ami lehetővé teszi a hibák közel optimális méretezését a becsült "\hat{\phi} $" fázisban, nagyon alacsony memóriával.

A protokoll egy hozzávetőleges Bayes-következtetési módszert használ, amely feltételezi, hogy az előző eloszlás a Gauss.
Ez a Gauss-feltevés lehetővé teszi, hogy a kísérlethez olyan analitikai képletet használjon, amely a hátsó variancia minimalizálását végzi.
Az algoritmus ezután a kísérlet eredménye alapján áthelyezi a $ \phi $ értéket egy előre meghatározott összeggel balra vagy jobbra, és egy előre meghatározott összeggel csökkenti a variancia értékét.
Ez a középérték és a variancia adja meg az összes olyan információt, amely szükséges a Gauss megadásához a $ \phi $ értéknél a következő kísérletnél.
A nem várt mérési hibák, vagy a kezdeti előtt az igaz eredmény az, hogy ez a metódus sikertelen lesz.
A művelet sikertelenül helyreállítja a kísérleteket, hogy tesztelje, hogy a jelenlegi középérték és szórás megfelelő-e a rendszer számára.
Ha nem, akkor az algoritmus a séta inverz lépését és a folyamat folytatását is folytatja.
A visszafelé lépés lehetővé teszi, hogy az algoritmus még akkor is tudjon tanulni, ha a kezdeti korábbi szórás inapropriately kicsi.

## <a name="calling-phase-estimation-algorithms"></a>Hívási fázisok becslési algoritmusai ##

A Canon által biztosított minden fázis-becslési művelet Q# különböző bemeneteket használ a parameterizing, amelyet a végleges becslés $ \hat{\phi} $ értékkel együtt igényel.
Ezek a különböző bemenetek azonban a közösen több bemenetet is megosztanak, például a minőségi paraméterekben lévő részleges alkalmazások közös aláírást eredményeznek.
A <xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation> következő szakaszban tárgyalt művelet például a következő aláírással rendelkezik:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

A `bitsPrecision` bemenet egyedi `RobustPhaseEstimation` , míg a `oracle` és a `eigenstate` közös.
Így ahogy a **H2Sample** is látható, egy művelet elfogadhat egy iterációs fázis-értékelési algoritmust, amely az űrlap bemenetével `(DiscreteOracle, Qubit[]) => Unit` lehetővé teszi, hogy a felhasználó tetszőleges fázisú becslési algoritmusokat adjon meg:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Ezek a számtalan fázis-becslési algoritmusok különböző tulajdonságokra és bemeneti paraméterekre vannak optimalizálva, amelyeket érdemes értelmezni a célalkalmazás legmegfelelőbb választásához. Például egyes fázis-becslési algoritmusok adaptívak, ami azt jelenti, hogy a jövőbeli lépéseket a korábbi lépések mérési eredményei klasszikusan szabályozzák. Egyesek számára lehetővé kell tenni, hogy a fekete dobozos egységes Oracle-t tetszőleges valós hatáskörökkel exponentiate, mások pedig csak egész hatásköröket igényelnek, de csak a 2. számú, 2 \ PI $ adatmennyiséget tudják feloldani. Némelyikhez számos kiegészítő qubits szükséges, mások pedig csak egyet igényelnek.

Hasonlóképpen, ha a véletlenszerű séta fázisának becslését használja, ugyanúgy, mint a canonhoz tartozó más algoritmusokkal:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
