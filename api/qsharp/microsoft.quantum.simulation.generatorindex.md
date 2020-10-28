---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723906"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="0b65c-102">GeneratorIndex-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="0b65c-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="0b65c-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0b65c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0b65c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b65c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b65c-105">Egyetlen primitív kifejezést képvisel az összes dinamikus generátor készletében, például a Hermitian operátorok esetében, amelyekhez az adott generátor által adott idő-evolúciós folyamaton alapuló Térkép áll rendelkezésre `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="0b65c-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="0b65c-106">Az első elem (int [], Double []) indexeli ezt az egyszeri kifejezést – például a 0,5-as együtthatóval rendelkező XXY-karakterláncot ([1, 1, 2], [0,5]) indexeli.</span><span class="sxs-lookup"><span data-stu-id="0b65c-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="0b65c-107">Azt is megteheti, hogy egy folytonos változó (például X cos φ + Y Sin φ) által Hamiltonians paramétert a (z) ([], [φ]) által reprezentált példány lehet.</span><span class="sxs-lookup"><span data-stu-id="0b65c-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="0b65c-108">A második elem indexeli azt az alrendszert, amelyen a létrehozó működik.</span><span class="sxs-lookup"><span data-stu-id="0b65c-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="0b65c-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0b65c-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0b65c-110">Az an értelmezése nincs `GeneratorIndex` definiálva, kivéve a generátorok adott készletére mutató hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="0b65c-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b65c-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0b65c-111">See Also</span></span>

- [<span data-ttu-id="0b65c-112">Microsoft. Quantum. szimulációs. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="0b65c-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="0b65c-113">Microsoft. Quantum. szimulációs. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="0b65c-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)