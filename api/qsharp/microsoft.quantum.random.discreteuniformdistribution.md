---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853720"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="8b8e6-102">DiscreteUniformDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="8b8e6-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="8b8e6-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8b8e6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8b8e6-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8b8e6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8b8e6-105">Egy adott befogadó tartományon belüli egységes eloszlást ad vissza.</span><span class="sxs-lookup"><span data-stu-id="8b8e6-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="8b8e6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8b8e6-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="8b8e6-107">min.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b8e6-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b8e6-108">A rajzolni kívánt legkisebb egész szám.</span><span class="sxs-lookup"><span data-stu-id="8b8e6-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="8b8e6-109">Max.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b8e6-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b8e6-110">A kirajzolni kívánt legnagyobb egész szám.</span><span class="sxs-lookup"><span data-stu-id="8b8e6-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="8b8e6-111">Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="8b8e6-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="8b8e6-112">Olyan eloszlás, amelynek véletlenszerű változói a befogadó tartományon belüli egész szám, `min` `max` egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="8b8e6-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="8b8e6-113">Példa</span><span class="sxs-lookup"><span data-stu-id="8b8e6-113">Example</span></span>

<span data-ttu-id="8b8e6-114">A következő Q # kódrészlet véletlenszerűen görget egy hat oldalas Die:</span><span class="sxs-lookup"><span data-stu-id="8b8e6-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="8b8e6-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8b8e6-115">Remarks</span></span>

<span data-ttu-id="8b8e6-116">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="8b8e6-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b8e6-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8b8e6-117">See Also</span></span>

- [<span data-ttu-id="8b8e6-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="8b8e6-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)