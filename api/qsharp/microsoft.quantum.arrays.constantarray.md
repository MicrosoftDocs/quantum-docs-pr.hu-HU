---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210063"
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

