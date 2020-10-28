---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724453"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="6caf1-102">TruthTablesFromPermutationFolder függvény</span><span class="sxs-lookup"><span data-stu-id="6caf1-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="6caf1-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6caf1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6caf1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6caf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6caf1-105">Egyváltozós indexek kibontási logikája</span><span class="sxs-lookup"><span data-stu-id="6caf1-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="6caf1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6caf1-106">Description</span></span>

<span data-ttu-id="6caf1-107">Ez a jelenlegi állapotba kerül, és egy frissített permutációt hoz létre, és esetleg új funkciókat ad az ellenőrzött kapuk számára.</span><span class="sxs-lookup"><span data-stu-id="6caf1-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="6caf1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6caf1-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="6caf1-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6caf1-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="6caf1-110">állapot: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="6caf1-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="6caf1-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6caf1-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="6caf1-112">Kimenet: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="6caf1-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

