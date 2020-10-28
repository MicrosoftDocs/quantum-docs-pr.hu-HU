---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720281"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="eda61-102">DrawCategorical művelet</span><span class="sxs-lookup"><span data-stu-id="eda61-102">DrawCategorical operation</span></span>

<span data-ttu-id="eda61-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="eda61-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="eda61-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eda61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eda61-105">Véletlenszerű mintát rajzol egy probablities által meghatározott kategorikus eloszlásból.</span><span class="sxs-lookup"><span data-stu-id="eda61-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="eda61-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="eda61-106">Description</span></span>

<span data-ttu-id="eda61-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="eda61-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="eda61-108">A nullával egyenlő tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="eda61-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="eda61-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="eda61-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="eda61-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eda61-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="eda61-111">Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eda61-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eda61-112">Egy lebegőpontos számokból álló tömb, amely az egyes indexek kiválasztásának valószínűségével arányos.</span><span class="sxs-lookup"><span data-stu-id="eda61-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="eda61-113">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eda61-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eda61-114">Egy egész szám $i $, a következő valószínűséggel: $ \Pr (i) = p_i/\ sum_i p_i $, ahol $p _i $ a $i $ th eleme `probs` .</span><span class="sxs-lookup"><span data-stu-id="eda61-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="eda61-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="eda61-115">See Also</span></span>

- [<span data-ttu-id="eda61-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="eda61-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)