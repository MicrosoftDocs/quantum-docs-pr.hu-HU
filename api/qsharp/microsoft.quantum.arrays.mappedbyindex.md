---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845664"
---
# <a name="mappedbyindex-function"></a>MappedByIndex függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Példa

A következő két sor egyenértékű:

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

és

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. leképezve](xref:Microsoft.Quantum.Arrays.Mapped)