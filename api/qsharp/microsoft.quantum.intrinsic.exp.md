---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212409"
---
# <a name="exp-operation"></a><span data-ttu-id="38fe4-102">Exp művelet</span><span class="sxs-lookup"><span data-stu-id="38fe4-102">Exp operation</span></span>

<span data-ttu-id="38fe4-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="38fe4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="38fe4-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="38fe4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="38fe4-105">Egy több qubit Pauli-operátor exponenciális értékének alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="38fe4-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="38fe4-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, ahol $P _i $ a $i $ th eleme `paulis` , és hol $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="38fe4-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="38fe4-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="38fe4-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="38fe4-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="38fe4-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="38fe4-109">A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.</span><span class="sxs-lookup"><span data-stu-id="38fe4-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="38fe4-110">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38fe4-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38fe4-111">Az adott qubit Pauli-kezelőre vonatkozó szög, amellyel a cél-regisztrációt el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="38fe4-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="38fe4-112">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="38fe4-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="38fe4-113">Regisztrálja, hogy a megadott rotációt alkalmazza a következőre:.</span><span class="sxs-lookup"><span data-stu-id="38fe4-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38fe4-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38fe4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

