---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711022"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="ed226-102">LocalUnivariateMinimum függvény</span><span class="sxs-lookup"><span data-stu-id="ed226-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="ed226-103">Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="ed226-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="ed226-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed226-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed226-105">Egy univariate függvényhez tartozó helyi minimális értéket adja vissza, amely egy aranysárga intervallumos keresés használatával történik.</span><span class="sxs-lookup"><span data-stu-id="ed226-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="ed226-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ed226-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="ed226-107">FN: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed226-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed226-108">A univariate függvényt a lehető legkisebbre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="ed226-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="ed226-109">korlátok: ([dupla](xref:microsoft.quantum.lang-ref.double),[dupla](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="ed226-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="ed226-110">Az az időköz, amelyben a helyi minimumot meg kell találni.</span><span class="sxs-lookup"><span data-stu-id="ed226-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ed226-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed226-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed226-112">A függvény bemenetének pontossága.</span><span class="sxs-lookup"><span data-stu-id="ed226-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="ed226-113">A helyi Optima-keresés folytatódni fog, amíg az intervallum nem kisebb a tűréshatárnál.</span><span class="sxs-lookup"><span data-stu-id="ed226-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="ed226-114">Kimenet: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="ed226-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="ed226-115">Az adott függvény helyi Optima, amely a megadott határokon belül található.</span><span class="sxs-lookup"><span data-stu-id="ed226-115">A local optima of the given function, located within the given bounds.</span></span>