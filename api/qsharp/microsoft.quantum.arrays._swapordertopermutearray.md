---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221708"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="79d84-102">_SwapOrderToPermuteArray függvény</span><span class="sxs-lookup"><span data-stu-id="79d84-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="79d84-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="79d84-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="79d84-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79d84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79d84-105">Egy tömb Order elemeit adja vissza egy rendezett tömb létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="79d84-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="79d84-106">Feltételezi, hogy a swapok a helyükön történnek.</span><span class="sxs-lookup"><span data-stu-id="79d84-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="79d84-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="79d84-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="79d84-108">Leadva: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="79d84-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="79d84-109">Tömb, amely az új tömb indexeit tartalmazó permutációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="79d84-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="79d84-110">$N $ elemnek kell lennie, és mindegyiknek egyedi egész számnak kell lennie a $0 $ és a $n-$1 között.</span><span class="sxs-lookup"><span data-stu-id="79d84-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="79d84-111">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="79d84-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="79d84-112">A rekord a felcserélni kívánt két indexet jelöli.</span><span class="sxs-lookup"><span data-stu-id="79d84-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="79d84-113">A swap a legalacsonyabb indexnél kezdődik.</span><span class="sxs-lookup"><span data-stu-id="79d84-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="79d84-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="79d84-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="79d84-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="79d84-115">Psuedocode</span></span>

<span data-ttu-id="79d84-116">for (index in 0.. length (leadva)-1) {while leadva [index]! = index {switch leadva [index] a leadva [leadva [index]]}}</span><span class="sxs-lookup"><span data-stu-id="79d84-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>