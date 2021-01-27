---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846223"
---
# <a name="constantarray-function"></a>ConstantArray függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott hosszúságú tömböt hoz létre a megadott értékkel egyenlő összes elemmel.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="length--int"></a>Hossz: [int](xref:microsoft.quantum.lang-ref.int)

Az új tömb hossza.


### <a name="value--t"></a>érték: nem

Az új tömb egyes elemeinek értéke.



## <a name="output--t"></a>Kimenet: 'T []

Egy új hosszúságú tömb `length` , amely minden elemnél `value` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="example"></a>Példa

A következő kód három logikai értékből álló tömböt hoz létre, amelyek mindegyike egyenlő `true` :

```qsharp
let array = ConstantArray(3, true);
```