---
uid: Microsoft.Quantum.Arrays.Count
title: Függvény száma
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221555"
---
# <a name="count-function"></a><span data-ttu-id="5dfae-102">Függvény száma</span><span class="sxs-lookup"><span data-stu-id="5dfae-102">Count function</span></span>

<span data-ttu-id="5dfae-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5dfae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5dfae-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5dfae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5dfae-105">Egy tömb és egy olyan predikátum, amely a tömb elemeihez van meghatározva, az elemek számát adja vissza, amely a predikátumnak megfelelő elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="5dfae-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="5dfae-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5dfae-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="5dfae-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5dfae-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5dfae-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="5dfae-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="5dfae-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="5dfae-109">array : 'T[]</span></span>

<span data-ttu-id="5dfae-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="5dfae-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="5dfae-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dfae-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dfae-112">Azon elemek száma, `array` amelyek megfelelnek a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="5dfae-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5dfae-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="5dfae-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5dfae-114">Nem</span><span class="sxs-lookup"><span data-stu-id="5dfae-114">'T</span></span>

<span data-ttu-id="5dfae-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="5dfae-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dfae-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5dfae-116">Remarks</span></span>

<span data-ttu-id="5dfae-117">A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="5dfae-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>