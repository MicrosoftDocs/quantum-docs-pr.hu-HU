---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723990"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


Véletlenszerű valós számot rajzol egy adott befogadó intervallumban.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Bevitel

### <a name="min--double"></a>minimum: [dupla](xref:microsoft.quantum.lang-ref.double)

A rajzolni kívánt legkisebb valós szám.


### <a name="max--double"></a>Max: [dupla](xref:microsoft.quantum.lang-ref.double)

A kirajzolni kívánt legnagyobb valós szám.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

Egy véletlenszerű valós szám a befogadó intervallumban `min` , `max` és egységes valószínűséggel.

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)