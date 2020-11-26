---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207258"
---
# <a name="controlledonint-function"></a>ControlledOnInt függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan egységes operátort ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott pozitív egész számnak felel meg.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Pozitív egész szám.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egységes operátor.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egy egységes operátor, amely a `oracle` cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a szám állapotnak `numberState` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

A értéke `numberState` kis endian kódolással értelmezhető.