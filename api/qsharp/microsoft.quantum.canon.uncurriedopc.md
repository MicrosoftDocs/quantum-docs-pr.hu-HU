---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715209"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.
A módosító `C` azt jelzi, hogy a műveletek ellenőrizhetők.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Bevitel

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL

Egy függvény, amely visszaadja A műveleteket.



## <a name="output--tu--unit-ctl"></a>Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL

Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Egy Currie-függvény első argumentumának típusa.
### <a name="u"></a>' U

Egy Currie-függvény második argumentumának típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)