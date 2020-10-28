---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719056"
---
# <a name="mappedbyindex-function"></a>MappedByIndex függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy tömb és egy függvény, amely a tömb indexelt elemeihez van definiálva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Bevitel

### <a name="mapper--intt---u"></a>Mapper: ([int](xref:microsoft.quantum.lang-ref.int), 't) – > U

A-ből származó függvény, `(Int, 'T)` `'U` amely az elemek és az indexek hozzárendelésére szolgál.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--u"></a>Kimenet: ' U []

`'U[]`A függvény által leképezett elemek tömbje `mapper` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .
### <a name="u"></a>' U

A függvény eredményének típusa `mapper` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. leképezve](xref:Microsoft.Quantum.Arrays.Mapped)