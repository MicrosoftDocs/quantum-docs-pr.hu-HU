---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840075"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="d32a3-102">TrotterStepSize függvény</span><span class="sxs-lookup"><span data-stu-id="d32a3-102">TrotterStepSize function</span></span>

<span data-ttu-id="d32a3-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d32a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d32a3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d32a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d32a3-105">Kiszámítja a Trotter-szimulációs algoritmus rekurzív megvalósításának Trotter.</span><span class="sxs-lookup"><span data-stu-id="d32a3-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d32a3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d32a3-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="d32a3-107">megrendelés: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d32a3-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="d32a3-108">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d32a3-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="d32a3-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d32a3-109">Remarks</span></span>

<span data-ttu-id="d32a3-110">Ez a művelet egy eltérő indexelési konvenciót használ, mint a [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="d32a3-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="d32a3-111">Különösen `DecomposedIntoTimeStepsCA(_, 4)` megfelel a skaláris $p _2 (\lambda) $ a Quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="d32a3-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>