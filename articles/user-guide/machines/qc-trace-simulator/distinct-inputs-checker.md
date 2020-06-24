---
title: Különálló bemenet-ellenőrzési
description: 'Ismerje meg a Microsoft QDK DISTINCT Inputs-ellenőrzőt, amely a Q # kódját ellenőrzi a megosztott qubits lehetséges ütközések esetén.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274930"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="a64ba-103">Különálló bemenet-ellenőrzési</span><span class="sxs-lookup"><span data-stu-id="a64ba-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="a64ba-104">A a `Distinct Inputs Checker` Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="a64ba-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="a64ba-105">Ez a kód a lehetséges hibák észlelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="a64ba-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="a64ba-106">A csomag által észlelt problémák szemléltetéséhez vegye figyelembe az alábbi Q #-kódot:</span><span class="sxs-lookup"><span data-stu-id="a64ba-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="a64ba-107">Amikor a felhasználó megkeresi a programot, feltételezi, hogy a `op1` és a `op2` hívási sorrend nem számít, mert `q1` és különböző `q2` qubits és műveletek különböző qubits-feladatokkal működnek.</span><span class="sxs-lookup"><span data-stu-id="a64ba-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="a64ba-108">Most Vegyünk példaként egy példát, ahol ezt a műveletet használják:</span><span class="sxs-lookup"><span data-stu-id="a64ba-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="a64ba-109">Most `op1` és `op2` mindkettőt részleges alkalmazás használatával szerezték be, és megosztanak egy qubit.</span><span class="sxs-lookup"><span data-stu-id="a64ba-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="a64ba-110">Ha a felhasználó a `ApplyBoth` fenti példában meghívja a művelet eredményét, a és a belső sorrendtől `op1` függ `op2` `ApplyBoth` .</span><span class="sxs-lookup"><span data-stu-id="a64ba-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="a64ba-111">Ez biztosan nem az, amit a felhasználó elvár.</span><span class="sxs-lookup"><span data-stu-id="a64ba-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="a64ba-112">A az `Distinct Inputs Checker` ilyen helyzeteket fogja felderíteni, ha engedélyezve van, és a rendszer kidobja `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="a64ba-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="a64ba-113">További részletekért tekintse meg a [DISTINCTINPUTSCHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="a64ba-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="a64ba-114">A különböző input-ellenőrök használata a C# programban</span><span class="sxs-lookup"><span data-stu-id="a64ba-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="a64ba-115">Az alábbi példa egy C#-illesztőprogram-kódra mutat be, amely a Quantum Computer Trace Simulator használatát teszi `Distinct Inputs Checker` lehetővé:</span><span class="sxs-lookup"><span data-stu-id="a64ba-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="a64ba-116">Az osztály `QCTraceSimulatorConfiguration` tárolja a kvantum-számítógép nyomkövetési szimulátor konfigurációját, és a konstruktor argumentumként is elérhető `QCTraceSimulator` .</span><span class="sxs-lookup"><span data-stu-id="a64ba-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="a64ba-117">Ha `useDistinctInputsChecker` a értéke TRUE (igaz `Distinct Inputs Checker` ), akkor az engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="a64ba-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="a64ba-118">További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="a64ba-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="a64ba-119">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a64ba-119">See also</span></span>

- <span data-ttu-id="a64ba-120">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="a64ba-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
