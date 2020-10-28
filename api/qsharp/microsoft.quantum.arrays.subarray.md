---
uid: Microsoft.Quantum.Arrays.Subarray
title: Tömb függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718841"
---
# <a name="subarray-function"></a><span data-ttu-id="927c7-102">Tömb függvény</span><span class="sxs-lookup"><span data-stu-id="927c7-102">Subarray function</span></span>

<span data-ttu-id="927c7-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="927c7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="927c7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="927c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="927c7-105">Egy tömböt és egy listát hoz létre, és létrehoz egy új tömböt az eredeti tömb elemeiből, amelyek megfelelnek az adott helyeknek.</span><span class="sxs-lookup"><span data-stu-id="927c7-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="927c7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="927c7-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="927c7-107">indexek: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="927c7-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="927c7-108">Az altömb definiálásához használt egész számok listája.</span><span class="sxs-lookup"><span data-stu-id="927c7-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="927c7-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="927c7-109">array : 'T[]</span></span>

<span data-ttu-id="927c7-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="927c7-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="927c7-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="927c7-111">Output : 'T[]</span></span>

<span data-ttu-id="927c7-112">Olyan elemek tömbje `out` , amelyek indexei az altömbnek felelnek meg, például: `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="927c7-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="927c7-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="927c7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="927c7-114">Nem</span><span class="sxs-lookup"><span data-stu-id="927c7-114">'T</span></span>

<span data-ttu-id="927c7-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="927c7-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="927c7-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="927c7-116">Remarks</span></span>

<span data-ttu-id="927c7-117">A függvény általános típusokhoz van definiálva, azaz, ha van egy tömb, `'T[]` és `Int[]` az altömbet meghatározó helyszínek listája.</span><span class="sxs-lookup"><span data-stu-id="927c7-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="927c7-118">Az altömb felépítése azon alapul, hogy az adott tömb új, részletes másolatát hozza létre a hivatkozások fenntartása mellett.</span><span class="sxs-lookup"><span data-stu-id="927c7-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="927c7-119">Ha `Length(indices) < Length(array)` Ez a függvény a következő részhalmazát fogja visszaadni: `array` .</span><span class="sxs-lookup"><span data-stu-id="927c7-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="927c7-120">Másfelől, ha `indices` ismétlődő elemeket tartalmaz, a megfelelő elemek is `array` megismétlődnek.</span><span class="sxs-lookup"><span data-stu-id="927c7-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="927c7-121">Ha `indices` `array` a és az azonos hosszúságú, akkor ez a függvény a következő funkciókat biztosítja: `array` .</span><span class="sxs-lookup"><span data-stu-id="927c7-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>