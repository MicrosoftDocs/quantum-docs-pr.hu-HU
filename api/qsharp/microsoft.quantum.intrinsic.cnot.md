---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNEM művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 90e84f7d0ea7373498632474dfafa23335f0c78e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198976"
---
# <a name="cnot-operation"></a>CNEM művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A vezérelt-NOT (CNEM) kaput alkalmazza egy qubits.

\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

a sorok és oszlopok sorrendjét a Quantum Concepts útmutatója tartalmazza.

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="control--qubit"></a>vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A CNEM-kapu qubit vezérlése.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A CNEM kapu cél qubit.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Egyenértékű a következővel:

```qsharp
Controlled X([control], target);
```