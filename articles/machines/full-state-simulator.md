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
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="7b2bd-103">Quantum Development Kit teljes állapotú szimulátor</span><span class="sxs-lookup"><span data-stu-id="7b2bd-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="7b2bd-104">A Quantum Development Kit olyan teljes állapotú kvantum-szimulátort biztosít, mint a [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) a Microsoft Research-től.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="7b2bd-105">Ez a szimulátor felhasználható a Q #-ban írt kvantum-algoritmusok végrehajtásához és hibakereséséhez a számítógépen.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="7b2bd-106">Ez a Quantum Simulator a `QuantumSimulator` osztályon keresztül érhető el.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="7b2bd-107">A szimulátor használatához egyszerűen hozza létre ennek az osztálynak egy példányát, és adja át a végrehajtani kívánt kvantum-művelet `Run` metódusának a többi paraméterrel együtt:</span><span class="sxs-lookup"><span data-stu-id="7b2bd-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="7b2bd-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="7b2bd-108">IDisposable</span></span>

<span data-ttu-id="7b2bd-109">A `QuantumSimulator` osztály <xref:System.IDisposable>t valósít meg, ezért a `Dispose` metódust kell meghívni, ha a szimulátor példányát már nem használják.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="7b2bd-110">Ennek a legjobb módja, ha a szimulátort egy `using` utasításon belül becsomagolja, ahogy a fenti példában is látható.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="7b2bd-111">kezdőérték</span><span class="sxs-lookup"><span data-stu-id="7b2bd-111">Seed</span></span>

<span data-ttu-id="7b2bd-112">A `QuantumSimulator` véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="7b2bd-113">Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="7b2bd-114">Ezt úgy teheti meg, hogy a `QuantumSimulator`konstruktorában a `randomNumberGeneratorSeed` paraméterrel megadhat egy magot a véletlenszerű számú generátorhoz:</span><span class="sxs-lookup"><span data-stu-id="7b2bd-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="7b2bd-115">Szálak</span><span class="sxs-lookup"><span data-stu-id="7b2bd-115">Threads</span></span>

<span data-ttu-id="7b2bd-116">A `QuantumSimulator` a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="7b2bd-117">Alapértelmezés szerint az OpenMP az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubittel rendelkező programok gyakran lassabban futnak, mert a szükséges koordináció mellett eltörpül a tényleges munka.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="7b2bd-118">Ezt úgy lehet megjavítani, ha a környezeti változót kis számra állítja `OMP_NUM_THREADS`.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="7b2bd-119">Nagyon nagy általánosságban nézve 1 szál nagyjából 4 qubithez elég, onnantól pedig qubitenként további 1 szálra van szükség, de ezek a számok nagyban függenek az adott algoritmustól.</span><span class="sxs-lookup"><span data-stu-id="7b2bd-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

