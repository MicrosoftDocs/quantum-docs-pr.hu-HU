---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223986"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="e4097-102">_flipToBasis művelet</span><span class="sxs-lookup"><span data-stu-id="e4097-102">_flipToBasis operation</span></span>

<span data-ttu-id="e4097-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e4097-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e4097-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e4097-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e4097-105">A $ \ket {0} \otimes\cdots\ket {0} $ és $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $ unitaries alkalmazza, ahol a $ \ket{\ psi_k} $ érték függ `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="e4097-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="e4097-106">Az érték `basis[k]` és a $ \ket{\ psi_k} $ közötti megfelelés a következő:</span><span class="sxs-lookup"><span data-stu-id="e4097-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="e4097-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="e4097-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="e4097-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="e4097-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="e4097-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="e4097-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="e4097-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate: Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="e4097-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e4097-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e4097-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="e4097-112">alap: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e4097-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e4097-113">Az qubit-alapú állapot-azonosítók tömbje (0 <= azonosító <= 3), az egyik a qubits minden eleméhez.</span><span class="sxs-lookup"><span data-stu-id="e4097-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e4097-114">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4097-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4097-115">A Qubit.</span><span class="sxs-lookup"><span data-stu-id="e4097-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4097-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4097-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

