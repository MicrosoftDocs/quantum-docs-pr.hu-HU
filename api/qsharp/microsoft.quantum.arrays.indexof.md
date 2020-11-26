---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221011"
---
# <a name="indexof-function"></a><span data-ttu-id="b0855-102">IndexOf függvény</span><span class="sxs-lookup"><span data-stu-id="b0855-102">IndexOf function</span></span>

<span data-ttu-id="b0855-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b0855-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b0855-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0855-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0855-105">Egy olyan tömb első elemének első indexét adja vissza, amely megfelel egy adott predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="b0855-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="b0855-106">Ha nem létezik ilyen elem, a a-1 értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b0855-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="b0855-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b0855-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="b0855-108">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b0855-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b0855-109">Egy predikátum-függvény, amely a tömb elemein működik.</span><span class="sxs-lookup"><span data-stu-id="b0855-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="b0855-110">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="b0855-110">arr : 'T[]</span></span>

<span data-ttu-id="b0855-111">A megadott predikátum használatával keresendő tömb.</span><span class="sxs-lookup"><span data-stu-id="b0855-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="b0855-112">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0855-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0855-113">Vagy a legkisebb index `idx` , amely `predicate(arr[idx])` igaz, vagy-1, ha nincs ilyen elem.</span><span class="sxs-lookup"><span data-stu-id="b0855-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b0855-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b0855-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0855-115">Nem</span><span class="sxs-lookup"><span data-stu-id="b0855-115">'T</span></span>

