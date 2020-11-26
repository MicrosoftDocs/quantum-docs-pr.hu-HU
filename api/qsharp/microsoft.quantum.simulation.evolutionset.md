---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229409"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="316de-102">EvolutionSet-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="316de-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="316de-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="316de-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="316de-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="316de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="316de-105">Egy olyan kaput jelöl, amely könnyen megvalósítható és használható a szimulációs algoritmusok megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="316de-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="316de-106">A készletben lévő elemeket az a indexeli  <xref:microsoft.quantum.simulation.generatorindex> , és az egyes készleteket a-tól származó függvények írják le `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> , amelyek az időt jelképező valós számmal rendelkező műveletek.</span><span class="sxs-lookup"><span data-stu-id="316de-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

