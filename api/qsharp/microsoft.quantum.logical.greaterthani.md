---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709986"
---
# <a name="greaterthani-function"></a>GreaterThanI függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Az összehasonlításhoz használandó első érték.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```