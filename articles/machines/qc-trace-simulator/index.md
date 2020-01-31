---
title: Kvantumszámítógép nyomkövetési szimulátora | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820436"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="71b1e-103">Kvantum-nyomkövetési szimulátor</span><span class="sxs-lookup"><span data-stu-id="71b1e-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="71b1e-104">A Microsoft kvantumszámítógépekhez való nyomkövetési szimulátora egy kvantumprogramot hajt végre a kvantumszámítógép állapotának tényleges szimulálása nélkül.</span><span class="sxs-lookup"><span data-stu-id="71b1e-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="71b1e-105">Emiatt a nyomkövetési szimulátor olyan kvantumprogramokat is futtathat, amelyek több ezer qubitet használnak.</span><span class="sxs-lookup"><span data-stu-id="71b1e-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="71b1e-106">Ez két főbb okból lehet hasznos:</span><span class="sxs-lookup"><span data-stu-id="71b1e-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="71b1e-107">Olyan klasszikus kódok hibakeresésekor, amelyek egy kvantumprogram részei.</span><span class="sxs-lookup"><span data-stu-id="71b1e-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="71b1e-108">Annak a megbecsléséhez, mennyi erőforrásra van szükség a kvantumprogramok egy adott példányának a kvantumszámítógépen való futtatásához.</span><span class="sxs-lookup"><span data-stu-id="71b1e-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="71b1e-109">A nyomkövetési szimulátor a felhasználó által a mérések végrehajtásakor megadandó további információkra támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="71b1e-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="71b1e-110">További részletekért tekintse meg a [mérési eredmények valószínűségének biztosításával](#providing-the-probability-of-measurement-outcomes) foglalkozó témakört.</span><span class="sxs-lookup"><span data-stu-id="71b1e-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="71b1e-111">Mérési eredmények valószínűségének biztosítása</span><span class="sxs-lookup"><span data-stu-id="71b1e-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="71b1e-112">A kvantumalgoritmusokban kétféle mérték szerepel.</span><span class="sxs-lookup"><span data-stu-id="71b1e-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="71b1e-113">Az első kiegészítő szerepet tölt be, mert a felhasználó általában ismeri a kimenetel valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="71b1e-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="71b1e-114">Ebben az esetben a felhasználó beírhat egy <xref:microsoft.quantum.intrinsic.assertprob> műveletet a <xref:microsoft.quantum.intrinsic> névtérből, hogy kifejezze a birtokában lévő tudást.</span><span class="sxs-lookup"><span data-stu-id="71b1e-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="71b1e-115">A következő példa ezt illusztrálja:</span><span class="sxs-lookup"><span data-stu-id="71b1e-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="71b1e-116">Amikor a nyomkövetési szimulátor végrehajtja az `AssertProb` műveletet, rögzíti, hogy a `PauliZ` mérése a `source` és az `q` esetében 0,5-ös valószínűséggel `Zero` eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="71b1e-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="71b1e-117">Ha a szimulátor később végrehajtja az `M` műveletet, megtalálja a kimeneti valószínűséghez rögzített értékeket, és az `M` 0,5-ös valószínűséggel `Zero` vagy `One` eredményt ad ki.</span><span class="sxs-lookup"><span data-stu-id="71b1e-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="71b1e-118">Ha ugyanazt a kódot egy olyan szimulátoron hajtja végre, amely nyomon követi a kvantumállapotot, a szimulátor ellenőrizni fogja, hogy az `AssertProb` megadott valószínűségei helyesek-e.</span><span class="sxs-lookup"><span data-stu-id="71b1e-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="71b1e-119">Program futtatása a kvantumszámítógép nyomkövetési szimulátorával</span><span class="sxs-lookup"><span data-stu-id="71b1e-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="71b1e-120">A kvantumszámítógép nyomkövetési szimulátora tekinthető úgy, mint egy másik célszámítógép.</span><span class="sxs-lookup"><span data-stu-id="71b1e-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="71b1e-121">A használatára szolgáló C#-illesztő nagyon hasonló a bármelyik másik kvantumszimulátorhoz használthoz:</span><span class="sxs-lookup"><span data-stu-id="71b1e-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="71b1e-122">Figyelje meg, hogy ha legalább egy mérést nem látott el jegyzettel az `AssertProb` használatával, a szimulátor `UnconstrainedMeasurementException` kivételt ad vissza a `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` névtérből.</span><span class="sxs-lookup"><span data-stu-id="71b1e-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="71b1e-123">További részleteket az [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) API-dokumentációban találhat.</span><span class="sxs-lookup"><span data-stu-id="71b1e-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="71b1e-124">A kvantumprogramok futtatása mellett a nyomkövetési szimulátor öt olyan összetevővel is rendelkezik, amelyek képesek a kvantumprogramok hibáinak észlelésére és erőforrás-becsléseinek végrehajtására:</span><span class="sxs-lookup"><span data-stu-id="71b1e-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="71b1e-125">Eltérő bemenetek ellenőrzője</span><span class="sxs-lookup"><span data-stu-id="71b1e-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="71b1e-126">Érvénytelenített qubithasználat ellenőrzője</span><span class="sxs-lookup"><span data-stu-id="71b1e-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="71b1e-127">Primitív műveletek számlálója</span><span class="sxs-lookup"><span data-stu-id="71b1e-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="71b1e-128">Kvantumkörök mélységének számlálója</span><span class="sxs-lookup"><span data-stu-id="71b1e-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="71b1e-129">Kvantumkörök szélességének számlálója</span><span class="sxs-lookup"><span data-stu-id="71b1e-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="71b1e-130">Ezek az összetevők a megfelelő jelzők beállításával engedélyezhetők a `QCTraceSimulatorConfiguration` elemnél.</span><span class="sxs-lookup"><span data-stu-id="71b1e-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="71b1e-131">Az egyes összetevők használatáról további részleteket a megfelelő referenciafájlokban talál.</span><span class="sxs-lookup"><span data-stu-id="71b1e-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="71b1e-132">A részletekért tekintse meg a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) API-dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="71b1e-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="71b1e-133">Lásd még</span><span class="sxs-lookup"><span data-stu-id="71b1e-133">See also</span></span>
<span data-ttu-id="71b1e-134">A kvantumszámítógép [nyomkövetési szimulátorának](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C#-referenciája</span><span class="sxs-lookup"><span data-stu-id="71b1e-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

