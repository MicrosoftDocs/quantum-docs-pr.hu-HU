---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: dbbbb2b67dcf191c74e593f61eb894192acb4d48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854728"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="0a844-102">TimeDependentGeneratorSystem-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="0a844-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="0a844-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0a844-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0a844-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a844-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a844-105">Egy időfüggő dinamikus generátort jelöl, amely az idő és a dinamikus generátor értékének a függvénye.</span><span class="sxs-lookup"><span data-stu-id="0a844-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

