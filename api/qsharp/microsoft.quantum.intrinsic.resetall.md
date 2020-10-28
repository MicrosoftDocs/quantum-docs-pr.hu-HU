---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711414"
---
# <a name="resetall-operation"></a>ResetAll művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag [](https://nuget.org/packages/)


A qubits egy tömbje, amely méri őket, és gondoskodik arról, hogy a (z) | 0 ⟩ állapotban legyenek, így biztonságosan közzétehetők.

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Azon qubits tömbje, amelynek állapotait vissza kell állítani a $ \ket $ értékre {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

