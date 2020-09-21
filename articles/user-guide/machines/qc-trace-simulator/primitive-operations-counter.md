---
title: Primitív művelet számláló – Quantum Development Kit
description: Ismerje meg a Microsoft QDK primitív műveleti számlálóját, amely a Quantum Trace Simulator használatával követi nyomon a programban végzett műveletek által használt primitív folyamatokat Q# .
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8ee9ce25e680112e2f3c68d82ae9267c1b0fb355
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835978"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="6050e-103">Quantum Trace Simulator: primitív műveleti számláló</span><span class="sxs-lookup"><span data-stu-id="6050e-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="6050e-104">A primitív műveleti számláló a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="6050e-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6050e-105">Megszámolja a kvantum-programban meghívott összes művelet által használt primitív folyamatok számát.</span><span class="sxs-lookup"><span data-stu-id="6050e-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="6050e-106">Az összes <xref:microsoft.quantum.intrinsic> művelet az qubit-Forgások, a T-műveletek, az Qubit Clifford-műveletek, a cnem-műveletek és a több Qubit Pauli-observables mérései alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="6050e-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="6050e-107">A primitív műveletek számlálója összesíti és statisztikai adatokat gyűjt a művelet [hívási gráfjának](https://en.wikipedia.org/wiki/Call_graph)összes széléről.</span><span class="sxs-lookup"><span data-stu-id="6050e-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="6050e-108">A primitív műveleti számláló meghívása</span><span class="sxs-lookup"><span data-stu-id="6050e-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="6050e-109">Ha a kvantum-nyomkövetési szimulátort a primitív műveleti számlálóval szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, a `UsePrimitiveOperationsCounter` tulajdonságot **igaz**értékre kell állítania, majd létre kell hoznia egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt a `QCTraceSimulatorConfiguration` paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="6050e-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="6050e-110">A primitív műveleti számláló használata C#-gazdagép programban</span><span class="sxs-lookup"><span data-stu-id="6050e-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="6050e-111">Az ebben a szakaszban szereplő C#-példa azt mutatja, hogy hány <xref:microsoft.quantum.intrinsic.t> műveletre van szükség a művelet megvalósításához a <xref:microsoft.quantum.intrinsic.ccnot> következő Q# mintakód alapján:</span><span class="sxs-lookup"><span data-stu-id="6050e-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="6050e-112">A következő C#-kód használatával ellenőrizze, hogy a működéséhez `CCNOT` hét `T` művelet szükséges-e `ApplySampleWithCCNOT` , és nyolc műveletet futtat-e `T` :</span><span class="sxs-lookup"><span data-stu-id="6050e-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

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

<span data-ttu-id="6050e-113">A program első része fut `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="6050e-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="6050e-114">A második rész a [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metódus használatával kéri le a `T` által futtatott műveletek számát `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="6050e-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="6050e-115">Ha `GetMetric` két típusú paramétert hív meg, akkor az egy adott hívási gráf szegélyéhez társított metrika értékét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="6050e-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="6050e-116">Az előző példában a program meghívja a `Primitive.CCNOT` műveletet belül, `ApplySampleWithCCNOT` ezért a hívási gráf tartalmazza a peremhálózat szegélyét `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="6050e-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="6050e-117">A használt műveletek számának beolvasásához `CNOT` adja hozzá a következő sort:</span><span class="sxs-lookup"><span data-stu-id="6050e-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="6050e-118">Végezetül a következő paranccsal állíthatja be a primitív műveleti számláló által összegyűjtött összes statisztikát CSV formátumban:</span><span class="sxs-lookup"><span data-stu-id="6050e-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="6050e-119">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6050e-119">See also</span></span>

- <span data-ttu-id="6050e-120">A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="6050e-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="6050e-121">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6050e-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="6050e-122">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6050e-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="6050e-123">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6050e-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>