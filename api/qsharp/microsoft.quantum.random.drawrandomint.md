---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724662"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="cd500-102">DrawRandomInt művelet</span><span class="sxs-lookup"><span data-stu-id="cd500-102">DrawRandomInt operation</span></span>

<span data-ttu-id="cd500-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cd500-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cd500-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd500-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd500-105">Egy véletlenszerű egész számot rajzol egy adott befogadó tartományban.</span><span class="sxs-lookup"><span data-stu-id="cd500-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="cd500-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cd500-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="cd500-107">min.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd500-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd500-108">A rajzolni kívánt legkisebb egész szám.</span><span class="sxs-lookup"><span data-stu-id="cd500-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="cd500-109">Max.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd500-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd500-110">A kirajzolni kívánt legnagyobb egész szám.</span><span class="sxs-lookup"><span data-stu-id="cd500-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="cd500-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd500-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd500-112">Egy egész szám a befogadó tartományban a és a érték között, `min` `max` egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="cd500-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd500-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cd500-113">Remarks</span></span>

<span data-ttu-id="cd500-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="cd500-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd500-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="cd500-115">See Also</span></span>

- [<span data-ttu-id="cd500-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="cd500-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)