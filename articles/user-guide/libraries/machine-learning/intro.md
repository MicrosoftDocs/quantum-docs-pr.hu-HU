---
title: Kvantum gépi tanulási kódtár
description: Ismerje meg, hogyan használják a gépi tanulást a kvantum-rendszereken
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f7f892fb2b76432942c86163497c22f0c73d51f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833802"
---
# <a name="introduction-to-quantum-machine-learning"></a>Bevezetés a Quantum Machine Learningba

## <a name="framework-and-goals"></a>Keretrendszer és célok

A kvantum-kódolás és az adatok feldolgozása a klasszikus gépi tanulás Quantum-besorolásának hatékony alternatívája. A szolgáltatás lehetővé teszi, hogy az adatokat olyan kvantum-regiszterekben kódolja, amelyek a funkciók számához képest tömörek, és a kvantum-felakadás számítási erőforrásként, valamint a besorolási osztályon alapuló kvantum-mérést alkalmazva használják.
Az áramköri központú kvantum-osztályozó egy viszonylag egyszerű, az adatkódolást egy gyorsan összekapcsoló/szétválasztó kvantum-megoldás, majd a mérések, amelyekkel az adatmintákhoz tartozó címkék kikövetkeztethető.
A cél a tulajdonosi áramkörök klasszikus jellemzésének és tárolásának biztosítása, valamint az áramköri paraméterek hibrid Quantum/klasszikus képzése, még a rendkívül nagy méretű funkciók esetében is.

## <a name="classifier-architecture"></a>Osztályozó architektúra

A besorolás egy felügyelt gépi tanulási feladat, amelyben a cél az, hogy az \{ egyes adatmintákhoz tartozó címkéket $ y_1, y_2, \ldots, y_d \} $. A "betanítási adatkészlet" a \mathcal{D} = \{ (x, y)} $ minták gyűjteménye, ismert előre hozzárendelt címkékkel. Itt $x $ egy adatminta, és a $y $ a "betanítási címke" nevű ismert címkéje.
Némileg hasonló a hagyományos módszerekhez, a Quantum besorolás három lépésből áll:
- adatkódolás
- osztályozó állapot előkészítése
- mérés a mérés valószínűségi természete miatt ezt a három lépést többször kell megismételni. Az osztályozó állapot kódolása és számítástechnikai szintje a *kvantum-áramkörök*segítségével történik. Míg a kódolási áramkör általában adatvezérelt és paraméter nélküli, az osztályozó áramkör a megszerezhető paraméterek megfelelő készletét tartalmazza. 

A javasolt megoldásban az osztályozó áramkör egy qubit és két qubit vezérelt rotációból áll. A megtekinthető paraméterek itt az elforgatási szögek. A rotációs és a vezérelt rotációs kapuk *univerzálisak* a Quantum számítási feladataihoz, ami azt jelenti, hogy az egységes súlyozási mátrixok egy elég hosszú áramkörből állhatnak, amely ilyen kapukat tartalmaz.

A javasolt verzióban a rendszer csak egy áramkört támogat, amelyet egyetlen gyakorisági becslés követ.
Így a megoldás egy olyan, a támogató vektoros számítógép, amely egy alacsony fokú polinom-kernelt biztosít.

![Többrétegű perceptron vs. Circuit központú osztályozó](~/media/DLvsQCC.png)

Egy egyszerű kvantum-osztályozó kialakítás összehasonlítható egy hagyományos támogatási vektoros (SVM) megoldással. Ha a SVM esetében egy adatminta $x $-re vonatkozó következtetést használ, az optimális kernel formát használja a $ \sum \ alpha_j k (x_j, x) $ értékre, ahol a $k $ egy bizonyos kernel-függvény.

Ezzel szemben a Quantum osztályozó a prediktív $p (y │ x, U (\theta)) = 〈 U (\theta) x | M | U (\theta) x 〉 $, amely hasonló a Szellemhez, de technikailag egészen más. Így, ha egyszerű amplitúdó-kódolást használ, $p (y │ x, U (\theta)) $ egy másodfokú űrlap a $x $ amplitúdójában, de az űrlaphoz tartozó együtthatók már nem jelennek meg egymástól függetlenül; Ehelyett az áramköri $U (\theta) $ mátrix elemeiből összesítve vannak, ami általában lényegesen kevesebb, mint a vektor $x $-hoz tartozó dimenziója. A (z) $p (y │ x, U (\theta)) $ az eredeti funkciókban az eredeti szolgáltatásokban a (z) $2 ^ l $x $l $ értékre növelhető.

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

A következő lépésekben látható mintakód mellett az [oktatóanyagban](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification) is megkezdheti a kvantum-besorolás felfedezését 
