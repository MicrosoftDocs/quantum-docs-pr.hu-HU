---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Kibontott függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845367"
---
# <a name="unzipped-function"></a>Kibontott függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A 2-rekordok tömbje egy két tömbből álló tömböt ad vissza, amely a bemeneti tömb rekordok elemeit tartalmazza.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Bevitel

### <a name="arr--tu"></a>ARR: (nem, ' U) []

2 – rekordok tartalmazó tömb



## <a name="output--tu"></a>Kimenet: ('T [], ' U [])

Két tömb, amely a bemeneti rekordok első elemeit tartalmazza, a második pedig a bemeneti rekordok összes elemét tartalmazza.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes rekordokban az első elem típusa
### <a name="u"></a>' U

Az egyes rekordokban szereplő második elem típusa

## <a name="example"></a>Példa

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)