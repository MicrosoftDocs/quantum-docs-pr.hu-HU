---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842226"
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