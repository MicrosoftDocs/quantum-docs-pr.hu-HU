---
uid: Microsoft.Quantum.Arrays.All
title: Minden függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719477"
---
# <a name="all-function"></a><span data-ttu-id="a03cf-102">Minden függvény</span><span class="sxs-lookup"><span data-stu-id="a03cf-102">All function</span></span>

<span data-ttu-id="a03cf-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a03cf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a03cf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a03cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a03cf-105">Egy tömböt és egy predikátumot adott meg, amely a tömb elemeihez van meghatározva, és ellenőrzi, hogy a tömb összes eleme megfelel-e a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="a03cf-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="a03cf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a03cf-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="a03cf-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a03cf-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a03cf-108">Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.</span><span class="sxs-lookup"><span data-stu-id="a03cf-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="a03cf-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="a03cf-109">array : 'T[]</span></span>

<span data-ttu-id="a03cf-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="a03cf-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a03cf-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a03cf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a03cf-112">Az `Bool` összes elemre alkalmazott PREDIKÁTUM és függvényének értéke.</span><span class="sxs-lookup"><span data-stu-id="a03cf-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a03cf-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="a03cf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a03cf-114">Nem</span><span class="sxs-lookup"><span data-stu-id="a03cf-114">'T</span></span>

<span data-ttu-id="a03cf-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="a03cf-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="a03cf-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a03cf-116">Remarks</span></span>

<span data-ttu-id="a03cf-117">A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy az összes elem megfelel-e `predicate` .</span><span class="sxs-lookup"><span data-stu-id="a03cf-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>