---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230345"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Szimulálható kapuk készletének és a Pauli-alapú bővítésnek a dinamikus generátort jelöli.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Kimenet: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Egy `EvolutionSet` , a (z) és a (z) egy `GeneratorIndex` EvolutionUnitary.

## <a name="remarks"></a>Megjegyzések

Ezt a részleges alkalmazása szerzi be <xref:microsoft.quantum.simulation.paulievolutionfunction> .