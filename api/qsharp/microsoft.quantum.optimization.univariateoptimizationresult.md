---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194032"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="ad853-102">UnivariateOptimizationResult-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="ad853-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="ad853-103">Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="ad853-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="ad853-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad853-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad853-105">Egy univariate függvény optimalizálásának eredményét jelöli.</span><span class="sxs-lookup"><span data-stu-id="ad853-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="ad853-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="ad853-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="ad853-107">Koordináta: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad853-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad853-108">Az a bemenet, amelyben az optimális érték található.</span><span class="sxs-lookup"><span data-stu-id="ad853-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="ad853-109">Érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad853-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad853-110">A függvény által visszaadott érték az optimálisnál.</span><span class="sxs-lookup"><span data-stu-id="ad853-110">Value returned by the function at its optimum.</span></span>