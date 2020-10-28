---
uid: Microsoft.Quantum.Arrays.Count
title: Függvény száma
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719404"
---
# <a name="count-function"></a><span data-ttu-id="8f4ad-102">Függvény száma</span><span class="sxs-lookup"><span data-stu-id="8f4ad-102">Count function</span></span>

<span data-ttu-id="8f4ad-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8f4ad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8f4ad-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f4ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f4ad-105">Egy tömb és egy olyan predikátum, amely a tömb elemeihez van meghatározva, az elemek számát adja vissza, amely a predikátumnak megfelelő elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="8f4ad-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="8f4ad-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8f4ad-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8f4ad-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f4ad-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f4ad-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="8f4ad-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="8f4ad-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="8f4ad-109">array : 'T[]</span></span>

<span data-ttu-id="8f4ad-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="8f4ad-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="8f4ad-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8f4ad-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8f4ad-112">Azon elemek száma, `array` amelyek megfelelnek a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="8f4ad-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8f4ad-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8f4ad-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f4ad-114">Nem</span><span class="sxs-lookup"><span data-stu-id="8f4ad-114">'T</span></span>

<span data-ttu-id="8f4ad-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="8f4ad-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f4ad-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8f4ad-116">Remarks</span></span>

<span data-ttu-id="8f4ad-117">A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="8f4ad-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>