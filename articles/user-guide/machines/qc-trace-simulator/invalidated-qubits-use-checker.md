---
title: Érvénytelenített qubithasználat ellenőrzője
description: 'Ismerje meg a Microsoft QDK érvénytelenített qubits használatát ellenőrző eszközt, amely ellenőrzi a Q # kódját a potenciálisan érvénytelen qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274900"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="732ce-103">Érvénytelenített qubits-ellenőrző használata</span><span class="sxs-lookup"><span data-stu-id="732ce-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="732ce-104">A a `Invalidated Qubits Use Checker` Quantum Computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) része, amely a kódban rejlő esetleges hibák észlelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="732ce-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="732ce-105">Vegye figyelembe a következő Q #-kódrészletet, hogy bemutassa a által észlelt problémákat `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="732ce-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="732ce-106">Ha a `H` alkalmazás rá van alkalmazva, `q[0]` egy már kiadott qubit mutat.</span><span class="sxs-lookup"><span data-stu-id="732ce-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="732ce-107">Ez nem definiált viselkedést okozhat.</span><span class="sxs-lookup"><span data-stu-id="732ce-107">This can cause undefined behavior.</span></span> <span data-ttu-id="732ce-108">Ha a `Invalidated Qubits Use Checker` beállítás engedélyezve van, a kivétel akkor kerül megadásra, `InvalidatedQubitsUseCheckerException` Ha egy művelet már megjelent qubit van alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="732ce-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="732ce-109">További részletekért tekintse meg a [INVALIDATEDQUBITSUSECHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="732ce-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="732ce-110">Az érvénytelenített qubits használata a C# programban</span><span class="sxs-lookup"><span data-stu-id="732ce-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="732ce-111">A következőkben egy példa a C# illesztőprogram-kódra, amely lehetővé teszi a kvantum-számítógép használatát az `Trace
Simulator` `Invalidated Qubits Use Checker` engedélyezve:</span><span class="sxs-lookup"><span data-stu-id="732ce-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="732ce-112">Az osztály `QCTraceSimulatorConfiguration` tárolja a kvantum-számítógép nyomkövetési szimulátor konfigurációját, és a konstruktor argumentumként is elérhető `QCTraceSimulator` .</span><span class="sxs-lookup"><span data-stu-id="732ce-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="732ce-113">Ha `useInvalidatedQubitsUseChecker` a értéke TRUE (igaz `Invalidated Qubits Use Checker` ), akkor az engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="732ce-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="732ce-114">További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="732ce-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="732ce-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="732ce-115">See also</span></span> ##

- <span data-ttu-id="732ce-116">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="732ce-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
