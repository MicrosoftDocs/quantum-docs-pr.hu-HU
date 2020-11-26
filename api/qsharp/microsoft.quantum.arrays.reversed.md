---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fordított függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220433"
---
# <a name="reversed-function"></a>Fordított függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hozzon létre egy tömböt, amely ugyanazokat az elemeket tartalmazza, mint a bemeneti tömb, de fordított sorrendben.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="array--t"></a>tömb: 'T []

Olyan tömb, amelynek elemeit fordított sorrendben kell másolni.



## <a name="output--t"></a>Kimenet: 'T []

Az elemeket tartalmazó tömb `array[Length(array) - 1]` . `array[0]`.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A tömb elemeinek típusa