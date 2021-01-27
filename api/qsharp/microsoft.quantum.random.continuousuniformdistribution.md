---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842319"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egységes eloszlást ad vissza egy adott befogadó intervallumon belül.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Bevitel

### <a name="min--double"></a>minimum: [dupla](xref:microsoft.quantum.lang-ref.double)

A rajzolni kívánt legkisebb valós szám.


### <a name="max--double"></a>Max: [dupla](xref:microsoft.quantum.lang-ref.double)

A kirajzolni kívánt legnagyobb valós szám.



## <a name="output--continuousdistribution"></a>Kimenet: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Olyan eloszlás, amelynek véletlenszerű változói valós számok a és a közötti, `min` egységes valószínűséggel rendelkező, befogadó intervallumban `max` .

## <a name="example"></a>Példa

A következő Q # kódrészlet véletlenszerűen rajzolja meg a $0 $ és a $2 \pi $ közötti szöget:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)