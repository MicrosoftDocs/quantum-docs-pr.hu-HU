---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192910"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="a9c44-102">DrawRandomInt művelet</span><span class="sxs-lookup"><span data-stu-id="a9c44-102">DrawRandomInt operation</span></span>

<span data-ttu-id="a9c44-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a9c44-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a9c44-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a9c44-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a9c44-105">Egy véletlenszerű egész számot rajzol egy adott befogadó tartományban.</span><span class="sxs-lookup"><span data-stu-id="a9c44-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a9c44-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a9c44-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="a9c44-107">min.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9c44-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9c44-108">A rajzolni kívánt legkisebb egész szám.</span><span class="sxs-lookup"><span data-stu-id="a9c44-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="a9c44-109">Max.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9c44-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9c44-110">A kirajzolni kívánt legnagyobb egész szám.</span><span class="sxs-lookup"><span data-stu-id="a9c44-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="a9c44-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9c44-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9c44-112">Egy egész szám a befogadó tartományban a és a érték között, `min` `max` egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="a9c44-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9c44-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a9c44-113">Remarks</span></span>

<span data-ttu-id="a9c44-114">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="a9c44-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9c44-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a9c44-115">See Also</span></span>

- [<span data-ttu-id="a9c44-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="a9c44-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)