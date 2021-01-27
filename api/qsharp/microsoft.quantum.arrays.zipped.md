---
uid: Microsoft.Quantum.Arrays.Zipped
title: Tömörített függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845338"
---
# <a name="zipped-function"></a><span data-ttu-id="e00e3-102">Tömörített függvény</span><span class="sxs-lookup"><span data-stu-id="e00e3-102">Zipped function</span></span>

<span data-ttu-id="e00e3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e00e3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e00e3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e00e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e00e3-105">Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="e00e3-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="e00e3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e00e3-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="e00e3-107">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="e00e3-107">left : 'T[]</span></span>

<span data-ttu-id="e00e3-108">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="e00e3-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="e00e3-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="e00e3-109">right : 'U[]</span></span>

<span data-ttu-id="e00e3-110">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="e00e3-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="e00e3-111">Kimenet: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="e00e3-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="e00e3-112">Egy tömb, amely az űrlaphoz tartozó párokat tartalmaz `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="e00e3-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="e00e3-113">Ha a két tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="e00e3-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e00e3-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e00e3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e00e3-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e00e3-115">'T</span></span>

<span data-ttu-id="e00e3-116">A bal oldali tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="e00e3-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="e00e3-117">' U</span><span class="sxs-lookup"><span data-stu-id="e00e3-117">'U</span></span>

<span data-ttu-id="e00e3-118">A jobb oldali tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="e00e3-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="e00e3-119">Példa</span><span class="sxs-lookup"><span data-stu-id="e00e3-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="e00e3-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e00e3-120">See Also</span></span>

- [<span data-ttu-id="e00e3-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="e00e3-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="e00e3-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="e00e3-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="e00e3-123">Microsoft. Quantum. Arrays. kibontva</span><span class="sxs-lookup"><span data-stu-id="e00e3-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)