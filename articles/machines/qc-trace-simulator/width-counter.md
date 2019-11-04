---
title: Szélesség számlálója | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442405"
---
# <a name="width-counter"></a><span data-ttu-id="4d029-103">Szélesség számlálója</span><span class="sxs-lookup"><span data-stu-id="4d029-103">Width Counter</span></span>

<span data-ttu-id="4d029-104">A `Width Counter` megszámolja az egyes műveletek által lefoglalt és kölcsönzött qubits számát.</span><span class="sxs-lookup"><span data-stu-id="4d029-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="4d029-105">A `Microsoft.Quantum.Primitive` névtérből származó összes művelet az egyszeres qubit Forgások, a T Gates, az egyetlen qubit Clifford Gates, a CNEM Gates és a multi-qubit Pauli observables mérései alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="4d029-105">All operations from the `Microsoft.Quantum.Primitive` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="4d029-106">Néhány primitív művelet további qubits foglalhat le.</span><span class="sxs-lookup"><span data-stu-id="4d029-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="4d029-107">Például: szorzás vezérelt `X` Gates vagy vezérelt `T` Gates.</span><span class="sxs-lookup"><span data-stu-id="4d029-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="4d029-108">Tegyük fel, hogy kiszámítjuk a szorzás vezérelt `X` kapu megvalósításával kiosztott extra qubits számát:</span><span class="sxs-lookup"><span data-stu-id="4d029-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="4d029-109">C# Programon belüli szélességi számláló használata</span><span class="sxs-lookup"><span data-stu-id="4d029-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="4d029-110">Az 5 qubits teljes körűen szabályozott `X` kiosztása 2 kiegészítő qubits, a bemeneti szélessége pedig 5 lesz.</span><span class="sxs-lookup"><span data-stu-id="4d029-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="4d029-111">A következő C# program használatával ellenőrizhető, hogy ez a helyzet-e:</span><span class="sxs-lookup"><span data-stu-id="4d029-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="4d029-112">A program első része `MultiControlledXDriver`hajt végre.</span><span class="sxs-lookup"><span data-stu-id="4d029-112">The first part of the program executes `MultiControlledXDriver`.</span></span> <span data-ttu-id="4d029-113">A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a lefoglalt qubits számának lekérésére, valamint a bevitt `X` által vezérelt qubits számának beolvasására.</span><span class="sxs-lookup"><span data-stu-id="4d029-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="4d029-114">Végezetül a következő műveleteket végezheti el a szélességi számláló által összegyűjtött összes statisztika CSV-formátumban való kinyomtatásához:</span><span class="sxs-lookup"><span data-stu-id="4d029-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="4d029-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4d029-115">See also</span></span> ##

- <span data-ttu-id="4d029-116">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="4d029-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
