---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819012"
---
# <a name="exp-operation"></a><span data-ttu-id="dee2b-102">Exp művelet</span><span class="sxs-lookup"><span data-stu-id="dee2b-102">Exp operation</span></span>

<span data-ttu-id="dee2b-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="dee2b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="dee2b-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dee2b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dee2b-105">Egy több qubit Pauli-operátor exponenciális értékének alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="dee2b-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="dee2b-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, ahol $P _i $ a $i $ th eleme `paulis` , és hol $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="dee2b-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dee2b-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dee2b-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="dee2b-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="dee2b-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="dee2b-109">A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.</span><span class="sxs-lookup"><span data-stu-id="dee2b-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="dee2b-110">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dee2b-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dee2b-111">Az adott qubit Pauli-kezelőre vonatkozó szög, amellyel a cél-regisztrációt el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="dee2b-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="dee2b-112">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dee2b-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dee2b-113">Regisztrálja, hogy a megadott rotációt alkalmazza a következőre:.</span><span class="sxs-lookup"><span data-stu-id="dee2b-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dee2b-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dee2b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

