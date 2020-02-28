---
title: Primitív műveleti számláló
description: Ismerje meg a Microsoft QDK primitív műveleti számlálóját, amely nyomon követi a kvantum-programban végzett műveletek által használt primitív végrehajtások számát.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905947"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="16501-103">Primitív műveleti számláló</span><span class="sxs-lookup"><span data-stu-id="16501-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="16501-104">A `Primitive Operations Counter` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="16501-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="16501-105">A kvantum-programban meghívott összes művelet által használt primitív végrehajtások számát számítja fel.</span><span class="sxs-lookup"><span data-stu-id="16501-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="16501-106">Az `Microsoft.Quantum.Intrinsic` összes művelete egyetlen qubit-rotációs, T Gates, egyetlen qubit Clifford Gates, CNEM Gates és a multi-qubit Pauli observables mértékegysége alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="16501-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="16501-107">Az összegyűjtött statisztikákat a rendszer az Operations Call gráf szélein összesíti.</span><span class="sxs-lookup"><span data-stu-id="16501-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="16501-108">Most megszámoljuk, hány `T` kapura van szükség a `CCNOT` művelet megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="16501-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="16501-109">A primitív műveleti számláló használata egy C# programon belül</span><span class="sxs-lookup"><span data-stu-id="16501-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="16501-110">Annak ellenőrzését, hogy `CCNOT` valóban 7 `T` kaput igényel, és hogy a `ApplySampleWithCCNOT` 8 `T` kaput hajt végre C# , a következő kódot használhatja:</span><span class="sxs-lookup"><span data-stu-id="16501-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="16501-111">A program első része `ApplySampleWithCCNOT`hajt végre.</span><span class="sxs-lookup"><span data-stu-id="16501-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="16501-112">A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a `ApplySampleWithCCNOT`által végrehajtott T-kapuk számának lekéréséhez:</span><span class="sxs-lookup"><span data-stu-id="16501-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="16501-113">Ha a `GetMetric` kétféle paraméterrel van meghívva, az egy adott hívási gráf szegélyéhez társított metrika értékét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="16501-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="16501-114">A példában szereplő művelet `Primitive.CCNOT` `ApplySampleWithCCNOT`, ezért a hívási gráf tartalmazza a Edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span><span class="sxs-lookup"><span data-stu-id="16501-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="16501-115">A felhasznált `CNOT` Gates számának lekéréséhez a következő sort tudjuk felvenni:</span><span class="sxs-lookup"><span data-stu-id="16501-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="16501-116">Végezetül a következő lépésekkel állíthatja be a kapu számlálója által összegyűjtött összes statisztikát CSV-formátumban:</span><span class="sxs-lookup"><span data-stu-id="16501-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="16501-117">Lásd még</span><span class="sxs-lookup"><span data-stu-id="16501-117">See also</span></span> ##

- <span data-ttu-id="16501-118">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="16501-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
