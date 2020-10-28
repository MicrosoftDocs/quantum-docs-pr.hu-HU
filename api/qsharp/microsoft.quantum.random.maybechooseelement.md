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
# <a name="maybechooseelement-operation"></a>MaybeChooseElement művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


Az adattömb és az indexek közötti eloszlás miatt a véletlenszerűen kiválasztott elem kiválasztását kísérli meg.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Bevitel

### <a name="data--t"></a>adatértékek: 'T []

Az a tömb, amelyből ki kell választani egy elemet.


### <a name="indexdistribution--discretedistribution"></a>indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Az indexeken keresztüli eloszlás `data` .



## <a name="output--boolt"></a>Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

