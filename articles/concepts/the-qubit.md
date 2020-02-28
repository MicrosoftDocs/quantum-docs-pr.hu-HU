---
title: A Quantum Computing qubit
description: Ismerje meg a qubits, a Quantum Computing információinak alapvető egységét.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 770b739d95f5c1512234f6f7d2ca4544f1d80e64
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907528"
---
# <a name="the-qubit"></a>A Qubit

Akárcsak a BITS a klasszikus számítástechnikai információk alapvető információi, a [*qubits*](https://en.wikipedia.org/wiki/Qubit) (Quantum BITS) a kvantum-számítástechnika alapvető információi.  A levelezés megismeréséhez nézzük meg a legegyszerűbb példát: egyetlen qubit.

## <a name="representing-a-qubit"></a>Qubit jelölő

Egy kis-vagy bináris számjegy esetében akár $0 $ vagy $1 $ értékű is lehet, a qubit értéke a következők egyike lehet, vagy pedig a $0 $ és a $1 $ érték kvantum-kiosztása.

Egyetlen qubit állapotát az egység normájának kétdimenziós oszlopos vektora írja le, azaz a bejegyzéseinek nagyságrendjét a $1 $ értékre kell állítani. Ez a "Quantum State Vector" nevű vektor tartalmazza az összes olyan információt, amely az qubit kvantum-rendszer leírásához szükséges, ugyanúgy, mint egyetlen bit a bináris változók állapotának leírásához szükséges összes információt tartalmazza.

A valós vagy komplex számú, a $1 $-os normával rendelkező kétdimenziós oszlop a qubit által tárolt lehetséges kvantum-állapotot jelöli. Így a $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ qubit-állapotot jelöl, ha a $ \alpha $ és a $ \beta $ olyan összetett számok, amelyek megfelelnek a $ | \alpha | ^ 2 + | \beta | ^ 2 = $1. Néhány példa a qubits jelölő érvényes kvantum-állapotú vektorokra

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{és} \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{i}{\sqrt{2}} \end{bmatrix}. $ $

A Quantum State vectors $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ és $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $, és egy speciális szerepkört is igénybe vehetik. Ez a két vektor képezi a qubit állapotát leíró vektoros terület alapját. Ez azt jelenti, hogy a kvantum-állapot vektora ezen alapul szolgáló vektorok összegeként írható. Pontosabban, az \begin{bmatrix} x \\\\ y \end{bmatrix} $ $x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ értéket lehet írni. Habár ezek a vektorok bármilyen forgása tökéletesen érvényes alapként szolgál a qubit számára, úgy döntünk, hogy ezt a jogosultságot a *számítási alap*meghívásával emeljük ki.

Ezt a két kvantum-állapotot a klasszikus bit két állapotának, azaz a $0 $ és a $1 $ értéknek kell megfelelnie. A standard konvenció a következő választás

$ $0 \ EQUIV \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad 1 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}, $ $

Habár a szemközti választási lehetőség is megfelelő lehet. Így a lehetséges qubit kvantum-állapotú vektorok végtelen száma közül csak kettő felel meg a klasszikus bitek állapotának. az összes többi kvantum-állapot nem.

## <a name="measuring-a-qubit"></a>Qubit mérése

Most, hogy már tudjuk, hogyan jelentheti a qubit, megtudhatjuk, hogy mit jelentenek ezek az államok a [*mérés*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)koncepciójának megvitatása során. Egy mérték megfelel a "looking" qubit, amely azonnal Összecsukja a kvantum-állapotot a két klasszikus állapot közül a $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ vagy a $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ értéket. Ha a Quantum State Vector $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ értékkel megadott qubit mérik, a $0 $ értéket kapjuk meg, a valószínűség: $ | \alpha | ^ 2 $, valamint a $1 $ értéket a valószínűség $ | \beta | ^ 2 $. A $0 $ értéknél a qubit új állapota $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $; $1 $ után az állapota $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $. Vegye figyelembe, hogy ezek a valószínűségek összege $1 $, a normalizálás feltétele miatt $ | \alpha | ^ 2 + | \beta | ^ 2 = $1.

A mérés tulajdonságai azt is jelenti, hogy a kvantum-állapot vektorának általános aláírása lényegtelen. A vektor megtagadásával egyenértékű a $ \alpha \rightarrow-\alpha $ és a $ \beta \rightarrow-\beta $ értékkel. Mivel a $0 $ és a $1 $ mérés valószínűsége a feltételek méretétől függ, az ilyen jelek beillesztése nem változtatja meg a valószínűségeket. Az ilyen fázisokat általában [``*globális fázisokban*(""](https://en.wikipedia.org/wiki/Phase_factor) ), és általánosabban lehet $e ^ {i \phi} $, nem csupán $ \pm $1.

A mérés utolsó fontos tulajdonsága, hogy nem szükségszerűen károsítja az összes kvantum-állapotú vektort. Ha a \begin{bmatrix} \\1. állapotú qubit kezdődnek, \\ 0 \end{bmatrix} $, amely a klasszikus állapot $0 $-nak felel meg, akkor a mérés ez az állapot mindig a $0 $ eredményt adja, és változatlanul hagyja a kvantum-állapotot. Ebben az értelemben, ha csak a klasszikus BITS (azaz a qubits $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix} $ vagy $ \begin{bmatrix}0 \\\\ 1 \end{bmatrix} $), akkor a mérés nem károsítja a rendszerét. Ez azt jelenti, hogy a klasszikus adatmennyiséget replikálhatja, és a kvantum-számítógépeken ugyanúgy kezelheti azt, mint egy klasszikus számítógépen. Ugyanakkor az információk mindkét állapotban való tárolása egyszerre történik, ami túlmutat a kvantum-számítástechnika a klasszikusan lehetségesnél, és tovább megfosztja a kvantum-számítógépeket a Quantum-adatok válogatás nélküli másolásának lehetőségével, lásd még [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Qubits és átalakítások megjelenítése a Bloch szférával

A qubits a [*Bloch szféra*](https://en.wikipedia.org/wiki/Bloch_sphere) képviseletének használatával is megjelenhet a 3 $ D-ben.  A Bloch szférában egy qubit kvantum-állapot (amely egy kétdimenziós, összetett vektor), amely háromdimenziós, valós értékű vektor.  Ez azért fontos, mert lehetővé teszi, hogy megjelenítse az qubit állapotokat, és ezáltal a qubit állapotok megismerése szempontjából felbecsülhetetlen értékűek legyenek.  A Bloch gömb a következőképpen látható:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch gömb](~/media/concepts_bloch.png)

Az ábrán látható nyilak azt mutatják be, hogy a kvantum-állapot vektora hogyan mutat, és a nyíl minden átalakítása a kardinális tengelyek egyikére mutat.
Miközben a kvantum-számítási folyamatra gondol, mivel a Forgások sorozatából egy hatékony intuíció van, nagy kihívást jelent az algoritmusok megtervezése és leírása. A Q # ezt a problémát úgy enyhíti, ha az ilyen elforgatások leírására szolgáló nyelvet biztosít.

## <a name="single-qubit-operations"></a>Qubit műveletek

A kvantum-számítógépek a kvantum-kapuk univerzális készletének használatával dolgozzák fel az adatfeldolgozást, amely a kvantum-állapot vektorának bármilyen forgását Emulálhatja.
Ez az egyetemességi koncepció hasonlít a hagyományos (azaz klasszikus) számítástechnikai koncepcióhoz, ahol a kapuk univerzálisnak tekintendők, ha a bemeneti bitek minden átalakítása véges hosszúságú áramkör használatával végezhető el.
A kvantum-számítástechnika esetében a qubit elvégezhető érvényes átalakítások egységes átalakítások és mérések.
A *adjoint művelet* vagy az összetett konjugátum átültetése rendkívül fontos a Quantum Computing számára, mivel ez szükséges a kvantum-átalakítások megfordításához.
A Q # ezt a módszert mutatja be azáltal, hogy olyan metódusokat biztosít, amelyek automatikusan lefordítják a Gate-sorozatot a adjoint, ami sok esetben menti a programozót, hogy a adjoints. Alább látható egy példa:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Bár ez egy triviális példa (mivel a <xref:microsoft.quantum.intrinsic.h> művelet önadjoint), láthatja, hogy ez felbecsülhetetlen értékűebb qubit-műveletekből válik.
További információ: [Operations and functions](xref:microsoft.quantum.techniques.opsandfunctions).

A klasszikus számítógépeken csak négy függvény képezhető le egy kicsit. Ezzel szemben a kvantum-számítógépek egyetlen qubit végtelen számú egységes átalakítás létezik. Ezért a " [*Gates*](https://en.wikipedia.org/wiki/Quantum_logic_gate)" nevű egyszerű kvantum-műveletek egyetlen véges halmaza sem tudja pontosan replikálni a kvantum-számítástechnikai szolgáltatásban engedélyezett, egységes átalakítások végtelen készletét. Ez azt jelenti, hogy a klasszikus számítástechnikai rendszertől eltérően a kvantum-számítógép nem tudja megvalósítani az összes lehetséges kvantum-programot, amely pontosan véges számú kaput használ. Így a kvantum-számítógépek nem lehetnek univerzálisak a klasszikus számítógépek azonos értelemben. Ennek eredményeképpen, amikor azt mondjuk, hogy a kapuk halmaza *univerzális* a Quantum Computing esetében, valójában némileg gyengébb, mint a klasszikus számítástechnika.
Az egyetemesség esetében követelmény, hogy a kvantum-számítógép csak a véges hosszúságú Gate-sorozatot használva *közelítse* meg az összes egységes mátrixot egy véges hibán belül.
Más szóval, a Gates egy univerzális Gate-készlet, ha bármely egységes átalakítás a készletből származó Gates-termékként is írható. Megköveteljük, hogy az előírt hibákhoz kötve legyenek a Gates $G _{1}, a G_{2}, a \ldots, a G_N $ a kapu készletből, hogy

$ $ G_N G_ {N-1} \cdots G_2 G_1 \approx U. $ $

Vegye figyelembe, hogy mivel a mátrixok szorzási konvenciója a jobbról az első kapu műveletének $G _N $ értéket adja meg, valójában az utolsó, amelyet a kvantum-állapot vektorára alkalmaztak. Többek között úgy mondhatjuk, hogy egy ilyen Gate-készlet univerzális, ha minden hibatűrés $ \epsilon > 0 $ létezik $G _1, \ldots, G_N $, hogy a $G _N \ldots G_1 $ és $U $ közötti távolság legfeljebb $ \epsilon $. Ideális esetben $N $ $ \epsilon $ eléréséhez szükséges értéknek kell megfelelnie a Poly-logaritmikusan és a $1/\ epszilon $ közötti méretnek.

Mit jelent ez az univerzális Gate-készlet a gyakorlatban?  Az egyszeres qubit kapuk legegyszerűbb univerzális kapuja csak két kapuból áll: a Hadamard Gate $H $ és az úgynevezett $T $-Gate (más néven $ \ PI/8 $ Gate):

$ $ H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}, \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ {i \ PI/4} \end{bmatrix}.
$$

A kvantum-hibák kijavításával kapcsolatos gyakorlati okok miatt azonban kényelmesebb lehet a nagyobb kapuk készletének megfontolása, azaz az $H $ és a $T $ használatával hozható létre.
A Quantum Gates két kategóriába sorolhatók: Clifford Gates és $T $-Gate.
Ez az albontás azért hasznos, mert számos kvantum-hibajavítási sémában az úgynevezett Clifford-kapuk könnyen megvalósítható, ezért nagyon kevés erőforrásra van szükségük a műveletek és a qubits terén a hibatűrő működés megvalósításához, míg a nem Clifford-kapuk rendkívül költséges, ha hibatűrést igényel. A [Q #-ban alapértelmezés](xref:microsoft.quantum.libraries.standard.prelude)szerint a qubit Clifford Gates standard készlete tartalmazza a következőket:

$ $ H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}, \qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2, \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4H, $ $

$ $ Y = \begin{bmatrix} 0 &-i \\\\ & 0 \end{bmatrix} = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix}1 & 0\\\\ 0 &-1 \end{bmatrix} = T ^ 4.
$$

Itt az Operations $X $, $Y $ és a $Z $ is különösen gyakran használatos, és a megnevezett [*Pauli-operátorok*](https://en.wikipedia.org/wiki/Pauli_matrices) a Wolfgang Pauli létrehozója után.
A nem Clifford-kapuval (a $T $-Gate) együtt ezek a műveletek összeállíthatók egyetlen qubit egységes átalakításának megközelítve.

További információ ezekről a műveletekről, a Bloch-szférában végzett képviseletekről és a Q # implementációról: [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Példa arra, hogy ezekből a primitívekről hogyan lehet az egységes átalakításokat felépíteni, a fenti Bloch-szférákban látható három átalakítás a Gate-sorozatot illeti. \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $.

Míg az előző a legnépszerűbb primitív kapuk, amelyek a verem logikai szintjén lévő műveletek leírására szolgálnak (gondoljunk a logikai szintre, mint a kvantum-algoritmus szintje), gyakran kényelmes, hogy kevesebb alapszintű műveletet lehessen figyelembe venni az algoritmuson. szint, például a függvények leírási szintjéhez közelebbi műveletek. Szerencsére a Q # is rendelkezik a magasabb szintű unitaries megvalósításához szükséges módszerekkel, amelyek lehetővé teszik a magas szintű algoritmusok megvalósítását anélkül, hogy a Clifford és a $T $-Gates-t explicit módon el kellene bontani.

A legegyszerűbb ilyen primitív az egyetlen qubit. A rendszer általában három qubit-rotációt vesz figyelembe: $R _x $, $R _y $ és $R _z $. A rotációs $R _x (\theta) $ művelet működésének megjelenítéséhez tegyük fel, hogy a jobb oldali hüvelykujja a Bloch gömb $x $ tengelyének irányába mutat, és a vektort a kezével $ \ THÉTA/2 $ radián fölé mozgatja. Ez a $2 $-es zavaros tényező abból ered, hogy a (z) a Bloch-szférában a merőleges vektorok száma 180 ^ \circ $, de a a Bloch-gömbön kívül ténylegesen $90 ^ \circ $ fok. A megfelelő egységes mátrixok a következők:

\begin{align *} & R_z (\theta) = e ^ {-I\theta z/2} = \begin{bmatrix} e ^ {-i \ THÉTA/2} & 0\\\\ 0 & e ^ {i \ THÉTA/2} \end{bmatrix}, \\\\ & R_x (\theta) = e ^ {-I\theta x/2} = HR_z (\theta) H = \begin{bmatrix} \cos (\ THÉTA/2) &-i\sin (\ THÉTA/2)\\\\-i\sin (\ THÉTA/2) & \cos (\ THÉTA/2) \end{bmatrix}, \\\\ & R_y (\theta) = e ^ {-I\theta y/2} = SHR_z (\theta) HS ^ \dagger = \begin{bmatrix} \cos (\ THÉTA/2) &-\sin (\ THÉTA/2)\\\\ \sin (\ THÉTA/2) & \cos (\ THÉTA/2) \end{bmatrix}. \end{align*}

Ugyanúgy, mint három rotációt kombinálva, hogy tetszőleges rotációt végezzen három dimenzióban, láthatja a Bloch szférából, hogy bármely egységes mátrix három rotációs folyamatként is írható. Pontosabban, minden egységes mátrix $U $ esetén létezik a $ \alpha, a \beta, a \gamma, a \delta $, amely $U = e ^ {i\alpha} R_x (\beta) R_z (\gamma) R_x (\delta) $. Így a $R _z (\theta) $ és a $H $ is egy univerzális Gate-készletet alkot, bár nem különálló készlet, mert a $ \theta $ bármilyen értéket igénybe vehet. Emiatt, és a kvantum-szimuláció alkalmazásai miatt az ilyen folyamatos kapuk elengedhetetlenek a kvantum-számításokhoz, különösen a Quantum algoritmus tervezési szintjén. A hibatűrő hardverek megvalósításához végső soron különálló kapuk lesznek lefordítva, amelyek szorosan megközelítik ezeket a rotációs folyamatokat.
