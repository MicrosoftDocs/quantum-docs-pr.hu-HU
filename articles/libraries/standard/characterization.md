---
title: Quantum jellemzés és statisztika
description: Ebből a szakaszból megtudhatja, hogyan használhatók a mérési statisztikák a fázis-becslésekben a kvantum-programozás eredményeinek becsléséhez.
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7ed92c29020ccf389faa099f5bd80516af525578
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907188"
---
# <a name="quantum-characterization-and-statistics"></a>Quantum jellemzés és statisztika #

Fontos, hogy képes legyen jellemezni a műveletek hatásait a hasznos kvantum-algoritmusok kifejlesztése érdekében.
Ez kihívást jelenthet, mivel a kvantumrendszer minden mérése legfeljebb egy kis mennyiségű adatot eredményez.
Egy sajátérték megismeréséhez, amely lehetővé teszi a kvantum-állapotot, a számos mérés eredményét össze kell keverni, hogy a felhasználó fel tudja venni az ilyen fogalmak ábrázolásához szükséges sok bitet.
A kvantum-állapotok különösen bosszantóak, mert a [nem klónozási tétel](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) azt jelzi, hogy az állapot egyetlen példányáról sem lehet tetszőleges kvantum-állapotot betanulni, mert ezzel az állapot másolatait is lehetővé tenné.
A rendszer a kvantum-állapotnak a felhasználótól való összezavarodott állapotát tükrözi abban a tényben, hogy a Q # nem tesz elérhetővé vagy nem határozza meg *, hogy milyen állapotban* legyenek a kvantum-programok.
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
Az [adatstruktúrákban](xref:microsoft.quantum.libraries.data-structures)található Oracle-k című szakaszban leírtak szerint a Q # canon a <xref:microsoft.quantum.oracles.discreteoracle> felhasználó által definiált típus alapján végzi el a műveleteket, `((Int, Qubit[]) => Unit : Adjoint, Controlled)`a rekord típusa határozza meg.
Konkrétan, ha `U : DiscreteOracle`, `U(m)` implementálja $U ^ millió $ értéket `m : Int`.

Ennek a definíciónak a helyén az ismétlődő fázisok becslésének minden lépése a $ \ket{+} $ állapotú kiegészítő qubit előkészítésével jár együtt, a kezdeti állapot pedig az $ \ket{\phi} $, amelyet feltételezzük, [hogy az $U](xref:microsoft.quantum.concepts.matrix-advanced) (m) $, azaz $U (m) \ket{\phi} = e ^ {im\phi} \ ket {\ Phi} $.  
A rendszer a `U(m)` vezérelt alkalmazását használja, amely előkészíti a $ \left (R\_1 (m \phi) \ket{+} \right) \ket{\phi} $ állapotot.
Ahogy a Quantum Case esetében, az Oracle `U(m)` ellenőrzött alkalmazásának hatása pontosan ugyanaz, mint a $ \ket{+} $-on az ismeretlen fázisra vonatkozó $R _1 $ alkalmazásának hatása, így a $U $-re vonatkozó hatások ebben az egyszerűbb módon is leírható.
Szükség esetén az algoritmus elforgatja a vezérlő qubit úgy, hogy $R _1 (-m\theta) $ érték beszerzésével beszerezze a következő állapotot: $ \ket{\psi} = \left (R\_1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
A `U(m)` vezérlőként használt kiegészítő qubit $X $ alapon mérhető, hogy egyetlen klasszikus `Result`szerezzen be.

Ezen a ponton az iterációs fázis becslése által beszerzett `Result`i értékek fokozatos kiépítése a klasszikus statisztikai következtetési probléma.
A $m $ értékének megkeresése, amely maximalizálja a szerzett adatokat, mivel a rögzített következtetési módszer miatt egyszerűen probléma van a statisztikában.
Ezt úgy hangsúlyozzuk, hogy röviden leírja az iterációs fázisok becslését elméleti szinten a Bayes-as paraméter alapján, mielőtt folytatná a Q # Canonban található statisztikai algoritmusok leírását a klasszikus következtetési probléma megoldásához.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Iterációs fázis becslése Eigenstates nélkül ###

Ha olyan bemeneti állapotot ad meg, amely nem eigenstate, azaz ha $U (m) \ket{\phi\_j} = e ^ {im\phi\_j} $, akkor a fázisok becslésének folyamata nem determinisztikus módon a kvantum-állapotot egyetlen energetikai eigenstate irányába.  A eigenstate végül az a eigenstate, amely legvalószínűbb a megfigyelt `Result`előállítása.

Pontosabban, a PE egyetlen lépése a következő, nem egységes átalakítást hajtja végre az állapot \begin{align} \ sum_j \sqrt{\Pr (\phi\_j)} \ket{\phi\_j} \mapsto \sum\_j\frac {\ SQRT {\ PR (\phi\_j)} \sqrt{\Pr (\text{Result} | \phi\_j)} \ket{\phi\_j}} {\sqrt{\Pr (\phi\_j) \sum\_j \Pr (\text{Result} | \phi\_j)}}.
\end{align}, mivel ez a folyamat több `Result` értékre van megismételve, de a $ \ prod_k \Pr (\text{Result}\_k | \phi\_j) $ maximális értékkel nem rendelkező eigenstates exponenciálisan le lesz tiltva.
Ennek eredményeképpen a következtetési folyamat általában egyetlen sajátérték rendelkező állapotokra lesz átszervezve, ha a kísérletek megfelelően vannak kiválasztva.

A Bayes "tétel továbbra is javasolja, hogy a fázis becslésének eredményét a \begin{align} \frac{\sqrt{\Pr (\phi\_j)} \sqrt{\Pr (\text{Result} | \phi\_j)} \ket{\phi\_j}} {\sqrt{\Pr (\phi\_j) \sum\_j \Pr (\text{Result} | \phi\_j)}} = \ sum_j \sqrt{\Pr (\phi\_j | \text{Result})} \ket{\phi\_j}.
\end{align} itt $ \Pr (\phi\_j | \text{Result}) $ lehet értelmezendő, mivel a valószínűsége az, hogy az egyes hipotézisek az adott eigenstates kapcsolatban szerepelnek:

1. a kvantum állapot ismerete a mérés előtt
2. $U $ és eigenstates ismerete
3. $U $ eigenvalues ismerete.

A három dolog megismerése gyakran exponenciálisan megnehezíti a klasszikus számítógépeket.
A fázisok becslésének segédprogramja nem csupán kis mértékben áll fenn, mert az ilyen típusú kvantum-tanulási feladatot anélkül is elvégezhet, hogy azok ismerete lenne.
Ennek az okának a becslése számos olyan kvantum-algoritmuson belül jelenik meg, amelyek exponenciális sebességeket biztosítanak.

### <a name="bayesian-phase-estimation"></a>A Bayes fázis becslése ###

> [!TIP]
> A következő témakörben talál további információt a Bayes fázis becsléséről a gyakorlatban: [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) minta.

A Bayes-fázis becslésének ötlete egyszerű.
A fázis-becslési protokollból gyűjti a mérési statisztikát, majd az eredményeket a Bayes-következtetéssel dolgozza fel, és megbecsüli a paramétert.
Ez a feldolgozás a sajátérték, valamint a becsült bizonytalanságot is megadja.
Lehetővé teszi az adaptív kísérletek elvégzését és az előzetes információk felhasználását is.
A metódusok elvi hátránya, hogy számítási feltételként kell megkövetelni.

Ha meg szeretné tudni, hogyan működik ez a Bayes-féle következtetési folyamat, vegye figyelembe, hogy az egyetlen `Zero` eredmény feldolgozásának esete.
Vegye figyelembe, hogy $X = \ket{+} \bra{+}-\ket{-}\bra{-}$, így a $ \ket{+} $ érték az egyetlen pozitív eigenstate, amely `Zero`nak megfelelő $X $.
A [`PauliX` mérések](xref:microsoft.quantum.concepts.pauli) `Zero`ának valószínűsége az első qubit vonatkozóan, amely a $ \ket{\psi}\ket{\phi} $ bemeneti állapotot kapta, így \begin{Equation} \Pr (\texttt{Zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} az ismétlődő fázisok becslése esetén a $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, például \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\\\ & = \left | \frac12 \left (\bra{0} + \bra{1} \right) \left (\ket{0} + e ^ {i m [\phi-\theta]} \ket{1} \right) \right | ^ 2 \\\\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}}{2} \right | ^ 2 \\\\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: Phase-est-valószínűség}.
a \end{align} az iterációs fázis becslése egy szinuszos függvény rezgő gyakoriságának megismerését jelenti, amely lehetővé teszi, hogy egy érmet a sinusoid által adott torzítással lehessen átadni.
A hagyományos klasszikus terminológiát követve a $ \eqref{EQ: Phase-est-valószínűség} $ értéket hívjuk az iterációs fázis becslésének *valószínűségi függvényében* .

Miután megfigyelte az iterációs fázis becsült valószínűségi függvényének `Result`ét, a Bayes szabályt használva megadhatja, hogy mit higgyünk a megfigyelés követésének fázisában.
Konkrétan, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation}, ahol $d \in \\{\texttt{Zero}, \texttt{One}\\} $ egy `Result`, és ahol $ \Pr (\phi) $ leírja a $ \phi $-vel kapcsolatos korábbi hiedelmeket
Ekkor az iterációs fázis becslésének iterációs jellege egyértelművé válik, mivel a posterior Distribution $ \Pr (\phi | d) $ a következő `Result`megfigyelését követően azonnal leírja a hitét.

Ebben az eljárásban bármely ponton jelentést készíthetünk a klasszikus vezérlő által a \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \text{Data}] = \int \phi \Pr (\phi | \text{Data}) {\mathrm d} \phi, \end{Equation}, ahol $ \text{Data} $ a kapott összes `Result` érték teljes \hat{\phi}.

A Bayes-következtetések pontos megállapítása a gyakorlatban megoldhatatlan.
Ehhez Képzelje el, hogy $n $-bit változót szeretne megtanulni $x $-ra.
A korábbi Distribution $ \Pr (x) $ támogatás több mint $2 ^ n $ feltételezett értéket támogat a $x $ értéknél.
Ez azt jelenti, hogy ha nagyon pontos becslésre van szükségünk, $x $, akkor a Bayes-fázis becslése tiltó memóriát és feldolgozási időt igényel.
Egyes alkalmazások, például a kvantum-szimulációk esetében a limitted pontossága nem zárja ki az ilyen metódusokat, például a rövid algoritmust, a szakasz becslésének lépésein belül nem használhatók a pontos Bayes-következtetések.  Ezért megvalósításokat is biztosítunk a Bayes-as módszerekhez, például a [véletlenszerű RWPE-becslésekhez](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation) , valamint a nem bayesos megközelítésekhez, például a [robusztus fázisok becsléséhez](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Robusztus fázis becslése ###

A mérési eredményekből származó fázisok becsült *utólagos* újraépítése exponenciálisan megnehezíti a legrosszabb esetben. Így a gyakorlatban a gyakorlati fázis becslése algoritmusok bizonyos minőségeket feláldoznak a rekonstrukcióban, a klasszikus feldolgozások mennyiségét pedig az elvégzett mérések számával együtt.

Egy ilyen példa egy hatékony klasszikus utólagos feldolgozási lépés a [robusztus fázis-becslési algoritmus](https://arxiv.org/abs/1502.02677), amely a fent említett aláírást és bemeneteket is megjeleníti. Ez azt feltételezi, hogy a bemeneti $U $ beviteli mezők `DiscreteOracle` típusként vannak becsomagolva, ezért csak az ellenőrzött $U $ értékre vonatkozó egész hatásköröket kérdezik le. Ha a `Qubit[]`-regisztráció bemeneti állapota egy eigenstate $U \ket{\psi} = e ^ {i\phi} \ ket {\ psi} $, a robusztus fázis-becslési algoritmus a becslés $ \hat{\phi}\in [-\pi, \pi) $ $ \phi $ értéket adja vissza `Double`ként.

A robusztus fázisok becslésének legfontosabb funkciója, amelyet a legtöbb más hasznos változatban megosztanak, az, hogy a $ \hat{\phi} $ újraépítési minőség bizonyos értelemben Heisenberg korlátozott. Ez azt jelenti, hogy ha a valódi érték $ \hat{\phi} $ értéke a $ \sigma $, akkor a $ \sigma $ függvény fordítottan arányos – az ellenőrzött $U $-ra, azaz a $ \sigma = \mathcal{O} (1/Q) $ értékű $Q lekérdezések teljes számával arányosan. Az eltérés definíciója most a különböző becslési algoritmusok között változik. Bizonyos esetekben előfordulhat, hogy legalább $ \mathcal{O} (1) $ valószínűséggel, a becslési hiba $ | \hat{\phi}-\phi |\_\circ\le \sigma $ egy körkörös mértékben $ \circ $. A robusztus fázisok becsléséhez az eltérés pontosan a $ \sigma ^ 2 = \mathbb{E}\_\hat{\phi} [(\mod\_{2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $, ha az időszakos fázisokat egyetlen véges intervallumra (-\pi, \pi] $-ra csomagoljuk. Pontosabban, a robusztus fázisok becslésének szórása megfelel a $ $ \begin{align} 2,0 \pi/Q \Le \sigma \Le 2 \ pi/2 ^ {n} \Le 10.7 \ PI/Q, \end{align} $ $, ahol az alsó határ elérte a nagy $Q $ izomorf korlátot, és a felső határ garantált a kis méretű minták esetében is.  Vegye figyelembe, hogy a `bitsPrecision` bemenet által kiválasztott $n $, amely implicit módon meghatározza a $Q $ értéket.

A további releváns részletek közé tartozik például a $1 $ Ancilla qubit, illetve az eljárás nem adaptív, azaz a kvantum-kísérletek szükséges sorozata független a köztes mérési eredményektől. Ebben és a közelgő példákban a fázis-becslési algoritmus kiválasztása fontos, az egyiknek a dokumentációra kell hivatkoznia, például a @"microsoft.quantum.characterization.robustphaseestimation"ra és a hivatkozott kiadványokra a további információért és a megvalósításhoz.

> [!TIP]
> Számos minta van, ahol robusztus fázis-becslést használunk. A különböző fizikai rendszerek alapvető állapotának kinyeréséhez szükséges fázis-becsléshez tekintse meg a [ **H2-szimulációs** mintát](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line), a [ **SimpleIsing** mintát](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)és a [ **Hubbard Model** mintát](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Folyamatos Oracle- ###

A fentiekben ismertetett Oracle-modellből is általánosíthat, hogy a folyamatos Oracle-ket a Canon Type <xref:microsoft.quantum.oracles.continuousoracle>modellezi.
Vegye figyelembe, hogy ahelyett, hogy egyetlen, egységes operátort $U $-t használunk, az egységes operátorok családja $U (t) $, $t \in \mathbb{R} $, hogy $U (t) U (s) $ = $U (t + s) $.
Ez egy gyengébb utasítás, mint a diszkrét esetekben, mivel a <xref:microsoft.quantum.oracles.discreteoracle> a $t = m\,\delta t $ korlátozásával lehet kialakítani, hogy egyes rögzített $ \delta t $.
A [Stone-tétel](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ egyes operátorok esetében $H $, ahol a $ \exp $ a mátrix exponenciális értéke a [speciális mátrixok](xref:microsoft.quantum.concepts.matrix-advanced)részben leírtak szerint.
Egy eigenstate $ \ket{\phi} $ $H $-ból, amely $H \ket{\phi} = \phi \ket{\phi} $-t is eigenstate $U (t) $ az összes $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

A [Bayes fázis becslésének](#bayesian-phase-estimation) pontos elemzése is alkalmazható, és a valószínűségi függvény pontosan ugyanaz ennél az általános Oracle-modellnél: $ $ \Pr (\texttt{Zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]}{2}\right).
$ $ Továbbá, ha $U $ egy dinamikus generátor szimulációja, mint a [Hamilton-szimuláció](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)esetében, akkor a $ \phi $ értéket használjuk energiaként.
Így a folyamatos lekérdezésekkel a fázisok becslése lehetővé teszi, hogy megismerjük a molekulák, [anyagok](https://arxiv.org/abs/1510.03859) vagy [mezők elméletének](https://arxiv.org/abs/1111.3633v2) szimulált [energia-spektrumát](https://arxiv.org/abs/quant-ph/0604193)anélkül, hogy az $t

### <a name="random-walk-phase-estimation"></a>Véletlenszerű séta fázisának becslése ###

A Q # hasznos közelítést nyújt a Bayes-fázis becsléséhez, amelyet úgy terveztek, hogy olyan kvantum-eszközökhöz közelítse a használatot, amelyek az iterációs fázis becslése által beszerzett adatrekordon egy véletlenszerű sétával működnek.
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

A Q # Canon által biztosított minden fázis-becslési művelet különböző bemeneti adatokat vesz igénybe, amelyek a végleges becslés $ \hat{\phi} $ parameterizing.
Ezek a különböző bemenetek azonban a közösen több bemenetet is megosztanak, például a minőségi paraméterekben lévő részleges alkalmazások közös aláírást eredményeznek.
Például a következő szakaszban tárgyalt <xref:microsoft.quantum.characterization.robustphaseestimation> művelet a következő aláírással rendelkezik:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

A `bitsPrecision`-bemenet egyedi `RobustPhaseEstimation`, míg a `oracle` és a `eigenstate` közösek.
Így a **H2Sample**-ben látható módon egy művelet elfogadhat egy iterációs fázis-értékelési algoritmust, amely a `(DiscreteOracle, Qubit[]) => Unit` űrlap bemenetével lehetővé teszi, hogy a felhasználó tetszőleges fázis-becslési algoritmusokat adjon meg:

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
