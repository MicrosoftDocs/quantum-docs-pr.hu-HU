---
title: Teljes állapotú szimulátor
description: 'Megtudhatja, hogyan futtathatja a Q # programokat a Microsoft Quantum Development Kit teljes állapotú szimulátoron.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274947"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Quantum Development Kit teljes állapotú szimulátor

A Quantum Development Kit olyan teljes állapotú kvantum-szimulátort biztosít, mint a [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) a Microsoft Research-től.
Ez a szimulátor felhasználható a Q #-ban írt kvantum-algoritmusok végrehajtásához és hibakereséséhez a számítógépen.

Ezt a kvantum-szimulátort a osztályon keresztül teszi elérhetővé `QuantumSimulator` . A szimulátor használatához egyszerűen hozza létre az osztály egy példányát, és adja át a `Run` végrehajtani kívánt kvantum-művelet metódusának a többi paraméterrel együtt:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

Az `QuantumSimulator` osztály implementálja <xref:System.IDisposable> , így a `Dispose` metódust akkor kell meghívni, ha már nincs használatban a szimulátor példánya. Ennek a legjobb módja, ha egy utasításon belül becsomagolja a szimulátort `using` , ahogy a fenti példában is látható.

## <a name="seed"></a>Kezdőérték

A `QuantumSimulator` véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében. Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata. Ezt úgy teheti meg, hogy a (z) paraméterrel létrehoz egy magot a véletlenszerű számú generátorhoz a `QuantumSimulator` konstruktorban `randomNumberGeneratorSeed` :

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Szálak

A `QuantumSimulator` a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges. Alapértelmezés szerint az OpenMP az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubittel rendelkező programok gyakran lassabban futnak, mert a szükséges koordináció mellett eltörpül a tényleges munka. Ezt úgy lehet megjavítani, hogy a környezeti változót `OMP_NUM_THREADS` kis számra állítja be. Nagyon nagy általánosságban nézve 1 szál nagyjából 4 qubithez elég, onnantól pedig qubitenként további 1 szálra van szükség, de ezek a számok nagyban függenek az adott algoritmustól.

