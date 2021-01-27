---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853720"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Példa

A következő Q # kódrészlet véletlenszerűen görget egy hat oldalas Die:

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)