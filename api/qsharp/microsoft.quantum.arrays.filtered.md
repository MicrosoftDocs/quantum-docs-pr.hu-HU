---
uid: Microsoft.Quantum.Arrays.Filtered
title: Szűrt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221266"
---
# <a name="filtered-function"></a><span data-ttu-id="f22d1-102">Szűrt függvény</span><span class="sxs-lookup"><span data-stu-id="f22d1-102">Filtered function</span></span>

<span data-ttu-id="f22d1-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f22d1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f22d1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f22d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f22d1-105">Egy tömb és egy, a tömb elemeihez definiált predikátum miatt egy tömböt ad vissza, amely a predikátumnak megfelelő elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="f22d1-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f22d1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f22d1-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f22d1-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f22d1-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f22d1-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="f22d1-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="f22d1-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="f22d1-109">array : 'T[]</span></span>

<span data-ttu-id="f22d1-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="f22d1-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="f22d1-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="f22d1-111">Output : 'T[]</span></span>

<span data-ttu-id="f22d1-112">`'T[]`A predikátumnak megfelelő elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="f22d1-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f22d1-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f22d1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f22d1-114">Nem</span><span class="sxs-lookup"><span data-stu-id="f22d1-114">'T</span></span>

<span data-ttu-id="f22d1-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="f22d1-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="f22d1-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f22d1-116">Remarks</span></span>

<span data-ttu-id="f22d1-117">A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="f22d1-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>