---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850886"
---
# <a name="zip4-function"></a><span data-ttu-id="bfb69-102">Zip4 függvény</span><span class="sxs-lookup"><span data-stu-id="bfb69-102">Zip4 function</span></span>

<span data-ttu-id="bfb69-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bfb69-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bfb69-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bfb69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="bfb69-105">A Zip4 elavult.</span><span class="sxs-lookup"><span data-stu-id="bfb69-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="bfb69-106">Használja <xref:Microsoft.Quantum.Arrays.Zipped4> helyette.</span><span class="sxs-lookup"><span data-stu-id="bfb69-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="bfb69-107">A megadott négy tömb a 4 rekordok egy új tömbjét adja vissza, amely minden 4 rekord tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="bfb69-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="bfb69-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bfb69-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="bfb69-109">első: nem 1 []</span><span class="sxs-lookup"><span data-stu-id="bfb69-109">first : 'T1[]</span></span>

<span data-ttu-id="bfb69-110">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="bfb69-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="bfb69-111">második: nem 2 []</span><span class="sxs-lookup"><span data-stu-id="bfb69-111">second : 'T2[]</span></span>

<span data-ttu-id="bfb69-112">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="bfb69-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="bfb69-113">harmadik: nem 3 []</span><span class="sxs-lookup"><span data-stu-id="bfb69-113">third : 'T3[]</span></span>

<span data-ttu-id="bfb69-114">Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="bfb69-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="bfb69-115">negyedik: nem 4 []</span><span class="sxs-lookup"><span data-stu-id="bfb69-115">fourth : 'T4[]</span></span>

<span data-ttu-id="bfb69-116">Az egyes rekordokhoz tartozó negyedik elem értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="bfb69-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="bfb69-117">Kimenet: (nem 1, nem 2, nem 3, nem 4) []</span><span class="sxs-lookup"><span data-stu-id="bfb69-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="bfb69-118">Egy tömb, amely 4 – rekordok tartalmaz az űrlapokhoz `(first[idx], second[idx], third[idx], fourth[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="bfb69-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="bfb69-119">Ha a négy tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="bfb69-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bfb69-120">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bfb69-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="bfb69-121">Nem 1</span><span class="sxs-lookup"><span data-stu-id="bfb69-121">'T1</span></span>

<span data-ttu-id="bfb69-122">Az első tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="bfb69-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="bfb69-123">Nem 2</span><span class="sxs-lookup"><span data-stu-id="bfb69-123">'T2</span></span>

<span data-ttu-id="bfb69-124">A második tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="bfb69-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="bfb69-125">Nem 3</span><span class="sxs-lookup"><span data-stu-id="bfb69-125">'T3</span></span>

<span data-ttu-id="bfb69-126">A harmadik tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="bfb69-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="bfb69-127">Nem 4</span><span class="sxs-lookup"><span data-stu-id="bfb69-127">'T4</span></span>

<span data-ttu-id="bfb69-128">A negyedik tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="bfb69-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfb69-129">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bfb69-129">See Also</span></span>

- [<span data-ttu-id="bfb69-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="bfb69-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="bfb69-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="bfb69-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)