---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856073"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="30111-102">EvolutionSet-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="30111-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="30111-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="30111-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="30111-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30111-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30111-105">Egy olyan kaput jelöl, amely könnyen megvalósítható és használható a szimulációs algoritmusok megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="30111-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="30111-106">A készletben lévő elemeket az a indexeli  <xref:microsoft.quantum.simulation.generatorindex> , és az egyes készleteket a-tól származó függvények írják le `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> , amelyek az időt jelképező valós számmal rendelkező műveletek.</span><span class="sxs-lookup"><span data-stu-id="30111-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

