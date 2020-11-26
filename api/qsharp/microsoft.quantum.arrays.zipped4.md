---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219634"
---
# <a name="zipped4-function"></a><span data-ttu-id="55d19-102">Zipped4 függvény</span><span class="sxs-lookup"><span data-stu-id="55d19-102">Zipped4 function</span></span>

<span data-ttu-id="55d19-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="55d19-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="55d19-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55d19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55d19-105">A megadott négy tömb a 4 rekordok egy új tömbjét adja vissza, amely minden 4 rekord tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="55d19-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="55d19-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="55d19-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="55d19-107">első: nem 1 []</span><span class="sxs-lookup"><span data-stu-id="55d19-107">first : 'T1[]</span></span>

<span data-ttu-id="55d19-108">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="55d19-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="55d19-109">második: nem 2 []</span><span class="sxs-lookup"><span data-stu-id="55d19-109">second : 'T2[]</span></span>

<span data-ttu-id="55d19-110">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="55d19-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="55d19-111">harmadik: nem 3 []</span><span class="sxs-lookup"><span data-stu-id="55d19-111">third : 'T3[]</span></span>

<span data-ttu-id="55d19-112">Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="55d19-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="55d19-113">negyedik: nem 4 []</span><span class="sxs-lookup"><span data-stu-id="55d19-113">fourth : 'T4[]</span></span>

<span data-ttu-id="55d19-114">Az egyes rekordokhoz tartozó negyedik elem értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="55d19-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="55d19-115">Kimenet: (nem 1, nem 2, nem 3, nem 4) []</span><span class="sxs-lookup"><span data-stu-id="55d19-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="55d19-116">Egy tömb, amely 4 – rekordok tartalmaz az űrlapokhoz `(first[idx], second[idx], third[idx], fourth[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="55d19-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="55d19-117">Ha a négy tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="55d19-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="55d19-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="55d19-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="55d19-119">Nem 1</span><span class="sxs-lookup"><span data-stu-id="55d19-119">'T1</span></span>

<span data-ttu-id="55d19-120">Az első tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="55d19-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="55d19-121">Nem 2</span><span class="sxs-lookup"><span data-stu-id="55d19-121">'T2</span></span>

<span data-ttu-id="55d19-122">A második tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="55d19-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="55d19-123">Nem 3</span><span class="sxs-lookup"><span data-stu-id="55d19-123">'T3</span></span>

<span data-ttu-id="55d19-124">A harmadik tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="55d19-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="55d19-125">Nem 4</span><span class="sxs-lookup"><span data-stu-id="55d19-125">'T4</span></span>

<span data-ttu-id="55d19-126">A negyedik tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="55d19-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="55d19-127">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="55d19-127">See Also</span></span>

- [<span data-ttu-id="55d19-128">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="55d19-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="55d19-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="55d19-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)