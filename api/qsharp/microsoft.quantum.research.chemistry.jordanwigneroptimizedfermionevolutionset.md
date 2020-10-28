---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: d2d916655b7538b39d5739d67dbb3fc9920cf67a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722142"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="f6711-102">JordanWignerOptimizedFermionEvolutionSet függvény</span><span class="sxs-lookup"><span data-stu-id="f6711-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="f6711-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f6711-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f6711-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6711-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6711-105">Szimulálható kapuk készletének és a Pauli-alapú bővítésnek a dinamikus generátort jelöli.</span><span class="sxs-lookup"><span data-stu-id="f6711-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="f6711-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f6711-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="f6711-107">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f6711-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f6711-108">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="f6711-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="f6711-109">Kimenet: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="f6711-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="f6711-110">Egy `EvolutionSet` , az `GeneratorIndex` JWOptimized-t egy "EvolutionUnitary" képezi.</span><span class="sxs-lookup"><span data-stu-id="f6711-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>