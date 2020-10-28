---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNEM művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722674"
---
# <a name="cnot-operation"></a><span data-ttu-id="114e7-102">CNEM művelet</span><span class="sxs-lookup"><span data-stu-id="114e7-102">CNOT operation</span></span>

<span data-ttu-id="114e7-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="114e7-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="114e7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="114e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="114e7-105">A vezérelt-NOT (CNEM) kaput alkalmazza egy qubits.</span><span class="sxs-lookup"><span data-stu-id="114e7-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="114e7-106">\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="114e7-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="114e7-107">a sorok és oszlopok sorrendjét a Quantum Concepts útmutatója tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="114e7-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="114e7-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="114e7-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="114e7-109">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="114e7-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="114e7-110">A CNEM-kapu qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="114e7-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="114e7-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="114e7-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="114e7-112">A CNEM kapu cél qubit.</span><span class="sxs-lookup"><span data-stu-id="114e7-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="114e7-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="114e7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="114e7-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="114e7-114">Remarks</span></span>

<span data-ttu-id="114e7-115">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="114e7-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```