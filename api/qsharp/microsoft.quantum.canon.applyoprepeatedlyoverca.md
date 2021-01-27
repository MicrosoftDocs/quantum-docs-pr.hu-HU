---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: ApplyOpRepeatedlyOverCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 9b7f0897009d9913fc886f99b2e29f3fc1040666
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841602"
---
# <a name="applyoprepeatedlyoverca-operation"></a>ApplyOpRepeatedlyOverCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ugyanazokat az op-ket alkalmazza a qubit-regisztrációnál többször.

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="op--qubit--unit--is-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

A qubit-regisztráción többször alkalmazandó művelet


### <a name="targets--int"></a>célok: [int](xref:microsoft.quantum.lang-ref.int)[] []

Az op céljait leíró beágyazott tömbök. Minden tömbnek tartalmaznia kell a használni kívánt qubits leíró csoportcsomagból listáját.


### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A Qubit-regisztrációt kell követni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)