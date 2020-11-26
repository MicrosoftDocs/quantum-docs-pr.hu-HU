---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210250"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy diszkrét kategorikus eloszlást ad vissza, amely során a rendszer explicit módon megadja az adott kimenetek véges listájának valószínűségét.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Bevitel

### <a name="probs--double"></a>Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]

A kategorikus eloszlás minden egyes eredményének valószínűsége.
Előfordulhat, hogy ezek a valószínűségek nem normalizáltak, de mindegyiknek nem negatívnak kell lennie.



## <a name="output--discretedistribution"></a>Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Az index a `i` valószínűséggel `probs[i] / sum` , ahol `sum` a a `probs` által megadott összeg `Fold(PlusD, 0.0, probs)` .