---
title: Kvantumszimulátorok és Q#-programok
description: A Q#-programok számára célgépként elérhető kvantumszimulátorokat ismerteti.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: conceptual
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 408c636d5383cf594e7ebec6ab2edd66e20ffb82
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858770"
---
# <a name="quantum-simulators"></a>Kvantumszimulátorok

A kvantumszimulátorok a klasszikus számítógépeken futó szoftverek, amelyek *célgépként* érhetők el Q#-programok számára, és segítségükkel a kvantumprogramok olyan környezetben futtathatók és tesztelhetők, amely előre jelzi, hogy a qubitek hogyan fognak reagálni a különböző műveletekre. Ez a cikk ismerteti, hogy milyen kvantumszimulátorokat tartalmaz a Quantum Development Kit (QDK), és milyen módokon adható át egy Q#-program a kvantumszimulátorok számára, például a parancssorból vagy klasszikus nyelven írt illesztőkóddal.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>A Quantum Development Kit (QDK) kvantumszimulátorai

A kvantumszimulátor felel a kvantumprimitívek implementálásáért egy algoritmus esetében. Ezekbe beletartoznak olyan primitív műveletek, mint a `H`, a `CNOT` és a `Measure`, továbbá a qubitek kezelése és nyomkövetése. A QDK-ban megtalálható kvantumszimulátorok különböző osztályai ugyanazon kvantumalgoritmus különböző szimulálási módjait jelölik. 


Minden egyes kvantumszimulátor-típus ezen primitívek más-más implementációját biztosíthatja. Például a [teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator) futtatja a kvantumalgoritmust a [kvantumállapot-vektor](xref:microsoft.quantum.glossary#quantum-state) teljes körű szimulálásával, míg a [kvantumszámítógép nyomkövetési szimulátora](xref:microsoft.quantum.machines.qc-trace-simulator.intro) egyáltalán nem veszi figyelembe a tényleges kvantumállapotot. hanem az algoritmus kapu-, qubit- és egyéb erőforrás-felhasználását követi nyomon.

### <a name="quantum-machine-classes"></a>Kvantumszámítógép-osztályok

A jövőben a QDK további kvantumgéposztályokat fog meghatározni további szimulációtípusok és a kvantumhardveren történő futtatás támogatása érdekében. Ha az algoritmus számára lehetővé tesszük, hogy változatlan maradjon, miközben a mögöttes gépimplementáció módosul, az megkönnyíti az algoritmusok tesztelését és hibakeresését egy szimulációban, majd futtatásukat valódi hardveren, miközben biztos lehet benne, hogy az algoritmusok nem változtak.

A QDK számos kvantumszámítógép-osztályt tartalmaz, ezek mindegyike meg van határozva a `Microsoft.Quantum.Simulation.Simulators` névtérben.

|Szimulátor |Osztály|Leírás|
|-----|------|---|
|[Teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Kvantumalgoritmusokat futtat, hibakeresést végez rajtuk, és kb. 30 qubitre van korlátozva. |
|[Egyszerű erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Végrehajtja a kvantumalgoritmusok futtatásához szükséges erőforrások átfogó elemzését, és több ezer qubitet támogat.|
|[Nyomkövetés-alapú erőforrásbecslő](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Az algoritmus teljes hívási gráfjának speciális erőforrás-használati elemzését futtatja, és több ezer qubitet támogat.|
|[Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Olyan kvantumalgoritmusokat szimulál, amelyek `X`, `CNOT` és több elem által vezérelt `X` kvantumműveletekre vannak korlátozva, és több millió qubitet támogat. |

## <a name="invoking-the-quantum-simulator"></a>A kvantumszimulátor meghívása

[A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) szakasz háromféle megoldást mutat be a Q#-kód kvantumszimulátor számára való átadására: 

* A parancssor használata
* Python-gazdaprogram használata
* C#-gazdaprogram használata

A kvantumgépek normál .NET-osztályok példányai, így a .NET-osztályokhoz hasonlóan a konstruktoruk meghívásával jönnek létre. Ennek végrehajtása attól függ, hogyan futtatja a Q#-programot.

## <a name="next-steps"></a>Következő lépések

* A célgépek Q#-programokhoz különböző környezetekben való meghívásának részleteiért tekintse meg [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) szakaszt.
