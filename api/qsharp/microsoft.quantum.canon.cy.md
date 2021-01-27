---
uid: Microsoft.Quantum.Canon.CY
title: CY-művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840732"
---
# <a name="cy-operation"></a><span data-ttu-id="d705b-102">CY-művelet</span><span class="sxs-lookup"><span data-stu-id="d705b-102">CY operation</span></span>

<span data-ttu-id="d705b-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d705b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d705b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d705b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d705b-105">A vezérelt-Y (CY) kaput alkalmazza egy pár qubits.</span><span class="sxs-lookup"><span data-stu-id="d705b-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="d705b-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i 0 & 0 \\ \\ & i & 0 \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="d705b-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d705b-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d705b-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="d705b-108">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d705b-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d705b-109">A CY Gate qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="d705b-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d705b-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d705b-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d705b-111">A CY Gate cél qubit.</span><span class="sxs-lookup"><span data-stu-id="d705b-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d705b-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d705b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d705b-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d705b-113">Remarks</span></span>

<span data-ttu-id="d705b-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="d705b-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```