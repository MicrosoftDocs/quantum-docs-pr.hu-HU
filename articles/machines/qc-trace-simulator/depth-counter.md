---
title: Mélységi számláló | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A Quantum Computer Trace Simulator áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184899"
---
# <a name="depth-counter"></a><span data-ttu-id="9954f-103">Mélységi számláló</span><span class="sxs-lookup"><span data-stu-id="9954f-103">Depth Counter</span></span>

<span data-ttu-id="9954f-104">A `Depth Counter` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="9954f-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="9954f-105">A rendszer a kvantum-programban meghívott összes művelet mélységi számának összegyűjtésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="9954f-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="9954f-106">Az <xref:microsoft.quantum.intrinsic> összes művelete egyetlen qubit-rotációs, T Gates, egyetlen qubit Clifford Gates, CNEM Gates és a multi-qubit Pauli observables mértékegysége alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="9954f-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="9954f-107">A felhasználók a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>`gateTimes` mezője segítségével állíthatják be az egyes primitív műveletek mélységét.</span><span class="sxs-lookup"><span data-stu-id="9954f-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="9954f-108">Alapértelmezés szerint az összes művelet 0 mélységgel rendelkezik, kivéve az 1. mélységgel rendelkező T kaput.</span><span class="sxs-lookup"><span data-stu-id="9954f-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="9954f-109">Ez azt jelenti, hogy alapértelmezés szerint a rendszer csak a T mélységű műveleteket számítja ki (ami gyakran kívánatos).</span><span class="sxs-lookup"><span data-stu-id="9954f-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="9954f-110">Az összegyűjtött statisztikákat a rendszer az Operations Call gráf összes szélénél összesíti.</span><span class="sxs-lookup"><span data-stu-id="9954f-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="9954f-111">Most kiszámítjuk a <xref:microsoft.quantum.intrinsic.ccnot> művelet <xref:microsoft.quantum.intrinsic.t> mélységét.</span><span class="sxs-lookup"><span data-stu-id="9954f-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="9954f-112">A következő Q # illesztőprogram-kódot fogjuk használni:</span><span class="sxs-lookup"><span data-stu-id="9954f-112">We will use the following Q# driver code:</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="9954f-113">A C# mélység számláló használata programon belül</span><span class="sxs-lookup"><span data-stu-id="9954f-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="9954f-114">Annak vizsgálatához, hogy `CCNOT` rendelkezik-e `T` 5. mélységtel, és `CCNOTDriver` `T` mélysége 6, a következő C# kódot használhatja:</span><span class="sxs-lookup"><span data-stu-id="9954f-114">To check that `CCNOT` has `T` depth 5 and `CCNOTDriver` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="9954f-115">A program első része `CCNOTDriver`hajt végre.</span><span class="sxs-lookup"><span data-stu-id="9954f-115">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="9954f-116">A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a `CCNOT` és `CCNOTDriver``T` mélységének beszerzéséhez:</span><span class="sxs-lookup"><span data-stu-id="9954f-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `CCNOTDriver`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="9954f-117">Végezetül, a `Depth Counter` által gyűjtött összes statisztika CSV formátumban való kinyomtatásához a következőket tudjuk használni:</span><span class="sxs-lookup"><span data-stu-id="9954f-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="9954f-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9954f-118">See also</span></span> ##

- <span data-ttu-id="9954f-119">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="9954f-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
