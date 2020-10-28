---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719489"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="4f326-102">_SwapOrderToPermuteArray függvény</span><span class="sxs-lookup"><span data-stu-id="4f326-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="4f326-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4f326-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4f326-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f326-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f326-105">Egy tömb Order elemeit adja vissza egy rendezett tömb létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4f326-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="4f326-106">Feltételezi, hogy a swapok a helyükön történnek.</span><span class="sxs-lookup"><span data-stu-id="4f326-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="4f326-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4f326-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="4f326-108">Leadva: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4f326-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4f326-109">Tömb, amely az új tömb indexeit tartalmazó permutációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="4f326-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="4f326-110">$N $ elemnek kell lennie, és mindegyiknek egyedi egész számnak kell lennie a $0 $ és a $n-$1 között.</span><span class="sxs-lookup"><span data-stu-id="4f326-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="4f326-111">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="4f326-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="4f326-112">A rekord a felcserélni kívánt két indexet jelöli.</span><span class="sxs-lookup"><span data-stu-id="4f326-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="4f326-113">A swap a legalacsonyabb indexnél kezdődik.</span><span class="sxs-lookup"><span data-stu-id="4f326-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f326-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4f326-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="4f326-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="4f326-115">Psuedocode</span></span>

<span data-ttu-id="4f326-116">for (index in 0.. length (leadva)-1) {while leadva [index]! = index {switch leadva [index] a leadva [leadva [index]]}}</span><span class="sxs-lookup"><span data-stu-id="4f326-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>