---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718564"
---
# <a name="xbits-function"></a>XBits függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag [](https://nuget.org/packages/)


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