---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209927"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="2c43d-102">MappedByIndex függvény</span><span class="sxs-lookup"><span data-stu-id="2c43d-102">MappedByIndex function</span></span>

<span data-ttu-id="2c43d-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2c43d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2c43d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c43d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c43d-105">Egy tömb és egy függvény, amely a tömb indexelt elemeihez van definiálva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="2c43d-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="2c43d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2c43d-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="2c43d-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), 't) – > U</span><span class="sxs-lookup"><span data-stu-id="2c43d-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="2c43d-108">A-ből származó függvény, `(Int, 'T)` `'U` amely az elemek és az indexek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="2c43d-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="2c43d-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="2c43d-109">array : 'T[]</span></span>

<span data-ttu-id="2c43d-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="2c43d-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="2c43d-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="2c43d-111">Output : 'U[]</span></span>

<span data-ttu-id="2c43d-112">`'U[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="2c43d-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2c43d-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2c43d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c43d-114">Nem</span><span class="sxs-lookup"><span data-stu-id="2c43d-114">'T</span></span>

<span data-ttu-id="2c43d-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="2c43d-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="2c43d-116">' U</span><span class="sxs-lookup"><span data-stu-id="2c43d-116">'U</span></span>

<span data-ttu-id="2c43d-117">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="2c43d-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c43d-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2c43d-118">See Also</span></span>

- [<span data-ttu-id="2c43d-119">Microsoft. Quantum. Arrays. leképezve</span><span class="sxs-lookup"><span data-stu-id="2c43d-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)