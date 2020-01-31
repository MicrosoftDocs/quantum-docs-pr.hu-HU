---
title: Mélységi számláló | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820470"
---
# <a name="depth-counter"></a><span data-ttu-id="2a336-103">Mélységi számláló</span><span class="sxs-lookup"><span data-stu-id="2a336-103">Depth Counter</span></span>

<span data-ttu-id="2a336-104">A `Depth Counter` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="2a336-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="2a336-105">A rendszer a kvantum-programban meghívott összes művelet mélységi számának összegyűjtésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="2a336-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="2a336-106">Az <xref:microsoft.quantum.intrinsic> összes művelete egyetlen qubit-rotációs, T Gates, egyetlen qubit Clifford Gates, CNEM Gates és a multi-qubit Pauli observables mértékegysége alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="2a336-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="2a336-107">A felhasználók a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>`gateTimes` mezője segítségével állíthatják be az egyes primitív műveletek mélységét.</span><span class="sxs-lookup"><span data-stu-id="2a336-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="2a336-108">Alapértelmezés szerint az összes művelet 0 mélységgel rendelkezik, kivéve az 1. mélységgel rendelkező T kaput.</span><span class="sxs-lookup"><span data-stu-id="2a336-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="2a336-109">Ez azt jelenti, hogy alapértelmezés szerint a rendszer csak a T mélységű műveleteket számítja ki (ami gyakran kívánatos).</span><span class="sxs-lookup"><span data-stu-id="2a336-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="2a336-110">Az összegyűjtött statisztikákat a rendszer az Operations Call gráf összes szélénél összesíti.</span><span class="sxs-lookup"><span data-stu-id="2a336-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="2a336-111">Most kiszámítjuk a <xref:microsoft.quantum.intrinsic.ccnot> művelet <xref:microsoft.quantum.intrinsic.t> mélységét.</span><span class="sxs-lookup"><span data-stu-id="2a336-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="2a336-112">A következő Q # mintakód-kódot fogjuk használni:</span><span class="sxs-lookup"><span data-stu-id="2a336-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="2a336-113">A C# mélység számláló használata programon belül</span><span class="sxs-lookup"><span data-stu-id="2a336-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="2a336-114">Annak vizsgálatához, hogy `CCNOT` rendelkezik-e `T` 5. mélységtel, és `ApplySampleWithCCNOT` `T` mélysége 6, a következő C# kódot használhatja:</span><span class="sxs-lookup"><span data-stu-id="2a336-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="2a336-115">A program első része `ApplySampleWithCCNOT`hajt végre.</span><span class="sxs-lookup"><span data-stu-id="2a336-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="2a336-116">A második részben a `QCTraceSimulator.GetMetric` metódust használjuk a `CCNOT` és `ApplySampleWithCCNOT``T` mélységének beszerzéséhez:</span><span class="sxs-lookup"><span data-stu-id="2a336-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="2a336-117">Végezetül, a `Depth Counter` által gyűjtött összes statisztika CSV formátumban való kinyomtatásához a következőket tudjuk használni:</span><span class="sxs-lookup"><span data-stu-id="2a336-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="2a336-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2a336-118">See also</span></span> ##

- <span data-ttu-id="2a336-119">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="2a336-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
