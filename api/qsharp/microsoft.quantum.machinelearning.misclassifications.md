---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Nem kategorizált besorolási függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723584"
---
# <a name="misclassifications-function"></a><span data-ttu-id="98838-102">Nem kategorizált besorolási függvény</span><span class="sxs-lookup"><span data-stu-id="98838-102">Misclassifications function</span></span>

<span data-ttu-id="98838-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="98838-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="98838-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98838-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98838-105">A kikövetkeztetett címkék és a megfelelő címkék halmaza miatt a rendszer az indexeket adja vissza, amelyekben az egyes címkék eltérőek.</span><span class="sxs-lookup"><span data-stu-id="98838-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="98838-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="98838-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="98838-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98838-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98838-108">Egy adott képzésre vagy érvényesítési csoportra hivatkozó címkék.</span><span class="sxs-lookup"><span data-stu-id="98838-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="98838-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98838-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98838-110">Egy adott képzés vagy érvényesítési csoport valódi címkéi.</span><span class="sxs-lookup"><span data-stu-id="98838-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="98838-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98838-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98838-112">Olyan indexek tömbje `idx` , amelyek ilyenek `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="98838-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>