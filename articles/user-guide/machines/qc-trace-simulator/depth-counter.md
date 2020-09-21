---
title: Mélységi számláló – Quantum Development Kit
description: Ismerje meg a Microsoft QDK mélységi számlálóját, amely a Quantum Trace Simulator használatával gyűjti össze a programban meghívott összes művelet mélységét Q# .
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8280783adfcc2867c3a598a6f57d827125aadcfd
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833443"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="e5181-103">Quantum Trace Simulator: mélységi számláló</span><span class="sxs-lookup"><span data-stu-id="e5181-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="e5181-104">A mélységi számláló a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="e5181-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="e5181-105">Felhasználhatja a kvantum-programokban meghívott összes művelet mélységének alsó határát képviselő számok gyűjtésére.</span><span class="sxs-lookup"><span data-stu-id="e5181-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="e5181-106">Mélységi értékek</span><span class="sxs-lookup"><span data-stu-id="e5181-106">Depth values</span></span>

<span data-ttu-id="e5181-107">Alapértelmezés szerint az összes művelet a művelet kivételével **0** mélységgel rendelkezik `T` , amelynek mélysége **1**.</span><span class="sxs-lookup"><span data-stu-id="e5181-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="e5181-108">Ez azt jelenti, hogy alapértelmezés szerint a `T` rendszer csak a műveletek mélységét számítja ki (ami gyakran kívánatos).</span><span class="sxs-lookup"><span data-stu-id="e5181-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="e5181-109">A mélységi számláló összesíti és statisztikai adatokat gyűjt a művelet [hívási gráfjának](https://en.wikipedia.org/wiki/Call_graph)összes szélénél.</span><span class="sxs-lookup"><span data-stu-id="e5181-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="e5181-110">Az összes <xref:microsoft.quantum.intrinsic> művelet az qubit-Forgások, a <xref:microsoft.quantum.intrinsic.t> műveletek, az qubit Clifford-műveletek, a <xref:microsoft.quantum.intrinsic.cnot> műveletek és a több qubit Pauli-observables mérései alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="e5181-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="e5181-111">A felhasználók a mezőn keresztül állíthatják be az egyes primitív műveletek mélységét `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="e5181-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="e5181-112">A mélységi számláló meghívása</span><span class="sxs-lookup"><span data-stu-id="e5181-112">Invoking the depth counter</span></span>

<span data-ttu-id="e5181-113">Ha a kvantum-nyomkövetési szimulátort a mélységi számlálóval szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, a tulajdonságát igaz értékre kell állítania `UseDepthCounter` , majd létre kell hoznia egy **true**új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="e5181-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="e5181-114">A mélység számláló használata C# gazda programban</span><span class="sxs-lookup"><span data-stu-id="e5181-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="e5181-115">Az ebben a szakaszban szereplő C#-példa a következő mintakód alapján kiszámítja a `T` művelet mélységét `CCNOT` Q# :</span><span class="sxs-lookup"><span data-stu-id="e5181-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="e5181-116">A következő C#-kód megadásával ellenőrizhető, hogy az `CCNOT` `T` **5** . mélység és `ApplySampleWithCCNOT` `T` a mélység **6**:</span><span class="sxs-lookup"><span data-stu-id="e5181-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="e5181-117">A program első része fut `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="e5181-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="e5181-118">A második rész a [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metódust használja a és a mélységének lekéréséhez `T` `CCNOT` `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="e5181-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="e5181-119">Végezetül a következő lépésekkel állíthatja be az összes, a mélységi számláló által gyűjtött statisztikát CSV formátumban:</span><span class="sxs-lookup"><span data-stu-id="e5181-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="e5181-120">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e5181-120">See also</span></span>

- <span data-ttu-id="e5181-121">A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="e5181-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="e5181-122">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="e5181-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="e5181-123">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="e5181-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="e5181-124">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="e5181-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
