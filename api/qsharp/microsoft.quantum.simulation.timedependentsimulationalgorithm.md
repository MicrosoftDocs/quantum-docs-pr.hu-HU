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
# <a name="timedependentsimulationalgorithm-user-defined-type"></a>TimeDependentSimulationAlgorithm-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Egy időfüggő szimulációs algoritmust jelöl.

Egy időfüggő szimulációs módszer átalakítja a <xref:microsoft.quantum.simulation.evolutionschedule>
az egyes időintervallumok szerinti egységes időbeli alakuláshoz.

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

