---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710588"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="b7d07-102">InterpolatedEvolution függvény</span><span class="sxs-lookup"><span data-stu-id="b7d07-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="b7d07-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b7d07-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b7d07-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7d07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7d07-105">A két generátor közötti, egységes ütemtervtel rendelkező és egy olyan műveletet ad vissza, amely a szimulált evolúciót alkalmazza az eredményül kapott időfüggő generátorban egy qubit-regiszterbe.</span><span class="sxs-lookup"><span data-stu-id="b7d07-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b7d07-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b7d07-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="b7d07-107">interpolationTime: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7d07-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7d07-108">Az interpoláció végrehajtásához szükséges idő.</span><span class="sxs-lookup"><span data-stu-id="b7d07-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="b7d07-109">evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="b7d07-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="b7d07-110">A kezdeti generátor szimulálja az evolúciót a alatt.</span><span class="sxs-lookup"><span data-stu-id="b7d07-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="b7d07-111">evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="b7d07-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="b7d07-112">A végső generátor szimulálja az evolúciót a alatt.</span><span class="sxs-lookup"><span data-stu-id="b7d07-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="b7d07-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="b7d07-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="b7d07-114">Egy időfüggő szimuláló algoritmus, amely az evolúció szimulálása érdekében lesz felhasználva az egységes interpolációs ütemtervben.</span><span class="sxs-lookup"><span data-stu-id="b7d07-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="b7d07-115">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="b7d07-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="b7d07-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b7d07-116">Remarks</span></span>

<span data-ttu-id="b7d07-117">Ha az interpolációs idő úgy van kiválasztva, hogy megfeleljen a adiabatic feltételeinek, akkor ez a függvény olyan műveletet ad vissza, amely adiabatic állapot-előkészítést végez a végső dinamikus generátorhoz.</span><span class="sxs-lookup"><span data-stu-id="b7d07-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>