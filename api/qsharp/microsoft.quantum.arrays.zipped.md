---
uid: Microsoft.Quantum.Arrays.Zipped
title: Tömörített függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219753"
---
# <a name="zipped-function"></a><span data-ttu-id="9bca7-102">Tömörített függvény</span><span class="sxs-lookup"><span data-stu-id="9bca7-102">Zipped function</span></span>

<span data-ttu-id="9bca7-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9bca7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9bca7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9bca7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9bca7-105">Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="9bca7-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="9bca7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9bca7-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="9bca7-107">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="9bca7-107">left : 'T[]</span></span>

<span data-ttu-id="9bca7-108">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="9bca7-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="9bca7-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="9bca7-109">right : 'U[]</span></span>

<span data-ttu-id="9bca7-110">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="9bca7-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="9bca7-111">Kimenet: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="9bca7-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="9bca7-112">Egy tömb, amely az űrlaphoz tartozó párokat tartalmaz `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="9bca7-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="9bca7-113">Ha a két tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="9bca7-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9bca7-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9bca7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9bca7-115">Nem</span><span class="sxs-lookup"><span data-stu-id="9bca7-115">'T</span></span>

<span data-ttu-id="9bca7-116">A bal oldali tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="9bca7-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="9bca7-117">' U</span><span class="sxs-lookup"><span data-stu-id="9bca7-117">'U</span></span>

<span data-ttu-id="9bca7-118">A jobb oldali tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="9bca7-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bca7-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9bca7-119">See Also</span></span>

- [<span data-ttu-id="9bca7-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="9bca7-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="9bca7-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="9bca7-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="9bca7-122">Microsoft. Quantum. Arrays. kibontva</span><span class="sxs-lookup"><span data-stu-id="9bca7-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)