---
uid: Microsoft.Quantum.Canon.CZ
title: CZ-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716343"
---
# <a name="cz-operation"></a><span data-ttu-id="117f2-102">CZ-művelet</span><span class="sxs-lookup"><span data-stu-id="117f2-102">CZ operation</span></span>

<span data-ttu-id="117f2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="117f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="117f2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="117f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="117f2-105">A vezérelt-Z (CZ) kaput alkalmazza egy pár qubits.</span><span class="sxs-lookup"><span data-stu-id="117f2-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="117f2-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="117f2-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="117f2-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="117f2-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="117f2-108">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="117f2-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="117f2-109">A CZ Gate qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="117f2-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="117f2-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="117f2-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="117f2-111">A CZ Gate cél qubit.</span><span class="sxs-lookup"><span data-stu-id="117f2-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="117f2-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="117f2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="117f2-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="117f2-113">Remarks</span></span>

<span data-ttu-id="117f2-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="117f2-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```