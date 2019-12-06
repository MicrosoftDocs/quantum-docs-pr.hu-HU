---
title: Érvénytelenített qubits-használat ellenőrzője | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 283cc7d7d88f731f40fa396c38ae5ea8dd90537f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863180"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="eb12c-103">Érvénytelenített qubits-ellenőrző használata</span><span class="sxs-lookup"><span data-stu-id="eb12c-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="eb12c-104">A `Invalidated Qubits Use Checker` a Quantum Computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) azon része, amely a kódban rejlő esetleges hibák észlelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="eb12c-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="eb12c-105">Vegye figyelembe a következő Q #-kódot a `Invalidated Qubits Use Checker`által észlelt problémák szemléltetése érdekében.</span><span class="sxs-lookup"><span data-stu-id="eb12c-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="eb12c-106">Ha `H` van alkalmazva, `q[0]` egy már kiadott qubit mutat.</span><span class="sxs-lookup"><span data-stu-id="eb12c-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="eb12c-107">Ez nem definiált viselkedést okozhat.</span><span class="sxs-lookup"><span data-stu-id="eb12c-107">This can cause undefined behavior.</span></span> <span data-ttu-id="eb12c-108">Ha a `Invalidated Qubits Use Checker` engedélyezve van, akkor a kivétel `InvalidatedQubitsUseCheckerException` kerül, ha egy művelet egy már kiadott qubit van alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="eb12c-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="eb12c-109">További részletekért tekintse meg a [INVALIDATEDQUBITSUSECHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="eb12c-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="eb12c-110">Az érvénytelenített qubits használata a-ellenőrző használatával a C# programban</span><span class="sxs-lookup"><span data-stu-id="eb12c-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="eb12c-111">A következőkben egy példa látható C# arra az illesztőprogram-kódra, amely a quantum Computer `Trace
Simulator` használatát engedélyezi a `Invalidated Qubits Use Checker` engedélyezve:</span><span class="sxs-lookup"><span data-stu-id="eb12c-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="eb12c-112">Az osztály `QCTraceSimulatorConfiguration` a kvantum-számítógép nyomkövetési szimulátorjának konfigurációját tárolja, és a `QCTraceSimulator` konstruktor argumentumként is elérhető.</span><span class="sxs-lookup"><span data-stu-id="eb12c-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="eb12c-113">Ha a `useInvalidatedQubitsUseChecker` értéke TRUE (igaz), akkor a `Invalidated Qubits Use Checker` engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="eb12c-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="eb12c-114">További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="eb12c-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb12c-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="eb12c-115">See also</span></span> ##

- <span data-ttu-id="eb12c-116">A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="eb12c-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
