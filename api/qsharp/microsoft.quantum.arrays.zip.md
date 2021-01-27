---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip-függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850901"
---
# <a name="zip-function"></a><span data-ttu-id="0f9d8-102">Zip-függvény</span><span class="sxs-lookup"><span data-stu-id="0f9d8-102">Zip function</span></span>

<span data-ttu-id="0f9d8-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0f9d8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0f9d8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f9d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="0f9d8-105">A zip elavult.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-105">Zip has been deprecated.</span></span> <span data-ttu-id="0f9d8-106">Használja <xref:Microsoft.Quantum.Arrays.Zipped> helyette.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="0f9d8-107">Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="0f9d8-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0f9d8-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="0f9d8-109">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="0f9d8-109">left : 'T[]</span></span>

<span data-ttu-id="0f9d8-110">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="0f9d8-111">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="0f9d8-111">right : 'U[]</span></span>

<span data-ttu-id="0f9d8-112">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="0f9d8-113">Kimenet: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="0f9d8-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="0f9d8-114">Egy tömb, amely az űrlaphoz tartozó párokat tartalmaz `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="0f9d8-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="0f9d8-115">Ha a két tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f9d8-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="0f9d8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f9d8-117">Nem</span><span class="sxs-lookup"><span data-stu-id="0f9d8-117">'T</span></span>

<span data-ttu-id="0f9d8-118">A bal oldali tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="0f9d8-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="0f9d8-119">' U</span><span class="sxs-lookup"><span data-stu-id="0f9d8-119">'U</span></span>

<span data-ttu-id="0f9d8-120">A jobb oldali tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="0f9d8-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="0f9d8-121">Példa</span><span class="sxs-lookup"><span data-stu-id="0f9d8-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="0f9d8-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0f9d8-122">See Also</span></span>

- [<span data-ttu-id="0f9d8-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="0f9d8-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="0f9d8-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="0f9d8-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="0f9d8-125">Microsoft. Quantum. Arrays. kibontva</span><span class="sxs-lookup"><span data-stu-id="0f9d8-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)