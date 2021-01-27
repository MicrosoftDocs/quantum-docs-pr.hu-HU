---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: ApplyOpRepeatedlyOverA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 30e91d8a0292c7389ad83f14e1b7d4a8248cbb96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841624"
---
# <a name="applyoprepeatedlyovera-operation"></a>ApplyOpRepeatedlyOverA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ugyanazokat az op-ket alkalmazza a qubit-regisztrációnál többször.

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Bevitel

### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

A qubit-regisztráción többször alkalmazandó művelet


### <a name="targets--int"></a>célok: [int](xref:microsoft.quantum.lang-ref.int)[] []

Az op céljait leíró beágyazott tömbök. Minden tömbnek tartalmaznia kell a használni kívánt qubits leíró csoportcsomagból listáját.


### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A Qubit-regisztrációt kell követni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)