---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713136"
---
# <a name="_prepareentangledstate-operation"></a>_prepareEntangledState művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


A két regisztráció során a rendszer előkészíti a maximálisan kusza állapotot a megfelelő regisztereken található egyes qubits között.
Minden qubits a (z) | 0 ⟩ állapotban kell kezdődnie.

Ennek eredményeképpen az egyes regisztrációk qubits tartozó párok a $ \bra{\ beta_ {00} } \ket{\ beta_} $ értékben találhatók {00} .

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="left--qubit"></a>balra: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit tömb a $ \ket{0\cdots 0} $ állapotban


### <a name="right--qubit"></a>jobb: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit tömb a $ \ket{0\cdots 0} $ állapotban



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

