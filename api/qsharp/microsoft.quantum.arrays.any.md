---
uid: Microsoft.Quantum.Arrays.Any
title: Bármely függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221657"
---
# <a name="any-function"></a><span data-ttu-id="fe848-102">Bármely függvény</span><span class="sxs-lookup"><span data-stu-id="fe848-102">Any function</span></span>

<span data-ttu-id="fe848-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe848-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe848-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe848-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe848-105">A tömb elemeihez megadott tömb és predikátum alapján a rendszer ellenőrzi, hogy a tömb legalább egy eleme megfelel-e a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="fe848-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="fe848-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fe848-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="fe848-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe848-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe848-108">Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.</span><span class="sxs-lookup"><span data-stu-id="fe848-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="fe848-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="fe848-109">array : 'T[]</span></span>

<span data-ttu-id="fe848-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="fe848-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe848-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe848-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe848-112">Az `Bool` összes elemre alkalmazott PREDIKÁTUM vagy függvényének értéke.</span><span class="sxs-lookup"><span data-stu-id="fe848-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe848-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="fe848-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe848-114">Nem</span><span class="sxs-lookup"><span data-stu-id="fe848-114">'T</span></span>

<span data-ttu-id="fe848-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="fe848-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe848-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fe848-116">Remarks</span></span>

<span data-ttu-id="fe848-117">A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy egyes elemek megfelelnek-e `predicate` .</span><span class="sxs-lookup"><span data-stu-id="fe848-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>