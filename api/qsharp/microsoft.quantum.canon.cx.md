---
uid: Microsoft.Quantum.Canon.CX
title: CX-művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840761"
---
# <a name="cx-operation"></a><span data-ttu-id="1f971-102">CX-művelet</span><span class="sxs-lookup"><span data-stu-id="1f971-102">CX operation</span></span>

<span data-ttu-id="1f971-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f971-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f971-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f971-105">A vezérelt-X (CX) kaput alkalmazza egy pár qubits.</span><span class="sxs-lookup"><span data-stu-id="1f971-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="1f971-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, ahol a sorok és oszlopok a Quantum Concepts útmutatóban vannak rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="1f971-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1f971-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1f971-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="1f971-108">vezérlés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1f971-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1f971-109">A CX-kapu qubit vezérlése.</span><span class="sxs-lookup"><span data-stu-id="1f971-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1f971-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1f971-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1f971-111">A CX-kapu cél qubit.</span><span class="sxs-lookup"><span data-stu-id="1f971-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f971-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f971-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1f971-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1f971-113">Remarks</span></span>

<span data-ttu-id="1f971-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="1f971-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="1f971-115">és:</span><span class="sxs-lookup"><span data-stu-id="1f971-115">and to:</span></span>

```qsharp
CNOT(control, target);
```