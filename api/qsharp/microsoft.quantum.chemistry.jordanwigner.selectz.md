---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713794"
---
# <a name="selectz-operation"></a>SelectZ művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag [](https://nuget.org/packages/)


Egy egységes $U $, amely a Pauli $Z $ Gate-t alkalmazza egy qubits, $p $ \ket{p} $ index állapotú. Ez a $ $ \begin{align} U\ket {p} \ ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A regisztrációhoz tartozó $ \ket{p} $ érték határozza meg azt a qubit, amelyen a $Z $ értéket alkalmazza a rendszer.


### <a name="targetregister--qubit"></a>targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Azon qubits regisztrálása, amelyeken a Pauli-operátorok vannak alkalmazva.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

