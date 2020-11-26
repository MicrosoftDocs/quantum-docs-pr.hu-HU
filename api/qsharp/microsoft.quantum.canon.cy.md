---
uid: Microsoft.Quantum.Canon.CY
title: CY-művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216574"
---
# <a name="cy-operation"></a><span data-ttu-id="0a43a-102">CY-művelet</span><span class="sxs-lookup"><span data-stu-id="0a43a-102">CY operation</span></span>

<span data-ttu-id="0a43a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a43a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a43a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a43a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a43a-105">A vezérelt-Y (CY) kaput alkalmazza egy pár qubits.</span><span class="sxs-lookup"><span data-stu-id="0a43a-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="0a43a-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i 0 & 0 \\ \\ & i & 0 \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="0a43a-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a43a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0a43a-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="0a43a-108">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0a43a-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0a43a-109">A CY Gate qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="0a43a-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0a43a-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0a43a-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0a43a-111">A CY Gate cél qubit.</span><span class="sxs-lookup"><span data-stu-id="0a43a-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a43a-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a43a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0a43a-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0a43a-113">Remarks</span></span>

<span data-ttu-id="0a43a-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="0a43a-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```