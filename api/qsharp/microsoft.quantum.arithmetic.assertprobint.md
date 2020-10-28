---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721361"
---
# <a name="assertprobint-operation"></a>AssertProbInt művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


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

