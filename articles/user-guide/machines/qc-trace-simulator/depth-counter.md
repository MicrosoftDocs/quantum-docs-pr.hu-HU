---
title: Mélységi számláló
description: Ismerje meg a Microsoft QDK mélységi számlálóját, amely összefoglalja a kvantum-programban meghívott összes művelet mélységét.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415262"
---
# <a name="depth-counter"></a><span data-ttu-id="c2763-103">Mélységi számláló</span><span class="sxs-lookup"><span data-stu-id="c2763-103">Depth Counter</span></span>

<span data-ttu-id="c2763-104">A a `Depth Counter` Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="c2763-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="c2763-105">A rendszer a kvantum-programban meghívott összes művelet mélységének alsó határát képviselő darabszámok gyűjtésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="c2763-105">It is used to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="c2763-106">Az összes művelet az <xref:microsoft.quantum.intrinsic> egyetlen qubit-forgás, a T Gates, az Qubit Clifford Gates, a cnem Gates és a multi-Qubit Pauli observables mértékegységei alapján van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="c2763-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="c2763-107">A felhasználók a mezőn keresztül állíthatják be az egyes primitív műveletek mélységét `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="c2763-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="c2763-108">Alapértelmezés szerint az összes művelet 0 mélységgel rendelkezik, kivéve az 1. mélységgel rendelkező T kaput.</span><span class="sxs-lookup"><span data-stu-id="c2763-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="c2763-109">Ez azt jelenti, hogy alapértelmezés szerint a rendszer csak a T mélységű műveleteket számítja ki (ami gyakran kívánatos).</span><span class="sxs-lookup"><span data-stu-id="c2763-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="c2763-110">Az összegyűjtött statisztikákat a rendszer az Operations Call gráf összes szélénél összesíti.</span><span class="sxs-lookup"><span data-stu-id="c2763-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="c2763-111">Most kiszámítjuk a <xref:microsoft.quantum.intrinsic.t> művelet mélységét <xref:microsoft.quantum.intrinsic.ccnot> .</span><span class="sxs-lookup"><span data-stu-id="c2763-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="c2763-112">A következő Q # mintakód-kódot fogjuk használni:</span><span class="sxs-lookup"><span data-stu-id="c2763-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="c2763-113">A mélységi számláló használata C# programon belül</span><span class="sxs-lookup"><span data-stu-id="c2763-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="c2763-114">Ha szeretné megnézni, hogy a `CCNOT` `T` mélység 5, `ApplySampleWithCCNOT` `T` mélysége 6, a következő C#-kódot használhatja:</span><span class="sxs-lookup"><span data-stu-id="c2763-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

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

<span data-ttu-id="c2763-115">A program első része hajtja végre `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="c2763-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="c2763-116">A második részben a metódust használjuk a `QCTraceSimulator.GetMetric` és a mélységének beszerzéséhez `T` `CCNOT` `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="c2763-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="c2763-117">Végül, a CSV-formátumban gyűjtött összes statisztika kimenetének kinyomtatásához `Depth Counter` a következőket tudjuk használni:</span><span class="sxs-lookup"><span data-stu-id="c2763-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="c2763-118">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c2763-118">See also</span></span> ##

- <span data-ttu-id="c2763-119">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="c2763-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
