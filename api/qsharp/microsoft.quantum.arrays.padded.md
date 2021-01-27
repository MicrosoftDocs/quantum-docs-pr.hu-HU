---
uid: Microsoft.Quantum.Arrays.Padded
title: Párnázott függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845562"
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

## <a name="example"></a>Példa

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```