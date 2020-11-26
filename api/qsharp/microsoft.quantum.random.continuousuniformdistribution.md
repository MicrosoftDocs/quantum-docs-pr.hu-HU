---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193080"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="db9f8-102">ContinuousUniformDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="db9f8-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="db9f8-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="db9f8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="db9f8-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="db9f8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="db9f8-105">Egységes eloszlást ad vissza egy adott befogadó intervallumon belül.</span><span class="sxs-lookup"><span data-stu-id="db9f8-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="db9f8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="db9f8-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="db9f8-107">minimum: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db9f8-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db9f8-108">A rajzolni kívánt legkisebb valós szám.</span><span class="sxs-lookup"><span data-stu-id="db9f8-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="db9f8-109">Max: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db9f8-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db9f8-110">A kirajzolni kívánt legnagyobb valós szám.</span><span class="sxs-lookup"><span data-stu-id="db9f8-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="db9f8-111">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="db9f8-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="db9f8-112">Olyan eloszlás, amelynek véletlenszerű változói valós számok a és a közötti, `min` egységes valószínűséggel rendelkező, befogadó intervallumban `max` .</span><span class="sxs-lookup"><span data-stu-id="db9f8-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="db9f8-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="db9f8-113">Remarks</span></span>

<span data-ttu-id="db9f8-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="db9f8-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="db9f8-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="db9f8-115">See Also</span></span>

- [<span data-ttu-id="db9f8-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="db9f8-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)