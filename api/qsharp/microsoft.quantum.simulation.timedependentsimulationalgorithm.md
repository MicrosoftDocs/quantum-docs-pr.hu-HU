---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725754"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="8b989-102">TimeDependentSimulationAlgorithm-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="8b989-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="8b989-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8b989-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8b989-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b989-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b989-105">Egy időfüggő szimulációs algoritmust jelöl.</span><span class="sxs-lookup"><span data-stu-id="8b989-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="8b989-106">Egy időfüggő szimulációs módszer átalakítja a <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="8b989-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="8b989-107">az egyes időintervallumok szerinti egységes időbeli alakuláshoz.</span><span class="sxs-lookup"><span data-stu-id="8b989-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

