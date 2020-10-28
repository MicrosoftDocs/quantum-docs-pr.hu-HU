---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722045"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Szimulálható kapuk készletének és a Pauli-alapú bővítésnek a dinamikus generátort jelöli.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Kimenet: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Egy `EvolutionSet` , a (z) és a (z) egy `GeneratorIndex` EvolutionUnitary.

## <a name="remarks"></a>Megjegyzések

Ezt a részleges alkalmazása szerzi be <xref:microsoft.quantum.simulation.paulievolutionfunction> .