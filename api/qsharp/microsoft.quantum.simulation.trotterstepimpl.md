---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725321"
---
# <a name="trotterstepimpl-operation"></a>TrotterStepImpl művelet

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Az a-ben foglalt kifejezéssel valósítja meg az időbeli alakulást `GeneratorSystem` .

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

A szimulálni kívánt rendszer teljes leírása.


### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Egész index egy kifejezésre a leírt rendszeren.


### <a name="stepsize--double"></a>stepsize: [dupla](xref:microsoft.quantum.lang-ref.double)

Szorzó az időtartamra vonatkozóan – a által indexelt időszak szerinti evolúció `idx` .


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A qubits a szimuláció alapján működött.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

