---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198027"
---
# <a name="greaterthand-function"></a>GreaterThanD függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--double"></a>a: [dupla](xref:microsoft.quantum.lang-ref.double)

Az összehasonlításhoz használandó első érték.


### <a name="b--double"></a>b: [dupla](xref:microsoft.quantum.lang-ref.double)

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```