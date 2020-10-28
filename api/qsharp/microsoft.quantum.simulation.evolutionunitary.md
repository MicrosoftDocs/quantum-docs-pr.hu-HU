---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724858"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="ea759-102">EvolutionUnitary-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="ea759-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="ea759-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ea759-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ea759-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea759-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea759-105">Egy egységes idő-Evolution operátort jelöl.</span><span class="sxs-lookup"><span data-stu-id="ea759-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="ea759-106">Az első paraméter a Time-Evolution (időtartam), a második paraméter pedig a qubit-regisztráció, amelyet az egységes egység végez.</span><span class="sxs-lookup"><span data-stu-id="ea759-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

