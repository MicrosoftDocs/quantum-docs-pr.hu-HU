---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718805"
---
# <a name="tuplearrayasnestedarray-function"></a>TupleArrayAsNestedArray függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy beágyazott tömbbe bekapcsolja a 2 – rekordok listáját.

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a>Bevitel

### <a name="tuplelist--tt"></a>tupleList: (nem, 'T) []

A beágyazott tömbbe bekapcsolni kívánt 2 – rekordok listája.



## <a name="output--t"></a>Kimenet: 'T [] []

Beágyazott tömb, amely a tupleList egyező hosszúságú.

## <a name="example"></a>Példa

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

