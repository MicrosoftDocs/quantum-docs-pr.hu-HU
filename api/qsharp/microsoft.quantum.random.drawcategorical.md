---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192995"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="4d6d2-102">DrawCategorical művelet</span><span class="sxs-lookup"><span data-stu-id="4d6d2-102">DrawCategorical operation</span></span>

<span data-ttu-id="4d6d2-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4d6d2-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4d6d2-105">Véletlenszerű mintát rajzol egy probablities által meghatározott kategorikus eloszlásból.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="4d6d2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4d6d2-106">Description</span></span>

<span data-ttu-id="4d6d2-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="4d6d2-108">A nullával egyenlő tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="4d6d2-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="4d6d2-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4d6d2-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="4d6d2-111">Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4d6d2-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4d6d2-112">Egy lebegőpontos számokból álló tömb, amely az egyes indexek kiválasztásának valószínűségével arányos.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="4d6d2-113">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d6d2-114">Egy egész szám $i $, a következő valószínűséggel: $ \Pr (i) = p_i/\ sum_i p_i $, ahol $p _i $ a $i $ th eleme `probs` .</span><span class="sxs-lookup"><span data-stu-id="4d6d2-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d6d2-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4d6d2-115">See Also</span></span>

- [<span data-ttu-id="4d6d2-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="4d6d2-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)