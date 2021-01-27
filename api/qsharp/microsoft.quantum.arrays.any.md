---
uid: Microsoft.Quantum.Arrays.Any
title: Bármely függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846283"
---
# <a name="any-function"></a><span data-ttu-id="ab669-102">Bármely függvény</span><span class="sxs-lookup"><span data-stu-id="ab669-102">Any function</span></span>

<span data-ttu-id="ab669-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ab669-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ab669-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab669-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab669-105">A tömb elemeihez megadott tömb és predikátum alapján a rendszer ellenőrzi, hogy a tömb legalább egy eleme megfelel-e a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="ab669-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="ab669-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ab669-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ab669-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab669-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab669-108">Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.</span><span class="sxs-lookup"><span data-stu-id="ab669-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ab669-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="ab669-109">array : 'T[]</span></span>

<span data-ttu-id="ab669-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="ab669-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ab669-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab669-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab669-112">Az `Bool` összes elemre alkalmazott PREDIKÁTUM vagy függvényének értéke.</span><span class="sxs-lookup"><span data-stu-id="ab669-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ab669-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ab669-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab669-114">Nem</span><span class="sxs-lookup"><span data-stu-id="ab669-114">'T</span></span>

<span data-ttu-id="ab669-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="ab669-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="ab669-116">Példa</span><span class="sxs-lookup"><span data-stu-id="ab669-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="ab669-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ab669-117">Remarks</span></span>

<span data-ttu-id="ab669-118">A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy egyes elemek megfelelnek-e `predicate` .</span><span class="sxs-lookup"><span data-stu-id="ab669-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>