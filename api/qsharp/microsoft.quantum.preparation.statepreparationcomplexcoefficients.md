---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722912"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


Egy olyan műveletet ad vissza, amely egy adott kvantum-állapotot készít elő.

A visszaadott művelet $U $ felkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási alapból $ \ket{0...0} $ értékre.

Az U egy újonnan lefoglalt regisztrációra vonatkozó műveletét $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="coefficients--complexpolar"></a>együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Legfeljebb $2 ^ n $ összetett együtthatók, amelyek abszolút értéke és a $ (r_j, t_j) $. A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.



## <a name="output--littleendian--unit-adj--ctl"></a>Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL

Az állapot-előkészítési egységes művelet $U $.

## <a name="remarks"></a>Megjegyzések

A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel. `coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.