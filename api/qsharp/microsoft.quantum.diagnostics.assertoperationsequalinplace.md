---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853488"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A két művelet miatt a azt állítja, hogy az összes bemeneti állapot esetében azonos módon működnek.

Ez az állítás a műveleteknek a (z) $V _0 \otimes... \otimes V_ {n-1} $, ahol a $V _k $ egyike a (z) $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ (+ 1 Eigenstate Pauli Y operátor) állapotának ellenőrzésével valósul meg.

Ez az állítás $n $ qubits használ, és több hívást igényel a műveletekhez képest.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, $n $, amelyeken a műveletek `givenU` és `expectedU` működnek.


### <a name="givenu--qubit--unit"></a>givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits műveletet kell ellenőrizni.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

A (z) $n $ qubits hivatkozási művelete, amelyet `givenU` össze kell hasonlítani.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Hivatkozások

A $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ állapotú államok alapja Chuang-Nielsen a következő: [ *i. L., M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)