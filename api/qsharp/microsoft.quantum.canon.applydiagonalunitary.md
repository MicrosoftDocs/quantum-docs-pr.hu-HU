---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 14ab8d7beddda26594967225934d472d52bac9eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841893"
---
# <a name="applydiagonalunitary-operation"></a>ApplyDiagonalUnitary művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Összetett fázisokat alkalmaz a qubits regiszterének numerikus állapotára.

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ez a művelet egy olyan átlós egységes implementációt valósít meg, amely egy összetett fázist alkalmaz $e ^ {i \ theta_j} $ értékre a következő $n $-qubit Number State $ \ket{j} $.
Ez a művelet különösen a következő lehet:

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.
\end{align} $ $

## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

Legfeljebb $2 ^ n $ együttható, $ \ theta_j $. A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.

## <a name="references"></a>Hivatkozások

- A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApproximatelyApplyDiagonalUnitary](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)