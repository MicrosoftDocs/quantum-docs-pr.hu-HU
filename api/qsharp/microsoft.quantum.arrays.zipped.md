---
uid: Microsoft.Quantum.Arrays.Zipped
title: Tömörített függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845338"
---
# <a name="zipped-function"></a>Tömörített függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Bevitel

### <a name="left--t"></a>balra: nem []

Az egyes adatrekordok első elemének értékeit tartalmazó tömb.


### <a name="right--u"></a>Right: ' U []

A rekord második elemének értékeit tartalmazó tömb.



## <a name="output--tu"></a>Kimenet: (nem, ' U) []

Egy tömb, amely az űrlaphoz tartozó párokat tartalmaz `(left[idx], right[idx])` `idx` . Ha a két tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A bal oldali tömb elemeinek típusa
### <a name="u"></a>' U

A jobb oldali tömb elemeinek típusa.

## <a name="example"></a>Példa

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Lásd még:

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. Arrays. kibontva](xref:Microsoft.Quantum.Arrays.Unzipped)