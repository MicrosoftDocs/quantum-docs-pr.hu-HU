---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719176"
---
# <a name="indexof-function"></a><span data-ttu-id="e8595-102">IndexOf függvény</span><span class="sxs-lookup"><span data-stu-id="e8595-102">IndexOf function</span></span>

<span data-ttu-id="e8595-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8595-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8595-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8595-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8595-105">Egy olyan tömb első elemének első indexét adja vissza, amely megfelel egy adott predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="e8595-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="e8595-106">Ha nem létezik ilyen elem, a a-1 értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e8595-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="e8595-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e8595-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="e8595-108">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e8595-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e8595-109">Egy predikátum-függvény, amely a tömb elemein működik.</span><span class="sxs-lookup"><span data-stu-id="e8595-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e8595-110">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="e8595-110">arr : 'T[]</span></span>

<span data-ttu-id="e8595-111">A megadott predikátum használatával keresendő tömb.</span><span class="sxs-lookup"><span data-stu-id="e8595-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="e8595-112">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8595-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8595-113">Vagy a legkisebb index `idx` , amely `predicate(arr[idx])` igaz, vagy-1, ha nincs ilyen elem.</span><span class="sxs-lookup"><span data-stu-id="e8595-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e8595-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e8595-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8595-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e8595-115">'T</span></span>

