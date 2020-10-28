---
uid: Microsoft.Quantum.Arrays.Mapped
title: Leképezett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719080"
---
# <a name="mapped-function"></a><span data-ttu-id="5d709-102">Leképezett függvény</span><span class="sxs-lookup"><span data-stu-id="5d709-102">Mapped function</span></span>

<span data-ttu-id="5d709-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5d709-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5d709-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d709-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d709-105">Egy tömb és egy függvény, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="5d709-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="5d709-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5d709-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="5d709-107">Mapper: nem > U</span><span class="sxs-lookup"><span data-stu-id="5d709-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="5d709-108">Az `'T` `'U` elemekhez tartozó függvény, amely az elemek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="5d709-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="5d709-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="5d709-109">array : 'T[]</span></span>

<span data-ttu-id="5d709-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="5d709-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="5d709-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="5d709-111">Output : 'U[]</span></span>

<span data-ttu-id="5d709-112">`'U[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="5d709-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d709-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="5d709-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d709-114">Nem</span><span class="sxs-lookup"><span data-stu-id="5d709-114">'T</span></span>

<span data-ttu-id="5d709-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="5d709-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="5d709-116">' U</span><span class="sxs-lookup"><span data-stu-id="5d709-116">'U</span></span>

<span data-ttu-id="5d709-117">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="5d709-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d709-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5d709-118">Remarks</span></span>

<span data-ttu-id="5d709-119">A függvény általános típusokhoz van definiálva, azaz a tömb `'T[]` `mapper: 'T -> 'U` elemeinek leképezhetők, és egy új típusú tömb is létrehozható `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="5d709-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>