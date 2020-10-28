---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722815"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


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