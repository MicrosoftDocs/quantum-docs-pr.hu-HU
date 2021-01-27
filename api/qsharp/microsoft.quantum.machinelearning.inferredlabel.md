---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848417"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="fa7c8-102">InferredLabel függvény</span><span class="sxs-lookup"><span data-stu-id="fa7c8-102">InferredLabel function</span></span>

<span data-ttu-id="fa7c8-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fa7c8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fa7c8-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fa7c8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="fa7c8-105">A besorolási valószínűség és a torzítás miatt a rendszer visszaadja az adott valószínűség alapján kikövetkeztetett címkét.</span><span class="sxs-lookup"><span data-stu-id="fa7c8-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="fa7c8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fa7c8-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="fa7c8-107">torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa7c8-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa7c8-108">A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.</span><span class="sxs-lookup"><span data-stu-id="fa7c8-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="fa7c8-109">valószínűség: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa7c8-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa7c8-110">Egy adott minta besorolási valószínűsége, jellemzően a besorolás gyakoriságának becslése miatt.</span><span class="sxs-lookup"><span data-stu-id="fa7c8-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="fa7c8-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa7c8-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa7c8-112">A címkét a megadott besorolási valószínűség alapján következtették ki.</span><span class="sxs-lookup"><span data-stu-id="fa7c8-112">The label inferred from the given classification probability.</span></span>