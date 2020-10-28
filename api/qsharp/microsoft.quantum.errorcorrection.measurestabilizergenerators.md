---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712268"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


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


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __érvénytelen <Result>__ 

Egy multiqubit Pauli-operátor mérését megadó művelet.



## <a name="output--syndrome"></a>Kimenet: [szindróma](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

A mérések eredménye.

## <a name="remarks"></a>Megjegyzések

Ezzel a beállítással nem ellenőrizhető, hogy az adott generátorok vannak-e ingázások.
Ha nem az ingázást végzik, lehetséges, hogy a mérések eredménye tetszőleges.