---
title: Quantum Development Kit teljes állapotú szimulátor | Microsoft Docs
description: A Microsoft Quantum Development Kit teljes állapotú Szimulátorjának áttekintése
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184678"
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

## <a name="seed"></a>Kezdőérték

A `QuantumSimulator` véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében. Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata. Ezt úgy teheti meg, hogy a `QuantumSimulator`konstruktorában a `randomNumberGeneratorSeed` paraméterrel megadhat egy magot a véletlenszerű számú generátorhoz:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Szálak

A `QuantumSimulator` a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges. Alapértelmezés szerint a OpenMP dokumentáció az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubits rendelkező programok gyakran lassabban futnak, mert a szükséges koordináció eltörpül a tényleges munkától. Ezt úgy lehet megjavítani, ha a környezeti változót kis számra állítja `OMP_NUM_THREADS`. Egy nagyon durva szabály, 1 szál akár 4 qubits is jó, és a qubit egy további szála jó, bár ez nagy mértékben függ az algoritmustól.

