---
title: Érvénytelenített qubits-használat ellenőrzője – Quantum Development Kit
description: Ismerkedjen meg a Microsoft QDK által érvénytelenített qubits-ellenőrzővel, amely a Quantum Trace Simulator használatával ellenőrzi, hogy a Q# kód esetleg érvénytelen qubits-e.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868287"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="6ed69-103">Quantum Trace Simulator: érvénytelenített qubits-ellenőrző használata</span><span class="sxs-lookup"><span data-stu-id="6ed69-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="6ed69-104">A nem érvényesített qubits használja az ellenőrzőt a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részeként.</span><span class="sxs-lookup"><span data-stu-id="6ed69-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6ed69-105">Felhasználhatja a kódban az érvénytelen qubits által okozott lehetséges hibák észlelésére.</span><span class="sxs-lookup"><span data-stu-id="6ed69-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="6ed69-106">Érvénytelen qubits</span><span class="sxs-lookup"><span data-stu-id="6ed69-106">Invalid qubits</span></span>

<span data-ttu-id="6ed69-107">Vegye figyelembe a következő Q# kódrészletet a nem érvényesített qubits-ellenőrző által észlelt problémák szemléltetéséhez:</span><span class="sxs-lookup"><span data-stu-id="6ed69-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="6ed69-108">Amikor alkalmazza a műveletet a alkalmazásra `H` `q[0]` , az egy már kiadott qubit mutat, amely nem definiált viselkedést okozhat.</span><span class="sxs-lookup"><span data-stu-id="6ed69-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="6ed69-109">Ha a érvénytelenített qubits használata ellenőrző engedélyezve van, akkor a kivételt képez, `InvalidatedQubitsUseCheckerException` Ha a program egy már kiadott qubit alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="6ed69-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="6ed69-110">További információ: <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="6ed69-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="6ed69-111">A érvénytelenített qubits használatának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6ed69-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="6ed69-112">Ha a kvantum-nyomkövetési szimulátort a érvénytelenítve qubits használatával szeretné futtatni, hozzon létre egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, állítsa a `UseInvalidatedQubitsUseChecker` tulajdonságot **true (igaz**) értékre, majd hozzon létre egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="6ed69-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="6ed69-113">A devalidated qubits használata a C# gazdagép programban</span><span class="sxs-lookup"><span data-stu-id="6ed69-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="6ed69-114">A következőkben egy példa látható a C#-alapú gazdagépekre, amelyek a kvantum-nyomkövetési szimulátort használják a nem érvényesített qubits-használati ellenőrző használatával:</span><span class="sxs-lookup"><span data-stu-id="6ed69-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6ed69-115">További információ</span><span class="sxs-lookup"><span data-stu-id="6ed69-115">See also</span></span>

- <span data-ttu-id="6ed69-116">A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="6ed69-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="6ed69-117">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6ed69-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="6ed69-118">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6ed69-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="6ed69-119">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6ed69-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>