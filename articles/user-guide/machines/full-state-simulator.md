---
title: Teljes állapotú Quantum Simulator – Quantum Development Kit
description: Ismerje meg, hogyan futtathatja a Q# programokat a Microsoft Quantum Development Kit teljes állapotú szimulátoron.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 632af681c5818ab7246c0f5849a8b8e716b570cb
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833371"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="8579c-103">Quantum Development Kit (QDK) teljes állapotú szimulátor</span><span class="sxs-lookup"><span data-stu-id="8579c-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="8579c-104">A QDK teljes állapotú szimulátort biztosít, amely a helyi számítógépen lévő kvantum-gépet szimulálja.</span><span class="sxs-lookup"><span data-stu-id="8579c-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="8579c-105">A teljes állapot szimulátorral futtathatja és hibakeresést végezhet a-ben írt kvantum-algoritmusokkal, és akár 30 qubits is felhasználhat Q# .</span><span class="sxs-lookup"><span data-stu-id="8579c-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="8579c-106">A teljes állapot szimulátor hasonló a  [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) platformon a Microsoft Research szolgáltatásban használt kvantum-szimulátorhoz.</span><span class="sxs-lookup"><span data-stu-id="8579c-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="8579c-107">A teljes állapotú szimulátor meghívása és futtatása</span><span class="sxs-lookup"><span data-stu-id="8579c-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="8579c-108">A teljes állapotú szimulátort a osztályon keresztül teheti elérhetővé `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="8579c-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="8579c-109">További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="8579c-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="8579c-110">A szimulátor meghívása C-ről #</span><span class="sxs-lookup"><span data-stu-id="8579c-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="8579c-111">Hozza létre a osztály egy példányát, `QuantumSimulator` majd adja át a `Run` kvantum-művelet metódusának, valamint a további paramétereket.</span><span class="sxs-lookup"><span data-stu-id="8579c-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="8579c-112">Mivel az `QuantumSimulator` osztály implementálja az <xref:System.IDisposable> illesztőfelületet, meg kell hívnia a `Dispose` metódust, ha már nincs szüksége a szimulátor példányára.</span><span class="sxs-lookup"><span data-stu-id="8579c-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="8579c-113">Ennek a legjobb módja a szimulátor deklarációjának és műveleteinek becsomagolása egy [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) utasításon belül, amely automatikusan meghívja a `Dispose` metódust.</span><span class="sxs-lookup"><span data-stu-id="8579c-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="8579c-114">A szimulátor meghívása a Pythonból</span><span class="sxs-lookup"><span data-stu-id="8579c-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="8579c-115">Használja a [szimulálás ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) metódust a Q# Python-könyvtárból az importált Q# művelettel:</span><span class="sxs-lookup"><span data-stu-id="8579c-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="8579c-116">A szimulátor meghívása a parancssorból</span><span class="sxs-lookup"><span data-stu-id="8579c-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="8579c-117">Ha a Q# parancssorból futtat egy programot, a teljes állapot szimulátor az alapértelmezett célszámítógép.</span><span class="sxs-lookup"><span data-stu-id="8579c-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="8579c-118">Igény szerint a **--Simulator** (vagy **-s** parancsikon) paraméterrel megadhatja a kívánt célszámítógépet.</span><span class="sxs-lookup"><span data-stu-id="8579c-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="8579c-119">Mindkét alábbi parancs a teljes állapotú szimulátor használatával futtat egy programot.</span><span class="sxs-lookup"><span data-stu-id="8579c-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="8579c-120">A szimulátor meghívása Juptyer-jegyzetfüzetekről</span><span class="sxs-lookup"><span data-stu-id="8579c-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="8579c-121">A Q# művelet futtatásához használja a I Magic Command [% szimulálás](xref:microsoft.quantum.iqsharp.magic-ref.simulate) parancsot Q# .</span><span class="sxs-lookup"><span data-stu-id="8579c-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="8579c-122">A szimulátor kivetése</span><span class="sxs-lookup"><span data-stu-id="8579c-122">Seeding the simulator</span></span>

<span data-ttu-id="8579c-123">Alapértelmezés szerint a teljes állapot szimulátor egy véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="8579c-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="8579c-124">Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata.</span><span class="sxs-lookup"><span data-stu-id="8579c-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="8579c-125">Egy C#-programban ezt úgy hajthatja végre, hogy a `QuantumSimulator` paraméterrel a konstruktorban található véletlenszerű számú generátorhoz biztosít magot `randomNumberGeneratorSeed` .</span><span class="sxs-lookup"><span data-stu-id="8579c-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="8579c-126">Szálak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8579c-126">Configuring threads</span></span>

<span data-ttu-id="8579c-127">A teljes körű állapot szimulátor a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges.</span><span class="sxs-lookup"><span data-stu-id="8579c-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="8579c-128">Alapértelmezés szerint a OpenMP dokumentáció az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubits rendelkező programok gyakran lassan futnak, mert a szükséges koordináció a tényleges munka.</span><span class="sxs-lookup"><span data-stu-id="8579c-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="8579c-129">Ezt a környezeti változó kis számra állításával javíthatja `OMP_NUM_THREADS` .</span><span class="sxs-lookup"><span data-stu-id="8579c-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="8579c-130">A hüvelykujj szabályként legfeljebb négy qubits konfigurálhat egy szálat, majd qubit egy további szálat.</span><span class="sxs-lookup"><span data-stu-id="8579c-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="8579c-131">Előfordulhat, hogy az algoritmustól függően módosítania kell a változót.</span><span class="sxs-lookup"><span data-stu-id="8579c-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="8579c-132">Lásd még</span><span class="sxs-lookup"><span data-stu-id="8579c-132">See also</span></span>

- [<span data-ttu-id="8579c-133">Kvantumerőforrás-becslő</span><span class="sxs-lookup"><span data-stu-id="8579c-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="8579c-134">Toffoli-kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="8579c-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="8579c-135">Quantum Trace Simulator</span><span class="sxs-lookup"><span data-stu-id="8579c-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)