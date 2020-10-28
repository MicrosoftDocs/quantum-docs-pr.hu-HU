---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716413"
---
# <a name="controlledonint-function"></a>ControlledOnInt függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy olyan egységes operátort ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott pozitív egész számnak felel meg.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Pozitív egész szám.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Egységes operátor.



## <a name="output--qubitt--unit-adj--ctl"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], nem) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Egy egységes operátor, amely a `oracle` cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a szám állapotnak `numberState` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

A értéke `numberState` kis endian kódolással értelmezhető.