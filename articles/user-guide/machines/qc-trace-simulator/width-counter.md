---
title: Szélesség számláló – Quantum Development Kit
description: Ismerkedjen meg a Microsoft QDK szélességi számlálójának használatával, amely a Quantum Trace Simulator használatával számítja ki, hogy hány qubits van kiosztva, és hogyan kölcsönzött a program műveletei által Q# .
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835944"
---
# <a name="quantum-trace-simulator-width-counter"></a>Quantum Trace Simulator: szélesség számláló

A szélesség számláló a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi. A használatával megszámolhatja a program egyes műveletei által lefoglalt qubits számát Q# . Néhány primitív művelet több qubits is kioszthat, például szorzásra vezérelt `X` vagy vezérelt `T` műveleteket.

## <a name="invoking-the-width-counter"></a>A szélességi számláló meghívása

Ha a kvantum-nyomkövetési szimulátort a szélességi számlálóval szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, a `UseWidthCounter` tulajdonságot **igaz**értékre kell állítania, majd létre kell hoznia egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt a `QCTraceSimulatorConfiguration` paraméterrel. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>A szélesség számláló használata C#-gazdagép programban

Az ebben a szakaszban ismertetett C#-példa a következő mintakód alapján kiszámítja a szorzás által vezérelt művelet megvalósításával lefoglalt extra qubits számát <xref:microsoft.quantum.intrinsic.x> Q# :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

A szorzás <xref:microsoft.quantum.intrinsic.x> által vezérelt művelet összesen öt qubits működik, és két [kiegészítő qubits](xref:microsoft.quantum.glossary#ancilla)foglal le, és a bemeneti szélessége **5**. A következő C# program használatával ellenőrizheti a számlálókat:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

A program első része futtatja a `ApplyMultiControlledX` műveletet. A második rész a [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metódus használatával kéri le a lefoglalt qubits számát, valamint azt a qubits-számot, amelyet a `Controlled X` művelet bemenetként kapott. 

Végezetül a következő paranccsal állíthatja be az összes olyan statisztikát, amelyet a szélességi számláló a CSV formátumban gyűjtött:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Lásd még

- A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API-hivatkozás.
