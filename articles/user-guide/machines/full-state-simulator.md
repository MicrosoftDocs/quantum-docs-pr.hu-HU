---
title: Teljes állapotú Quantum Simulator – Quantum Development Kit
description: 'Megtudhatja, hogyan futtathatja a Q # programokat a Microsoft Quantum Development Kit teljes állapotú szimulátoron.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871178"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Quantum Development Kit (QDK) teljes állapotú szimulátor

A QDK teljes állapotú szimulátort biztosít, amely a helyi számítógépen lévő kvantum-gépet szimulálja. A teljes állapot szimulátorral a Q #-ban írt kvantum-algoritmusokat futtathat és hibakeresést végezhet, akár 30 qubits is felhasználhatja. A teljes állapot szimulátor hasonló a [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) platformon a Microsoft Research szolgáltatásban használt kvantum-szimulátorhoz.

## <a name="invoking-and-running-the-full-state-simulator"></a>A teljes állapotú szimulátor meghívása és futtatása

A teljes állapotú szimulátort a osztályon keresztül teheti elérhetővé `QuantumSimulator` . További részleteket a [Q # program futtatásának módjai](xref:microsoft.quantum.guide.host-programs)című témakörben talál.

### <a name="invoking-the-simulator-from-c"></a>A szimulátor meghívása C-ről #

Hozza létre a osztály egy példányát, `QuantumSimulator` majd adja át a `Run` kvantum-művelet metódusának, valamint a további paramétereket.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Mivel az `QuantumSimulator` osztály implementálja az <xref:System.IDisposable> illesztőfelületet, meg kell hívnia a `Dispose` metódust, ha már nincs szüksége a szimulátor példányára. Ennek a legjobb módja a szimulátor deklarációjának és műveleteinek becsomagolása egy [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) utasításon belül, amely automatikusan meghívja a `Dispose` metódust.

### <a name="invoking-the-simulator-from-python"></a>A szimulátor meghívása a Pythonból

Használja a Q # Python könyvtár [szimulálása ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódusát az importált q # művelettel:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>A szimulátor meghívása a parancssorból

Ha Q # programot futtat a parancssorból, a teljes állapot szimulátor az alapértelmezett célszámítógép. Igény szerint a **--Simulator** (vagy **-s** parancsikon) paraméterrel megadhatja a kívánt célszámítógépet. Mindkét alábbi parancs a teljes állapotú szimulátor használatával futtat egy programot. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>A szimulátor meghívása Juptyer-jegyzetfüzetekről

A Q # művelet futtatásához használja az IQ # Magic Command [% szimulálása](xref:microsoft.quantum.iqsharp.magic-ref.simulate) parancsot.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>A szimulátor kivetése

Alapértelmezés szerint a teljes állapot szimulátor egy véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében. Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata. Egy C#-programban ezt úgy hajthatja végre, hogy a `QuantumSimulator` paraméterrel a konstruktorban található véletlenszerű számú generátorhoz biztosít magot `randomNumberGeneratorSeed` .

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Szálak konfigurálása

A teljes körű állapot szimulátor a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges. Alapértelmezés szerint a OpenMP dokumentáció az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubits rendelkező programok gyakran lassan futnak, mert a szükséges koordináció a tényleges munka. Ezt a környezeti változó kis számra állításával javíthatja `OMP_NUM_THREADS` . A hüvelykujj szabályként legfeljebb négy qubits konfigurálhat egy szálat, majd qubit egy további szálat. Előfordulhat, hogy az algoritmustól függően módosítania kell a változót.

## <a name="see-also"></a>Lásd még

- [Quantum-erőforrások kalkulátora](xref:microsoft.quantum.machines.resources-estimator)
- [Quantum Toffoli szimulátor](xref:microsoft.quantum.machines.toffoli-simulator)
- [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)