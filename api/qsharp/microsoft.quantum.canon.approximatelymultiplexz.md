---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: b69b4de62241a7d16c2f07449115f864defda45d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841091"
---
# <a name="approximatelymultiplexz-operation"></a>ApproximatelyMultiplexZ művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy qubits tömbön alkalmazza a Pauli Z rotációs feltételt, amely egy adott tűréshatárnak megfelelően lerövidíti a kisméretű rotációs szögeket.

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ez a szorzás vezérelt, egységes műveletét alkalmazza, amely a $ \ theta_j $ szöget hajtja végre az qubit Pauli-operátoron $Z $ értékkel, ha az $n $-qubit Number State $ \ket{j} $ értékkel van elvégezve.
Ez a művelet különösen a következő lehet:

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{align} $ $

## <a name="input"></a>Bevitel

### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a tűréshatár, amely alatt a kis együtthatók csonkítva vannak.


### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

Legfeljebb $2 ^ n $ együttható, $ \ theta_j $. A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.


### <a name="control--littleendian"></a>vezérlés: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egyetlen qubit-regisztráció, amelyet $e ^ {i P \ theta_j} $ elforgat.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.

## <a name="references"></a>Hivatkozások

- A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. MultiplexZ](xref:Microsoft.Quantum.Canon.MultiplexZ)