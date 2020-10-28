---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722520"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="e6abe-102">InferredLabel függvény</span><span class="sxs-lookup"><span data-stu-id="e6abe-102">InferredLabel function</span></span>

<span data-ttu-id="e6abe-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e6abe-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e6abe-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6abe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6abe-105">A besorolási valószínűség és a torzítás miatt a rendszer visszaadja az adott valószínűség alapján kikövetkeztetett címkét.</span><span class="sxs-lookup"><span data-stu-id="e6abe-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="e6abe-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e6abe-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="e6abe-107">torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6abe-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6abe-108">A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.</span><span class="sxs-lookup"><span data-stu-id="e6abe-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="e6abe-109">valószínűség: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6abe-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6abe-110">Egy adott minta besorolási valószínűsége, jellemzően a besorolás gyakoriságának becslése miatt.</span><span class="sxs-lookup"><span data-stu-id="e6abe-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="e6abe-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e6abe-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e6abe-112">A címkét a megadott besorolási valószínűség alapján következtették ki.</span><span class="sxs-lookup"><span data-stu-id="e6abe-112">The label inferred from the given classification probability.</span></span>