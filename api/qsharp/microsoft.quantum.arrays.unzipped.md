---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Kibontott függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718792"
---
# <a name="unzipped-function"></a>Kibontott függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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