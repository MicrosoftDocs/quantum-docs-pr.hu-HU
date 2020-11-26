---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: e1eeed0dcd4084401e2680ff1188db4225ee85ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214755"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="37619-102">JordanWignerFermionFunction függvény</span><span class="sxs-lookup"><span data-stu-id="37619-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="37619-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="37619-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="37619-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="37619-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="37619-105">A dinamikus generátort szimulálható kapuk készlete jelöli, a JordanWigner pedig kibővíthető.</span><span class="sxs-lookup"><span data-stu-id="37619-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="37619-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37619-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="37619-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="37619-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="37619-108">Egy, az JordanWigner-ben egységes evolúcióként megjeleníteni kívánt generátor-index.</span><span class="sxs-lookup"><span data-stu-id="37619-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="37619-109">Kimenet: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="37619-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="37619-110">A `EvolutionUnitary` "generatorIndex" kifejezésben hivatkozott idő szerinti evolúció.</span><span class="sxs-lookup"><span data-stu-id="37619-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>