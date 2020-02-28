---
title: Mélységi számláló
description: Ismerje meg a Microsoft QDK mélységi számlálóját, amely összefoglalja a kvantum-programban meghívott összes művelet mélységét.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906100"
---
# <a name="depth-counter"></a>Mélységi számláló

A `Depth Counter` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.
A rendszer a kvantum-programban meghívott összes művelet mélységi számának összegyűjtésére szolgál. Az <xref:microsoft.quantum.intrinsic> összes művelete egyetlen qubit-rotációs, T Gates, egyetlen qubit Clifford Gates, CNEM Gates és a multi-qubit Pauli observables mértékegysége alapján van kifejezve. A felhasználók a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>`gateTimes` mezője segítségével állíthatják be az egyes primitív műveletek mélységét.

Alapértelmezés szerint az összes művelet 0 mélységgel rendelkezik, kivéve az 1. mélységgel rendelkező T kaput. Ez azt jelenti, hogy alapértelmezés szerint a rendszer csak a T mélységű műveleteket számítja ki (ami gyakran kívánatos). Az összegyűjtött statisztikákat a rendszer az Operations Call gráf összes szélénél összesíti. 

Most kiszámítjuk a <xref:microsoft.quantum.intrinsic.ccnot> művelet <xref:microsoft.quantum.intrinsic.t> mélységét. A következő Q # mintakód-kódot fogjuk használni:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>A C# mélység számláló használata programon belül

Annak vizsgálatához, hogy `CCNOT` rendelkezik-e `T` 5. mélységtel, és `ApplySampleWithCCNOT` `T` mélysége 6, a következő C# kódot használhatja:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

A program első része `ApplySampleWithCCNOT`hajt végre. A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a `CCNOT` és `ApplySampleWithCCNOT``T` mélységének beszerzéséhez: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Végezetül, a `Depth Counter` által gyűjtött összes statisztika CSV formátumban való kinyomtatásához a következőket tudjuk használni:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Lásd még ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
