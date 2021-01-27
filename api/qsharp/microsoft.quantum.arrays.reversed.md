---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fordított függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845452"
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