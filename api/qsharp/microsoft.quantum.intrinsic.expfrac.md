---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198995"
---
# <a name="expfrac-operation"></a>ExpFrac művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy több qubit Pauli operátor exponenciális értékének alkalmazása egy dyadic-frakció által megadott argumentummal.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align}, ahol $P _i $ a $i $ th eleme `paulis` , és hol $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
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

