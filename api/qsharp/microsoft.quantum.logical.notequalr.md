---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197194"
---
# <a name="notequalr-function"></a>NotEqualR függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--__invalidresult__"></a>a: __érvénytelen <Result>__

Az összehasonlításhoz használandó első érték.


### <a name="b--__invalidresult__"></a>b: __érvénytelen <Result>__

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` nem egyenlő `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```