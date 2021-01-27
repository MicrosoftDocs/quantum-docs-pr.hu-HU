---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851141"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy véletlenszerű egész számot rajzol egy adott befogadó tartományban.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="min--int"></a>min.: [int](xref:microsoft.quantum.lang-ref.int)

A rajzolni kívánt legkisebb egész szám.


### <a name="max--int"></a>Max.: [int](xref:microsoft.quantum.lang-ref.int)

A kirajzolni kívánt legnagyobb egész szám.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész szám a befogadó tartományban a és a érték között, `min` `max` egységes valószínűséggel.

## <a name="example"></a>Példa

A következő Q # kódrészlet véletlenszerűen görget egy hat oldalas Die:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)