---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845330"
---
# <a name="zipped4-function"></a>Zipped4 függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A megadott négy tömb a 4 rekordok egy új tömbjét adja vissza, amely minden 4 rekord tartalmaz egy elemet az eredeti tömbből.

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Bevitel

### <a name="first--t1"></a>első: nem 1 []

Az egyes adatrekordok első elemének értékeit tartalmazó tömb.


### <a name="second--t2"></a>második: nem 2 []

A rekord második elemének értékeit tartalmazó tömb.


### <a name="third--t3"></a>harmadik: nem 3 []

Az egyes adatrekordok harmadik elemének értékeit tartalmazó tömb.


### <a name="fourth--t4"></a>negyedik: nem 4 []

Az egyes rekordokhoz tartozó negyedik elem értékeit tartalmazó tömb.



## <a name="output--t1t2t3t4"></a>Kimenet: (nem 1, nem 2, nem 3, nem 4) []

Egy tömb, amely 4 – rekordok tartalmaz az űrlapokhoz `(first[idx], second[idx], third[idx], fourth[idx])` `idx` . Ha a négy tömb nem egyenlő hosszúságú, a kimenet a lehető legrövidebb lesz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t1"></a>Nem 1

Az első tömb elemeinek típusa
### <a name="t2"></a>Nem 2

A második tömb elemeinek típusa
### <a name="t3"></a>Nem 3

A harmadik tömb elemeinek típusa.
### <a name="t4"></a>Nem 4

A negyedik tömb elemeinek típusa

## <a name="see-also"></a>Lásd még:

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)