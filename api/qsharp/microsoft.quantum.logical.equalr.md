---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710029"
---
# <a name="equalr-function"></a>EQUAL függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--__invalidresult__"></a>a: __érvénytelen <Result>__

Az összehasonlításhoz használandó első érték.


### <a name="b--__invalidresult__"></a>b: __érvénytelen <Result>__

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` egyenlő `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```