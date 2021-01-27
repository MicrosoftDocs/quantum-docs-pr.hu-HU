---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848580"
---
# <a name="foreach-operation"></a>ForEach művelet

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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