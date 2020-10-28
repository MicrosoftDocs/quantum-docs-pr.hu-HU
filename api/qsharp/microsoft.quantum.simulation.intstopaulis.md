---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709454"
---
# <a name="intstopaulis-function"></a>IntsToPaulis függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Egész számok tömbjét alakítja át egy qubit Pauli-operátorok tömbje számára.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Bevitel

### <a name="ints--int"></a>csoportcsomagból: [int](xref:microsoft.quantum.lang-ref.int)[]

Az egész számokból álló tömb a `0..3`  Pauli-operátorokra konvertálandó tartományban.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis`A Pauli-operátorok tömbje `Pauli[]` azonos hosszúságú, mint `ints` `paulis[idxPauli]` a megadott elemnek `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .