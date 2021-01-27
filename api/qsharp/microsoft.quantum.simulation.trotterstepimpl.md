---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 33dc922cd5a60590a1306369fb99615fc6575b22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856729"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="c79e5-102">TrotterStepImpl művelet</span><span class="sxs-lookup"><span data-stu-id="c79e5-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="c79e5-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c79e5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c79e5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c79e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c79e5-105">Az a-ben foglalt kifejezéssel valósítja meg az időbeli alakulást `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="c79e5-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c79e5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c79e5-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="c79e5-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="c79e5-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="c79e5-108">A szimulálni kívánt rendszer teljes leírása.</span><span class="sxs-lookup"><span data-stu-id="c79e5-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="c79e5-109">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c79e5-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c79e5-110">Egész index egy kifejezésre a leírt rendszeren.</span><span class="sxs-lookup"><span data-stu-id="c79e5-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c79e5-111">stepsize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c79e5-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c79e5-112">Szorzó az időtartamra vonatkozóan – a által indexelt időszak szerinti evolúció `idx` .</span><span class="sxs-lookup"><span data-stu-id="c79e5-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c79e5-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c79e5-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c79e5-114">A qubits a szimuláció alapján működött.</span><span class="sxs-lookup"><span data-stu-id="c79e5-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c79e5-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c79e5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

