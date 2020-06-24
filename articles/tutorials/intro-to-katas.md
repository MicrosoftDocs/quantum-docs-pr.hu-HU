---
title: A Kvantum Katák bemutatása
description: Ismerje meg a Microsoft Quantum Development Kitben (QDK) található katákat (gyakorlófeladatokat).
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 1c4dfa5c47aa38935cd5936cd256e357b6605371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275231"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Ismerkedés a kvantum-számítástechnikával a Kvantum Katák segítségével

[A Quantum katas](https://github.com/Microsoft/QuantumKatas/) olyan nyílt forráskódú, saját tempóban elsajátított oktatóanyagok és programozási gyakorlatok, amelyek a Quantum Computing és a Q # programozási elemek egyidejű tanítására szolgálnak.

## <a name="learning-by-doing"></a>Gyakorlati tanulás

Az ebben a projektben összegyűjtött oktatóanyagok és gyakorlatok a gyakorlati tanulást támogatják: különböző témaköröket érintő programozási feladatokat tartalmaznak, a legegyszerűbbektől az igen bonyolultakig. Minden feladatnál kódokat kell létrehoznia. Az első feladatokban előfordul, hogy csak egy sorra lesz szüksége, a későbbieknél viszont már akár hosszabb kódrészletekre is.

A legfontosabb, hogy a katas olyan tesztelési keretrendszereket tartalmaz, amelyek a feladatokhoz tartozó megoldásokat állítanak be, futtatnak és érvényesítenek. Ezáltal Ön azonnali visszajelzést kaphat a megoldását illetően, és újragondolhatja a megközelítését, ha az helytelen.

A katas for learning-et használhatja a választott környezetben:

* Online Jupyter-notebookok a Binder-környezetben
* Helyi gépen futó Jupyter-notebookok
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Mit tanulhatok meg a Kvantum Katákkal?

Ismerkedjen meg a kvantum-számítástechnika alapjaival és alapjaival, vagy mélyebben tekintse meg a kvantum-algoritmusokat és a protokollokat. Javasoljuk, hogy kezdetben kövesse ezt a képzési tervet, hogy kellő alapossággal megismerje a kvantum-számítástechnika alapfogalmait. Ha valamelyik témát már jól ismeri (például az összetett aritmetikát), azt természetesen kihagyhatja, és az algoritmusokat bármilyen tetszőleges sorrendben megismerheti.

### <a name="introduction-to-quantum-computing-concepts"></a>Bevezetés a kvantum-számítástechnikai fogalmakba

| Kata | Leírás |
|:-----|-------------|
|[Összetett aritmetika](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic):|Ez az oktatóanyag a kvantum-számítástechnika, például a képzeletbeli és az összetett számok használatához szükséges matematikai hátteret ismerteti.|
|[Lineáris algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|A lineáris algebra a Quantum állapotok és a kvantum-számítástechnikai műveletek ábrázolására szolgál. Ez az oktatóanyag az alapokat, például a mátrixokat és a vektorokat ismerteti.|
|[A qubit fogalma](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|A qubits megismerése – a Quantum Computing legfontosabb alapfogalmai. |
|[Egyqubites kvantumkapuk](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|Ez az oktatóanyag egy qubit kvantum-kaput vezet be, amely a kvantum-algoritmusok építőelemeként működik, és különböző módokon alakítja át a Quantum qubit-állapotokat.|
|[Többqubites rendszerek](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|Ez az oktatóanyag bemutatja a qubit rendszereket, azok ábrázolását matematikai jelöléssel és Q # kódban, valamint a felakadás koncepcióját.|
|[Több qubit Quantum Gates](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Ez az oktatóanyag az [qubit Quantum Gates](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) oktatóanyagát követi, és a Quantum Gates több qubit rendszerre való alkalmazására koncentrál.|

### <a name="quantum-computing-fundamentals"></a>Kvantum-számítástechnikai alapfogalmak

| Kata | Leírás |
|:-----|-------------|
|[Kvantumkapuk felismerése](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|A Q #-ban az alapszintű kvantum-kapuk megismerésére tervezett gyakorlatok sorozata. Az alapszintű qubit-és qubit-kapuk, adjoint és vezérelt kapuk, valamint a kapuk használata a qubit állapotának módosításához.|
|[Kvantum-szuperpozíció létrehozása](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Ezekkel a gyakorlatokkal megismerheti a Felfekvés és a programozás fogalmát a Q # használatával. Az alapszintű egyqubitű és több qubit kapuk, a túlterhelések és a folyamatok vezérlésének és rekurziójának gyakorlata a Q #-ban.|
|[Kvantumállapotok megkülönböztetése mérésekkel](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Oldja meg ezeket a gyakorlatokat a kvantum-mérések, valamint a merőleges és nem merőleges állapotok megismerése során. |
|[Közös mérések](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Ismerje meg a közös paritásos méréseket, és azt, hogyan használható a [mérték](xref:microsoft.quantum.intrinsic.measure) művelet a kvantum-állapotok megkülönböztetéséhez.|

### <a name="algorithms"></a>Algoritmusok

| Kata | Leírás |
|:-----|-------------|
|[Kvantumteleportáció](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|Ez a Kata egy olyan protokollt vizsgál, amely lehetővé teszi, hogy a kvantum-állapotot csak a klasszikus kommunikáció és a korábban megosztott kvantum-felakadás használatával kommunikáljon.|
|[Szupersűrű kódolás](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|A többszintű kódolás egy olyan protokoll, amely lehetővé teszi két bites klasszikus információ továbbítását úgy, hogy csak egy qubit küld el, amely korábban megosztott kvantum-felakadás használ.  |
|[A Deutsch–Jozsa-algoritmus](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Ez az algoritmus egy olyan kvantum-algoritmus egyik első példája, amely exponenciálisan gyorsabb, mint bármely klasszikus determinisztikus algoritmus.|
|[A Grover-féle keresőalgoritmus általános tulajdonságai](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|Magas szintű bevezetés a Quantum Computing egyik legismertebb algoritmusával. Feloldja a problémát, amely egy adott kimenetet eredményező fekete dobozba (Oracle) való bevitelt keres. |
|[A Grover-féle keresőalgoritmus implementálása](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Ez a Kata mélyebben felfedi a a a a megkeresését, és leírja az Oracle-ket, az algoritmus lépéseinek elvégzését, végül pedig a teljes összeállítását.|
|[Valós problémák megoldása a a a (z)-algoritmus használatával: SAT-problémák](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|Olyan gyakorlatok sorozata, amelyek a a satisfiability-val [kapcsolatos](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) reális problémák megoldására használják a a a a a a (SAT) algoritmust, amely egy példaként használható.  |
|[Valós problémák megoldása a a a (z)-algoritmus használatával: gráfok színezésével kapcsolatos problémák](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Ez a Kata tovább vizsgálja a a a [megkötések megelégedettségével kapcsolatos problémák](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem)megoldására szolgáló, a a a a a megszorítások terén felmerülő problémát. |

### <a name="protocols-and-libraries"></a>Protokollok és kódtárak

| Kata | Leírás |
|:-----|-------------|
|[BB84 protokoll a kvantumkulcs-elosztáshoz](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Ismerje meg és implementálja a Quantum Key Distribution Protocol, a [BB84](https://en.wikipedia.org/wiki/BB84), a qubits használatával a titkosítási kulcsok cseréjét. |
|[Bit-flip hiba a kód kijavítani](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|Ismerje meg a kvantum-hibajavítást a Quantum Error-Correction (KARANTÉNKÉNYSZERÍTÉSI) kódok közül a legegyszerűbben a három qubit-kód megadásával.|
|[Fázisbecslés](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|A fázis-becslési algoritmusok a kvantum-számítástechnika egyik legalapvetőbb építőelemei. Ismerje meg a fázisok becslését ezekkel a gyakorlatokkal, amelyek a kvantum fázisok becslését és a fázis-becslési rutinok előkészítését és futtatását ismertetik a Q #|
|[Quantum aritmetika: a lüktetés kiépítése – kiegészítések készítése](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|Részletes sorozat, amely a rendszerhullám-számítógépeken is felderíti a [hullámok folytatását](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) . Hozzon létre egy helybeni kvantum-kiegészítést, bontsa ki azt egy másik algoritmussal, és végül hozzon létre egy helyi kvantum-altraktort.   |

### <a name="entanglement-games"></a>Összefonódási játékok

| Kata | Leírás |
|:-----|-------------|
|[CHSH játék](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|Ismerje meg a Quantum felakadás a [chsh](https://en.wikipedia.org/wiki/CHSH_inequality) játék megvalósításával. Ez a nem [helyi](https://en.wikipedia.org/wiki/Quantum_refereed_game) játék azt mutatja be, hogyan használható a Quantum felakadás, hogy növelje a játékosok esélyét arra, hogy a lehető leghatékonyabban klasszikus stratégiával lehessen nyerni.|
|[GHZ játék](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|A GHZ-es játék egy másik nem helyi játék, de három játékost is magában foglal.|
|[A Mermin–Peres-féle bűvös négyzetek játéka](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|Olyan gyakorlatok sorozata, amelyek felderítik a [Quantum pszeudo-telepátiaat](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) a Magic Square-játékok megoldásához.  |

## <a name="resources"></a>További források

A [Kvantum Katák](https://github.com/microsoft/QuantumKatas) teljes sorozatának megtekintése

[A katák online futtatása](https://aka.ms/try-quantum-katas)
