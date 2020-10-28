---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fordított függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718912"
---
# <a name="reversed-function"></a>Fordított függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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