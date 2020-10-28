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
# <a name="paulievolutionset-function"></a><span data-ttu-id="48b29-102">PauliEvolutionSet függvény</span><span class="sxs-lookup"><span data-stu-id="48b29-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="48b29-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="48b29-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="48b29-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48b29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48b29-105">Szimulálható kapuk készletének és a Pauli-alapú bővítésnek a dinamikus generátort jelöli.</span><span class="sxs-lookup"><span data-stu-id="48b29-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="48b29-106">Kimenet: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="48b29-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="48b29-107">Egy `EvolutionSet` , a (z) és a (z) egy `GeneratorIndex` EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="48b29-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="48b29-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="48b29-108">Remarks</span></span>

<span data-ttu-id="48b29-109">Ezt a részleges alkalmazása szerzi be <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="48b29-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>