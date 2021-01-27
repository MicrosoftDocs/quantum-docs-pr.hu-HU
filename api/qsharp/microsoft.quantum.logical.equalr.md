---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815977"
---
# <a name="equalr-function"></a>EQUAL függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```