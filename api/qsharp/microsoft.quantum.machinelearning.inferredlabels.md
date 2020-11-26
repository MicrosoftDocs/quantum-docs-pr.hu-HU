---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196361"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="e06f3-102">InferredLabels függvény</span><span class="sxs-lookup"><span data-stu-id="e06f3-102">InferredLabels function</span></span>

<span data-ttu-id="e06f3-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e06f3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e06f3-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e06f3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e06f3-105">A besorolási valószínűségek és a torzítások tömbje az egyes valószínűségek alapján kikövetkeztetett címkét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e06f3-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="e06f3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e06f3-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="e06f3-107">torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e06f3-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e06f3-108">A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.</span><span class="sxs-lookup"><span data-stu-id="e06f3-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="e06f3-109">valószínűségek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e06f3-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e06f3-110">Több minta besorolási valószínűségének tömbje, amely jellemzően a besorolási gyakoriságok becslését eredményezi.</span><span class="sxs-lookup"><span data-stu-id="e06f3-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="e06f3-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e06f3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e06f3-112">Az egyes besorolási valószínűségtől kikövetkeztetett címke.</span><span class="sxs-lookup"><span data-stu-id="e06f3-112">The label inferred from each classification probability.</span></span>