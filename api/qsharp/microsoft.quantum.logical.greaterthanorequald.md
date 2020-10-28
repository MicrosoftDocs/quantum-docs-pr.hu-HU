---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711373"
---
# <a name="greaterthanorequald-function"></a>GreaterThanOrEqualD függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb vagy egyenlő, mint egy másik szám.

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--double"></a>a: [dupla](xref:microsoft.quantum.lang-ref.double)

Az összehasonlításhoz használandó első érték.


### <a name="b--double"></a>b: [dupla](xref:microsoft.quantum.lang-ref.double)

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` nagyobb vagy egyenlő, mint `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```