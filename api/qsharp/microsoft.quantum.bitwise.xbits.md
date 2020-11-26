---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209757"
---
# <a name="xbits-function"></a>XBits függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy olyan egész számot ad vissza, amely a Pauli-operátorok tömbje X biteit jelképezi.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Az egész számként megjelenítendő Pauli-operátorok tömbje.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész $x $, bináris ábrázolással $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, ahol $p _i = $0 `paulis[i]` , ha az `PauliI` vagy `PauliZ` , és ahol $p _i = $1 `paulis[i]` , ha a `PauliX` vagy a `PauliY` .

## <a name="remarks"></a>Megjegyzések

A függvény eldönti, hogy a tömb hossza nagyobb-e, `paulis` mint 63.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. bitenkénti. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)