---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845145"
---
# <a name="applyccnotchain-operation"></a>ApplyCCNOTChain művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy kaszkád CCNOT-kaput valósít meg, amely a két qubit-regiszter megfelelő BITS-nyilvántartásába van irányítva, amely az egyik regiszter következő qubit működik.
A (z) 0. pozícióban lévő qubits kezdve a CCNOT a rendszer a qubit 1. pozíciójában alkalmazza, majd az 1. pozícióban a qubit a cél-regiszter 2. pozíciójában, a célként megadott qubit a pozícióban végződő művelettel végződik `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-regisztráció, csak vezérlőelemekhez használatos.


### <a name="targets--qubit"></a>célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-regisztráció, vezérlőelemekhez és célként használva.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A cél qubit-regisztrációnak egy qubit kell lennie, mint a többi regiszternél.