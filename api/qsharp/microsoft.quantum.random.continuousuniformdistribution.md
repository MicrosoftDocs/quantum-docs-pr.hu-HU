---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709427"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution függvény

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)