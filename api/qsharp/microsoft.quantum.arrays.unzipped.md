---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Kibontott függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219957"
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

## <a name="see-also"></a>Lásd még:

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)