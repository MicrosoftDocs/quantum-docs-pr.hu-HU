---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814190"
---
# <a name="normaldistribution-function"></a>NormalDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy normál eloszlást ad vissza, amely egy adott középérték és variancia.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Bevitel

### <a name="mean--double"></a>középérték: [dupla](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>variancia: [dupla](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Példa

A következő 10 mintát rajzol a normál eloszlásból a 2. és a 0,1-es standard szórással:

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Random. StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)