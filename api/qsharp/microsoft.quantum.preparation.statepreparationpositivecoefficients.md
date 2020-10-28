---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722898"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


Egy olyan műveletet ad vissza, amely előkészíti a megadott kvantum-állapotot.

A visszaadott művelet $U $ előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) a következő pozitív együtthatókkal: $ \ alpha_j \ge $0 az $n $-qubit számítási alapja $ \ket{0...0} $.

Az U művelet az újonnan lefoglalt regisztrációhoz $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

Legfeljebb $2 ^ n $ együttható, $ \ alpha_j $. A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.



## <a name="output--littleendian--unit-adj--ctl"></a>Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL

Az állapot-előkészítési egységes művelet $U $.

## <a name="remarks"></a>Megjegyzések

A negatív bemeneti együtthatók $ \ alpha_j < $0 a (z) $ | \ alpha_j | $ értékű pozitív értékkel lesznek kezelve. `coefficients` a $ \ alpha_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.