---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851156"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="a43dd-102">DrawCategorical művelet</span><span class="sxs-lookup"><span data-stu-id="a43dd-102">DrawCategorical operation</span></span>

<span data-ttu-id="a43dd-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a43dd-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a43dd-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a43dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a43dd-105">Véletlenszerű mintát rajzol egy probablities által meghatározott kategorikus eloszlásból.</span><span class="sxs-lookup"><span data-stu-id="a43dd-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="a43dd-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a43dd-106">Description</span></span>

<span data-ttu-id="a43dd-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="a43dd-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="a43dd-108">A nullával egyenlő tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="a43dd-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="a43dd-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="a43dd-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="a43dd-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a43dd-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="a43dd-111">Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a43dd-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a43dd-112">Egy lebegőpontos számokból álló tömb, amely az egyes indexek kiválasztásának valószínűségével arányos.</span><span class="sxs-lookup"><span data-stu-id="a43dd-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="a43dd-113">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a43dd-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a43dd-114">Egy egész szám $i $, a következő valószínűséggel: $ \Pr (i) = p_i/\ sum_i p_i $, ahol $p _i $ a $i $ th eleme `probs` .</span><span class="sxs-lookup"><span data-stu-id="a43dd-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a43dd-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a43dd-115">See Also</span></span>

- [<span data-ttu-id="a43dd-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="a43dd-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)