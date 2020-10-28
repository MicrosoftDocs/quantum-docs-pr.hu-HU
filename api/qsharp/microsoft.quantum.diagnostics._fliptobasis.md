---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713150"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="0f74c-102">_flipToBasis művelet</span><span class="sxs-lookup"><span data-stu-id="0f74c-102">_flipToBasis operation</span></span>

<span data-ttu-id="0f74c-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0f74c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0f74c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f74c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f74c-105">A $ \ket {0} \otimes\cdots\ket {0} $ és $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $ unitaries alkalmazza, ahol a $ \ket{\ psi_k} $ érték függ `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="0f74c-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="0f74c-106">Az érték `basis[k]` és a $ \ket{\ psi_k} $ közötti megfelelés a következő:</span><span class="sxs-lookup"><span data-stu-id="0f74c-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="0f74c-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0f74c-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="0f74c-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="0f74c-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="0f74c-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="0f74c-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="0f74c-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate: Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="0f74c-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0f74c-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0f74c-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="0f74c-112">alap: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0f74c-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0f74c-113">Az qubit-alapú állapot-azonosítók tömbje (0 <= azonosító <= 3), az egyik a qubits minden eleméhez.</span><span class="sxs-lookup"><span data-stu-id="0f74c-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0f74c-114">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f74c-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f74c-115">A Qubit.</span><span class="sxs-lookup"><span data-stu-id="0f74c-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f74c-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f74c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

