---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715237"
---
# <a name="uncurriedop-function"></a>UncurriedOp függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Bevitel

### <a name="curriedop--t---u--unit"></a>curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy függvény, amely visszaadja A műveleteket.



## <a name="output--tu--unit"></a>Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az első bemeneti adat típusa egy Currie-művelethez.
### <a name="u"></a>' U

A többszintű művelet második bemenetének típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. Quantum. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. Quantum. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)