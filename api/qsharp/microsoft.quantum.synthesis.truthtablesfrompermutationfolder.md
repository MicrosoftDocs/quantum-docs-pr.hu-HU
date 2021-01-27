---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 881bb8e29d3d7761cc521837502ea79b0714b381
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855249"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="a60b9-102">TruthTablesFromPermutationFolder függvény</span><span class="sxs-lookup"><span data-stu-id="a60b9-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="a60b9-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a60b9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a60b9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a60b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a60b9-105">Egyváltozós indexek kibontási logikája</span><span class="sxs-lookup"><span data-stu-id="a60b9-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="a60b9-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a60b9-106">Description</span></span>

<span data-ttu-id="a60b9-107">Ez a jelenlegi állapotba kerül, és egy frissített permutációt hoz létre, és esetleg új funkciókat ad az ellenőrzött kapuk számára.</span><span class="sxs-lookup"><span data-stu-id="a60b9-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="a60b9-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a60b9-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="a60b9-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a60b9-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="a60b9-110">állapot: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="a60b9-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="a60b9-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a60b9-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="a60b9-112">Kimenet: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="a60b9-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

