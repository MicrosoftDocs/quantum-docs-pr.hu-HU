---
title: Érvénytelenített qubits-használat ellenőrzője – Quantum Development Kit
description: 'Ismerje meg a Microsoft QDK érvénytelenített qubits használatát ellenőrzőt, amely a Quantum Trace Simulator használatával ellenőrzi a Q # kódját a potenciálisan érvénytelen qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: fccf6d5784b587f4ad9b659e23027619acd06ffa
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871093"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="2e9f9-103">Quantum Trace Simulator: érvénytelenített qubits-ellenőrző használata</span><span class="sxs-lookup"><span data-stu-id="2e9f9-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="2e9f9-104">A nem érvényesített qubits használja az ellenőrzőt a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részeként.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="2e9f9-105">Felhasználhatja a kódban az érvénytelen qubits által okozott lehetséges hibák észlelésére.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="2e9f9-106">Érvénytelen qubits</span><span class="sxs-lookup"><span data-stu-id="2e9f9-106">Invalid qubits</span></span>

<span data-ttu-id="2e9f9-107">Vegye figyelembe a következő Q # Code-kódot, hogy bemutassa a invalidated qubits use ellenőrző által észlelt problémákat:</span><span class="sxs-lookup"><span data-stu-id="2e9f9-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="2e9f9-108">Amikor alkalmazza a műveletet a alkalmazásra `H` `q[0]` , az egy már kiadott qubit mutat, amely nem definiált viselkedést okozhat.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="2e9f9-109">Ha a érvénytelenített qubits használata ellenőrző engedélyezve van, akkor a kivételt képez, `InvalidatedQubitsUseCheckerException` Ha a program egy már kiadott qubit alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="2e9f9-110">További információ: <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="2e9f9-111">A érvénytelenített qubits használatának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="2e9f9-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="2e9f9-112">Ha a kvantum-nyomkövetési szimulátort a érvénytelenítve qubits használatával szeretné futtatni, hozzon létre egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, állítsa a `UseInvalidatedQubitsUseChecker` tulajdonságot **true (igaz**) értékre, majd hozzon létre egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="2e9f9-113">A devalidated qubits használata a C# gazdagép programban</span><span class="sxs-lookup"><span data-stu-id="2e9f9-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="2e9f9-114">A következőkben egy példa látható a C#-alapú gazdagépekre, amelyek a kvantum-nyomkövetési szimulátort használják a nem érvényesített qubits-használati ellenőrző használatával:</span><span class="sxs-lookup"><span data-stu-id="2e9f9-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="2e9f9-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="2e9f9-115">See also</span></span>

- <span data-ttu-id="2e9f9-116">A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="2e9f9-117">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="2e9f9-118">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="2e9f9-119">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="2e9f9-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>