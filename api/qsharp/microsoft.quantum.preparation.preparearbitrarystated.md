---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: PrepareArbitraryStateD művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 61f6614821951435828cd28edeb1447cb33f3648
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842375"
---
# <a name="preparearbitrarystated-operation"></a>PrepareArbitraryStateD művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az egyes együtthatók és egy kis endian kódolt kvantum-regisztráció miatt a rendszer előkészíti az adott regiszteren belüli olyan állapotot, amelyet a megadott együtthatók ismertetnek.

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ez a művelet előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási \ket{0 \cdots 0} $ értékről.
Különösen a művelet műveletét szimulálhatja az egységes átalakítás $U $, amely az összes nulla állapotot használja

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

Legfeljebb $2 ^ n $ valódi együtthatók tömbje. A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A Qubit endian formátumban regisztrálja a kódolási számokat. Ezt a rendszer a számítási alapon a $ \ket{0...0} $ értékkel inicializálja.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel. `coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.

## <a name="references"></a>Hivatkozások

- A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. előkészítés. ApproximatelyPrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)