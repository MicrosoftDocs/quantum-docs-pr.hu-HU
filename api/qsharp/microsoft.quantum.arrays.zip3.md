---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219821"
---
# <a name="zip3-function"></a><span data-ttu-id="66e81-102">Zip3 függvény</span><span class="sxs-lookup"><span data-stu-id="66e81-102">Zip3 function</span></span>

<span data-ttu-id="66e81-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="66e81-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="66e81-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66e81-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="66e81-105">A Zip3 elavult.</span><span class="sxs-lookup"><span data-stu-id="66e81-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="66e81-106">Használja <xref:Microsoft.Quantum.Arrays.Zipped3> helyette.</span><span class="sxs-lookup"><span data-stu-id="66e81-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="66e81-107">A három tömb esetében a rekordok egy új tömböt ad vissza, amely szerint minden 3 rekord tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="66e81-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="66e81-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="66e81-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="66e81-109">első: nem 1 []</span><span class="sxs-lookup"><span data-stu-id="66e81-109">first : 'T1[]</span></span>

<span data-ttu-id="66e81-110">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="66e81-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="66e81-111">második: nem 2 []</span><span class="sxs-lookup"><span data-stu-id="66e81-111">second : 'T2[]</span></span>

<span data-ttu-id="66e81-112">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="66e81-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="66e81-113">harmadik: nem 3 []</span><span class="sxs-lookup"><span data-stu-id="66e81-113">third : 'T3[]</span></span>

<span data-ttu-id="66e81-114">Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="66e81-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="66e81-115">Kimenet: (nem 1, nem 2, nem 3) []</span><span class="sxs-lookup"><span data-stu-id="66e81-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="66e81-116">Az űrlap 3 – rekordok tartalmazó tömbje `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="66e81-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="66e81-117">Ha a három tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="66e81-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="66e81-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="66e81-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="66e81-119">Nem 1</span><span class="sxs-lookup"><span data-stu-id="66e81-119">'T1</span></span>

<span data-ttu-id="66e81-120">Az első tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="66e81-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="66e81-121">Nem 2</span><span class="sxs-lookup"><span data-stu-id="66e81-121">'T2</span></span>

<span data-ttu-id="66e81-122">A második tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="66e81-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="66e81-123">Nem 3</span><span class="sxs-lookup"><span data-stu-id="66e81-123">'T3</span></span>

<span data-ttu-id="66e81-124">A harmadik tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="66e81-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="66e81-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="66e81-125">See Also</span></span>

- [<span data-ttu-id="66e81-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="66e81-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="66e81-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="66e81-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)