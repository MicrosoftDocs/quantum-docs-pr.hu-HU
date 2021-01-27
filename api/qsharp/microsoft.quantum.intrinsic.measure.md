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
# <a name="measure-operation"></a><span data-ttu-id="1ec73-102">Mérték művelet</span><span class="sxs-lookup"><span data-stu-id="1ec73-102">Measure operation</span></span>

<span data-ttu-id="1ec73-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1ec73-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1ec73-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1ec73-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1ec73-105">Egy vagy több qubits közös mérését hajtja végre a megadott Pauli-alapokon.</span><span class="sxs-lookup"><span data-stu-id="1ec73-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="1ec73-106">A kimenet eredményét a következő eloszlás adja meg: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align}, ahol $P _i $ a $i $ th eleme `bases` , és ahol $N = \texttt{length} (\texttt{bases}) $.</span><span class="sxs-lookup"><span data-stu-id="1ec73-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="1ec73-107">Ez azt eredményezi, hogy a mérés egy $d $ értéket ad vissza, `Result` hogy a megfigyelt mérési hatás sajátérték értéke $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="1ec73-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="1ec73-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1ec73-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="1ec73-109">alapok: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1ec73-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1ec73-110">A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.</span><span class="sxs-lookup"><span data-stu-id="1ec73-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1ec73-111">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1ec73-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1ec73-112">A mérendő qubits regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="1ec73-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1ec73-113">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="1ec73-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1ec73-114">`Zero` Ha a $ + $1 sajátérték meg van figyelve, és `One` Ha a $-$1 sajátérték meg van figyelve.</span><span class="sxs-lookup"><span data-stu-id="1ec73-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ec73-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1ec73-115">Remarks</span></span>

<span data-ttu-id="1ec73-116">Ha az alap tömb és a qubit tömb eltérő hosszúságú, akkor a művelet sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="1ec73-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>