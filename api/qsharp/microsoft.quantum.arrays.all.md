---
uid: Microsoft.Quantum.Arrays.All
title: Minden függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842903"
---
# <a name="all-function"></a><span data-ttu-id="348e7-102">Minden függvény</span><span class="sxs-lookup"><span data-stu-id="348e7-102">All function</span></span>

<span data-ttu-id="348e7-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="348e7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="348e7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="348e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="348e7-105">Egy tömböt és egy predikátumot adott meg, amely a tömb elemeihez van meghatározva, és ellenőrzi, hogy a tömb összes eleme megfelel-e a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="348e7-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="348e7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="348e7-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="348e7-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="348e7-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="348e7-108">Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.</span><span class="sxs-lookup"><span data-stu-id="348e7-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="348e7-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="348e7-109">array : 'T[]</span></span>

<span data-ttu-id="348e7-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="348e7-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="348e7-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="348e7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="348e7-112">Az `Bool` összes elemre alkalmazott PREDIKÁTUM és függvényének értéke.</span><span class="sxs-lookup"><span data-stu-id="348e7-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="348e7-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="348e7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="348e7-114">Nem</span><span class="sxs-lookup"><span data-stu-id="348e7-114">'T</span></span>

<span data-ttu-id="348e7-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="348e7-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="348e7-116">Példa</span><span class="sxs-lookup"><span data-stu-id="348e7-116">Example</span></span>

<span data-ttu-id="348e7-117">A következő kód ellenőrzi, hogy a tömb összes eleme nem nulla-e:</span><span class="sxs-lookup"><span data-stu-id="348e7-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="348e7-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="348e7-118">Remarks</span></span>

<span data-ttu-id="348e7-119">A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy az összes elem megfelel-e `predicate` .</span><span class="sxs-lookup"><span data-stu-id="348e7-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>