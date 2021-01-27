---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854609"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="961b8-102">LocalUnivariateMinimum függvény</span><span class="sxs-lookup"><span data-stu-id="961b8-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="961b8-103">Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="961b8-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="961b8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="961b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="961b8-105">Egy univariate függvényhez tartozó helyi minimális értéket adja vissza, amely egy aranysárga intervallumos keresés használatával történik.</span><span class="sxs-lookup"><span data-stu-id="961b8-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="961b8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="961b8-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="961b8-107">FN: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="961b8-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="961b8-108">A univariate függvényt a lehető legkisebbre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="961b8-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="961b8-109">korlátok: ([dupla](xref:microsoft.quantum.lang-ref.double),[dupla](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="961b8-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="961b8-110">Az az időköz, amelyben a helyi minimumot meg kell találni.</span><span class="sxs-lookup"><span data-stu-id="961b8-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="961b8-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="961b8-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="961b8-112">A függvény bemenetének pontossága.</span><span class="sxs-lookup"><span data-stu-id="961b8-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="961b8-113">A helyi Optima-keresés folytatódni fog, amíg az intervallum nem kisebb a tűréshatárnál.</span><span class="sxs-lookup"><span data-stu-id="961b8-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="961b8-114">Kimenet: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="961b8-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="961b8-115">Az adott függvény helyi Optima, amely a megadott határokon belül található.</span><span class="sxs-lookup"><span data-stu-id="961b8-115">A local optima of the given function, located within the given bounds.</span></span>