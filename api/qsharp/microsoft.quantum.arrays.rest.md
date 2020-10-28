---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718913"
---
# <a name="rest-function"></a>Rest-függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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