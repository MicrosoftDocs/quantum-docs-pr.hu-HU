---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 961c95e6787b69e35ca531fa36164cc988ad660d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847961"
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