---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845353"
---
# <a name="zip3-function"></a>Zip3 függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> A Zip3 elavult. Használja <xref:Microsoft.Quantum.Arrays.Zipped3> helyette.

A három tömb esetében a rekordok egy új tömböt ad vissza, amely szerint minden 3 rekord tartalmaz egy elemet az eredeti tömbből.

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Bevitel

### <a name="first--t1"></a>első: nem 1 []

Az egyes adatrekordok első elemének értékeit tartalmazó tömb.


### <a name="second--t2"></a>második: nem 2 []

A rekord második elemének értékeit tartalmazó tömb.


### <a name="third--t3"></a>harmadik: nem 3 []

Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.



## <a name="output--t1t2t3"></a>Kimenet: (nem 1, nem 2, nem 3) []

Az űrlap 3 – rekordok tartalmazó tömbje `(first[idx], second[idx], third[idx])` `idx` . Ha a három tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t1"></a>Nem 1

Az első tömb elemeinek típusa
### <a name="t2"></a>Nem 2

A második tömb elemeinek típusa
### <a name="t3"></a>Nem 3

A harmadik tömb elemeinek típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)