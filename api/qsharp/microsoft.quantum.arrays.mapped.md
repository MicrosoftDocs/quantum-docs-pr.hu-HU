---
uid: Microsoft.Quantum.Arrays.Mapped
title: Leképezett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719080"
---
# <a name="mapped-function"></a>Leképezett függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy tömb és egy függvény, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a függvényben található eredeti tömb képéből áll.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Bevitel

### <a name="mapper--t---u"></a>Mapper: nem > U

Az `'T` `'U` elemekhez tartozó függvény, amely az elemek hozzárendelésére szolgál.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--u"></a>Kimenet: ' U []

`'U[]`A függvény által leképezett elemek tömbje `mapper` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .
### <a name="u"></a>' U

A függvény eredményének típusa `mapper` .

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, azaz a tömb `'T[]` `mapper: 'T -> 'U` elemeinek leképezhetők, és egy új típusú tömb is létrehozható `'U[]` .