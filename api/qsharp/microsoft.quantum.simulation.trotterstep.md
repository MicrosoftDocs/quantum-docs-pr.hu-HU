---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725349"
---
# <a name="trotterstep-function"></a><span data-ttu-id="da765-102">TrotterStep függvény</span><span class="sxs-lookup"><span data-stu-id="da765-102">TrotterStep function</span></span>

<span data-ttu-id="da765-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="da765-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="da765-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da765-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da765-105">A `EvolutionGenerator` Trotter – Suzuki dekompozíció használatával egyetlen időpontot valósít meg a következő témakörben ismertetett módon: Evolution.</span><span class="sxs-lookup"><span data-stu-id="da765-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="da765-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="da765-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="da765-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="da765-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="da765-108">A szimulálni kívánt rendszer teljes leírása.</span><span class="sxs-lookup"><span data-stu-id="da765-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="da765-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da765-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da765-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="da765-110">Order of Trotter integrator.</span></span> <span data-ttu-id="da765-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="da765-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="da765-112">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="da765-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="da765-113">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="da765-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="da765-114">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="da765-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="da765-115">Egységes művelet, amely egy adott időpontra vonatkozó időbeli alakulást közelíti meg az időtartamhoz `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="da765-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="da765-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="da765-116">Remarks</span></span>

<span data-ttu-id="da765-117">A Trotter – Suzuki dekompozícióval kapcsolatos további információkért lásd: [Időrendezve](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="da765-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>