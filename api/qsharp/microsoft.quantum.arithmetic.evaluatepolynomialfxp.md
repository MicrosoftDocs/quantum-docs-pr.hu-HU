---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 4f6ed4b34af2e63dd8ee31fb9b93119e06e3ecbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223187"
---
# <a name="evaluatepolynomialfxp-operation"></a>EvaluatePolynomialFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


A polinom kiértékelése rögzített pontú ábrázolásban.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

A polinom és a kettős tömb együttes hatékonysága, azaz a következő tömb: $ [a_0, a_1,..., a_d] $ a polinom $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.


### <a name="result--fixedpoint"></a>eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Kimeneti rögzített pont száma, amely $P (x) $ értéket fogja tárolni. Kezdetben a $ \ket $ állapotban kell lennie {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

