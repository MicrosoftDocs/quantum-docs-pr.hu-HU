---
uid: Microsoft.Quantum.Arrays.All
title: Minden függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: a7c83e38c3c101b712215eb664486fe29863a52b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221691"
---
# <a name="all-function"></a><span data-ttu-id="6179e-102">Minden függvény</span><span class="sxs-lookup"><span data-stu-id="6179e-102">All function</span></span>

<span data-ttu-id="6179e-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6179e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6179e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6179e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6179e-105">Egy tömböt és egy predikátumot adott meg, amely a tömb elemeihez van meghatározva, és ellenőrzi, hogy a tömb összes eleme megfelel-e a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="6179e-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="6179e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6179e-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="6179e-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6179e-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6179e-108">Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.</span><span class="sxs-lookup"><span data-stu-id="6179e-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="6179e-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="6179e-109">array : 'T[]</span></span>

<span data-ttu-id="6179e-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="6179e-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6179e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6179e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6179e-112">Az `Bool` összes elemre alkalmazott PREDIKÁTUM és függvényének értéke.</span><span class="sxs-lookup"><span data-stu-id="6179e-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6179e-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6179e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6179e-114">Nem</span><span class="sxs-lookup"><span data-stu-id="6179e-114">'T</span></span>

<span data-ttu-id="6179e-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="6179e-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="6179e-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6179e-116">Remarks</span></span>

<span data-ttu-id="6179e-117">A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy az összes elem megfelel-e `predicate` .</span><span class="sxs-lookup"><span data-stu-id="6179e-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>