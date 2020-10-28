---
uid: Microsoft.Quantum.Canon.CY
title: CY-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716357"
---
# <a name="cy-operation"></a><span data-ttu-id="e36bf-102">CY-művelet</span><span class="sxs-lookup"><span data-stu-id="e36bf-102">CY operation</span></span>

<span data-ttu-id="e36bf-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e36bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e36bf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e36bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e36bf-105">A vezérelt-Y (CY) kaput alkalmazza egy pár qubits.</span><span class="sxs-lookup"><span data-stu-id="e36bf-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="e36bf-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i 0 & 0 \\ \\ & i & 0 \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="e36bf-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e36bf-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e36bf-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="e36bf-108">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e36bf-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e36bf-109">A CY Gate qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="e36bf-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e36bf-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e36bf-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e36bf-111">A CY Gate cél qubit.</span><span class="sxs-lookup"><span data-stu-id="e36bf-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e36bf-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e36bf-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e36bf-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e36bf-113">Remarks</span></span>

<span data-ttu-id="e36bf-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="e36bf-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```