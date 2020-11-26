---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192944"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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