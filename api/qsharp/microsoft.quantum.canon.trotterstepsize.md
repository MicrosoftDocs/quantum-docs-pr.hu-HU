---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204691"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="e5f8f-102">TrotterStepSize függvény</span><span class="sxs-lookup"><span data-stu-id="e5f8f-102">TrotterStepSize function</span></span>

<span data-ttu-id="e5f8f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e5f8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e5f8f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5f8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5f8f-105">Kiszámítja a Trotter-szimulációs algoritmus rekurzív megvalósításának Trotter.</span><span class="sxs-lookup"><span data-stu-id="e5f8f-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="e5f8f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e5f8f-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="e5f8f-107">megrendelés: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5f8f-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="e5f8f-108">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5f8f-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="e5f8f-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e5f8f-109">Remarks</span></span>

<span data-ttu-id="e5f8f-110">Ez a művelet egy eltérő indexelési konvenciót használ, mint a [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="e5f8f-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="e5f8f-111">Különösen `DecomposedIntoTimeStepsCA(_, 4)` megfelel a skaláris $p _2 (\lambda) $ a Quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="e5f8f-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>