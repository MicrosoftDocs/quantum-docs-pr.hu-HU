---
title: Kvantum-nyomkövetési szimulátor – Quantum Development Kit
description: Ismerje meg, hogyan használható a Microsoft kvantumszámítógépekhez való nyomkövetési szimulátora klasszikus kódok hibakereséséhez, illetve Q#-programok erőforrásigényeinek becsléséhez.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 54a1f63461cfcc8146f7dc4d18d321238d77454d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833365"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="16000-103">Microsoft Quantum Development Kit (QDK) – Kvantum-nyomkövetési szimulátor</span><span class="sxs-lookup"><span data-stu-id="16000-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="16000-104">A QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> osztály kvantumprogramot futtat a kvantumszámítógép állapotának tényleges szimulálása nélkül.</span><span class="sxs-lookup"><span data-stu-id="16000-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="16000-105">Emiatt a kvantum-nyomkövetési szimulátor olyan kvantumprogramokat is futtathat, amelyek több ezer qubitet használnak.</span><span class="sxs-lookup"><span data-stu-id="16000-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="16000-106">Ez két főbb okból lehet hasznos:</span><span class="sxs-lookup"><span data-stu-id="16000-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="16000-107">Olyan klasszikus kódok hibakeresésekor, amelyek egy kvantumprogram részei.</span><span class="sxs-lookup"><span data-stu-id="16000-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="16000-108">Annak a megbecsléséhez, mennyi erőforrásra van szükség a kvantumprogramok egy adott példányának a kvantumszámítógépen való futtatásához.</span><span class="sxs-lookup"><span data-stu-id="16000-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="16000-109">Az [Erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator), amely metrikák korlátozottabb készletét biztosítja, valójában a nyomkövetési szimulátorra épül.</span><span class="sxs-lookup"><span data-stu-id="16000-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="16000-110">A kvantum-nyomkövetési szimulátor meghívása</span><span class="sxs-lookup"><span data-stu-id="16000-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="16000-111">A kvantum-nyomkövetési szimulátorral bármilyen Q#-művelet futtatható.</span><span class="sxs-lookup"><span data-stu-id="16000-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="16000-112">Ahogy más célgépek esetében is, először a `QCTraceSimulator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.</span><span class="sxs-lookup"><span data-stu-id="16000-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="16000-113">Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `QCTraceSimulator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.</span><span class="sxs-lookup"><span data-stu-id="16000-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="16000-114">Mérési eredmények valószínűségének megadása</span><span class="sxs-lookup"><span data-stu-id="16000-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="16000-115">Mivel a kvantum-nyomkövetési szimulátor nem szimulálja a tényleges kvantumállapotot, ezért nem tudja kiszámolni a mérési eredmények valószínűségét egy műveletben.</span><span class="sxs-lookup"><span data-stu-id="16000-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="16000-116">Ezért ha a művelet méréseket tartalmaz, a valószínűségeket explicit módon kell megadnia a <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> művelettel a <xref:microsoft.quantum.diagnostics> névtérből.</span><span class="sxs-lookup"><span data-stu-id="16000-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="16000-117">A következő példa ezt illusztrálja:</span><span class="sxs-lookup"><span data-stu-id="16000-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="16000-118">Amikor a kvantum-nyomkövetési szimulátor végrehajtja az `AssertMeasurementProbability` műveletet, rögzíti, hogy a `PauliZ` mérése a `source` és a `q` esetében **0,5**-ös valószínűséggel `Zero` eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="16000-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="16000-119">Ha később futtatja az `M` műveletet, megkeresi a kimeneti valószínűségek rögzített értékeit, és az `M` **0,5**-ös valószínűséggel `Zero` vagy `One` eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="16000-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="16000-120">Ha ugyanazt a kódot egy olyan szimulátoron futtatja, amely nyomon követi a kvantumállapotot, a szimulátor ellenőrzi, hogy az `AssertMeasurementProbability` megadott valószínűségei helyesek-e.</span><span class="sxs-lookup"><span data-stu-id="16000-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="16000-121">Ügyeljen arra, hogy ha van legalább egy olyan mérési művelet, amely nem lett jegyzettel ellátva az `AssertMeasurementProbability` használatával, a szimulátor [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception) kivételt ad vissza.</span><span class="sxs-lookup"><span data-stu-id="16000-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="16000-122">Kvantum-nyomkövetési szimulátor – Eszközök</span><span class="sxs-lookup"><span data-stu-id="16000-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="16000-123">A QDK öt olyan, a kvantum-nyomkövetési szimulátorral használható eszközt foglal magába, amelyekkel észlelhetők a programok hibái és végrehajthatók a kvantumprogramok erőforrás-becslései:</span><span class="sxs-lookup"><span data-stu-id="16000-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="16000-124">Eszköz</span><span class="sxs-lookup"><span data-stu-id="16000-124">Tool</span></span> | <span data-ttu-id="16000-125">Leírás</span><span class="sxs-lookup"><span data-stu-id="16000-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="16000-126">Eltérő bemenetek ellenőrzője</span><span class="sxs-lookup"><span data-stu-id="16000-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="16000-127">A közös qubitek lehetséges ütközéseit ellenőrzi</span><span class="sxs-lookup"><span data-stu-id="16000-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="16000-128">Érvénytelenített qubithasználat ellenőrzője</span><span class="sxs-lookup"><span data-stu-id="16000-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="16000-129">Ellenőrzi, hogy a program alkalmaz-e műveletet egy már kiadott qubitre</span><span class="sxs-lookup"><span data-stu-id="16000-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="16000-130">Primitív műveletek számlálója</span><span class="sxs-lookup"><span data-stu-id="16000-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="16000-131">Megszámlálja a kvantumprogramban meghívott összes művelet által használt primitív folyamatokat</span><span class="sxs-lookup"><span data-stu-id="16000-131">Counts the number of primitive processes used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="16000-132">Mélységszámláló</span><span class="sxs-lookup"><span data-stu-id="16000-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="16000-133">Összegyűjti a kvantumprogramban meghívott összes művelet mélysége alsó határértékei darabszámát</span><span class="sxs-lookup"><span data-stu-id="16000-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="16000-134">Szélességszámláló</span><span class="sxs-lookup"><span data-stu-id="16000-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="16000-135">Megszámlálja a kvantumprogram egyes műveletei által lefoglalt és kölcsönzött qubiteket</span><span class="sxs-lookup"><span data-stu-id="16000-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="16000-136">Az eszközök engedélyezéséhez be kell állítani a megfelelő jelzőt a `QCTraceSimulatorConfiguration` elemnél, majd meg kell adni a konfigurációt a `QCTraceSimulator` deklarációhoz.</span><span class="sxs-lookup"><span data-stu-id="16000-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="16000-137">Az eszközök használatával kapcsolatos információk az előző listában lévő hivatkozásokon érhetők el.</span><span class="sxs-lookup"><span data-stu-id="16000-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="16000-138">További információk a `QCTraceSimulator` konfigurálásáról: [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="16000-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="16000-139">A QCTraceSimulator metódusai</span><span class="sxs-lookup"><span data-stu-id="16000-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="16000-140">A `QCTraceSimulator` többféle beépített metódussal rendelkezik a kvantumművelet során nyomon követett metrikák értékeinek lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="16000-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="16000-141">A [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) és a [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) metódusokra a [Primitív műveletek számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), a [Mélységszámláló](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) és a [Szélességszámláló](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) cikkekben talál példákat.</span><span class="sxs-lookup"><span data-stu-id="16000-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="16000-142">Az összes elérhető metódusról a Q# API-referencia [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) szakaszában talál további információkat.</span><span class="sxs-lookup"><span data-stu-id="16000-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="16000-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="16000-143">See also</span></span>

- [<span data-ttu-id="16000-144">Kvantumerőforrás-becslő</span><span class="sxs-lookup"><span data-stu-id="16000-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="16000-145">Toffoli-kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="16000-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="16000-146">Teljes körű funkciókkal rendelkező kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="16000-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 