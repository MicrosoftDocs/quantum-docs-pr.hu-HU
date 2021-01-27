---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847625"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="0acce-102">DrawRandomDouble művelet</span><span class="sxs-lookup"><span data-stu-id="0acce-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="0acce-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0acce-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0acce-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0acce-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0acce-105">Véletlenszerű valós számot rajzol egy adott befogadó intervallumban.</span><span class="sxs-lookup"><span data-stu-id="0acce-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="0acce-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0acce-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="0acce-107">minimum: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0acce-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0acce-108">A rajzolni kívánt legkisebb valós szám.</span><span class="sxs-lookup"><span data-stu-id="0acce-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="0acce-109">Max: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0acce-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0acce-110">A kirajzolni kívánt legnagyobb valós szám.</span><span class="sxs-lookup"><span data-stu-id="0acce-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="0acce-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0acce-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0acce-112">Egy véletlenszerű valós szám a befogadó intervallumban `min` , `max` és egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="0acce-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="0acce-113">Példa</span><span class="sxs-lookup"><span data-stu-id="0acce-113">Example</span></span>

<span data-ttu-id="0acce-114">A következő Q # kódrészlet véletlenszerűen rajzolja meg a $0 $ és a $2 \pi $ közötti szöget:</span><span class="sxs-lookup"><span data-stu-id="0acce-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="0acce-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0acce-115">Remarks</span></span>

<span data-ttu-id="0acce-116">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="0acce-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0acce-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0acce-117">See Also</span></span>

- [<span data-ttu-id="0acce-118">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="0acce-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)