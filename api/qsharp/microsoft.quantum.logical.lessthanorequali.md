---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709931"
---
# <a name="lessthanorequali-function"></a>LessThanOrEqualI függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb vagy egyenlő, mint egy másik szám.

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Az összehasonlításhoz használandó első érték.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` kisebb vagy egyenlő, `b` mint.

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```