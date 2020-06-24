---
title: Primitív műveleti számláló
description: Ismerje meg a Microsoft QDK primitív műveleti számlálóját, amely nyomon követi a kvantum-programban végzett műveletek által használt primitív végrehajtások számát.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274890"
---
# <a name="primitive-operations-counter"></a>Primitív műveleti számláló  

A a `Primitive Operations Counter` Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi. A kvantum-programban meghívott összes művelet által használt primitív végrehajtások számát számítja fel. Az összes művelet az `Microsoft.Quantum.Intrinsic` egyetlen qubit-forgás, a T Gates, az Qubit Clifford Gates, a cnem Gates és a multi-Qubit Pauli observables mértékegységei alapján van kifejezve. Az összegyűjtött statisztikákat a rendszer az Operations Call gráf szélein összesíti. Most megszámoljuk, hogy hány `T` kapura van szükség a `CCNOT` művelet végrehajtásához. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>A primitív műveleti számláló használata C# programon belül

Annak ellenőrzését, hogy `CCNOT` valóban 7 `T` kaput igényel, és `ApplySampleWithCCNOT` 8 `T` kaput hajt végre, a következő C#-kódot használhatja:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

A program első része hajtja végre `ApplySampleWithCCNOT` . A második részben a metódust használjuk a `QCTraceSimulator.GetMetric` által végrehajtott T-kapuk számának lekérésére `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Ha `GetMetric` két típusú paraméterrel van meghívva, az egy adott hívási gráf szegélyéhez társított metrika értékét adja vissza. A példában szereplő művelet a következőn `Primitive.CCNOT` belül lesz meghívva `ApplySampleWithCCNOT` , ezért a hívási gráf tartalmazza a peremhálózat szegélyét `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

A használt kapuk számának lekéréséhez `CNOT` a következő sort tudjuk felvenni:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Végezetül a következő lépésekkel állíthatja be a kapu számlálója által összegyűjtött összes statisztikát CSV-formátumban:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Lásd még ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
