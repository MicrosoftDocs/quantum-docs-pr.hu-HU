---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825756"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A stabilizátorok csoportjának adott készletét méri.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Bevitel

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Multiqubit Pauli-operátorok tömbje.
Például az egy `stabilizerGroup[0]` Qubit Pauli-mátrixok listája, amely a kétprocesszoros termék, amely egy stabilizátor generátor.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Olyan qubits tömbje, amelyben a stabilizátor kódja van meghatározva.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __érvénytelen <Result>__ 

Egy multiqubit Pauli-operátor mérését megadó művelet.



## <a name="output--syndrome"></a>Kimenet: [szindróma](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

A mérések eredménye.

## <a name="remarks"></a>Megjegyzések

Ezzel a beállítással nem ellenőrizhető, hogy az adott generátorok vannak-e ingázások.
Ha nem az ingázást végzik, lehetséges, hogy a mérések eredménye tetszőleges.