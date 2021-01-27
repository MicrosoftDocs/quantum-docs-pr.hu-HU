---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842353"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="b5101-102">CategoricalDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="b5101-102">CategoricalDistribution function</span></span>

<span data-ttu-id="b5101-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b5101-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b5101-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b5101-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b5101-105">Egy diszkrét kategorikus eloszlást ad vissza, amely során a rendszer explicit módon megadja az adott kimenetek véges listájának valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="b5101-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="b5101-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b5101-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="b5101-107">Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b5101-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b5101-108">A kategorikus eloszlás minden egyes eredményének valószínűsége.</span><span class="sxs-lookup"><span data-stu-id="b5101-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="b5101-109">Előfordulhat, hogy ezek a valószínűségek nem normalizáltak, de mindegyiknek nem negatívnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b5101-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="b5101-110">Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="b5101-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="b5101-111">Az index a `i` valószínűséggel `probs[i] / sum` , ahol `sum` a a `probs` által megadott összeg `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="b5101-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="b5101-112">Példa</span><span class="sxs-lookup"><span data-stu-id="b5101-112">Example</span></span>

<span data-ttu-id="b5101-113">A következő Q # kód a 0 értéket jeleníti meg, amelynek a valószínűsége 30% és 1 a valószínűséggel 70%:</span><span class="sxs-lookup"><span data-stu-id="b5101-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```