---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815955"
---
# <a name="greaterthani-function"></a>GreaterThanI függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```