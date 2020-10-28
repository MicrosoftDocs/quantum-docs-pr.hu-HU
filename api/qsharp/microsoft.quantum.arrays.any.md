---
uid: Microsoft.Quantum.Arrays.Any
title: Bármely függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719476"
---
# <a name="any-function"></a><span data-ttu-id="bce93-102">Bármely függvény</span><span class="sxs-lookup"><span data-stu-id="bce93-102">Any function</span></span>

<span data-ttu-id="bce93-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bce93-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bce93-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bce93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bce93-105">A tömb elemeihez megadott tömb és predikátum alapján a rendszer ellenőrzi, hogy a tömb legalább egy eleme megfelel-e a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="bce93-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="bce93-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bce93-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="bce93-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bce93-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bce93-108">Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.</span><span class="sxs-lookup"><span data-stu-id="bce93-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="bce93-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="bce93-109">array : 'T[]</span></span>

<span data-ttu-id="bce93-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="bce93-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bce93-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bce93-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bce93-112">Az `Bool` összes elemre alkalmazott PREDIKÁTUM vagy függvényének értéke.</span><span class="sxs-lookup"><span data-stu-id="bce93-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bce93-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bce93-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bce93-114">Nem</span><span class="sxs-lookup"><span data-stu-id="bce93-114">'T</span></span>

<span data-ttu-id="bce93-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="bce93-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="bce93-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bce93-116">Remarks</span></span>

<span data-ttu-id="bce93-117">A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy egyes elemek megfelelnek-e `predicate` .</span><span class="sxs-lookup"><span data-stu-id="bce93-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>