---
uid: Microsoft.Quantum.Canon.CZ
title: CZ-művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207207"
---
# <a name="cz-operation"></a>CZ-művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A vezérelt-Z (CZ) kaput alkalmazza egy pár qubits.

$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="control--qubit"></a>vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A CZ Gate qubit vezérlése.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A CZ Gate cél qubit.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Egyenértékű a következővel:

```qsharp
Controlled Z([control], target);
```