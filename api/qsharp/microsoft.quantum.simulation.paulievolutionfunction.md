---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: e581cd4d0a3caf96bece9979a1d850aad7842727
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230360"
---
# <a name="paulievolutionfunction-function"></a>PauliEvolutionFunction függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Szimulálható kapuk készletének és a Pauli-alapú bővítésnek a dinamikus generátort jelöli.

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Bevitel

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Egy olyan generátor-index, amely a Pauli-alapú, egységes evolúció formájában jelenik meg.



## <a name="output--evolutionunitary"></a>Kimenet: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

A `EvolutionUnitary` "generatorIndex" kifejezésben hivatkozott idő szerinti evolúció.