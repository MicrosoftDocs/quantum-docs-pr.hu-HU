---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845664"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="dc78c-102">MappedByIndex függvény</span><span class="sxs-lookup"><span data-stu-id="dc78c-102">MappedByIndex function</span></span>

<span data-ttu-id="dc78c-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dc78c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dc78c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc78c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc78c-105">Egy tömb és egy függvény, amely a tömb indexelt elemeihez van definiálva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="dc78c-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="dc78c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dc78c-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="dc78c-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), 't) – > U</span><span class="sxs-lookup"><span data-stu-id="dc78c-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="dc78c-108">A-ből származó függvény, `(Int, 'T)` `'U` amely az elemek és az indexek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="dc78c-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="dc78c-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="dc78c-109">array : 'T[]</span></span>

<span data-ttu-id="dc78c-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="dc78c-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="dc78c-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="dc78c-111">Output : 'U[]</span></span>

<span data-ttu-id="dc78c-112">`'U[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="dc78c-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dc78c-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dc78c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc78c-114">Nem</span><span class="sxs-lookup"><span data-stu-id="dc78c-114">'T</span></span>

<span data-ttu-id="dc78c-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="dc78c-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="dc78c-116">' U</span><span class="sxs-lookup"><span data-stu-id="dc78c-116">'U</span></span>

<span data-ttu-id="dc78c-117">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="dc78c-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="dc78c-118">Példa</span><span class="sxs-lookup"><span data-stu-id="dc78c-118">Example</span></span>

<span data-ttu-id="dc78c-119">A következő két sor egyenértékű:</span><span class="sxs-lookup"><span data-stu-id="dc78c-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="dc78c-120">és</span><span class="sxs-lookup"><span data-stu-id="dc78c-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="dc78c-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="dc78c-121">See Also</span></span>

- [<span data-ttu-id="dc78c-122">Microsoft. Quantum. Arrays. leképezve</span><span class="sxs-lookup"><span data-stu-id="dc78c-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)