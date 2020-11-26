---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 37fda4082a46870270414649f807659fa561962b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219685"
---
# <a name="zipped3-function"></a><span data-ttu-id="38576-102">Zipped3 függvény</span><span class="sxs-lookup"><span data-stu-id="38576-102">Zipped3 function</span></span>

<span data-ttu-id="38576-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="38576-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="38576-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38576-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38576-105">A három tömb esetében a rekordok egy új tömböt ad vissza, amely szerint minden 3 rekord tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="38576-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="38576-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="38576-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="38576-107">első: nem 1 []</span><span class="sxs-lookup"><span data-stu-id="38576-107">first : 'T1[]</span></span>

<span data-ttu-id="38576-108">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="38576-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="38576-109">második: nem 2 []</span><span class="sxs-lookup"><span data-stu-id="38576-109">second : 'T2[]</span></span>

<span data-ttu-id="38576-110">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="38576-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="38576-111">harmadik: nem 3 []</span><span class="sxs-lookup"><span data-stu-id="38576-111">third : 'T3[]</span></span>

<span data-ttu-id="38576-112">Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="38576-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="38576-113">Kimenet: (nem 1, nem 2, nem 3) []</span><span class="sxs-lookup"><span data-stu-id="38576-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="38576-114">Az űrlap 3 – rekordok tartalmazó tömbje `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="38576-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="38576-115">Ha a három tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="38576-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="38576-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="38576-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="38576-117">Nem 1</span><span class="sxs-lookup"><span data-stu-id="38576-117">'T1</span></span>

<span data-ttu-id="38576-118">Az első tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="38576-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="38576-119">Nem 2</span><span class="sxs-lookup"><span data-stu-id="38576-119">'T2</span></span>

<span data-ttu-id="38576-120">A második tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="38576-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="38576-121">Nem 3</span><span class="sxs-lookup"><span data-stu-id="38576-121">'T3</span></span>

<span data-ttu-id="38576-122">A harmadik tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="38576-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="38576-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="38576-123">See Also</span></span>

- [<span data-ttu-id="38576-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="38576-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="38576-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="38576-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)