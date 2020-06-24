---
title: Mélységi számláló
description: Ismerje meg a Microsoft QDK mélységi számlálóját, amely összefoglalja a kvantum-programban meghívott összes művelet mélységét.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274937"
---
# <a name="depth-counter"></a>Mélységi számláló

A a `Depth Counter` Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.
A rendszer a kvantum-programban meghívott összes művelet mélységi számának összegyűjtésére szolgál. Az összes művelet az <xref:microsoft.quantum.intrinsic> egyetlen qubit-forgás, a T Gates, az Qubit Clifford Gates, a cnem Gates és a multi-Qubit Pauli observables mértékegységei alapján van kifejezve. A felhasználók a mezőn keresztül állíthatják be az egyes primitív műveletek mélységét `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Alapértelmezés szerint az összes művelet 0 mélységgel rendelkezik, kivéve az 1. mélységgel rendelkező T kaput. Ez azt jelenti, hogy alapértelmezés szerint a rendszer csak a T mélységű műveleteket számítja ki (ami gyakran kívánatos). Az összegyűjtött statisztikákat a rendszer az Operations Call gráf összes szélénél összesíti. 

Most kiszámítjuk a <xref:microsoft.quantum.intrinsic.t> művelet mélységét <xref:microsoft.quantum.intrinsic.ccnot> . A következő Q # mintakód-kódot fogjuk használni:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>A mélységi számláló használata C# programon belül

Ha szeretné megnézni, hogy a `CCNOT` `T` mélység 5, `ApplySampleWithCCNOT` `T` mélysége 6, a következő C#-kódot használhatja:

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

A program első része hajtja végre `ApplySampleWithCCNOT` . A második részben a metódust használjuk a `QCTraceSimulator.GetMetric` és a mélységének beszerzéséhez `T` `CCNOT` `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Végül, a CSV-formátumban gyűjtött összes statisztika kimenetének kinyomtatásához `Depth Counter` a következőket tudjuk használni:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Lásd még ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
