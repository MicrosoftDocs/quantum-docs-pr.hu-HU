---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 023ac4a6aaee8e3d0514a471c33c575b86004b15
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203824"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a><span data-ttu-id="69e73-102">_JordanWignerClusterOperatorFunction függvény</span><span class="sxs-lookup"><span data-stu-id="69e73-102">_JordanWignerClusterOperatorFunction function</span></span>

<span data-ttu-id="69e73-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="69e73-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="69e73-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="69e73-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="69e73-105">A dinamikus generátort szimulálható kapuk készlete jelöli, a JordanWigner pedig kibővíthető.</span><span class="sxs-lookup"><span data-stu-id="69e73-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="69e73-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69e73-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="69e73-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="69e73-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="69e73-108">Egy, az JordanWigner-ben egységes evolúcióként megjeleníteni kívánt generátor-index.</span><span class="sxs-lookup"><span data-stu-id="69e73-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="69e73-109">Kimenet: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="69e73-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="69e73-110">A `EvolutionUnitary` "generatorIndex" kifejezésben hivatkozott idő szerinti evolúció.</span><span class="sxs-lookup"><span data-stu-id="69e73-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>