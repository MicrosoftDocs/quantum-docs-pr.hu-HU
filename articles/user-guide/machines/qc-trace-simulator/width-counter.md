---
title: Szélesség számláló – Quantum Development Kit
description: Ismerkedjen meg a Microsoft QDK szélességi számlálójának használatával, amely a Quantum Trace Simulator használatával számítja ki, hogy hány qubits van kiosztva, és hogyan kölcsönzött a program műveletei által Q# .
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868202"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="1be4a-103">Quantum Trace Simulator: szélesség számláló</span><span class="sxs-lookup"><span data-stu-id="1be4a-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="1be4a-104">A szélesség számláló a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi.</span><span class="sxs-lookup"><span data-stu-id="1be4a-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="1be4a-105">A használatával megszámolhatja a program egyes műveletei által lefoglalt qubits számát Q# .</span><span class="sxs-lookup"><span data-stu-id="1be4a-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="1be4a-106">Néhány primitív művelet több qubits is kioszthat, például szorzásra vezérelt `X` vagy vezérelt `T` műveleteket.</span><span class="sxs-lookup"><span data-stu-id="1be4a-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="1be4a-107">A szélességi számláló meghívása</span><span class="sxs-lookup"><span data-stu-id="1be4a-107">Invoking the width counter</span></span>

<span data-ttu-id="1be4a-108">Ha a kvantum-nyomkövetési szimulátort a szélességi számlálóval szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, a `UseWidthCounter` tulajdonságot **igaz**értékre kell állítania, majd létre kell hoznia egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt a `QCTraceSimulatorConfiguration` paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="1be4a-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="1be4a-109">A szélesség számláló használata C#-gazdagép programban</span><span class="sxs-lookup"><span data-stu-id="1be4a-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="1be4a-110">Az ebben a szakaszban ismertetett C#-példa a következő mintakód alapján kiszámítja a szorzás által vezérelt művelet megvalósításával lefoglalt extra qubits számát <xref:microsoft.quantum.intrinsic.x> Q# :</span><span class="sxs-lookup"><span data-stu-id="1be4a-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="1be4a-111">A szorzás <xref:microsoft.quantum.intrinsic.x> által vezérelt művelet összesen öt qubits működik, és két [kiegészítő qubits](xref:microsoft.quantum.glossary#ancilla)foglal le, és a bemeneti szélessége **5**.</span><span class="sxs-lookup"><span data-stu-id="1be4a-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="1be4a-112">A következő C# program használatával ellenőrizheti a számlálókat:</span><span class="sxs-lookup"><span data-stu-id="1be4a-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="1be4a-113">A program első része futtatja a `ApplyMultiControlledX` műveletet.</span><span class="sxs-lookup"><span data-stu-id="1be4a-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="1be4a-114">A második rész a [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metódus használatával kéri le a lefoglalt qubits számát, valamint azt a qubits-számot, amelyet a `Controlled X` művelet bemenetként kapott.</span><span class="sxs-lookup"><span data-stu-id="1be4a-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="1be4a-115">Végezetül a következő paranccsal állíthatja be az összes olyan statisztikát, amelyet a szélességi számláló a CSV formátumban gyűjtött:</span><span class="sxs-lookup"><span data-stu-id="1be4a-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="1be4a-116">További információ</span><span class="sxs-lookup"><span data-stu-id="1be4a-116">See also</span></span>

- <span data-ttu-id="1be4a-117">A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.</span><span class="sxs-lookup"><span data-stu-id="1be4a-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="1be4a-118">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="1be4a-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="1be4a-119">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="1be4a-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="1be4a-120">Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API-hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="1be4a-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
