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
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Megjegyzések

## <a name="psuedocode"></a>Psuedocode

for (index in 0.. length (leadva)-1) {while leadva [index]! = index {switch leadva [index] a leadva [leadva [index]]}}