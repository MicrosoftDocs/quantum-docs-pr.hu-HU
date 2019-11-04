---
title: Primitív műveleti számláló | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A Quantum Computer Trace Simulator áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184882"
---
# <a name="primitive-operations-counter"></a>Primitív műveleti számláló  

A `Primitive Operations Counter` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi. A kvantum-programban meghívott összes művelet által használt primitív végrehajtások számát számítja fel. Az `Microsoft.Quantum.Primitive` összes művelete egyetlen qubit-rotációs, T Gates, egyetlen qubit Clifford Gates, CNEM Gates és a multi-qubit Pauli observables mértékegysége alapján van kifejezve. Az összegyűjtött statisztikákat a rendszer az Operations Call gráf szélein összesíti. Most megszámoljuk, hány `T` kapura van szükség a `CCNOT` művelet megvalósításához. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>A primitív műveleti számláló használata egy C# programon belül

Annak ellenőrzését, hogy `CCNOT` valóban 7 `T` kaput igényel, és hogy a `CCNOTDriver` 8 `T` kaput hajt végre C# , a következő kódot használhatja:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

A program első része `CCNOTDriver`hajt végre. A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a `CCNOTDriver`által végrehajtott T-kapuk számának lekéréséhez: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Ha a `GetMetric` kétféle paraméterrel van meghívva, az egy adott hívási gráf szegélyéhez társított metrika értékét adja vissza. A példában szereplő művelet `Primitive.CCNOT` `CCNOTDriver`, ezért a hívási gráf tartalmazza a Edge `<Primitive.CCNOT,CCNOTDriver>`. 

A felhasznált `CNOT` Gates számának lekéréséhez a következő sort tudjuk felvenni:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Végezetül a következő lépésekkel állíthatja be a kapu számlálója által összegyűjtött összes statisztikát CSV-formátumban:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Lásd még: ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
