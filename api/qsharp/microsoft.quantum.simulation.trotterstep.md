---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 516b40ac9920a4a8acc09ad7f558db88dbeb41e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192808"
---
# <a name="trotterstep-function"></a><span data-ttu-id="e7a84-102">TrotterStep függvény</span><span class="sxs-lookup"><span data-stu-id="e7a84-102">TrotterStep function</span></span>

<span data-ttu-id="e7a84-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e7a84-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e7a84-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7a84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7a84-105">A `EvolutionGenerator` Trotter – Suzuki dekompozíció használatával egyetlen időpontot valósít meg a következő témakörben ismertetett módon: Evolution.</span><span class="sxs-lookup"><span data-stu-id="e7a84-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e7a84-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e7a84-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="e7a84-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="e7a84-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="e7a84-108">A szimulálni kívánt rendszer teljes leírása.</span><span class="sxs-lookup"><span data-stu-id="e7a84-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="e7a84-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7a84-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7a84-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="e7a84-110">Order of Trotter integrator.</span></span> <span data-ttu-id="e7a84-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e7a84-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="e7a84-112">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e7a84-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e7a84-113">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="e7a84-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="e7a84-114">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="e7a84-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e7a84-115">Egységes művelet, amely egy adott időpontra vonatkozó időbeli alakulást közelíti meg az időtartamhoz `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="e7a84-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7a84-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e7a84-116">Remarks</span></span>

<span data-ttu-id="e7a84-117">A Trotter – Suzuki dekompozícióval kapcsolatos további információkért lásd: [Időrendezve](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="e7a84-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>