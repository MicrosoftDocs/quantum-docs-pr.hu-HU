---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709735"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="6ee09-102">NMisclassifications függvény</span><span class="sxs-lookup"><span data-stu-id="6ee09-102">NMisclassifications function</span></span>

<span data-ttu-id="6ee09-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6ee09-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6ee09-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ee09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ee09-105">A kikövetkeztetett címkék és a megfelelő címkék egy halmaza adott számú indexet ad vissza, amelyekben az egyes címkék eltérőek.</span><span class="sxs-lookup"><span data-stu-id="6ee09-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="6ee09-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6ee09-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="6ee09-107">javasolt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6ee09-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="6ee09-108">tényleges: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6ee09-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="6ee09-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ee09-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ee09-110">Az indexek száma `idx` `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="6ee09-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>