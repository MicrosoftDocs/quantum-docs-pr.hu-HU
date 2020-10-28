---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724326"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="102e6-102">UnivariateOptimizationResult-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="102e6-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="102e6-103">Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="102e6-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="102e6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="102e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="102e6-105">Egy univariate függvény optimalizálásának eredményét jelöli.</span><span class="sxs-lookup"><span data-stu-id="102e6-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="102e6-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="102e6-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="102e6-107">Koordináta: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="102e6-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="102e6-108">Az a bemenet, amelyben az optimális érték található.</span><span class="sxs-lookup"><span data-stu-id="102e6-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="102e6-109">Érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="102e6-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="102e6-110">A függvény által visszaadott érték az optimálisnál.</span><span class="sxs-lookup"><span data-stu-id="102e6-110">Value returned by the function at its optimum.</span></span>