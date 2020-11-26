---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: dae23db9bee34be4aa99d96799efad64a66d7193
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229324"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="e12da-102">GeneratorIndex-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="e12da-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="e12da-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e12da-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e12da-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e12da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e12da-105">Egyetlen primitív kifejezést képvisel az összes dinamikus generátor készletében, például a Hermitian operátorok esetében, amelyekhez az adott generátor által adott idő-evolúciós folyamaton alapuló Térkép áll rendelkezésre `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="e12da-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="e12da-106">Az első elem (int [], Double []) indexeli ezt az egyszeri kifejezést – például a 0,5-as együtthatóval rendelkező XXY-karakterláncot ([1, 1, 2], [0,5]) indexeli.</span><span class="sxs-lookup"><span data-stu-id="e12da-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="e12da-107">Azt is megteheti, hogy egy folytonos változó (például X cos φ + Y Sin φ) által Hamiltonians paramétert a (z) ([], [φ]) által reprezentált példány lehet.</span><span class="sxs-lookup"><span data-stu-id="e12da-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="e12da-108">A második elem indexeli azt az alrendszert, amelyen a létrehozó működik.</span><span class="sxs-lookup"><span data-stu-id="e12da-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="e12da-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e12da-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e12da-110">Az an értelmezése nincs `GeneratorIndex` definiálva, kivéve a generátorok adott készletére mutató hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="e12da-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="e12da-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e12da-111">See Also</span></span>

- [<span data-ttu-id="e12da-112">Microsoft. Quantum. szimulációs. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="e12da-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="e12da-113">Microsoft. Quantum. szimulációs. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="e12da-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)