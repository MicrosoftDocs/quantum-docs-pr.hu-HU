---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203399"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="c6759-102">TrotterSimulationAlgorithmImpl művelet</span><span class="sxs-lookup"><span data-stu-id="c6759-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="c6759-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c6759-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c6759-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6759-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6759-105">Ismétlődő hívásokat kezdeményez `TrotterStep` a Time-Evolution operátor exp (_-iHt_) eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="c6759-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c6759-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c6759-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="c6759-107">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c6759-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c6759-108">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="c6759-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c6759-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6759-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6759-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="c6759-110">Order of Trotter integrator.</span></span> <span data-ttu-id="c6759-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c6759-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="c6759-112">maxTime: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c6759-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c6759-113">A szimuláció $t $ teljes időtartama.</span><span class="sxs-lookup"><span data-stu-id="c6759-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="c6759-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="c6759-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="c6759-115">A szimulálni kívánt rendszer teljes leírása.</span><span class="sxs-lookup"><span data-stu-id="c6759-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c6759-116">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c6759-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c6759-117">A qubits a szimuláció alapján működött.</span><span class="sxs-lookup"><span data-stu-id="c6759-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6759-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6759-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

