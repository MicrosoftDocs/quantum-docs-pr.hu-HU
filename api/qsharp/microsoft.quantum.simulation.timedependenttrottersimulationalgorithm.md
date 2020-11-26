---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 94bc606fdc46d77e8beb1470c78102a63e6d4e81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192774"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="bce0a-102">TimeDependentTrotterSimulationAlgorithm függvény</span><span class="sxs-lookup"><span data-stu-id="bce0a-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="bce0a-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bce0a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bce0a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bce0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bce0a-105">`TimeDependentSimulationAlgorithm` a függvény, amely egy Trotter – Suzuki dekompozíciót használ egy olyan egységes operátor közelítéséhez, amely megoldja az időfüggő Schrödinger-egyenletet.</span><span class="sxs-lookup"><span data-stu-id="bce0a-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="bce0a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bce0a-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="bce0a-107">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bce0a-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bce0a-108">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="bce0a-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="bce0a-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bce0a-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bce0a-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="bce0a-110">Order of Trotter integrator.</span></span> <span data-ttu-id="bce0a-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="bce0a-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="bce0a-112">Kimenet: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="bce0a-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="bce0a-113">Egy `TimeDependentSimulationAlgorithm` típus.</span><span class="sxs-lookup"><span data-stu-id="bce0a-113">A `TimeDependentSimulationAlgorithm` type.</span></span>