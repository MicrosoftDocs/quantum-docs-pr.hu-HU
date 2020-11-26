---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ-művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222762"
---
# <a name="maj-operation"></a>MAJ-művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ez a helyi többségi műveletet 3 qubits alkalmazza.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ha a célként megadott qubit állapotát a $ \ket{z} $ értékre, a bemeneti qubits pedig $ \ket{x} $ és $ \ket{y} $ értékre állítja be, akkor ez a művelet a következő átalakítást hajtja végre: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Bevitel

### <a name="input0--qubit"></a>input0: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az első bemeneti qubit.


### <a name="input1--qubit"></a>input1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A második bemeneti qubit.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A qubit, amelyre a rendszer alkalmazza a többségi függvényt.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

