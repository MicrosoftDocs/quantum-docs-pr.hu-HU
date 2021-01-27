---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848504"
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

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```