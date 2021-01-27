---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Nem kategorizált besorolási függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853926"
---
# <a name="misclassifications-function"></a><span data-ttu-id="367cf-102">Nem kategorizált besorolási függvény</span><span class="sxs-lookup"><span data-stu-id="367cf-102">Misclassifications function</span></span>

<span data-ttu-id="367cf-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="367cf-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="367cf-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="367cf-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="367cf-105">A kikövetkeztetett címkék és a megfelelő címkék halmaza miatt a rendszer az indexeket adja vissza, amelyekben az egyes címkék eltérőek.</span><span class="sxs-lookup"><span data-stu-id="367cf-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="367cf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="367cf-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="367cf-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="367cf-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="367cf-108">Egy adott képzésre vagy érvényesítési csoportra hivatkozó címkék.</span><span class="sxs-lookup"><span data-stu-id="367cf-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="367cf-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="367cf-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="367cf-110">Egy adott képzés vagy érvényesítési csoport valódi címkéi.</span><span class="sxs-lookup"><span data-stu-id="367cf-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="367cf-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="367cf-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="367cf-112">Olyan indexek tömbje `idx` , amelyek ilyenek `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="367cf-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="367cf-113">Példa</span><span class="sxs-lookup"><span data-stu-id="367cf-113">Example</span></span>

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```