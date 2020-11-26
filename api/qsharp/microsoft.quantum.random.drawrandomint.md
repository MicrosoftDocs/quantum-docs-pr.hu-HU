---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192910"
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

## <a name="remarks"></a>Megjegyzések

Sikertelen, ha `max <= min` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)