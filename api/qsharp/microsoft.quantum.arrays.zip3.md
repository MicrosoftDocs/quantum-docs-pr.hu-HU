---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718721"
---
# <a name="zip3-function"></a><span data-ttu-id="13bff-102">Zip3 függvény</span><span class="sxs-lookup"><span data-stu-id="13bff-102">Zip3 function</span></span>

<span data-ttu-id="13bff-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="13bff-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="13bff-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13bff-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="13bff-105">A Zip3 elavult.</span><span class="sxs-lookup"><span data-stu-id="13bff-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="13bff-106">Használja <xref:Microsoft.Quantum.Arrays.Zipped3> helyette.</span><span class="sxs-lookup"><span data-stu-id="13bff-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="13bff-107">A három tömb esetében a rekordok egy új tömböt ad vissza, amely szerint minden 3 rekord tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="13bff-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="13bff-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="13bff-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="13bff-109">első: nem 1 []</span><span class="sxs-lookup"><span data-stu-id="13bff-109">first : 'T1[]</span></span>

<span data-ttu-id="13bff-110">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="13bff-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="13bff-111">második: nem 2 []</span><span class="sxs-lookup"><span data-stu-id="13bff-111">second : 'T2[]</span></span>

<span data-ttu-id="13bff-112">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="13bff-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="13bff-113">harmadik: nem 3 []</span><span class="sxs-lookup"><span data-stu-id="13bff-113">third : 'T3[]</span></span>

<span data-ttu-id="13bff-114">Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="13bff-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="13bff-115">Kimenet: (nem 1, nem 2, nem 3) []</span><span class="sxs-lookup"><span data-stu-id="13bff-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="13bff-116">Az űrlap 3 – rekordok tartalmazó tömbje `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="13bff-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="13bff-117">Ha a három tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="13bff-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="13bff-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="13bff-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="13bff-119">Nem 1</span><span class="sxs-lookup"><span data-stu-id="13bff-119">'T1</span></span>

<span data-ttu-id="13bff-120">Az első tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="13bff-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="13bff-121">Nem 2</span><span class="sxs-lookup"><span data-stu-id="13bff-121">'T2</span></span>

<span data-ttu-id="13bff-122">A második tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="13bff-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="13bff-123">Nem 3</span><span class="sxs-lookup"><span data-stu-id="13bff-123">'T3</span></span>

<span data-ttu-id="13bff-124">A harmadik tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="13bff-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="13bff-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="13bff-125">See Also</span></span>

- [<span data-ttu-id="13bff-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="13bff-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="13bff-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="13bff-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)