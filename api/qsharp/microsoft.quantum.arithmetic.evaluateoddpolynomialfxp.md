---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223221"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>EvaluateOddPolynomialFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Kiértékeli a páratlan polinom-t egy rögzített pontos ábrázolásban.

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

A páratlan polinom és a kettős tömb együttes hatékonysága, azaz a következő tömb: $ [a_0, a_1,..., a_k] $ a páratlan polinom $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.


### <a name="result--fixedpoint"></a>eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Kimeneti rögzített pont szám, amely a P (x) értéket fogja tárolni. Kezdetben a $ \ket $ állapotban kell lennie {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

