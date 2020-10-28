---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720784"
---
# <a name="equalb-function"></a>EqualB függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Az összehasonlításhoz használandó első érték.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` egyenlő `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```