---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719861"
---
# <a name="trottersimulationalgorithm-function"></a>TrotterSimulationAlgorithm függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


`SimulationAlgorithm` a függvény, amely egy Trotter – Suzuki-lebomlást használ az idő-Evolution operátor _exp (-iHt)_ megközelítő értékének eléréséhez.

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a>Bevitel

### <a name="trotterstepsize--double"></a>trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

Szimulált idő időbeli alakulása egyetlen Trotter lépésben.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

A Trotter-integrátor sorrendje. Ennek 1 vagy páros számnak kell lennie.



## <a name="output--simulationalgorithm"></a>Kimenet: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)

Egy `SimulationAlgorithm` típus.