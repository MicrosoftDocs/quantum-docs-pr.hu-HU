---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845651"
---
# <a name="mappedoverrange-function"></a>MappedOverRange függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Példa

Ez a példa a páros számok egy tartományát adja hozzá 1-re:

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, például ha van egy függvény, amely `mapper: Int -> 'T` leképezi a tartomány értékeit, és létrehoz egy típusú tömböt `'T[]` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. leképezve](xref:Microsoft.Quantum.Arrays.Mapped)