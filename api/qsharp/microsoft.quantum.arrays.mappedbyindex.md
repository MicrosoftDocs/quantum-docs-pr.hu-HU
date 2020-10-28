---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719056"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="f946f-102">MappedByIndex függvény</span><span class="sxs-lookup"><span data-stu-id="f946f-102">MappedByIndex function</span></span>

<span data-ttu-id="f946f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f946f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f946f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f946f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f946f-105">Egy tömb és egy függvény, amely a tömb indexelt elemeihez van definiálva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="f946f-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="f946f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f946f-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="f946f-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), 't) – > U</span><span class="sxs-lookup"><span data-stu-id="f946f-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="f946f-108">A-ből származó függvény, `(Int, 'T)` `'U` amely az elemek és az indexek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="f946f-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="f946f-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="f946f-109">array : 'T[]</span></span>

<span data-ttu-id="f946f-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="f946f-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="f946f-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="f946f-111">Output : 'U[]</span></span>

<span data-ttu-id="f946f-112">`'U[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="f946f-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f946f-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f946f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f946f-114">Nem</span><span class="sxs-lookup"><span data-stu-id="f946f-114">'T</span></span>

<span data-ttu-id="f946f-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="f946f-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="f946f-116">' U</span><span class="sxs-lookup"><span data-stu-id="f946f-116">'U</span></span>

<span data-ttu-id="f946f-117">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="f946f-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="f946f-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f946f-118">See Also</span></span>

- [<span data-ttu-id="f946f-119">Microsoft. Quantum. Arrays. leképezve</span><span class="sxs-lookup"><span data-stu-id="f946f-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)