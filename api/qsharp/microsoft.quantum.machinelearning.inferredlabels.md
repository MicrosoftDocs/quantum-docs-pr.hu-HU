---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722479"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="82122-102">InferredLabels függvény</span><span class="sxs-lookup"><span data-stu-id="82122-102">InferredLabels function</span></span>

<span data-ttu-id="82122-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="82122-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="82122-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82122-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82122-105">A besorolási valószínűségek és a torzítások tömbje az egyes valószínűségek alapján kikövetkeztetett címkét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="82122-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="82122-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="82122-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="82122-107">torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82122-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82122-108">A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.</span><span class="sxs-lookup"><span data-stu-id="82122-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="82122-109">valószínűségek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="82122-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="82122-110">Több minta besorolási valószínűségének tömbje, amely jellemzően a besorolási gyakoriságok becslését eredményezi.</span><span class="sxs-lookup"><span data-stu-id="82122-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="82122-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="82122-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="82122-112">Az egyes besorolási valószínűségtől kikövetkeztetett címke.</span><span class="sxs-lookup"><span data-stu-id="82122-112">The label inferred from each classification probability.</span></span>