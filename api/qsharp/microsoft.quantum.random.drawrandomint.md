---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851141"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="fc0e5-102">DrawRandomInt művelet</span><span class="sxs-lookup"><span data-stu-id="fc0e5-102">DrawRandomInt operation</span></span>

<span data-ttu-id="fc0e5-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="fc0e5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="fc0e5-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fc0e5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fc0e5-105">Egy véletlenszerű egész számot rajzol egy adott befogadó tartományban.</span><span class="sxs-lookup"><span data-stu-id="fc0e5-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="fc0e5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fc0e5-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="fc0e5-107">min.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc0e5-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc0e5-108">A rajzolni kívánt legkisebb egész szám.</span><span class="sxs-lookup"><span data-stu-id="fc0e5-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="fc0e5-109">Max.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc0e5-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc0e5-110">A kirajzolni kívánt legnagyobb egész szám.</span><span class="sxs-lookup"><span data-stu-id="fc0e5-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="fc0e5-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc0e5-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc0e5-112">Egy egész szám a befogadó tartományban a és a érték között, `min` `max` egységes valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="fc0e5-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="fc0e5-113">Példa</span><span class="sxs-lookup"><span data-stu-id="fc0e5-113">Example</span></span>

<span data-ttu-id="fc0e5-114">A következő Q # kódrészlet véletlenszerűen görget egy hat oldalas Die:</span><span class="sxs-lookup"><span data-stu-id="fc0e5-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="fc0e5-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fc0e5-115">Remarks</span></span>

<span data-ttu-id="fc0e5-116">Sikertelen, ha `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="fc0e5-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc0e5-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fc0e5-117">See Also</span></span>

- [<span data-ttu-id="fc0e5-118">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="fc0e5-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)