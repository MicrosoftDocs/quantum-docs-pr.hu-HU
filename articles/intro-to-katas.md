---
title: A Kvantum Katák bemutatása
description: Ismerje meg a Microsoft Quantum Development Kitben (QDK) található katákat (gyakorlófeladatokat).
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 7fb8dba2a10f9a983ebee52e394260bbdc0d2f9c
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444140"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Ismerkedés a kvantum-számítástechnikával a Kvantum Katák segítségével

A [Kvantum Katák](https://github.com/Microsoft/QuantumKatas/) saját ütemben elvégezhető oktatóanyagok és programozási gyakorlatok nyílt forráskódú gyűjteményei, amelyek célja a kvantum-számítástechnika elemeinek és a Q#-programozás egyidejű megismertetése.

## <a name="learning-by-doing"></a>Gyakorlati tanulás

Az ebben a projektben összegyűjtött oktatóanyagok és katák a gyakorlati tanulást hangsúlyozzák: programozási feladatokat nyújtanak különböző témakörökben, a legegyszerűbbektől az igen bonyolultakig. Minden feladatnál kódokat kell létrehoznia. Az első feladatokban előfordul, hogy csak egy sorra lesz szüksége, a későbbieknél viszont már akár hosszabb kódrészletekre is.

A legfontosabb dolog, hogy a katák tartalmaznak tesztelési keretrendszereket is, amelyek összeállítják, lefuttatják és ellenőrzik a feladatok megoldásait. Ezáltal Ön azonnali visszajelzést kaphat a megoldását illetően, és újragondolhatja a megközelítését, ha az helytelen.

A Katákkal bármelyik Ön által választott környezetben tanulhat:

* Online Jupyter-notebookok a Binder-környezetben
* Helyi gépen futó Jupyter-notebookok
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Mit tanulhatok meg a Kvantum Katákkal?

A Kvantum Katák a következő fő témakörökkel foglalkoznak. Javasoljuk, hogy kezdetben kövesse ezt a képzési tervet, hogy kellő alapossággal megismerje a kvantum-számítástechnika alapfogalmait. Ha valamelyik témát már jól ismeri (például az összetett aritmetikát), azt természetesen kihagyhatja, és az algoritmusokat bármilyen tetszőleges sorrendben megismerheti.

### <a name="introduction-to-quantum-computing-concepts"></a>Bevezetés a kvantum-számítástechnikai fogalmakba

* [Összetett aritmetika](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic):
* [Lineáris algebra](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [A qubit fogalma](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [Egyqubites kvantumkapuk](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a>Kvantum-számítástechnikai alapfogalmak

* [Kvantumkapuk felismerése](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [Kvantum-szuperpozíció létrehozása](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [Kvantumállapotok megkülönböztetése mérésekkel](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [Közös mérések](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>Algoritmusok

* [Kvantumteleportáció](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [Szupersűrű kódolás](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [A Deutsch–Jozsa-algoritmus](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [A Grover-féle keresőalgoritmus implementálása](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [A Grover-féle keresőalgoritmus általános tulajdonságai](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* Valós problémák megoldása a Grover-algoritmussal: [SAT-problémák](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover) és [gráfszínezési problémák](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)

### <a name="protocols-and-libraries"></a>Protokollok és kódtárak

* [BB84 protokoll a kvantumkulcs-elosztáshoz](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* Kvantum-hibajavítás: [Bit flip hibaüzenet-javító kód](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [Fázisbecslés](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* Kvantum-aritmetika: [átvitel-továbbterjesztő összeadók létrehozása](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>Összefonódási játékok

* [CHSH játék](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [GHZ játék](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [A Mermin–Peres-féle bűvös négyzetek játéka](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>További források

* A [Kvantum Katák](https://github.com/microsoft/QuantumKatas) teljes sorozatának megtekintése
* [A katák online futtatása](https://aka.ms/try-quantum-katas)
