---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230531"
---
# <a name="intstopaulis-function"></a>IntsToPaulis függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egész számok tömbjét alakítja át egy qubit Pauli-operátorok tömbje számára.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Bevitel

### <a name="ints--int"></a>csoportcsomagból: [int](xref:microsoft.quantum.lang-ref.int)[]

Az egész számokból álló tömb a `0..3`  Pauli-operátorokra konvertálandó tartományban.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis`A Pauli-operátorok tömbje `Pauli[]` azonos hosszúságú, mint `ints` `paulis[idxPauli]` a megadott elemnek `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .