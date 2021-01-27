---
uid: Microsoft.Quantum.Arrays.Filtered
title: Szűrt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847164"
---
# <a name="filtered-function"></a><span data-ttu-id="656aa-102">Szűrt függvény</span><span class="sxs-lookup"><span data-stu-id="656aa-102">Filtered function</span></span>

<span data-ttu-id="656aa-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="656aa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="656aa-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="656aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="656aa-105">Egy tömb és egy, a tömb elemeihez definiált predikátum miatt egy tömböt ad vissza, amely a predikátumnak megfelelő elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="656aa-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="656aa-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="656aa-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="656aa-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="656aa-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="656aa-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="656aa-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="656aa-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="656aa-109">array : 'T[]</span></span>

<span data-ttu-id="656aa-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="656aa-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="656aa-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="656aa-111">Output : 'T[]</span></span>

<span data-ttu-id="656aa-112">`'T[]`A predikátumnak megfelelő elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="656aa-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="656aa-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="656aa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="656aa-114">Nem</span><span class="sxs-lookup"><span data-stu-id="656aa-114">'T</span></span>

<span data-ttu-id="656aa-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="656aa-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="656aa-116">Példa</span><span class="sxs-lookup"><span data-stu-id="656aa-116">Example</span></span>

<span data-ttu-id="656aa-117">A következő kód a "szűrt" függvényt mutatja be.</span><span class="sxs-lookup"><span data-stu-id="656aa-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="656aa-118">A predikátum a függvény használatával van definiálva @"microsoft.quantum.logical.greaterthani" :</span><span class="sxs-lookup"><span data-stu-id="656aa-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="656aa-119">Ennek a példának a várt eredménye egy 5-nél nagyobb számok tömbje lesz.</span><span class="sxs-lookup"><span data-stu-id="656aa-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="656aa-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="656aa-120">Remarks</span></span>

<span data-ttu-id="656aa-121">A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="656aa-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>