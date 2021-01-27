---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857800"
---
# <a name="standardnormaldistribution-function"></a><span data-ttu-id="f6959-102">StandardNormalDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="f6959-102">StandardNormalDistribution function</span></span>

<span data-ttu-id="f6959-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f6959-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f6959-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f6959-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f6959-105">Egy normál eloszlást ad vissza, amelynek középértéke 0 és variancia 1.</span><span class="sxs-lookup"><span data-stu-id="f6959-105">Returns a normal distribution with mean 0 and variance 1.</span></span>

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a><span data-ttu-id="f6959-106">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f6959-106">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="f6959-107">Példa</span><span class="sxs-lookup"><span data-stu-id="f6959-107">Example</span></span>

<span data-ttu-id="f6959-108">A következő 10 mintát rajzol a normál normál eloszlásból:</span><span class="sxs-lookup"><span data-stu-id="f6959-108">The following draws 10 samples from the standard normal distribution:</span></span>

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a><span data-ttu-id="f6959-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f6959-109">See Also</span></span>

- [<span data-ttu-id="f6959-110">Microsoft. Quantum. Random. NormalDistribution</span><span class="sxs-lookup"><span data-stu-id="f6959-110">Microsoft.Quantum.Random.NormalDistribution</span></span>](xref:Microsoft.Quantum.Random.NormalDistribution)