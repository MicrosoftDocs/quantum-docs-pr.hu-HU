---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857773"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A folyamatos terjesztés miatt egy új eloszlást ad vissza, amely egy adott függvény által az eredetit átalakítja.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Bevitel

### <a name="transform--double---double"></a>átalakítás: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)

Függvény, amely átalakítja az eredeti eloszlás változóit az átalakított terjesztésre.


### <a name="distribution--continuousdistribution"></a>eloszlás: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Az átalakítandó eredeti eloszlás.



## <a name="output--continuousdistribution"></a>Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Egy új, a által `distribution` a transzformációhoz kapcsolódó eloszlás `transform` .

## <a name="example"></a>Példa

A következő két eloszlás azonos:

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```