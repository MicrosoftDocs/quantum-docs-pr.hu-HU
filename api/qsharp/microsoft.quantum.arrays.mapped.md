---
uid: Microsoft.Quantum.Arrays.Mapped
title: Leképezett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845677"
---
# <a name="mapped-function"></a>Leképezett függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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