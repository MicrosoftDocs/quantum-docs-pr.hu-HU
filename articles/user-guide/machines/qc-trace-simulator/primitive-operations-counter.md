---
title: Primitív művelet számláló – Quantum Development Kit
description: Ismerje meg a Microsoft QDK primitív műveleti számlálóját, amely a Quantum Trace Simulator használatával követi nyomon a programok műveletei által használt primitív végrehajtásokat Q# .
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868236"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Quantum Trace Simulator: primitív műveleti számláló

A primitív műveleti számláló a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi. A kvantum-programban meghívott összes művelet által használt primitív végrehajtások számát számítja fel. 

Az összes <xref:microsoft.quantum.intrinsic> művelet az qubit-Forgások, a T-műveletek, az Qubit Clifford-műveletek, a cnem-műveletek és a több Qubit Pauli-observables mérései alapján van kifejezve. A primitív műveletek számlálója összesíti és statisztikai adatokat gyűjt a művelet [hívási gráfjának](https://en.wikipedia.org/wiki/Call_graph)összes széléről.

## <a name="invoking-the-primitive-operation-counter"></a>A primitív műveleti számláló meghívása

Ha a kvantum-nyomkövetési szimulátort a primitív műveleti számlálóval szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, a `UsePrimitiveOperationsCounter` tulajdonságot **igaz**értékre kell állítania, majd létre kell hoznia egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt a `QCTraceSimulatorConfiguration` paraméterrel.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>A primitív műveleti számláló használata C#-gazdagép programban

Az ebben a szakaszban szereplő C#-példa azt mutatja, hogy hány <xref:microsoft.quantum.intrinsic.t> műveletre van szükség a művelet megvalósításához a <xref:microsoft.quantum.intrinsic.ccnot> következő Q# mintakód alapján:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

A következő C#-kód használatával ellenőrizze, hogy a működéséhez `CCNOT` hét `T` művelet szükséges-e `ApplySampleWithCCNOT` , és nyolc műveletet futtat-e `T` :

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

A program első része fut `ApplySampleWithCCNOT` . A második rész a [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metódus használatával kéri le a `T` által futtatott műveletek számát `ApplySampleWithCCNOT` : 

Ha `GetMetric` két típusú paramétert hív meg, akkor az egy adott hívási gráf szegélyéhez társított metrika értékét adja vissza. Az előző példában a program meghívja a `Primitive.CCNOT` műveletet belül, `ApplySampleWithCCNOT` ezért a hívási gráf tartalmazza a peremhálózat szegélyét `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

A használt műveletek számának beolvasásához `CNOT` adja hozzá a következő sort:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Végezetül a következő paranccsal állíthatja be a primitív műveleti számláló által összegyűjtött összes statisztikát CSV formátumban:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>További információ

- A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API-hivatkozás.