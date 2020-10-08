---
title: Kvantumszimulátorok és Q#-programok
description: A Q#-programok számára célgépként elérhető kvantumszimulátorokat ismerteti.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: f40c63eed60379aa46a0cd9cfdd7d8de8c22c079
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771309"
---
# <a name="quantum-simulators"></a><span data-ttu-id="c9e09-103">Kvantumszimulátorok</span><span class="sxs-lookup"><span data-stu-id="c9e09-103">Quantum simulators</span></span>

<span data-ttu-id="c9e09-104">A kvantumszimulátorok a klasszikus számítógépeken futó szoftverek, amelyek *célgépként* érhetők el Q#-programok számára, és segítségükkel a kvantumprogramok olyan környezetben futtathatók és tesztelhetők, amely előre jelzi, hogy a qubitek hogyan fognak reagálni a különböző műveletekre.</span><span class="sxs-lookup"><span data-stu-id="c9e09-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="c9e09-105">Ez a cikk ismerteti, hogy milyen kvantumszimulátorokat tartalmaz a Quantum Development Kit (QDK), és milyen módokon adható át egy Q#-program a kvantumszimulátorok számára, például a parancssorból vagy klasszikus nyelven írt illesztőkóddal.</span><span class="sxs-lookup"><span data-stu-id="c9e09-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="c9e09-106">A Quantum Development Kit (QDK) kvantumszimulátorai</span><span class="sxs-lookup"><span data-stu-id="c9e09-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="c9e09-107">A kvantumszimulátor felel a kvantumprimitívek implementálásáért egy algoritmus esetében.</span><span class="sxs-lookup"><span data-stu-id="c9e09-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="c9e09-108">Ezekbe beletartoznak olyan primitív műveletek, mint a `H`, a `CNOT` és a `Measure`, továbbá a qubitek kezelése és nyomkövetése.</span><span class="sxs-lookup"><span data-stu-id="c9e09-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="c9e09-109">A QDK-ban megtalálható kvantumszimulátorok különböző osztályai ugyanazon kvantumalgoritmus különböző szimulálási módjait jelölik.</span><span class="sxs-lookup"><span data-stu-id="c9e09-109">The QDK includes different classes of quantum simulators representing different ways of simulating the same quantum algorithm.</span></span> 


<span data-ttu-id="c9e09-110">Minden egyes kvantumszimulátor-típus ezen primitívek más-más implementációját biztosíthatja.</span><span class="sxs-lookup"><span data-stu-id="c9e09-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="c9e09-111">Például a [teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator) futtatja a kvantumalgoritmust a [kvantumállapot-vektor](xref:microsoft.quantum.glossary#quantum-state) teljes körű szimulálásával, míg a [kvantumszámítógép nyomkövetési szimulátora](xref:microsoft.quantum.machines.qc-trace-simulator.intro) egyáltalán nem veszi figyelembe a tényleges kvantumállapotot.</span><span class="sxs-lookup"><span data-stu-id="c9e09-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="c9e09-112">hanem az algoritmus kapu-, qubit- és egyéb erőforrás-felhasználását követi nyomon.</span><span class="sxs-lookup"><span data-stu-id="c9e09-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="c9e09-113">Kvantumszámítógép-osztályok</span><span class="sxs-lookup"><span data-stu-id="c9e09-113">Quantum machine classes</span></span>

<span data-ttu-id="c9e09-114">A jövőben a QDK további kvantumgéposztályokat fog meghatározni további szimulációtípusok és a kvantumhardveren történő futtatás támogatása érdekében.</span><span class="sxs-lookup"><span data-stu-id="c9e09-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support running on quantum hardware.</span></span> <span data-ttu-id="c9e09-115">Ha az algoritmus számára lehetővé tesszük, hogy változatlan maradjon, miközben a mögöttes gépimplementáció módosul, az megkönnyíti az algoritmusok tesztelését és hibakeresését egy szimulációban, majd futtatásukat valódi hardveren, miközben biztos lehet benne, hogy az algoritmusok nem változtak.</span><span class="sxs-lookup"><span data-stu-id="c9e09-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="c9e09-116">A QDK számos kvantumszámítógép-osztályt tartalmaz, ezek mindegyike meg van határozva a `Microsoft.Quantum.Simulation.Simulators` névtérben.</span><span class="sxs-lookup"><span data-stu-id="c9e09-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="c9e09-117">Szimulátor</span><span class="sxs-lookup"><span data-stu-id="c9e09-117">Simulator</span></span> |<span data-ttu-id="c9e09-118">Osztály</span><span class="sxs-lookup"><span data-stu-id="c9e09-118">Class</span></span>|<span data-ttu-id="c9e09-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="c9e09-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="c9e09-120">Teljes körű funkciókkal rendelkező szimulátor</span><span class="sxs-lookup"><span data-stu-id="c9e09-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="c9e09-121">Kvantumalgoritmusokat futtat, hibakeresést végez rajtuk, és kb. 30 qubitre van korlátozva.</span><span class="sxs-lookup"><span data-stu-id="c9e09-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="c9e09-122">Egyszerű erőforrásbecslő</span><span class="sxs-lookup"><span data-stu-id="c9e09-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="c9e09-123">Végrehajtja a kvantumalgoritmusok futtatásához szükséges erőforrások átfogó elemzését, és több ezer qubitet támogat.</span><span class="sxs-lookup"><span data-stu-id="c9e09-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="c9e09-124">Nyomkövetés-alapú erőforrásbecslő</span><span class="sxs-lookup"><span data-stu-id="c9e09-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="c9e09-125">Az algoritmus teljes hívási gráfjának speciális erőforrás-használati elemzését futtatja, és több ezer qubitet támogat.</span><span class="sxs-lookup"><span data-stu-id="c9e09-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="c9e09-126">Toffoli-szimulátor</span><span class="sxs-lookup"><span data-stu-id="c9e09-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="c9e09-127">Olyan kvantumalgoritmusokat szimulál, amelyek `X`, `CNOT` és több elem által vezérelt `X` kvantumműveletekre vannak korlátozva, és több millió qubitet támogat.</span><span class="sxs-lookup"><span data-stu-id="c9e09-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="c9e09-128">A kvantumszimulátor meghívása</span><span class="sxs-lookup"><span data-stu-id="c9e09-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="c9e09-129">[A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) szakasz háromféle megoldást mutat be a Q#-kód kvantumszimulátor számára való átadására:</span><span class="sxs-lookup"><span data-stu-id="c9e09-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="c9e09-130">A parancssor használata</span><span class="sxs-lookup"><span data-stu-id="c9e09-130">Using the command line</span></span>
* <span data-ttu-id="c9e09-131">Python-gazdaprogram használata</span><span class="sxs-lookup"><span data-stu-id="c9e09-131">Using a Python host program</span></span>
* <span data-ttu-id="c9e09-132">C#-gazdaprogram használata</span><span class="sxs-lookup"><span data-stu-id="c9e09-132">Using a C# host program</span></span>

<span data-ttu-id="c9e09-133">A kvantumgépek normál .NET-osztályok példányai, így a .NET-osztályokhoz hasonlóan a konstruktoruk meghívásával jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="c9e09-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="c9e09-134">Ennek végrehajtása attól függ, hogyan futtatja a Q#-programot.</span><span class="sxs-lookup"><span data-stu-id="c9e09-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9e09-135">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="c9e09-135">Next steps</span></span>

* <span data-ttu-id="c9e09-136">A célgépek Q#-programokhoz különböző környezetekben való meghívásának részleteiért tekintse meg [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c9e09-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
