---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198690"
---
# <a name="resetall-operation"></a>ResetAll művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A qubits egy tömbje, amely méri őket, és gondoskodik arról, hogy a (z) | 0 ⟩ állapotban legyenek, így biztonságosan közzétehetők.

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Azon qubits tömbje, amelynek állapotait vissza kell állítani a $ \ket $ értékre {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

