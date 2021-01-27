---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846294"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="24a2c-102">_SwapOrderToPermuteArray függvény</span><span class="sxs-lookup"><span data-stu-id="24a2c-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="24a2c-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="24a2c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="24a2c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24a2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24a2c-105">Egy tömb Order elemeit adja vissza egy rendezett tömb létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="24a2c-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="24a2c-106">Feltételezi, hogy a swapok a helyükön történnek.</span><span class="sxs-lookup"><span data-stu-id="24a2c-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="24a2c-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="24a2c-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="24a2c-108">Leadva: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="24a2c-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="24a2c-109">Tömb, amely az új tömb indexeit tartalmazó permutációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="24a2c-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="24a2c-110">$N $ elemnek kell lennie, és mindegyiknek egyedi egész számnak kell lennie a $0 $ és a $n-$1 között.</span><span class="sxs-lookup"><span data-stu-id="24a2c-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="24a2c-111">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="24a2c-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="24a2c-112">A rekord a felcserélni kívánt két indexet jelöli.</span><span class="sxs-lookup"><span data-stu-id="24a2c-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="24a2c-113">A swap a legalacsonyabb indexnél kezdődik.</span><span class="sxs-lookup"><span data-stu-id="24a2c-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="24a2c-114">Példa</span><span class="sxs-lookup"><span data-stu-id="24a2c-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="24a2c-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="24a2c-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="24a2c-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="24a2c-116">Psuedocode</span></span>

<span data-ttu-id="24a2c-117">for (index in 0.. length (leadva)-1) {while leadva [index]! = index {switch leadva [index] a leadva [leadva [index]]}}</span><span class="sxs-lookup"><span data-stu-id="24a2c-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>