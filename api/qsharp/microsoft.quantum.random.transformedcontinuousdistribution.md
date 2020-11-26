---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226264"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="b5583-102">TransformedContinuousDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="b5583-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="b5583-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b5583-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b5583-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b5583-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b5583-105">A folyamatos terjesztés miatt egy új eloszlást ad vissza, amely egy adott függvény által az eredetit átalakítja.</span><span class="sxs-lookup"><span data-stu-id="b5583-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="b5583-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b5583-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="b5583-107">átalakítás: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5583-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5583-108">Függvény, amely átalakítja az eredeti eloszlás változóit az átalakított terjesztésre.</span><span class="sxs-lookup"><span data-stu-id="b5583-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="b5583-109">eloszlás: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b5583-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b5583-110">Az átalakítandó eredeti eloszlás.</span><span class="sxs-lookup"><span data-stu-id="b5583-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="b5583-111">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b5583-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b5583-112">Egy új, a által `distribution` a transzformációhoz kapcsolódó eloszlás `transform` .</span><span class="sxs-lookup"><span data-stu-id="b5583-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>