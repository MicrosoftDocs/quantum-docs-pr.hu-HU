---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 9b12dc4a05c99aad319799f8c6526cd3085e6dcd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847968"
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