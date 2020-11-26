---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219855"
---
# <a name="zip-function"></a>Zip-függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> A zip elavult. Használja <xref:Microsoft.Quantum.Arrays.Zipped> helyette.

Az adott két tömb a párok új tömbjét adja vissza, így minden pár tartalmaz egy elemet az eredeti tömbből.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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

## <a name="see-also"></a>Lásd még:

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Quantum. Arrays. kibontva](xref:Microsoft.Quantum.Arrays.Unzipped)