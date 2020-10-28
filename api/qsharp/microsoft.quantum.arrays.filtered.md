---
uid: Microsoft.Quantum.Arrays.Filtered
title: Szűrt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719272"
---
# <a name="filtered-function"></a><span data-ttu-id="d0a5f-102">Szűrt függvény</span><span class="sxs-lookup"><span data-stu-id="d0a5f-102">Filtered function</span></span>

<span data-ttu-id="d0a5f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0a5f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0a5f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0a5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0a5f-105">Egy tömb és egy, a tömb elemeihez definiált predikátum miatt egy tömböt ad vissza, amely a predikátumnak megfelelő elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="d0a5f-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d0a5f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d0a5f-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="d0a5f-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0a5f-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d0a5f-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="d0a5f-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="d0a5f-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="d0a5f-109">array : 'T[]</span></span>

<span data-ttu-id="d0a5f-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="d0a5f-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="d0a5f-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="d0a5f-111">Output : 'T[]</span></span>

<span data-ttu-id="d0a5f-112">`'T[]`A predikátumnak megfelelő elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="d0a5f-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0a5f-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d0a5f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0a5f-114">Nem</span><span class="sxs-lookup"><span data-stu-id="d0a5f-114">'T</span></span>

<span data-ttu-id="d0a5f-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="d0a5f-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0a5f-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d0a5f-116">Remarks</span></span>

<span data-ttu-id="d0a5f-117">A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="d0a5f-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>