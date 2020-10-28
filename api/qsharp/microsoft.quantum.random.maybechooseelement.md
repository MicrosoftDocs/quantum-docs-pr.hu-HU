---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722170"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="37641-102">MaybeChooseElement művelet</span><span class="sxs-lookup"><span data-stu-id="37641-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="37641-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="37641-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="37641-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37641-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37641-105">Az adattömb és az indexek közötti eloszlás miatt a véletlenszerűen kiválasztott elem kiválasztását kísérli meg.</span><span class="sxs-lookup"><span data-stu-id="37641-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="37641-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37641-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="37641-107">adatértékek: 'T []</span><span class="sxs-lookup"><span data-stu-id="37641-107">data : 'T[]</span></span>

<span data-ttu-id="37641-108">Az a tömb, amelyből ki kell választani egy elemet.</span><span class="sxs-lookup"><span data-stu-id="37641-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="37641-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="37641-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="37641-110">Az indexeken keresztüli eloszlás `data` .</span><span class="sxs-lookup"><span data-stu-id="37641-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="37641-111">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="37641-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37641-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="37641-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37641-113">Nem</span><span class="sxs-lookup"><span data-stu-id="37641-113">'T</span></span>

