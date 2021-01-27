---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854571"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="ff56f-102">UnivariateOptimizationResult-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="ff56f-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="ff56f-103">Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="ff56f-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="ff56f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff56f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff56f-105">Egy univariate függvény optimalizálásának eredményét jelöli.</span><span class="sxs-lookup"><span data-stu-id="ff56f-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="ff56f-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="ff56f-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="ff56f-107">Koordináta: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff56f-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff56f-108">Az a bemenet, amelyben az optimális érték található.</span><span class="sxs-lookup"><span data-stu-id="ff56f-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="ff56f-109">Érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff56f-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff56f-110">A függvény által visszaadott érték az optimálisnál.</span><span class="sxs-lookup"><span data-stu-id="ff56f-110">Value returned by the function at its optimum.</span></span>