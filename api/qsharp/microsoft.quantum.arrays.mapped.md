---
uid: Microsoft.Quantum.Arrays.Mapped
title: Leképezett függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220739"
---
# <a name="mapped-function"></a><span data-ttu-id="c3d27-102">Leképezett függvény</span><span class="sxs-lookup"><span data-stu-id="c3d27-102">Mapped function</span></span>

<span data-ttu-id="c3d27-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3d27-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3d27-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3d27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3d27-105">Egy tömb és egy függvény, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="c3d27-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c3d27-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c3d27-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="c3d27-107">Mapper: nem > U</span><span class="sxs-lookup"><span data-stu-id="c3d27-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="c3d27-108">Az `'T` `'U` elemekhez tartozó függvény, amely az elemek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="c3d27-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c3d27-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="c3d27-109">array : 'T[]</span></span>

<span data-ttu-id="c3d27-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="c3d27-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c3d27-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="c3d27-111">Output : 'U[]</span></span>

<span data-ttu-id="c3d27-112">`'U[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="c3d27-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3d27-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c3d27-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3d27-114">Nem</span><span class="sxs-lookup"><span data-stu-id="c3d27-114">'T</span></span>

<span data-ttu-id="c3d27-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="c3d27-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c3d27-116">' U</span><span class="sxs-lookup"><span data-stu-id="c3d27-116">'U</span></span>

<span data-ttu-id="c3d27-117">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="c3d27-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3d27-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c3d27-118">Remarks</span></span>

<span data-ttu-id="c3d27-119">A függvény általános típusokhoz van definiálva, azaz a tömb `'T[]` `mapper: 'T -> 'U` elemeinek leképezhetők, és egy új típusú tömb is létrehozható `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="c3d27-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>