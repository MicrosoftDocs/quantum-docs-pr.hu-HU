---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220391"
---
# <a name="rest-function"></a>Rest-függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, hogy az első tömb elem el lett dobva.

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="array--t"></a>tömb: 'T []

Az a tömb, amelynek az utolsó eleme a kimeneti tömb alkotása.



## <a name="output--t"></a>Kimenet: 'T []

Az elemeket tartalmazó tömb `array[1..Length(array) - 1]` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A tömb elemeinek típusa