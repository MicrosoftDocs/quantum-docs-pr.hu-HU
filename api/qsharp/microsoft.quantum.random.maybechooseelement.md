---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856116"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="c6db3-102">MaybeChooseElement művelet</span><span class="sxs-lookup"><span data-stu-id="c6db3-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="c6db3-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c6db3-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c6db3-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c6db3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c6db3-105">Az adattömb és az indexek közötti eloszlás miatt a véletlenszerűen kiválasztott elem kiválasztását kísérli meg.</span><span class="sxs-lookup"><span data-stu-id="c6db3-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="c6db3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c6db3-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="c6db3-107">adatértékek: 'T []</span><span class="sxs-lookup"><span data-stu-id="c6db3-107">data : 'T[]</span></span>

<span data-ttu-id="c6db3-108">Az a tömb, amelyből ki kell választani egy elemet.</span><span class="sxs-lookup"><span data-stu-id="c6db3-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="c6db3-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="c6db3-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="c6db3-110">Az indexeken keresztüli eloszlás `data` .</span><span class="sxs-lookup"><span data-stu-id="c6db3-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="c6db3-111">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="c6db3-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c6db3-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c6db3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c6db3-113">Nem</span><span class="sxs-lookup"><span data-stu-id="c6db3-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="c6db3-114">Példa</span><span class="sxs-lookup"><span data-stu-id="c6db3-114">Example</span></span>

<span data-ttu-id="c6db3-115">A következő Q # kódrészlet véletlenszerűen választ ki egy tömböt tartalmazó elemet:</span><span class="sxs-lookup"><span data-stu-id="c6db3-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```