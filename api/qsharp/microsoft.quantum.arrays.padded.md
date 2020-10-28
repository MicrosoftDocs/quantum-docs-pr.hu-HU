---
uid: Microsoft.Quantum.Arrays.Padded
title: Párnázott függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718984"
---
# <a name="padded-function"></a>Párnázott függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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