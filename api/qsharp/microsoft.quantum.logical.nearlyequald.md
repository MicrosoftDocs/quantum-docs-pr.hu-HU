---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814369"
---
# <a name="nearlyequald-function"></a>NearlyEqualD függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Igaz értéket ad vissza, ha két bemenet közel egyenlő (azaz a 1e-12 tűréshatáron belül).

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--double"></a>a: [dupla](xref:microsoft.quantum.lang-ref.double)

Az összehasonlításhoz használandó első érték.


### <a name="b--double"></a>b: [dupla](xref:microsoft.quantum.lang-ref.double)

Az összehasonlítandó második érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` majdnem egyenlő a következővel: `b` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```