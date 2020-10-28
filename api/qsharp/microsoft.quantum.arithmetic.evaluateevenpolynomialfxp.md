---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721204"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>EvaluateEvenPolynomialFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Kiértékeli a páros polinom-t egy rögzített pontos ábrázolásban.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

A páros polinom egyfajta együtthatója kettős tömbként, azaz a következő tömbben: $ [a_0, a_1,..., a_k] $ a páros polinom $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.


### <a name="result--fixedpoint"></a>eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Kimeneti rögzített pont száma, amely $P (x) $ értéket fogja tárolni. Kezdetben a $ \ket $ állapotban kell lennie {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

