---
uid: Microsoft.Quantum.Arrays.Subarray
title: Tömb függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845420"
---
# <a name="subarray-function"></a><span data-ttu-id="30c05-102">Tömb függvény</span><span class="sxs-lookup"><span data-stu-id="30c05-102">Subarray function</span></span>

<span data-ttu-id="30c05-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="30c05-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="30c05-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30c05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30c05-105">Egy tömböt és egy listát hoz létre, és létrehoz egy új tömböt az eredeti tömb elemeiből, amelyek megfelelnek az adott helyeknek.</span><span class="sxs-lookup"><span data-stu-id="30c05-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="30c05-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="30c05-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="30c05-107">indexek: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="30c05-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="30c05-108">Az altömb definiálásához használt egész számok listája.</span><span class="sxs-lookup"><span data-stu-id="30c05-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="30c05-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="30c05-109">array : 'T[]</span></span>

<span data-ttu-id="30c05-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="30c05-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="30c05-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="30c05-111">Output : 'T[]</span></span>

<span data-ttu-id="30c05-112">Olyan elemek tömbje `out` , amelyek indexei az altömbnek felelnek meg, például: `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="30c05-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="30c05-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="30c05-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="30c05-114">Nem</span><span class="sxs-lookup"><span data-stu-id="30c05-114">'T</span></span>

<span data-ttu-id="30c05-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="30c05-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="30c05-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="30c05-116">Remarks</span></span>

<span data-ttu-id="30c05-117">A függvény általános típusokhoz van definiálva, azaz, ha van egy tömb, `'T[]` és `Int[]` az altömbet meghatározó helyszínek listája.</span><span class="sxs-lookup"><span data-stu-id="30c05-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="30c05-118">Az altömb felépítése azon alapul, hogy az adott tömb új, részletes másolatát hozza létre a hivatkozások fenntartása mellett.</span><span class="sxs-lookup"><span data-stu-id="30c05-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="30c05-119">Ha `Length(indices) < Length(array)` Ez a függvény a következő részhalmazát fogja visszaadni: `array` .</span><span class="sxs-lookup"><span data-stu-id="30c05-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="30c05-120">Másfelől, ha `indices` ismétlődő elemeket tartalmaz, a megfelelő elemek is `array` megismétlődnek.</span><span class="sxs-lookup"><span data-stu-id="30c05-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="30c05-121">Ha `indices` `array` a és az azonos hosszúságú, akkor ez a függvény a következő funkciókat biztosítja: `array` .</span><span class="sxs-lookup"><span data-stu-id="30c05-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>