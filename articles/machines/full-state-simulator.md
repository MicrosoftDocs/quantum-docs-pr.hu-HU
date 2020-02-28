---
title: Teljes állapotú szimulátor
description: 'Megtudhatja, hogyan futtathatja a Q # programokat a Microsoft Quantum Development Kit teljes állapotú szimulátoron.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906117"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Quantum Development Kit teljes állapotú szimulátor

A Quantum Development Kit olyan teljes állapotú kvantum-szimulátort biztosít, mint a [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) a Microsoft Research-től.
Ez a szimulátor felhasználható a Q #-ban írt kvantum-algoritmusok végrehajtásához és hibakereséséhez a számítógépen.

Ez a Quantum Simulator a `QuantumSimulator` osztályon keresztül érhető el. A szimulátor használatához egyszerűen hozza létre ennek az osztálynak egy példányát, és adja át a végrehajtani kívánt kvantum-művelet `Run` metódusának a többi paraméterrel együtt:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

A `QuantumSimulator` osztály <xref:System.IDisposable>t valósít meg, ezért a `Dispose` metódust kell meghívni, ha a szimulátor példányát már nem használják. Ennek a legjobb módja, ha a szimulátort egy `using` utasításon belül becsomagolja, ahogy a fenti példában is látható.

## <a name="seed"></a>kezdőérték

A `QuantumSimulator` véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében. Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata. Ezt úgy teheti meg, hogy a `QuantumSimulator`konstruktorában a `randomNumberGeneratorSeed` paraméterrel megadhat egy magot a véletlenszerű számú generátorhoz:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Szálak

A `QuantumSimulator` a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges. Alapértelmezés szerint az OpenMP az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubittel rendelkező programok gyakran lassabban futnak, mert a szükséges koordináció mellett eltörpül a tényleges munka. Ezt úgy lehet megjavítani, ha a környezeti változót kis számra állítja `OMP_NUM_THREADS`. Nagyon nagy általánosságban nézve 1 szál nagyjából 4 qubithez elég, onnantól pedig qubitenként további 1 szálra van szükség, de ezek a számok nagyban függenek az adott algoritmustól.

