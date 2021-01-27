---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845234"
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