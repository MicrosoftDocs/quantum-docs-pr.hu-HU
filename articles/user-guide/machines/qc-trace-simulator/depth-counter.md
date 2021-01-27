---
title: Mélységi számláló – Quantum Development Kit
description: Ismerje meg a Microsoft QDK mélységi számlálóját, amely a Quantum Trace Simulator használatával gyűjti össze a programban meghívott összes művelet mélységét Q# .
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859051"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Quantum Trace Simulator: mélységi számláló

A mélységi számláló a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.
Felhasználhatja a kvantum-programokban meghívott összes művelet mélységének alsó határát képviselő számok gyűjtésére. 

## <a name="depth-values"></a>Mélységi értékek

Alapértelmezés szerint az összes művelet a művelet kivételével **0** mélységgel rendelkezik `T` , amelynek mélysége **1**. Ez azt jelenti, hogy alapértelmezés szerint a `T` rendszer csak a műveletek mélységét számítja ki (ami gyakran kívánatos). A mélységi számláló összesíti és statisztikai adatokat gyűjt a művelet [hívási gráfjának](https://en.wikipedia.org/wiki/Call_graph)összes szélénél.

Az összes <xref:Microsoft.Quantum.Intrinsic> művelet az qubit-Forgások, a <xref:Microsoft.Quantum.Intrinsic.T> műveletek, az qubit Clifford-műveletek, a <xref:Microsoft.Quantum.Intrinsic.CNOT> műveletek és a több qubit Pauli-observables mérései alapján van kifejezve. A felhasználók a mezőn keresztül állíthatják be az egyes primitív műveletek mélységét `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>A mélységi számláló meghívása

Ha a kvantum-nyomkövetési szimulátort a mélységi számlálóval szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, a tulajdonságát igaz értékre kell állítania `UseDepthCounter` , majd létre kell hoznia egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>A mélység számláló használata C# gazda programban

Az ebben a szakaszban szereplő C#-példa a következő mintakód alapján kiszámítja a `T` művelet mélységét `CCNOT` Q# :

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

A következő C#-kód megadásával ellenőrizhető, hogy az `CCNOT` `T` **5** . mélység és `ApplySampleWithCCNOT` `T` a mélység **6**:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

A program első része fut `ApplySampleWithCCNOT` . A második rész a [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metódust használja a és a mélységének lekéréséhez `T` `CCNOT` `ApplySampleWithCCNOT` . 

Végezetül a következő lépésekkel állíthatja be az összes, a mélységi számláló által gyűjtött statisztikát CSV formátumban:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Lásd még

- A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API-hivatkozás.
