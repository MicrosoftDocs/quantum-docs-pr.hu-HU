---
uid: Microsoft.Quantum.Arrays.Count
title: Függvény száma
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842838"
---
# <a name="count-function"></a><span data-ttu-id="e92b1-102">Függvény száma</span><span class="sxs-lookup"><span data-stu-id="e92b1-102">Count function</span></span>

<span data-ttu-id="e92b1-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e92b1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e92b1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e92b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e92b1-105">Egy tömb és egy olyan predikátum, amely a tömb elemeihez van meghatározva, az elemek számát adja vissza, amely a predikátumnak megfelelő elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e92b1-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="e92b1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e92b1-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="e92b1-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e92b1-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e92b1-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="e92b1-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="e92b1-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="e92b1-109">array : 'T[]</span></span>

<span data-ttu-id="e92b1-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="e92b1-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e92b1-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e92b1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e92b1-112">Azon elemek száma, `array` amelyek megfelelnek a predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="e92b1-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e92b1-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e92b1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e92b1-114">Nem</span><span class="sxs-lookup"><span data-stu-id="e92b1-114">'T</span></span>

<span data-ttu-id="e92b1-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="e92b1-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="e92b1-116">Példa</span><span class="sxs-lookup"><span data-stu-id="e92b1-116">Example</span></span>

<span data-ttu-id="e92b1-117">A következő kód a "Count" függvényt mutatja be.</span><span class="sxs-lookup"><span data-stu-id="e92b1-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="e92b1-118">A predikátum a függvény használatával van definiálva @"microsoft.quantum.logical.greaterthani" :</span><span class="sxs-lookup"><span data-stu-id="e92b1-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="e92b1-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e92b1-119">Remarks</span></span>

<span data-ttu-id="e92b1-120">A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="e92b1-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>