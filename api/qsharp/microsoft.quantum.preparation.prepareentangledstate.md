---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854369"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A páros két qubit-regisztrációt is összekever.

Ez azt eredményezi, hogy a két regisztráció során a rendszer előkészíti a maximálisan összefoglalt állapotot ($ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) a megfelelő regisztereken található egyes qubits között, feltételezve, hogy minden egyes regisztráció a $ \ket{0\cdots 0} $ állapottal kezdődik.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="left--qubit"></a>balra: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit tömb a $ \ket{0\cdots 0} $ állapotban


### <a name="right--qubit"></a>jobb: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit tömb a $ \ket{0\cdots 0} $ állapotban



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

