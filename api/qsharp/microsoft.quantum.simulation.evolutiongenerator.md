---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 9e0fc5a232070c238aad943ab73f064999237c15
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229443"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="4a67c-102">EvolutionGenerator-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="4a67c-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="4a67c-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4a67c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4a67c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a67c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a67c-105">A dinamikus generátort szimulálható kapuk készlete jelöli meg, és ennek az alapja a bővítése.</span><span class="sxs-lookup"><span data-stu-id="4a67c-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="4a67c-106">A feltételek számának utolsó paramétere.</span><span class="sxs-lookup"><span data-stu-id="4a67c-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

