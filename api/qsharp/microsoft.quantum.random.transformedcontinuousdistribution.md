---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710939"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


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