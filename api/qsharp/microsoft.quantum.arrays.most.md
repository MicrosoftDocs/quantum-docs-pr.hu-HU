---
uid: Microsoft.Quantum.Arrays.Most
title: A legtöbb függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220603"
---
# <a name="most-function"></a>A legtöbb függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, ha a legutolsó tömb elem el lett dobva.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="array--t"></a>tömb: 'T []

Egy tömb, amelynek első és utolsó eleme a kimeneti tömb alkotása.



## <a name="output--t"></a>Kimenet: 'T []

Az elemeket tartalmazó tömb `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A tömb elemeinek típusa