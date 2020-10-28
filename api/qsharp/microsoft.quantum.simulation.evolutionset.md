---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710616"
---
# <a name="evolutionset-user-defined-type"></a>EvolutionSet-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Egy olyan kaput jelöl, amely könnyen megvalósítható és használható a szimulációs algoritmusok megvalósításához.

A készletben lévő elemeket az a indexeli  <xref:microsoft.quantum.simulation.generatorindex> , és az egyes készleteket a-tól származó függvények írják le `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> , amelyek az időt jelképező valós számmal rendelkező műveletek.

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

