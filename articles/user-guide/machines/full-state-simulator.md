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
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="8bf63-103">Quantum Development Kit teljes állapotú szimulátor</span><span class="sxs-lookup"><span data-stu-id="8bf63-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="8bf63-104">A Quantum Development Kit olyan teljes állapotú kvantum-szimulátort biztosít, mint a [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) a Microsoft Research-től.</span><span class="sxs-lookup"><span data-stu-id="8bf63-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="8bf63-105">Ez a szimulátor felhasználható a Q #-ban írt kvantum-algoritmusok végrehajtásához és hibakereséséhez a számítógépen.</span><span class="sxs-lookup"><span data-stu-id="8bf63-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="8bf63-106">Ezt a kvantum-szimulátort a osztályon keresztül teszi elérhetővé `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="8bf63-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="8bf63-107">A szimulátor használatához egyszerűen hozza létre az osztály egy példányát, és adja át a `Run` végrehajtani kívánt kvantum-művelet metódusának a többi paraméterrel együtt:</span><span class="sxs-lookup"><span data-stu-id="8bf63-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="8bf63-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="8bf63-108">IDisposable</span></span>

<span data-ttu-id="8bf63-109">Az `QuantumSimulator` osztály implementálja <xref:System.IDisposable> , így a `Dispose` metódust akkor kell meghívni, ha már nincs használatban a szimulátor példánya.</span><span class="sxs-lookup"><span data-stu-id="8bf63-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="8bf63-110">Ennek a legjobb módja, ha egy utasításon belül becsomagolja a szimulátort `using` , ahogy a fenti példában is látható.</span><span class="sxs-lookup"><span data-stu-id="8bf63-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="8bf63-111">Kezdőérték</span><span class="sxs-lookup"><span data-stu-id="8bf63-111">Seed</span></span>

<span data-ttu-id="8bf63-112">A `QuantumSimulator` véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="8bf63-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="8bf63-113">Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata.</span><span class="sxs-lookup"><span data-stu-id="8bf63-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="8bf63-114">Ezt úgy teheti meg, hogy a (z) paraméterrel létrehoz egy magot a véletlenszerű számú generátorhoz a `QuantumSimulator` konstruktorban `randomNumberGeneratorSeed` :</span><span class="sxs-lookup"><span data-stu-id="8bf63-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="8bf63-115">Szálak</span><span class="sxs-lookup"><span data-stu-id="8bf63-115">Threads</span></span>

<span data-ttu-id="8bf63-116">A `QuantumSimulator` a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges.</span><span class="sxs-lookup"><span data-stu-id="8bf63-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="8bf63-117">Alapértelmezés szerint az OpenMP az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubittel rendelkező programok gyakran lassabban futnak, mert a szükséges koordináció mellett eltörpül a tényleges munka.</span><span class="sxs-lookup"><span data-stu-id="8bf63-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="8bf63-118">Ezt úgy lehet megjavítani, hogy a környezeti változót `OMP_NUM_THREADS` kis számra állítja be.</span><span class="sxs-lookup"><span data-stu-id="8bf63-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="8bf63-119">Nagyon nagy általánosságban nézve 1 szál nagyjából 4 qubithez elég, onnantól pedig qubitenként további 1 szálra van szükség, de ezek a számok nagyban függenek az adott algoritmustól.</span><span class="sxs-lookup"><span data-stu-id="8bf63-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

