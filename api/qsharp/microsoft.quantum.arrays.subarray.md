---
uid: Microsoft.Quantum.Arrays.Subarray
title: Tömb függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220161"
---
# <a name="subarray-function"></a><span data-ttu-id="c2019-102">Tömb függvény</span><span class="sxs-lookup"><span data-stu-id="c2019-102">Subarray function</span></span>

<span data-ttu-id="c2019-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c2019-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c2019-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2019-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2019-105">Egy tömböt és egy listát hoz létre, és létrehoz egy új tömböt az eredeti tömb elemeiből, amelyek megfelelnek az adott helyeknek.</span><span class="sxs-lookup"><span data-stu-id="c2019-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c2019-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c2019-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="c2019-107">indexek: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c2019-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c2019-108">Az altömb definiálásához használt egész számok listája.</span><span class="sxs-lookup"><span data-stu-id="c2019-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="c2019-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="c2019-109">array : 'T[]</span></span>

<span data-ttu-id="c2019-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="c2019-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="c2019-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="c2019-111">Output : 'T[]</span></span>

<span data-ttu-id="c2019-112">Olyan elemek tömbje `out` , amelyek indexei az altömbnek felelnek meg, például: `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="c2019-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c2019-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c2019-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2019-114">Nem</span><span class="sxs-lookup"><span data-stu-id="c2019-114">'T</span></span>

<span data-ttu-id="c2019-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="c2019-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2019-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c2019-116">Remarks</span></span>

<span data-ttu-id="c2019-117">A függvény általános típusokhoz van definiálva, azaz, ha van egy tömb, `'T[]` és `Int[]` az altömbet meghatározó helyszínek listája.</span><span class="sxs-lookup"><span data-stu-id="c2019-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="c2019-118">Az altömb felépítése azon alapul, hogy az adott tömb új, részletes másolatát hozza létre a hivatkozások fenntartása mellett.</span><span class="sxs-lookup"><span data-stu-id="c2019-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="c2019-119">Ha `Length(indices) < Length(array)` Ez a függvény a következő részhalmazát fogja visszaadni: `array` .</span><span class="sxs-lookup"><span data-stu-id="c2019-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="c2019-120">Másfelől, ha `indices` ismétlődő elemeket tartalmaz, a megfelelő elemek is `array` megismétlődnek.</span><span class="sxs-lookup"><span data-stu-id="c2019-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="c2019-121">Ha `indices` `array` a és az azonos hosszúságú, akkor ez a függvény a következő funkciókat biztosítja: `array` .</span><span class="sxs-lookup"><span data-stu-id="c2019-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>