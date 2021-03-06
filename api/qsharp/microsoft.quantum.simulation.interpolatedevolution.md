---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 4d2e04513c96c6e5f41e85f1df685e91e2973098
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858092"
---
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A két generátor közötti, egységes ütemtervtel rendelkező és egy olyan műveletet ad vissza, amely a szimulált evolúciót alkalmazza az eredményül kapott időfüggő generátorban egy qubit-regiszterbe.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="interpolationtime--double"></a>interpolationTime: [dupla](xref:microsoft.quantum.lang-ref.double)

Az interpoláció végrehajtásához szükséges idő.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

A kezdeti generátor szimulálja az evolúciót a alatt.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

A végső generátor szimulálja az evolúciót a alatt.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Egy időfüggő szimuláló algoritmus, amely az evolúció szimulálása érdekében lesz felhasználva az egységes interpolációs ütemtervben.



## <a name="output--qubit--unit--is-adj--ctl"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL



## <a name="remarks"></a>Megjegyzések

Ha az interpolációs idő úgy van kiválasztva, hogy megfeleljen a adiabatic feltételeinek, akkor ez a függvény olyan műveletet ad vissza, amely adiabatic állapot-előkészítést végez a végső dinamikus generátorhoz.