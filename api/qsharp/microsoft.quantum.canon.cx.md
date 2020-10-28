---
uid: Microsoft.Quantum.Canon.CX
title: CX-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716371"
---
# <a name="cx-operation"></a><span data-ttu-id="e5651-102">CX-művelet</span><span class="sxs-lookup"><span data-stu-id="e5651-102">CX operation</span></span>

<span data-ttu-id="e5651-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e5651-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e5651-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5651-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5651-105">A vezérelt-X (CX) kaput alkalmazza egy pár qubits.</span><span class="sxs-lookup"><span data-stu-id="e5651-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="e5651-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="e5651-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e5651-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e5651-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="e5651-108">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e5651-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e5651-109">A CX-kapu qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="e5651-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e5651-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e5651-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e5651-111">A CX-kapu cél qubit.</span><span class="sxs-lookup"><span data-stu-id="e5651-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e5651-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5651-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e5651-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e5651-113">Remarks</span></span>

<span data-ttu-id="e5651-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="e5651-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="e5651-115">és:</span><span class="sxs-lookup"><span data-stu-id="e5651-115">and to:</span></span>

```qsharp
CNOT(control, target);
```