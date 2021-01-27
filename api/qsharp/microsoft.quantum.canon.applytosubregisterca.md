---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: ApplyToSubregisterCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9f24c3ca9b152cf9bbf81e59b86f83a0ab459031
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841206"
---
# <a name="applytosubregisterca-operation"></a>ApplyToSubregisterCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy műveletet alkalmaz egy regiszter alnyilvántartásába, és az qubits egy tömb adja meg.
A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="op--qubit--unit--is-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

A alregisztrációra alkalmazandó művelet.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Indexek tömbje, amely azt jelzi, hogy a művelet mely qubits lesz alkalmazva.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Regisztrálja, hogy a művelet milyen műveleteket végez.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToSubregister](xref:Microsoft.Quantum.Canon.ApplyToSubregister)