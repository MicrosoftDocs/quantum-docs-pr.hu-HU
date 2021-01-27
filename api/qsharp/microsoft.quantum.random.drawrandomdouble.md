---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847625"
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

## <a name="example"></a>Példa

A következő Q # kódrészlet véletlenszerűen rajzolja meg a $0 $ és a $2 \pi $ közötti szöget:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)