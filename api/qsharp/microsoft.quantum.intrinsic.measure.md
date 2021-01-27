---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Mérték művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818771"
---
# <a name="measure-operation"></a>Mérték művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy vagy több qubits közös mérését hajtja végre a megadott Pauli-alapokon.

A kimenet eredményét a következő eloszlás adja meg: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align}, ahol $P _i $ a $i $ th eleme `bases` , és ahol $N = \texttt{length} (\texttt{bases}) $.
Ez azt eredményezi, hogy a mérés egy $d $ értéket ad vissza, `Result` hogy a megfigyelt mérési hatás sajátérték értéke $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Bevitel

### <a name="bases--pauli"></a>alapok: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A mérendő qubits regisztrálása.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

`Zero` Ha a $ + $1 sajátérték meg van figyelve, és `One` Ha a $-$1 sajátérték meg van figyelve.

## <a name="remarks"></a>Megjegyzések

Ha az alap tömb és a qubit tömb eltérő hosszúságú, akkor a művelet sikertelen lesz.