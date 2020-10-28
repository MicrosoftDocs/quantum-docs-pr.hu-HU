---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720293"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="54c4a-102">DiscreteUniformDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="54c4a-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="54c4a-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="54c4a-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="54c4a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54c4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54c4a-105">Egy adott befogadó tartományon belüli egységes eloszlást ad vissza.</span><span class="sxs-lookup"><span data-stu-id="54c4a-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="54c4a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="54c4a-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="54c4a-107">min.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54c4a-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54c4a-108">A rajzolni kívánt legkisebb egész szám.</span><span class="sxs-lookup"><span data-stu-id="54c4a-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="54c4a-109">Max.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54c4a-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54c4a-110">A kirajzolni kívánt legnagyobb egész szám.</span><span class="sxs-lookup"><span data-stu-id="54c4a-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="54c4a-111">Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="54c4a-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="54c4a-112">Olyan eloszlás, amelynek véletlenszerű változói a befogadó tartományon belüli egész szám, `min` `max` egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="54c4a-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="54c4a-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="54c4a-113">Remarks</span></span>

<span data-ttu-id="54c4a-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="54c4a-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="54c4a-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="54c4a-115">See Also</span></span>

- [<span data-ttu-id="54c4a-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="54c4a-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)