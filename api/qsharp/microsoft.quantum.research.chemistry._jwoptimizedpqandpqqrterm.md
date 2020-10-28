---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d9f0d17c091ae771702e4047d17e1769d6bb294
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722143"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a>_JWOptimizedPQandPQQRTerm művelet

Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)

Csomag [](https://nuget.org/packages/)


Alkalmazza az idő-evolúciót az a által leírt PQ vagy PQQR kifejezéssel `GeneratorIndex` .

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="term--generatorindex"></a>kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQ vagy PQQr kifejezést jelképez.


### <a name="stepsize--double"></a>stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

Az idő időbeli alakulása.


### <a name="parityqubit--qubit"></a>parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, amely meghatározza a Time-Evolution előjelét.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A Hamilton qubits.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

