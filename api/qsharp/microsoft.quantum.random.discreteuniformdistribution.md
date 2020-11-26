---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193012"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="c1eb2-102">DiscreteUniformDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="c1eb2-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="c1eb2-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c1eb2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c1eb2-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c1eb2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c1eb2-105">Egy adott befogadó tartományon belüli egységes eloszlást ad vissza.</span><span class="sxs-lookup"><span data-stu-id="c1eb2-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="c1eb2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c1eb2-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="c1eb2-107">min.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1eb2-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1eb2-108">A rajzolni kívánt legkisebb egész szám.</span><span class="sxs-lookup"><span data-stu-id="c1eb2-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="c1eb2-109">Max.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1eb2-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1eb2-110">A kirajzolni kívánt legnagyobb egész szám.</span><span class="sxs-lookup"><span data-stu-id="c1eb2-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="c1eb2-111">Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="c1eb2-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="c1eb2-112">Olyan eloszlás, amelynek véletlenszerű változói a befogadó tartományon belüli egész szám, `min` `max` egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="c1eb2-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1eb2-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c1eb2-113">Remarks</span></span>

<span data-ttu-id="c1eb2-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c1eb2-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1eb2-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c1eb2-115">See Also</span></span>

- [<span data-ttu-id="c1eb2-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c1eb2-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)