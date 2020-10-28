---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719044"
---
# <a name="mappedoverrange-function"></a>MappedOverRange függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy tartomány és egy olyan függvény, amely egy egész számot fogad a bemenetként, egy új tömböt ad vissza, amely a függvényben lévő tartomány értékeiből származó képekből áll.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="mapper--int---t"></a>Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> 't

A-ből származó függvény, `Int` `'T` amely a tartomány értékeit térképezi fel.


### <a name="range--range"></a>tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)

Egész számokból álló tartomány.



## <a name="output--t"></a>Kimenet: 'T []

`'T[]`A függvény által leképezett elemek tömbje `mapper` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A függvény eredményének típusa `mapper` .

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, például ha van egy függvény, amely `mapper: Int -> 'T` leképezi a tartomány értékeit, és létrehoz egy típusú tömböt `'T[]` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. leképezve](xref:Microsoft.Quantum.Arrays.Mapped)