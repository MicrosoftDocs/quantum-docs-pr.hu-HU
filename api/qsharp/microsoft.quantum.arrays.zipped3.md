---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842174"
---
# <a name="zipped3-function"></a><span data-ttu-id="efc24-102">Zipped3 függvény</span><span class="sxs-lookup"><span data-stu-id="efc24-102">Zipped3 function</span></span>

<span data-ttu-id="efc24-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="efc24-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="efc24-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="efc24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="efc24-105">A három tömb esetében a rekordok egy új tömböt ad vissza, amely szerint minden 3 rekord tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="efc24-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="efc24-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="efc24-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="efc24-107">első: nem 1 []</span><span class="sxs-lookup"><span data-stu-id="efc24-107">first : 'T1[]</span></span>

<span data-ttu-id="efc24-108">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="efc24-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="efc24-109">második: nem 2 []</span><span class="sxs-lookup"><span data-stu-id="efc24-109">second : 'T2[]</span></span>

<span data-ttu-id="efc24-110">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="efc24-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="efc24-111">harmadik: nem 3 []</span><span class="sxs-lookup"><span data-stu-id="efc24-111">third : 'T3[]</span></span>

<span data-ttu-id="efc24-112">Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="efc24-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="efc24-113">Kimenet: (nem 1, nem 2, nem 3) []</span><span class="sxs-lookup"><span data-stu-id="efc24-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="efc24-114">Az űrlap 3 – rekordok tartalmazó tömbje `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="efc24-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="efc24-115">Ha a három tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="efc24-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="efc24-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="efc24-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="efc24-117">Nem 1</span><span class="sxs-lookup"><span data-stu-id="efc24-117">'T1</span></span>

<span data-ttu-id="efc24-118">Az első tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="efc24-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="efc24-119">Nem 2</span><span class="sxs-lookup"><span data-stu-id="efc24-119">'T2</span></span>

<span data-ttu-id="efc24-120">A második tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="efc24-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="efc24-121">Nem 3</span><span class="sxs-lookup"><span data-stu-id="efc24-121">'T3</span></span>

<span data-ttu-id="efc24-122">A harmadik tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="efc24-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="efc24-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="efc24-123">See Also</span></span>

- [<span data-ttu-id="efc24-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="efc24-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="efc24-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="efc24-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)