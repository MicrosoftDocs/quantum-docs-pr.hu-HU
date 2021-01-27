---
uid: Microsoft.Quantum.Arrays.Mapped
title: Leképezett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845677"
---
# <a name="mapped-function"></a><span data-ttu-id="48fa3-102">Leképezett függvény</span><span class="sxs-lookup"><span data-stu-id="48fa3-102">Mapped function</span></span>

<span data-ttu-id="48fa3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="48fa3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="48fa3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48fa3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48fa3-105">Egy tömb és egy függvény, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="48fa3-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="48fa3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="48fa3-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="48fa3-107">Mapper: nem > U</span><span class="sxs-lookup"><span data-stu-id="48fa3-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="48fa3-108">Az `'T` `'U` elemekhez tartozó függvény, amely az elemek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="48fa3-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="48fa3-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="48fa3-109">array : 'T[]</span></span>

<span data-ttu-id="48fa3-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="48fa3-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="48fa3-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="48fa3-111">Output : 'U[]</span></span>

<span data-ttu-id="48fa3-112">`'U[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="48fa3-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48fa3-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="48fa3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48fa3-114">Nem</span><span class="sxs-lookup"><span data-stu-id="48fa3-114">'T</span></span>

<span data-ttu-id="48fa3-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="48fa3-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="48fa3-116">' U</span><span class="sxs-lookup"><span data-stu-id="48fa3-116">'U</span></span>

<span data-ttu-id="48fa3-117">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="48fa3-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="48fa3-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="48fa3-118">Remarks</span></span>

<span data-ttu-id="48fa3-119">A függvény általános típusokhoz van definiálva, azaz a tömb `'T[]` `mapper: 'T -> 'U` elemeinek leképezhetők, és egy új típusú tömb is létrehozható `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="48fa3-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>