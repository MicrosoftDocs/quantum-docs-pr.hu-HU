---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 98241f77bfbd73929896bb114fad060001016a86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856086"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="acb1e-102">EvolutionGenerator-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="acb1e-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="acb1e-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="acb1e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="acb1e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acb1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acb1e-105">A dinamikus generátort szimulálható kapuk készlete jelöli meg, és ennek az alapja a bővítése.</span><span class="sxs-lookup"><span data-stu-id="acb1e-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="acb1e-106">A feltételek számának utolsó paramétere.</span><span class="sxs-lookup"><span data-stu-id="acb1e-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

