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
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="5782b-103">Quantum Development Kit (QDK) teljes állapotú szimulátor</span><span class="sxs-lookup"><span data-stu-id="5782b-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="5782b-104">A QDK teljes állapotú szimulátort biztosít, amely a helyi számítógépen lévő kvantum-gépet szimulálja.</span><span class="sxs-lookup"><span data-stu-id="5782b-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="5782b-105">A teljes állapot szimulátorral a Q #-ban írt kvantum-algoritmusokat futtathat és hibakeresést végezhet, akár 30 qubits is felhasználhatja.</span><span class="sxs-lookup"><span data-stu-id="5782b-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="5782b-106">A teljes állapot szimulátor hasonló a [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) platformon a Microsoft Research szolgáltatásban használt kvantum-szimulátorhoz.</span><span class="sxs-lookup"><span data-stu-id="5782b-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="5782b-107">A teljes állapotú szimulátor meghívása és futtatása</span><span class="sxs-lookup"><span data-stu-id="5782b-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="5782b-108">A teljes állapotú szimulátort a osztályon keresztül teheti elérhetővé `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="5782b-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="5782b-109">További részleteket a [Q # program futtatásának módjai](xref:microsoft.quantum.guide.host-programs)című témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="5782b-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="5782b-110">A szimulátor meghívása C-ről #</span><span class="sxs-lookup"><span data-stu-id="5782b-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="5782b-111">Hozza létre a osztály egy példányát, `QuantumSimulator` majd adja át a `Run` kvantum-művelet metódusának, valamint a további paramétereket.</span><span class="sxs-lookup"><span data-stu-id="5782b-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="5782b-112">Mivel az `QuantumSimulator` osztály implementálja az <xref:System.IDisposable> illesztőfelületet, meg kell hívnia a `Dispose` metódust, ha már nincs szüksége a szimulátor példányára.</span><span class="sxs-lookup"><span data-stu-id="5782b-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="5782b-113">Ennek a legjobb módja a szimulátor deklarációjának és műveleteinek becsomagolása egy [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) utasításon belül, amely automatikusan meghívja a `Dispose` metódust.</span><span class="sxs-lookup"><span data-stu-id="5782b-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="5782b-114">A szimulátor meghívása a Pythonból</span><span class="sxs-lookup"><span data-stu-id="5782b-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="5782b-115">Használja a Q # Python könyvtár [szimulálása ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódusát az importált q # művelettel:</span><span class="sxs-lookup"><span data-stu-id="5782b-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="5782b-116">A szimulátor meghívása a parancssorból</span><span class="sxs-lookup"><span data-stu-id="5782b-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="5782b-117">Ha Q # programot futtat a parancssorból, a teljes állapot szimulátor az alapértelmezett célszámítógép.</span><span class="sxs-lookup"><span data-stu-id="5782b-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="5782b-118">Igény szerint a **--Simulator** (vagy **-s** parancsikon) paraméterrel megadhatja a kívánt célszámítógépet.</span><span class="sxs-lookup"><span data-stu-id="5782b-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="5782b-119">Mindkét alábbi parancs a teljes állapotú szimulátor használatával futtat egy programot.</span><span class="sxs-lookup"><span data-stu-id="5782b-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="5782b-120">A szimulátor meghívása Juptyer-jegyzetfüzetekről</span><span class="sxs-lookup"><span data-stu-id="5782b-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="5782b-121">A Q # művelet futtatásához használja az IQ # Magic Command [% szimulálása](xref:microsoft.quantum.iqsharp.magic-ref.simulate) parancsot.</span><span class="sxs-lookup"><span data-stu-id="5782b-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="5782b-122">A szimulátor kivetése</span><span class="sxs-lookup"><span data-stu-id="5782b-122">Seeding the simulator</span></span>

<span data-ttu-id="5782b-123">Alapértelmezés szerint a teljes állapot szimulátor egy véletlenszerű számú generátort használ a kvantum-véletlenszerűség szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="5782b-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="5782b-124">Tesztelési célokra időnként hasznos lehet a determinisztikus eredményeinek használata.</span><span class="sxs-lookup"><span data-stu-id="5782b-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="5782b-125">Egy C#-programban ezt úgy hajthatja végre, hogy a `QuantumSimulator` paraméterrel a konstruktorban található véletlenszerű számú generátorhoz biztosít magot `randomNumberGeneratorSeed` .</span><span class="sxs-lookup"><span data-stu-id="5782b-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="5782b-126">Szálak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5782b-126">Configuring threads</span></span>

<span data-ttu-id="5782b-127">A teljes körű állapot szimulátor a [OpenMP dokumentáció](http://www.openmp.org/) használatával integrálással a lineáris algebra szükséges.</span><span class="sxs-lookup"><span data-stu-id="5782b-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="5782b-128">Alapértelmezés szerint a OpenMP dokumentáció az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubits rendelkező programok gyakran lassan futnak, mert a szükséges koordináció a tényleges munka.</span><span class="sxs-lookup"><span data-stu-id="5782b-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="5782b-129">Ezt a környezeti változó kis számra állításával javíthatja `OMP_NUM_THREADS` .</span><span class="sxs-lookup"><span data-stu-id="5782b-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="5782b-130">A hüvelykujj szabályként legfeljebb négy qubits konfigurálhat egy szálat, majd qubit egy további szálat.</span><span class="sxs-lookup"><span data-stu-id="5782b-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="5782b-131">Előfordulhat, hogy az algoritmustól függően módosítania kell a változót.</span><span class="sxs-lookup"><span data-stu-id="5782b-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="5782b-132">Lásd még</span><span class="sxs-lookup"><span data-stu-id="5782b-132">See also</span></span>

- [<span data-ttu-id="5782b-133">Quantum-erőforrások kalkulátora</span><span class="sxs-lookup"><span data-stu-id="5782b-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="5782b-134">Quantum Toffoli szimulátor</span><span class="sxs-lookup"><span data-stu-id="5782b-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="5782b-135">Quantum Trace Simulator</span><span class="sxs-lookup"><span data-stu-id="5782b-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)