---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719416"
---
# <a name="constantarray-function"></a>ConstantArray függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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

