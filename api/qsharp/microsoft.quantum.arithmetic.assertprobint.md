---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843411"
---
# <a name="assertprobint-operation"></a>AssertProbInt művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja, hogy a kvantum-regiszter adott állapotának valószínűsége a várt érték.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Leírás

Adott egy $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, azt állítja, hogy a $ | \ alpha_j | ^ 2 $ a (z) $j $ indexelt állapotú $ \ket{j} $ indexben a várt érték szerepel.

## <a name="input"></a>Bevitel

### <a name="stateindex--int"></a>stateIndex: [int](xref:microsoft.quantum.lang-ref.int)

Egy regiszter által jelzett, $ \ket{j} $ állapotú $ $j $ index `LittleEndian` .


### <a name="expected--double"></a>várt érték: [Double](xref:microsoft.quantum.lang-ref.double)

A várt érték: $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A qubit regisztrálja a $ \ket{\psi} $ tárolót kis endian formátumban.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A tényleges és a várt érték közötti különbség abszolút tűréshatára.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

Tegyük fel, hogy a `qubits` regisztráció egy 3 qubit Quantum State $ \ket{\psi} = \ SQRT {1/8} \ ket {0} + \ SQRT {7/8} \ ket {6} $ értékű, kis endian formátumban kódolja.
Ez azt jelenti, hogy a szám állapota $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ és $ \ket {6} \equiv\ket {0} \ket {1} \ket {1} $. Ezután a következő érvényesítések sikeresek lesznek:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```