---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842319"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="c54ec-102">ContinuousUniformDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="c54ec-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="c54ec-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c54ec-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c54ec-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c54ec-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c54ec-105">Egységes eloszlást ad vissza egy adott befogadó intervallumon belül.</span><span class="sxs-lookup"><span data-stu-id="c54ec-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="c54ec-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c54ec-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="c54ec-107">minimum: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c54ec-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c54ec-108">A rajzolni kívánt legkisebb valós szám.</span><span class="sxs-lookup"><span data-stu-id="c54ec-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="c54ec-109">Max: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c54ec-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c54ec-110">A kirajzolni kívánt legnagyobb valós szám.</span><span class="sxs-lookup"><span data-stu-id="c54ec-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="c54ec-111">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="c54ec-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="c54ec-112">Olyan eloszlás, amelynek véletlenszerű változói valós számok a és a közötti, `min` egységes valószínűséggel rendelkező, befogadó intervallumban `max` .</span><span class="sxs-lookup"><span data-stu-id="c54ec-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="c54ec-113">Példa</span><span class="sxs-lookup"><span data-stu-id="c54ec-113">Example</span></span>

<span data-ttu-id="c54ec-114">A következő Q # kódrészlet véletlenszerűen rajzolja meg a $0 $ és a $2 \pi $ közötti szöget:</span><span class="sxs-lookup"><span data-stu-id="c54ec-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="c54ec-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c54ec-115">Remarks</span></span>

<span data-ttu-id="c54ec-116">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c54ec-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c54ec-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c54ec-117">See Also</span></span>

- [<span data-ttu-id="c54ec-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c54ec-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)