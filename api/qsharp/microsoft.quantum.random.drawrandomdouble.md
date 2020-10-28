---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723990"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="0d344-102">DrawRandomDouble művelet</span><span class="sxs-lookup"><span data-stu-id="0d344-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="0d344-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0d344-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0d344-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d344-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d344-105">Véletlenszerű valós számot rajzol egy adott befogadó intervallumban.</span><span class="sxs-lookup"><span data-stu-id="0d344-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="0d344-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0d344-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="0d344-107">minimum: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d344-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d344-108">A rajzolni kívánt legkisebb valós szám.</span><span class="sxs-lookup"><span data-stu-id="0d344-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="0d344-109">Max: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d344-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d344-110">A kirajzolni kívánt legnagyobb valós szám.</span><span class="sxs-lookup"><span data-stu-id="0d344-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="0d344-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d344-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d344-112">Egy véletlenszerű valós szám a befogadó intervallumban `min` , `max` és egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="0d344-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d344-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0d344-113">Remarks</span></span>

<span data-ttu-id="0d344-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="0d344-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d344-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0d344-115">See Also</span></span>

- [<span data-ttu-id="0d344-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="0d344-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)