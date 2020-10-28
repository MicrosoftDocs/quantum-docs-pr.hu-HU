---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710939"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="4e8e4-102">TransformedContinuousDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="4e8e4-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="4e8e4-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4e8e4-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4e8e4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e8e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e8e4-105">A folyamatos terjesztés miatt egy új eloszlást ad vissza, amely egy adott függvény által az eredetit átalakítja.</span><span class="sxs-lookup"><span data-stu-id="4e8e4-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="4e8e4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4e8e4-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="4e8e4-107">átalakítás: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e8e4-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e8e4-108">Függvény, amely átalakítja az eredeti eloszlás változóit az átalakított terjesztésre.</span><span class="sxs-lookup"><span data-stu-id="4e8e4-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="4e8e4-109">eloszlás: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="4e8e4-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="4e8e4-110">Az átalakítandó eredeti eloszlás.</span><span class="sxs-lookup"><span data-stu-id="4e8e4-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="4e8e4-111">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="4e8e4-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="4e8e4-112">Egy új, a által `distribution` a transzformációhoz kapcsolódó eloszlás `transform` .</span><span class="sxs-lookup"><span data-stu-id="4e8e4-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>