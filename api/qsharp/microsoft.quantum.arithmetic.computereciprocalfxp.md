---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223391"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Kiszámítja a $1/x $ értéket egy rögzített pont $x $ értékű számra.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="x--fixedpoint"></a>x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

A rögzített pont számának invertálása.


### <a name="result--fixedpoint"></a>eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Az eredményt tároló rögzített pont száma. A $ \ket{0.0} $ értékre kell inicializálni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

