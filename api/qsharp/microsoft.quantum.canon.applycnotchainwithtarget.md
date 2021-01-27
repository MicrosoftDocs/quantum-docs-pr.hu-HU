---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: ba1a4e99c411a4718b5a09fdcd57a7239eb4dbd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845117"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kiszámítja egy qubits-tömb paritását egy célként megadott qubit.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ha a tömb kezdetben a $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, a végleges állapotot a $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.

## <a name="input"></a>Bevitel

### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Azon qubits tömbje, amelyeken a paritás kiszámítása történik.


### <a name="targetqubit--qubit"></a>targetQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A végső qubit, amelybe a "qubits" paritása XORed.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

és

```qsharp
ApplyCNOTChain(qs);
```