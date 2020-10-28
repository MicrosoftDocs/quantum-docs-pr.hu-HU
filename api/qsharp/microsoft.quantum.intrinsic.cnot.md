---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNEM művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722674"
---
# <a name="cnot-operation"></a>CNEM művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag [](https://nuget.org/packages/)


A vezérelt-NOT (CNEM) kaput alkalmazza egy qubits.

\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

a sorok és oszlopok sorrendjét a Quantum Concepts útmutatója tartalmazza.

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
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