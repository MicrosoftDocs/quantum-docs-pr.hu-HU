---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223051"
---
# <a name="identicalpointposfactfxp-function"></a>IdenticalPointPosFactFxP függvény

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Azt állítja be, hogy a megadott tömbben lévő összes rögzített szintű szám azonos ponttal rendelkezik, amikor a legkevésbé jelentős mennyiségtől számít. Azaz a BITS mínusz pont pozíciójának állandónak kell lennie a tömbben lévő összes rögzített számnál.

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="fixedpoints--fixedpoint"></a>fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

A kompatibilitáshoz ellenőrizendő kvantum-pontokból álló számok tömbje (kijelentések használata).



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

