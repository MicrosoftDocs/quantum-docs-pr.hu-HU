---
uid: Microsoft.Quantum.Arrays.Most
title: A legtöbb függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718997"
---
# <a name="most-function"></a>A legtöbb függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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