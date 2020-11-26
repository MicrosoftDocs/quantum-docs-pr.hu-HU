---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192944"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="1ea39-102">DrawRandomDouble művelet</span><span class="sxs-lookup"><span data-stu-id="1ea39-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="1ea39-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1ea39-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1ea39-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1ea39-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1ea39-105">Véletlenszerű valós számot rajzol egy adott befogadó intervallumban.</span><span class="sxs-lookup"><span data-stu-id="1ea39-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="1ea39-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1ea39-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="1ea39-107">minimum: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ea39-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1ea39-108">A rajzolni kívánt legkisebb valós szám.</span><span class="sxs-lookup"><span data-stu-id="1ea39-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="1ea39-109">Max: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ea39-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1ea39-110">A kirajzolni kívánt legnagyobb valós szám.</span><span class="sxs-lookup"><span data-stu-id="1ea39-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="1ea39-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ea39-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1ea39-112">Egy véletlenszerű valós szám a befogadó intervallumban `min` , `max` és egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="1ea39-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ea39-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1ea39-113">Remarks</span></span>

<span data-ttu-id="1ea39-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="1ea39-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ea39-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="1ea39-115">See Also</span></span>

- [<span data-ttu-id="1ea39-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="1ea39-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)