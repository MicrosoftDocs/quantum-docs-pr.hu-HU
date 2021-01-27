---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: b2411950b90eb676b1da53bd06bde648099e2db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858889"
---
# <a name="trottersimulationalgorithmimpl-operation"></a>TrotterSimulationAlgorithmImpl művelet

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ismétlődő hívásokat kezdeményez `TrotterStep` a Time-Evolution operátor exp (_-iHt_) eléréséhez.

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="trotterstepsize--double"></a>trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

Szimulált idő időbeli alakulása egyetlen Trotter lépésben.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

A Trotter-integrátor sorrendje. Ennek 1 vagy páros számnak kell lennie.


### <a name="maxtime--double"></a>maxTime: [dupla](xref:microsoft.quantum.lang-ref.double)

A szimuláció $t $ teljes időtartama.


### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

A szimulálni kívánt rendszer teljes leírása.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A qubits a szimuláció alapján működött.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

