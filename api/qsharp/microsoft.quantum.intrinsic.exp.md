---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819012"
---
# <a name="exp-operation"></a>Exp művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy több qubit Pauli-operátor exponenciális értékének alkalmazása.

\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, ahol $P _i $ a $i $ th eleme `paulis` , és hol $N = $ `Length(paulis)` .

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.


### <a name="theta--double"></a>THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)

Az adott qubit Pauli-kezelőre vonatkozó szög, amellyel a cél-regisztrációt el kell forgatni.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Regisztrálja, hogy a megadott rotációt alkalmazza a következőre:.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

