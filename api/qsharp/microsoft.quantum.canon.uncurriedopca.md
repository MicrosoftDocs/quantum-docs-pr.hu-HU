---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840042"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.
A módosító `CA` azt jelzi, hogy a műveletek ellenőrizhetők és adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Bevitel

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy függvény, amely visszaadja A műveleteket.



## <a name="output--tu--unit--is-adj--ctl"></a>Kimenet: ('T, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Egy Currie-függvény első argumentumának típusa.
### <a name="u"></a>' U

Egy Currie-függvény második argumentumának típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)