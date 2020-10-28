---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719872"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="fbaff-102">TimeDependentTrotterSimulationAlgorithm függvény</span><span class="sxs-lookup"><span data-stu-id="fbaff-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="fbaff-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fbaff-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fbaff-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbaff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbaff-105">`TimeDependentSimulationAlgorithm` a függvény, amely egy Trotter – Suzuki dekompozíciót használ egy olyan egységes operátor közelítéséhez, amely megoldja az időfüggő Schrödinger-egyenletet.</span><span class="sxs-lookup"><span data-stu-id="fbaff-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="fbaff-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fbaff-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="fbaff-107">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fbaff-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fbaff-108">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="fbaff-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="fbaff-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbaff-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbaff-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="fbaff-110">Order of Trotter integrator.</span></span> <span data-ttu-id="fbaff-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="fbaff-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="fbaff-112">Kimenet: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="fbaff-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="fbaff-113">Egy `TimeDependentSimulationAlgorithm` típus.</span><span class="sxs-lookup"><span data-stu-id="fbaff-113">A `TimeDependentSimulationAlgorithm` type.</span></span>