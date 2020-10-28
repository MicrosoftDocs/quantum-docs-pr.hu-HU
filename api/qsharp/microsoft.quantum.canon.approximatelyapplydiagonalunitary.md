---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716819"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a>ApproximatelyApplyDiagonalUnitary művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Összetett fázisokat alkalmaz a qubits regiszterének numerikus állapotára, és lerövidíti a kis forgási szögeket egy adott tolerancia alapján.

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Leírás

Ez a művelet egy olyan átlós egységes implementációt valósít meg, amely egy összetett fázist alkalmaz $e ^ {i \ theta_j} $ értékre a következő $n $-qubit Number State $ \ket{j} $.
Ez a művelet különösen a következő lehet:

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.
\end{align} $ $

## <a name="input"></a>Bevitel

### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a tűréshatár, amely alatt a kis együtthatók csonkítva vannak.


### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

Legfeljebb $2 ^ n $ együttható, $ \ theta_j $. A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.

## <a name="references"></a>Referencia

- A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyDiagonalUnitary](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)