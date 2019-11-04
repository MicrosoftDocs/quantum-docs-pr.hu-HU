---
title: Erőforrás-számlálások beszerzése | Microsoft Docs
description: Erőforrás-számlálási dokumentumok beszerzése
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: f9311c1987ced4336c4e98bdb984fbee009e9acc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442461"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="5b386-103">Erőforrásszámok lekérése</span><span class="sxs-lookup"><span data-stu-id="5b386-103">Obtaining resource counts</span></span>

<span data-ttu-id="5b386-104">A klasszikus számítógépeken a $n $ qubits szimulálása a $n $-val exponenciálisan méretezhető.</span><span class="sxs-lookup"><span data-stu-id="5b386-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="5b386-105">Ez nagy mértékben korlátozza a kvantum-kémia szimulációt, amelyet a teljes állapotú szimulátorral lehet elvégezni.</span><span class="sxs-lookup"><span data-stu-id="5b386-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="5b386-106">A kémia nagy példányai esetében is hasznos információkhoz juthat.</span><span class="sxs-lookup"><span data-stu-id="5b386-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="5b386-107">Itt megvizsgáljuk, hogy az erőforrás-költségek, például a T-Gates vagy a CNEM-kapuk száma, a szimuláló kémia esetében a [nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro)használatával automatizált módon szerezhetők be.</span><span class="sxs-lookup"><span data-stu-id="5b386-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="5b386-108">Ezek az információk arra utalnak minket, hogy ha a kvantum-számítógépek elég nagyok ahhoz, hogy ezeket a kvantum-kémiai algoritmusokat futtatni tudják.</span><span class="sxs-lookup"><span data-stu-id="5b386-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="5b386-109">A hivatkozásokat lásd a megadott `GetGateCount` mintában.</span><span class="sxs-lookup"><span data-stu-id="5b386-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="5b386-110">Tegyük fel, hogy már van egy `FermionHamiltonian`-példányunk, azaz betöltve a Broombridge-sémából, ahogy azt a [fájl betöltése a következő](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) példában tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="5b386-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="5b386-111">Az erőforrás-becslések beszerzésének szintaxisa majdnem azonos az algoritmusnak a teljes állapotú szimulátoron való futtatásával.</span><span class="sxs-lookup"><span data-stu-id="5b386-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="5b386-112">Egyszerűen válasszon másik célszámítógépet.</span><span class="sxs-lookup"><span data-stu-id="5b386-112">We simply choose a different target machine.</span></span> <span data-ttu-id="5b386-113">Az erőforrás-becslések esetében elegendő az egyetlen Trotter-lépés vagy a Qubitization-módszer által létrehozott Quantum Walk-érték kiértékelése.</span><span class="sxs-lookup"><span data-stu-id="5b386-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="5b386-114">Az algoritmusok meghívásához használt szöveg a következő.</span><span class="sxs-lookup"><span data-stu-id="5b386-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="5b386-115">Most a nyomkövetési szimulátort úgy konfiguráltuk, hogy nyomon kövessük a kívánt erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="5b386-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="5b386-116">Ebben az esetben a primitív kvantum-műveleteket a `usePrimitiveOperationsCounter` jelző `true`re való beállításával számítjuk ki.</span><span class="sxs-lookup"><span data-stu-id="5b386-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="5b386-117">A technikai részletes `throwOnUnconstraintMeasurement` `false`re van beállítva, hogy elkerülje a kivételeket azokban az esetekben, amikor a Q # kód helytelenül állítja elő a mérési eredmények valószínűségét, ha vannak ilyenek.</span><span class="sxs-lookup"><span data-stu-id="5b386-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="5b386-118">Most a következő módon futtatjuk a Quantum algoritmust az illesztőprogram-programból.</span><span class="sxs-lookup"><span data-stu-id="5b386-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```