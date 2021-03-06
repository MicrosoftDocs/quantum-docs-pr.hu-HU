---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845479"
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