---
title: Kvantum gépi tanulási kódtár
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
ms.openlocfilehash: 4a4ecbb85cc5bbfb1ccb1f111309578bcc5bce3d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872658"
---
# <a name="introduction-to-quantum-machine-learning"></a>Bevezetés a Quantum Machine Learningba

## <a name="framework-and-goals"></a>Keretrendszer és célok

A kvantum-kódolás és az adatok feldolgozása a klasszikus gépi tanulási kvantum-besorolások hatékony alternatívája, amely különösen a funkciók számához képest tömör módon kódolja a kvantum-regiszterekben lévő adatokat, és rendszeresen alkalmazza a kvantum-felakadás számítási erőforrásként, és a besorolási osztályon alapuló kvantum-mérést alkalmaz.
Az áramköri központú kvantum-osztályozó egy viszonylag egyszerű, az adatkódolást egy gyorsan összekapcsoló/szétválasztó kvantum-megoldás, majd a mérések, amelyekkel az adatmintákhoz tartozó címkék kikövetkeztethető.
A cél a tulajdonosi áramkörök klasszikus jellemzésének és tárolásának biztosítása, valamint az áramköri paraméterek hibrid Quantum/klasszikus képzése, még a rendkívül nagy méretű funkciók esetében is.

## <a name="classifier-architecture"></a>Osztályozó architektúra

A besorolás egy felügyelt gépi tanulási feladat, amelyben a cél az, hogy az \{ egyes adatmintákhoz tartozó címkéket $ y_1, y_2, \ldots, y_d \} $. A "betanítási adatkészlet" a \mathcal{D} = \{ (x, y)} $ minták gyűjteménye, ismert előre hozzárendelt címkékkel. Itt $x $ egy adatminta, és a $y $ a "betanítási címke" nevű ismert címkéje.
Némileg hasonló a hagyományos módszerekhez, a Quantum besorolás három lépésből áll:
- adatkódolás
- osztályozó állapot előkészítése
- mérés a mérés valószínűségi természete miatt ezt a három lépést többször kell megismételni. A mérés a nem lineáris aktiválás kvantum-egyenértékként is megtekinthető.
Az osztályozó állapot kódolása és számítástechnikai szintje a *kvantum-áramkörök*segítségével történik. Míg a kódolási áramkör általában adatvezérelt és paraméter nélküli, az osztályozó áramkör a megszerezhető paraméterek megfelelő készletét tartalmazza. 

A javasolt megoldásban az osztályozó áramkör egy qubit és két qubit vezérelt rotációból áll. A megtekinthető paraméterek itt az elforgatási szögek. A rotációs és a vezérelt rotációs kapuk *univerzálisak* a Quantum számítási feladataihoz, ami azt jelenti, hogy az egységes súlyozási mátrixok egy elég hosszú áramkörből állhatnak, amely ilyen kapukat tartalmaz.

![Többrétegű perceptron vs. Circuit központú osztályozó](~/media/DLvsQCC.png)

Ezt a modellt összehasonlíthatja egy többrétegű perceptron, így jobban megismerheti az alapszintű szerkezetet. A perceptron a prediktív $p (y | x, \theta) $ értéket a parametrized a nem lineáris aktiválási funkciókat (neuronokat) összekapcsoló lineáris függvények meghatározása. Ezeket a paramétereket a modell létrehozásához lehet képezni. A kimeneti rétegben elérheti egy osztályhoz tartozó minta valószínűségét, ha nem lineáris aktiválási funkciókat (például SOFTMAX szoftvert fejlesztettek) használ. Az áramköri központhoz tartozó osztályozó esetében a prediktív parametrized az egy-qubit és a modell áramkörének qubit vezérelt forgási szöge határozza meg. Hasonló módon ezeket a paramétereket a színátmenet-elszívó algoritmus hibrid kvantum/klasszikus verziója is taníthatja. A nem lineáris aktiválási függvények helyett a kimenet kiszámításához az osztály valószínűségét úgy kapjuk meg, hogy az ellenőrzött elforgatások után ismétlődő méréseket olvas be egy adott qubit. A klasszikus adatmennyiség Quantum állapotban történő kódolásához az állapot-előkészítéshez egy megellenőrizhető Kódolási áramkört használunk.

Az architektúra felderíti a viszonylag sekélyebb áramköröket, ezért *gyorsan összekeverve* kell lennie ahhoz, hogy rögzítse az adatszolgáltatások közötti összes korrelációt az összes tartományban. Az alábbi ábrán egy példa látható a leghasznosabb, gyorsan összekeverhető áramkör-összetevőre. Annak ellenére, hogy az ezzel a geometriai kapcsolattal rendelkező áramkör csak $3 n + 1 $ kapuból áll, az IT által kiszámított egységes súlyozási mátrix a $2 ^ n $ funkciók között jelentős kölcsönös beszélgetést biztosít.

![Gyorsan összekeverhető a kvantum-áramkör 5 qubits (két ciklikus réteggel).](~/media/5-qubit-qccc.png)

A fenti példában szereplő áramkör 6 egyqubitű Gates $ (G_1, \ldots, G_5; G_ {16} ) $ és 10 2-qubits Gates $ (G_6, \ldots, G_ {15} ) $. Feltételezve, hogy a kapuk mindegyike egy beolvasható paraméterrel van definiálva, 16 megtekinthető paraméterrel rendelkezik, az 5 qubit Hilbert terület dimenziója pedig 32. Az ilyen áramköri geometria könnyen általánosítható bármely $n $-qubit regiszterre, ha $n $ páratlan, a $3 n + 1 $ paraméterekkel rendelkező áramköröket pedig a $2 ^ n $-Dimensional szolgáltatás területére.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Osztályozó képzés mint felügyelt tanulási feladat

Az osztályozó modellek betanítása magában foglalja az operatív paraméterek optimális értékeit, így azok maximalizálják a megfelelő képzési címkéknek a képzési mintákon való kiutalásának átlagos valószínűségét.
Itt csak két besorolási szintet érintünk, például $d = $2, és csak két osztályt $y _1, y_2 $ címkével.

> [!NOTE]
> A módszerek tetszőleges számú osztályra való általánosításának elvi módszere az qubits és a qudits, azaz a kvantum-egységek $d $-alapú állapottal való lecserélése, valamint a kétirányú mérés $d $-Way méréssel.

### <a name="likelihood-as-the-training-goal"></a>A képzési cél valószínűsége

Egy megszerezhető Quantum Circuit $U (\theta) $, ahol a $ \theta $ a paraméterek vektora, és az $M $ értékkel jelöli meg a végső mérést, a helyes címke átlagának valószínűsége $ $ \begin{align} \mathcal{L} (\theta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, y_1) \In\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $, ahol a $P (M = y | z) $ az a valószínűsége, hogy $y $ értéket kell mérni a Quantum State $z $ értékben.
Ebben az esetben elég megérteni, hogy a $ \mathcal{L} (\theta) $ értéke Smooth a $ \theta $-ben, és a származéka minden $ \ theta_j $-ben kiszámítható a számítási feladattal megegyező, a valószínűségi függvényt használó kvantum protokollal. Ez lehetővé teszi, hogy a $ \mathcal{L} (\theta) $ értéket a színátmenet leereszkedéssel optimalizálja.

### <a name="classifier-bias-and-training-score"></a>Osztályozó torzítás és betanítási pontszám

A $ \theta $ paraméterben megadott bizonyos közbenső (vagy végső) értékek esetében egyetlen valós értéket kell megadnia, $b $ minősítési *torzításként* a következtetés elvégzéséhez. A Label következtetési szabály a következőképpen működik: 
- A (z) $x $ típushoz hozzárendelt címke $y _2 $, ha $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1) (máskülönben hozzá van rendelve címke $y _1 $)

Egyértelműen $b $ értékének a $ (-0.5, + 0,5) $ értékűnek kell lennie, hogy legyen értelmezhető.

A $ (x, y) \in \mathcal{D} $ betanítási eset nem megfelelő $b *besorolásnak* minősül, mert a ($x $-ként a RULE1 $y-nek). A téves besorolások összesített száma az osztályozó *betanítási pontszáma* , amely a $b $ torzítást adja meg. Az *optimális* osztályozó torzítás $b $ a betanítási pontszám csökkentése. Könnyen látható, hogy az előre számított valószínűségi becslések szerint a $ \{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \} $, az optimális osztályozó torzítást a bináris keresés a $ (-0.5, + 0,5) $ intervallumban találja a legtöbb $ \ log_2 (| \mathcal{D} |) értékkel. $ lépések.

### <a name="reference"></a>Referencia

Ennek az információnak elégnek kell lennie ahhoz, hogy megkezdje a kód lejátszását. Ha azonban többet szeretne megtudni erről a modellről, olvassa el az eredeti javaslatot: [ *"Circuit-centrikus Quantum osztályozók", Maria Schuld, Alex Bocharov, Garai Viktória Svore és Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
