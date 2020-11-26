---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: e581cd4d0a3caf96bece9979a1d850aad7842727
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230360"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="fb854-102">PauliEvolutionFunction függvény</span><span class="sxs-lookup"><span data-stu-id="fb854-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="fb854-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fb854-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fb854-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb854-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb854-105">Szimulálható kapuk készletének és a Pauli-alapú bővítésnek a dinamikus generátort jelöli.</span><span class="sxs-lookup"><span data-stu-id="fb854-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="fb854-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fb854-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="fb854-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fb854-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fb854-108">Egy olyan generátor-index, amely a Pauli-alapú, egységes evolúció formájában jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fb854-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="fb854-109">Kimenet: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="fb854-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="fb854-110">A `EvolutionUnitary` "generatorIndex" kifejezésben hivatkozott idő szerinti evolúció.</span><span class="sxs-lookup"><span data-stu-id="fb854-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>