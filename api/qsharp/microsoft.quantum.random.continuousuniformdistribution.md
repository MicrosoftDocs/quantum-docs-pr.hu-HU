---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709427"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="ae79c-102">ContinuousUniformDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="ae79c-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="ae79c-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ae79c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ae79c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae79c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae79c-105">Egységes eloszlást ad vissza egy adott befogadó intervallumon belül.</span><span class="sxs-lookup"><span data-stu-id="ae79c-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="ae79c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ae79c-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="ae79c-107">minimum: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae79c-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae79c-108">A rajzolni kívánt legkisebb valós szám.</span><span class="sxs-lookup"><span data-stu-id="ae79c-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="ae79c-109">Max: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae79c-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae79c-110">A kirajzolni kívánt legnagyobb valós szám.</span><span class="sxs-lookup"><span data-stu-id="ae79c-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="ae79c-111">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ae79c-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ae79c-112">Olyan eloszlás, amelynek véletlenszerű változói valós számok a és a közötti, `min` egységes valószínűséggel rendelkező, befogadó intervallumban `max` .</span><span class="sxs-lookup"><span data-stu-id="ae79c-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae79c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ae79c-113">Remarks</span></span>

<span data-ttu-id="ae79c-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="ae79c-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae79c-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ae79c-115">See Also</span></span>

- [<span data-ttu-id="ae79c-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="ae79c-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)