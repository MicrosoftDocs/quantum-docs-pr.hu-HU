---
title: Szélesség számlálója
description: Ismerje meg a Microsoft QDK szélességi számlálóját, amely megszámolja a kvantum-programban a műveletek által lefoglalt és kölcsönvett qubits számát.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274897"
---
# <a name="width-counter"></a>Szélesség számlálója

A `Width Counter` megszámolja az egyes műveletek által lefoglalt és kölcsönzött qubits számát.
A névtérből származó összes művelet az `Microsoft.Quantum.Intrinsic` egyszeres qubit Forgások, a T Gates, az egyetlen Qubit Clifford Gates, a cnem Gates és a multi-Qubit Pauli observables mérései alapján van kifejezve. Néhány primitív művelet további qubits foglalhat le. Például: szorzás vezérelt `X` kapuk vagy vezérelt `T` kapuk. Tegyük fel, hogy kiszámítjuk a szorzás vezérelt kapu megvalósításával kiosztott extra qubits számát `X` :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>A szélesség számlálójának használata C#-programon belül

`X`Az összesen 5 qubits elvégezhető szorzási művelet 2 kiegészítő qubits foglal le, és a bemeneti szélessége 5 lesz. Ebben az esetben a következő C# programot használhatja:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

A program első része hajtja végre `ApplyMultiControlledX` . A második részben a metódus használatával lekéri `QCTraceSimulator.GetMetric` a lefoglalt qubits számát, valamint a bemenetként ellenőrzött qubits számát `X` . 

Végezetül a következő műveleteket végezheti el a szélességi számláló által összegyűjtött összes statisztika CSV-formátumban való kinyomtatásához:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Lásd még ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
