---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711485"
---
# <a name="expfrac-operation"></a>ExpFrac művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag [](https://nuget.org/packages/)


Egy több qubit Pauli operátor exponenciális értékének alkalmazása egy dyadic-frakció által megadott argumentummal.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align}, ahol $P _i $ a $i $ th eleme `paulis` , és hol $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.


### <a name="numerator--int"></a>számláló: [int](xref:microsoft.quantum.lang-ref.int)

A számláló ($k $) annak a szögnek a dyadic-frakciós ábrázolásában, amellyel a qubit-regisztrációt el kell forgatni.


### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

A két ($n $) ereje annak a szögnek a nevezőjét határozza meg, amellyel a qubit-regisztráció el lesz forgatva.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Regisztrálja, hogy a megadott rotációt alkalmazza a következőre:.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

