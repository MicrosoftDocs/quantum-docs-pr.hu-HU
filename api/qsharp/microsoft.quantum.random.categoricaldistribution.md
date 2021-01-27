---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842353"
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

## <a name="example"></a>Példa

A következő Q # kód a 0 értéket jeleníti meg, amelynek a valószínűsége 30% és 1 a valószínűséggel 70%:

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```