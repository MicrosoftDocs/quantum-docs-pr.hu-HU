---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722815"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="4fd80-102">CategoricalDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="4fd80-102">CategoricalDistribution function</span></span>

<span data-ttu-id="4fd80-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4fd80-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4fd80-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fd80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fd80-105">Egy diszkrét kategorikus eloszlást ad vissza, amely során a rendszer explicit módon megadja az adott kimenetek véges listájának valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="4fd80-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="4fd80-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4fd80-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="4fd80-107">Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4fd80-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4fd80-108">A kategorikus eloszlás minden egyes eredményének valószínűsége.</span><span class="sxs-lookup"><span data-stu-id="4fd80-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="4fd80-109">Előfordulhat, hogy ezek a valószínűségek nem normalizáltak, de mindegyiknek nem negatívnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4fd80-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="4fd80-110">Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="4fd80-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="4fd80-111">Az index a `i` valószínűséggel `probs[i] / sum` , ahol `sum` a a `probs` által megadott összeg `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="4fd80-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>