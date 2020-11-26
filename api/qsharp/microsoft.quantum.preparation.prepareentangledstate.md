---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210471"
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

