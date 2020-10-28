---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719201"
---
# <a name="foreach-operation"></a>ForEach művelet

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy tömb és egy olyan művelet, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a művelet alatt található eredeti tömb képéből áll.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Bevitel

### <a name="action--t--u"></a>művelet: nem => ' U 

Az `'T` `'U` összes elemre alkalmazott művelet.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--u"></a>Kimenet: ' U []

`'U[]`A művelet által leképezett elemek tömbje `action` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .
### <a name="u"></a>' U

A művelet eredményének típusa `action` .

## <a name="remarks"></a>Megjegyzések

A művelet általános típusokhoz van definiálva, azaz a tömb `'T[]` `action : 'T -> 'U` elemeinek leképezhetők, illetve egy új típusú tömb létrehozásához `'U[]` .