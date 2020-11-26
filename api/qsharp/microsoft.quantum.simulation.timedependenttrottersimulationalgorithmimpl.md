---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: f4f8a9265dc25305819da5ae1002f02b7efd1952
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203450"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="2834d-102">TimeDependentTrotterSimulationAlgorithmImpl művelet</span><span class="sxs-lookup"><span data-stu-id="2834d-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="2834d-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2834d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2834d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2834d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2834d-105">Több Trotter lépések megvalósítása egy olyan egységes operátor megközelítő megoldásához, amely megoldja az időfüggő Schrödinger-egyenletet.</span><span class="sxs-lookup"><span data-stu-id="2834d-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2834d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2834d-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="2834d-107">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2834d-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2834d-108">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="2834d-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="2834d-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2834d-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2834d-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="2834d-110">Order of Trotter integrator.</span></span> <span data-ttu-id="2834d-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2834d-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="2834d-112">maxTime: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2834d-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2834d-113">A szimuláció $t $ teljes időtartama.</span><span class="sxs-lookup"><span data-stu-id="2834d-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="2834d-114">evolutionSchedule: [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="2834d-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="2834d-115">A szimulálni kívánt időfüggő rendszer teljes leírása.</span><span class="sxs-lookup"><span data-stu-id="2834d-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2834d-116">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2834d-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2834d-117">A qubits a szimuláció alapján működött.</span><span class="sxs-lookup"><span data-stu-id="2834d-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2834d-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2834d-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

