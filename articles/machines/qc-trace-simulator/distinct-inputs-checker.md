---
title: Különböző bemenet-ellenőrök | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820963"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="e83fc-103">Különálló bemenet-ellenőrzési</span><span class="sxs-lookup"><span data-stu-id="e83fc-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="e83fc-104">A `Distinct Inputs Checker` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="e83fc-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="e83fc-105">Ez a kód a lehetséges hibák észlelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="e83fc-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="e83fc-106">A csomag által észlelt problémák szemléltetéséhez vegye figyelembe az alábbi Q #-kódot:</span><span class="sxs-lookup"><span data-stu-id="e83fc-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="e83fc-107">Amikor a felhasználó megkeresi ezt a programot, feltételezi, hogy a `op1` és `op2` meghívásának sorrendje nem számít, mert a `q1` és a `q2` különböző qubits és a különböző qubits-feladatokkal működő műveletek.</span><span class="sxs-lookup"><span data-stu-id="e83fc-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="e83fc-108">Most Vegyünk példaként egy példát, ahol ezt a műveletet használják:</span><span class="sxs-lookup"><span data-stu-id="e83fc-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="e83fc-109">Most `op1` és `op2` egyaránt a részleges alkalmazás használatával és a qubit megosztásával szerezhetők be.</span><span class="sxs-lookup"><span data-stu-id="e83fc-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="e83fc-110">Ha a felhasználó a fenti példában meghívja a `ApplyBoth`t, akkor a művelet eredménye `op1` és `op2` sorrendtől függ `ApplyBoth`.</span><span class="sxs-lookup"><span data-stu-id="e83fc-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="e83fc-111">Ez biztosan nem az, amit a felhasználó elvár.</span><span class="sxs-lookup"><span data-stu-id="e83fc-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="e83fc-112">A `Distinct Inputs Checker` akkor fogja felderíteni az ilyen helyzeteket, ha az engedélyezve van, és `DistinctInputsCheckerException`fog dobni.</span><span class="sxs-lookup"><span data-stu-id="e83fc-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="e83fc-113">További részletekért tekintse meg a [DISTINCTINPUTSCHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="e83fc-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="e83fc-114">A különböző input-ellenőrök használata a C# programban</span><span class="sxs-lookup"><span data-stu-id="e83fc-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="e83fc-115">A következőkben egy példa C# látható a Quantum Computer Trace Simulator használatára a `Distinct Inputs Checker` engedélyezve:</span><span class="sxs-lookup"><span data-stu-id="e83fc-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="e83fc-116">Az osztály `QCTraceSimulatorConfiguration` a kvantum-számítógép nyomkövetési szimulátorjának konfigurációját tárolja, és a `QCTraceSimulator` konstruktor argumentumként is elérhető.</span><span class="sxs-lookup"><span data-stu-id="e83fc-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="e83fc-117">Ha a `useDistinctInputsChecker` értéke TRUE (igaz), akkor a `Distinct Inputs Checker` engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="e83fc-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="e83fc-118">További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="e83fc-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="e83fc-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e83fc-119">See also</span></span>

- <span data-ttu-id="e83fc-120">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="e83fc-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
