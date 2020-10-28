---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719861"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="292f9-102">TrotterSimulationAlgorithm függvény</span><span class="sxs-lookup"><span data-stu-id="292f9-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="292f9-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="292f9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="292f9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="292f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="292f9-105">`SimulationAlgorithm` a függvény, amely egy Trotter – Suzuki-lebomlást használ az idő-Evolution operátor _exp (-iHt)_ megközelítő értékének eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="292f9-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="292f9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="292f9-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="292f9-107">trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="292f9-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="292f9-108">Szimulált idő időbeli alakulása egyetlen Trotter lépésben.</span><span class="sxs-lookup"><span data-stu-id="292f9-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="292f9-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="292f9-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="292f9-110">A Trotter-integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="292f9-110">Order of Trotter integrator.</span></span> <span data-ttu-id="292f9-111">Ennek 1 vagy páros számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="292f9-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="292f9-112">Kimenet: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="292f9-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="292f9-113">Egy `SimulationAlgorithm` típus.</span><span class="sxs-lookup"><span data-stu-id="292f9-113">A `SimulationAlgorithm` type.</span></span>