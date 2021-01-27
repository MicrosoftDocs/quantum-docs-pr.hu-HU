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
# <a name="maybechooseelement-operation"></a>MaybeChooseElement művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>Példa

A következő Q # kódrészlet véletlenszerűen választ ki egy tömböt tartalmazó elemet:

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```