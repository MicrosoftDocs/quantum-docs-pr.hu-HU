---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814190"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="a1f9f-102">NormalDistribution függvény</span><span class="sxs-lookup"><span data-stu-id="a1f9f-102">NormalDistribution function</span></span>

<span data-ttu-id="a1f9f-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a1f9f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a1f9f-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a1f9f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a1f9f-105">Egy normál eloszlást ad vissza, amely egy adott középérték és variancia.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="a1f9f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a1f9f-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="a1f9f-107">középérték: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1f9f-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="a1f9f-108">variancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1f9f-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="a1f9f-109">Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="a1f9f-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="a1f9f-110">Példa</span><span class="sxs-lookup"><span data-stu-id="a1f9f-110">Example</span></span>

<span data-ttu-id="a1f9f-111">A következő 10 mintát rajzol a normál eloszlásból a 2. és a 0,1-es standard szórással:</span><span class="sxs-lookup"><span data-stu-id="a1f9f-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="a1f9f-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a1f9f-112">See Also</span></span>

- [<span data-ttu-id="a1f9f-113">Microsoft. Quantum. Random. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="a1f9f-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)