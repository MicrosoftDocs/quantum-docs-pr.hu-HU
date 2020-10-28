---
uid: Microsoft.Quantum.Arrays.Zipped
title: Tömörített függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718709"
---
# <a name="zipped-function"></a><span data-ttu-id="203e2-102">Tömörített függvény</span><span class="sxs-lookup"><span data-stu-id="203e2-102">Zipped function</span></span>

<span data-ttu-id="203e2-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="203e2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="203e2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="203e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="203e2-105">Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.</span><span class="sxs-lookup"><span data-stu-id="203e2-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="203e2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="203e2-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="203e2-107">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="203e2-107">left : 'T[]</span></span>

<span data-ttu-id="203e2-108">Az egyes adatrekordok első elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="203e2-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="203e2-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="203e2-109">right : 'U[]</span></span>

<span data-ttu-id="203e2-110">A rekord második elemének értékeit tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="203e2-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="203e2-111">Kimenet: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="203e2-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="203e2-112">Egy tömb, amely az űrlaphoz tartozó párokat tartalmaz `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="203e2-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="203e2-113">Ha a két tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="203e2-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="203e2-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="203e2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="203e2-115">Nem</span><span class="sxs-lookup"><span data-stu-id="203e2-115">'T</span></span>

<span data-ttu-id="203e2-116">A bal oldali tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="203e2-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="203e2-117">' U</span><span class="sxs-lookup"><span data-stu-id="203e2-117">'U</span></span>

<span data-ttu-id="203e2-118">A jobb oldali tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="203e2-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="203e2-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="203e2-119">See Also</span></span>

- [<span data-ttu-id="203e2-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="203e2-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="203e2-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="203e2-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="203e2-122">Microsoft. Quantum. Arrays. kibontva</span><span class="sxs-lookup"><span data-stu-id="203e2-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)