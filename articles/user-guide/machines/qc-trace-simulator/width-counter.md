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
# <a name="width-counter"></a><span data-ttu-id="6ac80-103">Szélesség számlálója</span><span class="sxs-lookup"><span data-stu-id="6ac80-103">Width Counter</span></span>

<span data-ttu-id="6ac80-104">A `Width Counter` megszámolja az egyes műveletek által lefoglalt és kölcsönzött qubits számát.</span><span class="sxs-lookup"><span data-stu-id="6ac80-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="6ac80-105">A névtérből származó összes művelet az `Microsoft.Quantum.Intrinsic` egyszeres qubit Forgások, a T Gates, az egyetlen Qubit Clifford Gates, a cnem Gates és a multi-Qubit Pauli observables mérései alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="6ac80-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="6ac80-106">Néhány primitív művelet további qubits foglalhat le.</span><span class="sxs-lookup"><span data-stu-id="6ac80-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="6ac80-107">Például: szorzás vezérelt `X` kapuk vagy vezérelt `T` kapuk.</span><span class="sxs-lookup"><span data-stu-id="6ac80-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="6ac80-108">Tegyük fel, hogy kiszámítjuk a szorzás vezérelt kapu megvalósításával kiosztott extra qubits számát `X` :</span><span class="sxs-lookup"><span data-stu-id="6ac80-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="6ac80-109">A szélesség számlálójának használata C#-programon belül</span><span class="sxs-lookup"><span data-stu-id="6ac80-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="6ac80-110">`X`Az összesen 5 qubits elvégezhető szorzási művelet 2 kiegészítő qubits foglal le, és a bemeneti szélessége 5 lesz.</span><span class="sxs-lookup"><span data-stu-id="6ac80-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="6ac80-111">Ebben az esetben a következő C# programot használhatja:</span><span class="sxs-lookup"><span data-stu-id="6ac80-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="6ac80-112">A program első része hajtja végre `ApplyMultiControlledX` .</span><span class="sxs-lookup"><span data-stu-id="6ac80-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="6ac80-113">A második részben a metódus használatával lekéri `QCTraceSimulator.GetMetric` a lefoglalt qubits számát, valamint a bemenetként ellenőrzött qubits számát `X` .</span><span class="sxs-lookup"><span data-stu-id="6ac80-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="6ac80-114">Végezetül a következő műveleteket végezheti el a szélességi számláló által összegyűjtött összes statisztika CSV-formátumban való kinyomtatásához:</span><span class="sxs-lookup"><span data-stu-id="6ac80-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="6ac80-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6ac80-115">See also</span></span> ##

- <span data-ttu-id="6ac80-116">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="6ac80-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
