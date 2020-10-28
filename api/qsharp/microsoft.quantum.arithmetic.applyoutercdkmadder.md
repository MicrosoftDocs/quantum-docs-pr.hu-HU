---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721565"
---
# <a name="applyoutercdkmadder-operation"></a>ApplyOuterCDKMAdder művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Az alábbi, az egész számra kiterjedő művelet RippleCarryAdderCDKM használt, visszafordítható, helyi hullámos átviteli művelet.
A művelet két qubit-regisztrációt `xs` és `ys` azonos hosszúságú műveletet alkalmaz, és a cnem és a CCNOT-kapuk egy hullámos Carry-sorát alkalmazza a qubits, valamint `xs` `ys` a vezérlők és a qubits `xs` .

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Első qubit-regisztráció, amely tartalmazza a vezérlőket és a célokat.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

Második qubit-regisztráció, amely hozzájárul a vezérlőkhöz.


### <a name="ancilla--qubit"></a>Ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A RippleCarryAdderCDKM a műveletnek átadott Ancilla-qubit használja.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1