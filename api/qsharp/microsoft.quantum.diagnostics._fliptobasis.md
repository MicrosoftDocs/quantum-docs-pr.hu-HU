---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223986"
---
# <a name="_fliptobasis-operation"></a>_flipToBasis művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A $ \ket {0} \otimes\cdots\ket {0} $ és $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $ unitaries alkalmazza, ahol a $ \ket{\ psi_k} $ érték függ `basis[k]` .

Az érték `basis[k]` és a $ \ket{\ psi_k} $ közötti megfelelés a következő:

- `basis[k]=0` $ \rightarrow \ket {0} $.
- `basis[k]=1` $ \rightarrow \ket {1} $.
- `basis[k]=2` $ \rightarrow \ket{+} $.
- `basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate: Pauli Y).

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="basis--int"></a>alap: [int](xref:microsoft.quantum.lang-ref.int)[]

Az qubit-alapú állapot-azonosítók tömbje (0 <= azonosító <= 3), az egyik a qubits minden eleméhez.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A Qubit.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

