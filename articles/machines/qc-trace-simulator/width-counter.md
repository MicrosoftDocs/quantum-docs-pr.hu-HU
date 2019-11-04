---
title: Szélesség számlálója | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A Quantum Computer Trace Simulator áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: e202c527e7e26751361e0c46355ffcefa9c95091
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184916"
---
# <a name="width-counter"></a>Szélesség számlálója

A `Width Counter` megszámolja az egyes műveletek által lefoglalt és kölcsönzött qubits számát.
A `Microsoft.Quantum.Primitive` névtérből származó összes művelet az egyszeres qubit Forgások, a T Gates, az egyetlen qubit Clifford Gates, a CNEM Gates és a multi-qubit Pauli observables mérései alapján van kifejezve. Néhány primitív művelet további qubits foglalhat le. Például: szorzás vezérelt `X` Gates vagy vezérelt `T` Gates. Tegyük fel, hogy kiszámítjuk a szorzás vezérelt `X` kapu megvalósításával kiosztott extra qubits számát:

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

# <a name="using-width-counter-within-a-c-program"></a>C# Programon belüli szélességi számláló használata

Az 5 qubits teljes körűen szabályozott `X` kiosztása 2 kiegészítő qubits, a bemeneti szélessége pedig 5 lesz. A következő C# program használatával ellenőrizhető, hogy ez a helyzet-e:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

A program első része `MultiControlledXDriver`hajt végre. A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a lefoglalt qubits számának lekérésére, valamint a bevitt `X` által vezérelt qubits számának beolvasására. 

Végezetül a következő műveleteket végezheti el a szélességi számláló által összegyűjtött összes statisztika CSV-formátumban való kinyomtatásához:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Lásd még: ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
