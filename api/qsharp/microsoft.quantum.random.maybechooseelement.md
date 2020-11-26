---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192859"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="1cbf6-102">MaybeChooseElement művelet</span><span class="sxs-lookup"><span data-stu-id="1cbf6-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="1cbf6-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1cbf6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1cbf6-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1cbf6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1cbf6-105">Az adattömb és az indexek közötti eloszlás miatt a véletlenszerűen kiválasztott elem kiválasztását kísérli meg.</span><span class="sxs-lookup"><span data-stu-id="1cbf6-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="1cbf6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1cbf6-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="1cbf6-107">adatértékek: 'T []</span><span class="sxs-lookup"><span data-stu-id="1cbf6-107">data : 'T[]</span></span>

<span data-ttu-id="1cbf6-108">Az a tömb, amelyből ki kell választani egy elemet.</span><span class="sxs-lookup"><span data-stu-id="1cbf6-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="1cbf6-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="1cbf6-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="1cbf6-110">Az indexeken keresztüli eloszlás `data` .</span><span class="sxs-lookup"><span data-stu-id="1cbf6-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="1cbf6-111">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="1cbf6-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1cbf6-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1cbf6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1cbf6-113">Nem</span><span class="sxs-lookup"><span data-stu-id="1cbf6-113">'T</span></span>

