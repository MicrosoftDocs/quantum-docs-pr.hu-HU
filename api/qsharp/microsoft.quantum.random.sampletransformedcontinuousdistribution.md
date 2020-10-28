---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723976"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="96747-102">SampleTransformedContinuousDistribution művelet</span><span class="sxs-lookup"><span data-stu-id="96747-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="96747-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="96747-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="96747-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96747-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96747-105">Csak belső művelet az átalakított disztribúciók mintavételezéséhez.</span><span class="sxs-lookup"><span data-stu-id="96747-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="96747-106">Csak részleges alkalmazáson keresztül használható.</span><span class="sxs-lookup"><span data-stu-id="96747-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="96747-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="96747-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="96747-108">átalakítás: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96747-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="96747-109">eloszlás: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="96747-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="96747-110">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96747-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

