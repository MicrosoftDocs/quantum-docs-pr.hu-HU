---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720293"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


Egy adott befogadó tartományon belüli egységes eloszlást ad vissza.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Bevitel

### <a name="min--int"></a>min.: [int](xref:microsoft.quantum.lang-ref.int)

A rajzolni kívánt legkisebb egész szám.


### <a name="max--int"></a>Max.: [int](xref:microsoft.quantum.lang-ref.int)

A kirajzolni kívánt legnagyobb egész szám.



## <a name="output--discretedistribution"></a>Kimenet: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Olyan eloszlás, amelynek véletlenszerű változói a befogadó tartományon belüli egész szám, `min` `max` egységes valószínűséggel.

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)