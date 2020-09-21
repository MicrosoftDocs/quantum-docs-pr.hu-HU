---
title: DISTINCT Inputs-Dámajáték – Quantum Development Kit
description: Ismerkedjen meg a Microsoft QDK DISTINCT input-ellenőrzési szolgáltatásával, amely a Quantum Trace Simulator használatával vizsgálja meg, hogy milyen Q# ütközések lehetségesek a megosztott qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: bcb0bc92a546279496d27ad9b8c5f943ac133e2a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833464"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="84d9a-103">Quantum Trace Simulator: különálló bemenet-ellenőrzési</span><span class="sxs-lookup"><span data-stu-id="84d9a-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="84d9a-104">A DISTINCT input-ellenőrök a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezik.</span><span class="sxs-lookup"><span data-stu-id="84d9a-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="84d9a-105">A használatával észlelheti a programkódban előforduló esetleges hibákat a megosztott qubits ütközései miatt.</span><span class="sxs-lookup"><span data-stu-id="84d9a-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="84d9a-106">Ütközés megosztott qubits</span><span class="sxs-lookup"><span data-stu-id="84d9a-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="84d9a-107">Vegye figyelembe a következő Q# kódrészletet a különböző input-ellenőrök által észlelt problémák szemléltetéséhez:</span><span class="sxs-lookup"><span data-stu-id="84d9a-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="84d9a-108">Ha megtekinti ezt a programot, feltételezheti, hogy a meghívása `op1` és a `op2` nem számít, mivel a `q1` és a különböző `q2` qubits és műveletek különböző qubits-feladatokkal működnek.</span><span class="sxs-lookup"><span data-stu-id="84d9a-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="84d9a-109">Most gondolja át a következő példát:</span><span class="sxs-lookup"><span data-stu-id="84d9a-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="84d9a-110">Vegye figyelembe, hogy `op1` `op2` mindkettő részleges alkalmazás használatával és a qubit megosztásával is beszerezhető.</span><span class="sxs-lookup"><span data-stu-id="84d9a-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="84d9a-111">Ha ezt a `ApplyBoth` példát hívja meg, a művelet eredménye a és a belső sorrendtől függ, `op1` és nem az, `op2` `ApplyBoth` ami várható.</span><span class="sxs-lookup"><span data-stu-id="84d9a-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="84d9a-112">Ha engedélyezi a különböző bemenet-ellenőröket, az észleli az ilyen helyzeteket, és eldönti a `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="84d9a-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="84d9a-113">További információ: az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q# API-függvénytárban.</span><span class="sxs-lookup"><span data-stu-id="84d9a-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="84d9a-114">A különböző bemenet-ellenőrök meghívása</span><span class="sxs-lookup"><span data-stu-id="84d9a-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="84d9a-115">Ha a kvantum-nyomkövetési szimulátort a DISTINCT Inputs-előfizetési lehetőséggel szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, állítsa a `UseDistinctInputsChecker` tulajdonságot **igaz**értékre, majd hozzon létre egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="84d9a-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="84d9a-116">A különböző input-ellenőrök használata C#-gazdagép programban</span><span class="sxs-lookup"><span data-stu-id="84d9a-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="84d9a-117">A következőkben egy példa látható a C#-alapú gazdagépre, amely a kvantum-nyomkövetési szimulátort használja a különböző bemenet-ellenőrzési lehetőségekkel:</span><span class="sxs-lookup"><span data-stu-id="84d9a-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="84d9a-118">Lásd még</span><span class="sxs-lookup"><span data-stu-id="84d9a-118">See also</span></span>

- <span data-ttu-id="84d9a-119">A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="84d9a-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="84d9a-120">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="84d9a-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="84d9a-121">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="84d9a-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="84d9a-122">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="84d9a-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
