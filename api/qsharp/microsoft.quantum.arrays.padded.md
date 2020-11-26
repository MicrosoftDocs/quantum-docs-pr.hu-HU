---
uid: Microsoft.Quantum.Arrays.Padded
title: Párnázott függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220535"
---
# <a name="padded-function"></a>Párnázott függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan tömböt ad vissza, amely a megadott értékekkel megadott hosszúságú.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

A párnázott tömb hossza. Ha ez pozitív, `inputArray` akkor a rendszer a fej tetején található. Ha ez negatív, `inputArray` a rendszer a farok margóján található.


### <a name="defaultelement--t"></a>defaultElement: nem

A kitöltési elemekhez használandó alapértelmezett érték.


### <a name="inputarray--t"></a>inputArray: nem []

Az a tömb, amelynek értékei a kimeneti tömb élén vannak.



## <a name="output--t"></a>Kimenet: 'T []

Egy tömb `output` , amely a `inputArray` fej és a `defaultElement` `output` Hossz közötti távolságú `nElementsTotal`

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A tömb elemeinek típusa