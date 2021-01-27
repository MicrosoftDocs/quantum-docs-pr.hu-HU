---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842059"
---
# <a name="zbits-function"></a>ZBits függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy olyan egész számot ad vissza, amely a Pauli operátorok tömbének Z bitejét jelöli.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Az egész számként megjelenítendő Pauli-operátorok tömbje.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész $x $, bináris ábrázolással $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, ahol $p _i = $0 `paulis[i]` , ha az `PauliI` vagy `PauliX` , és ahol $p _i = $1 `paulis[i]` , ha a `PauliY` vagy a `PauliZ` .

## <a name="remarks"></a>Megjegyzések

A függvény eldönti, hogy a tömb hossza nagyobb-e, `paulis` mint 63.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. bitenkénti. XBits](xref:Microsoft.Quantum.Bitwise.XBits)