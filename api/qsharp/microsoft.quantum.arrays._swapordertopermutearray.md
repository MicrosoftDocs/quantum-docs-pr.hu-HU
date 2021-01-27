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
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömb Order elemeit adja vissza egy rendezett tömb létrehozásához.
Feltételezi, hogy a swapok a helyükön történnek.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Bevitel

### <a name="neworder--int"></a>Leadva: [int](xref:microsoft.quantum.lang-ref.int)[]

Tömb, amely az új tömb indexeit tartalmazó permutációval rendelkezik. $N $ elemnek kell lennie, és mindegyiknek egyedi egész számnak kell lennie a $0 $ és a $n-$1 között.



## <a name="output--intint"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

A rekord a felcserélni kívánt két indexet jelöli. A swap a legalacsonyabb indexnél kezdődik.

## <a name="example"></a>Példa

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Megjegyzések

## <a name="psuedocode"></a>Psuedocode

for (index in 0.. length (leadva)-1) {while leadva [index]! = index {switch leadva [index] a leadva [leadva [index]]}}