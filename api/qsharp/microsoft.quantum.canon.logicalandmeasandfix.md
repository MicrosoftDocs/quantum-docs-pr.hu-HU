---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715923"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Kiszámítja a logikai és a több qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="ctrlregister--qubit"></a>ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits az inputot a többszörös bemenet és a kapu számára.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a Qubit, amelynek kimenetét és tartalmát a rendszer a értékre írja. Ezt a rendszer feltételezi, hogy mindig a $ \ket {0} $ állapotban indul el.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ha `ctrlRegister` pontosan $2 $ qubits rendelkezik, ez egyenértékű a `CCNOT` művelettel, de fázisban $e ^ {i \ pi/2} $ $ \ket {001} $ és $-e ^ {i \ pi/2} $ on $ \ket {101} $ és $ \ket {011} $.
A Adjoint a mérték és a javítás is, amely az eredeti művelet inverze, csak speciális esetekben (lásd a hivatkozásokat), de kevesebb T-kaput használ.

## <a name="references"></a>Referencia

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)