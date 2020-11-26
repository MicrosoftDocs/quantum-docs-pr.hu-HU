---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 22af7a3704f88a4d1973149e7387ebb683468540
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208272"
---
# <a name="applytopartitionc-operation"></a>ApplyToPartitionC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy pár műveletet alkalmaz a regiszter egy adott partícióján két részre.
A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Bevitel

### <a name="op--qubitqubit--unit--is-ctl"></a>op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az adott partíción alkalmazni kívánt műveletek pár.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeket a rendszer a partíció első részébe helyez.
A fennmaradó qubits a partíció második részét képezik.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A megadott két művelet által particionált és üzemeltetett qubits-jegyzék.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)