---
title: Mélységi számláló | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A Quantum Computer Trace Simulator áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184899"
---
# <a name="depth-counter"></a>Mélységi számláló

A `Depth Counter` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.
A rendszer a kvantum-programban meghívott összes művelet mélységi számának összegyűjtésére szolgál. Az <xref:microsoft.quantum.intrinsic> összes művelete egyetlen qubit-rotációs, T Gates, egyetlen qubit Clifford Gates, CNEM Gates és a multi-qubit Pauli observables mértékegysége alapján van kifejezve. A felhasználók a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>`gateTimes` mezője segítségével állíthatják be az egyes primitív műveletek mélységét.

Alapértelmezés szerint az összes művelet 0 mélységgel rendelkezik, kivéve az 1. mélységgel rendelkező T kaput. Ez azt jelenti, hogy alapértelmezés szerint a rendszer csak a T mélységű műveleteket számítja ki (ami gyakran kívánatos). Az összegyűjtött statisztikákat a rendszer az Operations Call gráf összes szélénél összesíti. 

Most kiszámítjuk a <xref:microsoft.quantum.intrinsic.ccnot> művelet <xref:microsoft.quantum.intrinsic.t> mélységét. A következő Q # illesztőprogram-kódot fogjuk használni: 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>A C# mélység számláló használata programon belül

Annak vizsgálatához, hogy `CCNOT` rendelkezik-e `T` 5. mélységtel, és `CCNOTDriver` `T` mélysége 6, a következő C# kódot használhatja:

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

A program első része `CCNOTDriver`hajt végre. A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a `CCNOT` és `CCNOTDriver``T` mélységének beszerzéséhez: 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Végezetül, a `Depth Counter` által gyűjtött összes statisztika CSV formátumban való kinyomtatásához a következőket tudjuk használni:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Lásd még: ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
