---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211780"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="7f37f-102">InferredLabel függvény</span><span class="sxs-lookup"><span data-stu-id="7f37f-102">InferredLabel function</span></span>

<span data-ttu-id="7f37f-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7f37f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7f37f-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7f37f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7f37f-105">A besorolási valószínűség és a torzítás miatt a rendszer visszaadja az adott valószínűség alapján kikövetkeztetett címkét.</span><span class="sxs-lookup"><span data-stu-id="7f37f-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="7f37f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7f37f-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="7f37f-107">torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7f37f-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7f37f-108">A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.</span><span class="sxs-lookup"><span data-stu-id="7f37f-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="7f37f-109">valószínűség: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7f37f-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7f37f-110">Egy adott minta besorolási valószínűsége, jellemzően a besorolás gyakoriságának becslése miatt.</span><span class="sxs-lookup"><span data-stu-id="7f37f-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="7f37f-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f37f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f37f-112">A címkét a megadott besorolási valószínűség alapján következtették ki.</span><span class="sxs-lookup"><span data-stu-id="7f37f-112">The label inferred from the given classification probability.</span></span>