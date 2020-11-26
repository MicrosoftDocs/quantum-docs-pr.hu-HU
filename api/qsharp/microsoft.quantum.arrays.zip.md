---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219855"
---
# <a name="zip-function"></a><span data-ttu-id="56a8d-102">Zip-függvény</span><span class="sxs-lookup"><span data-stu-id="56a8d-102">Zip function</span></span>

<span data-ttu-id="56a8d-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="56a8d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="56a8d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56a8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="56a8d-105">A zip elavult.</span><span class="sxs-lookup"><span data-stu-id="56a8d-105">Zip has been deprecated.</span></span> <span data-ttu-id="56a8d-106">Használja <xref:Microsoft.Quantum.Arrays.Zipped> helyette.</span><span class="sxs-lookup"><span data-stu-id="56a8d-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="56a8d-107">Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="56a8d-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="56a8d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="56a8d-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="56a8d-109">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="56a8d-109">left : 'T[]</span></span>

<span data-ttu-id="56a8d-110">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="56a8d-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="56a8d-111">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="56a8d-111">right : 'U[]</span></span>

<span data-ttu-id="56a8d-112">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="56a8d-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="56a8d-113">Kimenet: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="56a8d-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="56a8d-114">Egy tömb, amely az űrlaphoz tartozó párokat tartalmaz `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="56a8d-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="56a8d-115">Ha a két tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="56a8d-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="56a8d-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="56a8d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56a8d-117">Nem</span><span class="sxs-lookup"><span data-stu-id="56a8d-117">'T</span></span>

<span data-ttu-id="56a8d-118">A bal oldali tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="56a8d-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="56a8d-119">' U</span><span class="sxs-lookup"><span data-stu-id="56a8d-119">'U</span></span>

<span data-ttu-id="56a8d-120">A jobb oldali tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="56a8d-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="56a8d-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="56a8d-121">See Also</span></span>

- [<span data-ttu-id="56a8d-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="56a8d-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="56a8d-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="56a8d-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="56a8d-124">Microsoft. Quantum. Arrays. kibontva</span><span class="sxs-lookup"><span data-stu-id="56a8d-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)