---
title: Quantum erőforrás-kalkulátor – Quantum Development Kit
description: Ismerje meg a Microsoft QDK erőforrásainak kalkulátorát, amely a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg Q# .
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57f6602effd25fff353a8fee7f27acc529ce82af
ms.sourcegitcommit: c3c892ef35eae6926d0c4339d9d26bfd8be77e9a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/30/2020
ms.locfileid: "96318490"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="85c81-103">A Quantum Development Kit (QDK) erőforrásainak kalkulátora</span><span class="sxs-lookup"><span data-stu-id="85c81-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="85c81-104">Ahogy a név is jelenti, az `ResourcesEstimator` osztály a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli Q# meg.</span><span class="sxs-lookup"><span data-stu-id="85c81-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="85c81-105">Ezt a kvantum-művelet futtatásával hajtja végre, a kvantum-számítógép állapotának tényleges szimulálása nélkül. Emiatt a Q# több ezer qubits-t használó műveletek erőforrásainak becslése, ha a kód klasszikus része ésszerű időn belül fut.</span><span class="sxs-lookup"><span data-stu-id="85c81-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="85c81-106">Az erőforrások becslése a [kvantum-nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a mérőszámok és eszközök sokoldalú készletét kínálja a programok hibakereséséhez Q# .</span><span class="sxs-lookup"><span data-stu-id="85c81-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="85c81-107">Az erőforrás-kalkulátor meghívása és futtatása</span><span class="sxs-lookup"><span data-stu-id="85c81-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="85c81-108">Az erőforrás-kalkulátor használatával bármilyen Q# műveletet futtathat.</span><span class="sxs-lookup"><span data-stu-id="85c81-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="85c81-109">További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="85c81-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="85c81-110">A C-ből származó erőforrások becslésének meghívása #</span><span class="sxs-lookup"><span data-stu-id="85c81-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="85c81-111">Ahogy más célgépek esetében is, először a `ResourceEstimator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.</span><span class="sxs-lookup"><span data-stu-id="85c81-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="85c81-112">Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `ResourceEstimator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.</span><span class="sxs-lookup"><span data-stu-id="85c81-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="85c81-113">A példa bemutatja `ResourcesEstimator` a `ToTSV()` metódust, amely létrehoz egy tabulátorral tagolt értékeket (TSV) tartalmazó táblázatot.</span><span class="sxs-lookup"><span data-stu-id="85c81-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="85c81-114">Mentheti a táblázatot egy fájlba, vagy megjelenítheti a konzolon az elemzéshez.</span><span class="sxs-lookup"><span data-stu-id="85c81-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="85c81-115">Az alábbi példa az előző program kimenetét jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="85c81-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="85c81-116">A `ResourcesEstimator` példányok nem állítják alaphelyzetbe a számításokat minden futtatáskor.</span><span class="sxs-lookup"><span data-stu-id="85c81-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="85c81-117">Ha ugyanazt a példányt használja egy másik művelet futtatására, az új eredményeket összegzi a meglévő eredményekkel.</span><span class="sxs-lookup"><span data-stu-id="85c81-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="85c81-118">Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden futtatáshoz.</span><span class="sxs-lookup"><span data-stu-id="85c81-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="85c81-119">Az erőforrás-kalkulátor meghívása a Pythonból</span><span class="sxs-lookup"><span data-stu-id="85c81-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="85c81-120">Használja az [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q# művelettel:</span><span class="sxs-lookup"><span data-stu-id="85c81-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="85c81-121">Az erőforrás-kalkulátor meghívása a parancssorból</span><span class="sxs-lookup"><span data-stu-id="85c81-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="85c81-122">Ha a Q# parancssorból futtat egy programot, használja a **--Simulator** (vagy **-s** parancsikon) paramétert a célszámítógép megadásához `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="85c81-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="85c81-123">A következő parancs egy programot futtat az erőforrás-kalkulátor használatával:</span><span class="sxs-lookup"><span data-stu-id="85c81-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="85c81-124">A Juptyer-jegyzetfüzetek erőforrásainak becslése</span><span class="sxs-lookup"><span data-stu-id="85c81-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="85c81-125">A Q# művelet futtatásához használja a I Magic parancs [%-os becslését](xref:microsoft.quantum.iqsharp.magic-ref.simulate) Q# .</span><span class="sxs-lookup"><span data-stu-id="85c81-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="85c81-126">A becsült adatok programozott beolvasása</span><span class="sxs-lookup"><span data-stu-id="85c81-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="85c81-127">A TSV-táblázat mellett programozott módon is lekérheti a Futtatás során becsült erőforrásokat az erőforrások becslésének `Data` tulajdonságán keresztül.</span><span class="sxs-lookup"><span data-stu-id="85c81-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="85c81-128">A `Data` tulajdonság egy olyan `System.DataTable` példányt biztosít, amelyben két oszlop szerepel: `Metric` és `Sum` a metrikák nevei vannak indexelve.</span><span class="sxs-lookup"><span data-stu-id="85c81-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="85c81-129">A következő kód bemutatja, hogyan lehet lekérdezni és kinyomtatni a műveletek teljes számát `QubitClifford` `T` és a `CNOT` műveletek által használt műveleteket Q# :</span><span class="sxs-lookup"><span data-stu-id="85c81-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="85c81-130">Jelentett metrikák</span><span class="sxs-lookup"><span data-stu-id="85c81-130">Metrics Reported</span></span>

<span data-ttu-id="85c81-131">Az erőforrások becslése a következő metrikákat követi nyomon:</span><span class="sxs-lookup"><span data-stu-id="85c81-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="85c81-132">Metric</span><span class="sxs-lookup"><span data-stu-id="85c81-132">Metric</span></span>|<span data-ttu-id="85c81-133">Leírás</span><span class="sxs-lookup"><span data-stu-id="85c81-133">Description</span></span>|
|----|----|
|<span data-ttu-id="85c81-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="85c81-134">__CNOT__</span></span>    |<span data-ttu-id="85c81-135">A műveletek futtatási száma `CNOT` (más néven vezérelt Pauli X-műveletek).</span><span class="sxs-lookup"><span data-stu-id="85c81-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="85c81-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="85c81-136">__QubitClifford__</span></span> |<span data-ttu-id="85c81-137">Egyetlen qubit Clifford-és Pauli-művelet futtatási száma.</span><span class="sxs-lookup"><span data-stu-id="85c81-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="85c81-138">__mérték__</span><span class="sxs-lookup"><span data-stu-id="85c81-138">__Measure__</span></span>    |<span data-ttu-id="85c81-139">A mérések futtatásának száma.</span><span class="sxs-lookup"><span data-stu-id="85c81-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="85c81-140">__R__</span><span class="sxs-lookup"><span data-stu-id="85c81-140">__R__</span></span>    |<span data-ttu-id="85c81-141">A qubit-Forgások futtatásának száma, kivéve a `T` Clifford és a Pauli műveletet.</span><span class="sxs-lookup"><span data-stu-id="85c81-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="85c81-142">__T__</span><span class="sxs-lookup"><span data-stu-id="85c81-142">__T__</span></span>    |<span data-ttu-id="85c81-143">A `T` műveletek és a konjugátumok futtatásának száma, beleértve a `T` műveleteket, a T_x = H. T. h és a T_y = a kifogyott. t. vízterületet.</span><span class="sxs-lookup"><span data-stu-id="85c81-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="85c81-144">__Mélység__</span><span class="sxs-lookup"><span data-stu-id="85c81-144">__Depth__</span></span>|<span data-ttu-id="85c81-145">A művelet által futtatott Quantum Circuit mélysége Q# (lásd [alább](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="85c81-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="85c81-146">Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja.</span><span class="sxs-lookup"><span data-stu-id="85c81-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="85c81-147">További részletekért lásd a [részletes számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="85c81-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="85c81-148">__Szélessége__</span><span class="sxs-lookup"><span data-stu-id="85c81-148">__Width__</span></span>|<span data-ttu-id="85c81-149">A művelet által futtatott kvantum-kör szélessége Q# (lásd [alább](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="85c81-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="85c81-150">Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja.</span><span class="sxs-lookup"><span data-stu-id="85c81-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="85c81-151">További részletek: a [szélesség számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="85c81-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="85c81-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="85c81-152">__QubitCount__</span></span>    |<span data-ttu-id="85c81-153">A művelet futtatása során lefoglalt qubits maximális számának alsó határa Q# .</span><span class="sxs-lookup"><span data-stu-id="85c81-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="85c81-154">Lehetséges, hogy ez a metrika nem kompatibilis a __mélységgel__ (lásd alább).</span><span class="sxs-lookup"><span data-stu-id="85c81-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="85c81-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="85c81-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="85c81-156">A műveleten belül kölcsönzött qubits maximális száma Q# .</span><span class="sxs-lookup"><span data-stu-id="85c81-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="85c81-157">Mélység, szélesség és QubitCount</span><span class="sxs-lookup"><span data-stu-id="85c81-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="85c81-158">A jelentett mélységi és szélességi becslések kompatibilisek egymással.</span><span class="sxs-lookup"><span data-stu-id="85c81-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="85c81-159">(Korábban mindkét szám elérhető volt, de a mélységhez és a szélességhez eltérő áramkörökre lenne szükség.) A párosban jelenleg mindkét metrikát ugyanazzal az áramkörrel lehet megvalósítani.</span><span class="sxs-lookup"><span data-stu-id="85c81-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="85c81-160">A következő metrikákat kell jelenteni:</span><span class="sxs-lookup"><span data-stu-id="85c81-160">The following metrics are reported:</span></span>

<span data-ttu-id="85c81-161">__Mélység:__ A gyökérszintű művelethez – az adott kapu időpontját feltételezve, hogy végre kell hajtania.</span><span class="sxs-lookup"><span data-stu-id="85c81-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="85c81-162">A (z) és a művelet végén a legutóbbi qubit rendelkezésre állási idő között meghívott vagy azt követő műveletek időeltolódása.</span><span class="sxs-lookup"><span data-stu-id="85c81-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="85c81-163">__Szélesség:__ A gyökérszintű művelethez – a ténylegesen a végrehajtáshoz használt qubits száma (és a művelet meghívása).</span><span class="sxs-lookup"><span data-stu-id="85c81-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="85c81-164">A vagy az azt követő műveletekhez – a művelet elején már használt qubits kívül még hány qubits használtak.</span><span class="sxs-lookup"><span data-stu-id="85c81-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="85c81-165">Vegye figyelembe, hogy az újrafelhasznált qubits nem járul hozzá ehhez a számhoz.</span><span class="sxs-lookup"><span data-stu-id="85c81-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="85c81-166">Ha azonban néhány qubits már megjelent a művelet elindítása előtt, és az A művelet által igényelt összes qubit (és az A-ból származó műveletek) a korábbi kiadási qubits újbóli használatával teljesültek, az A művelet szélességét 0-ra kell jelenteni.</span><span class="sxs-lookup"><span data-stu-id="85c81-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="85c81-167">A qubits sikeres kölcsönzése nem járul hozzá a szélességhez.</span><span class="sxs-lookup"><span data-stu-id="85c81-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="85c81-168">__QubitCount:__ A gyökérszintű művelethez – a művelet végrehajtásához elégséges qubits minimális száma (és az általa meghívott műveletek).</span><span class="sxs-lookup"><span data-stu-id="85c81-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="85c81-169">A vagy az azt követő műveletek műveletekhez – a qubits minimális száma, amely elegendő lenne a művelet külön történő végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="85c81-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="85c81-170">Ez a szám nem tartalmaz bemeneti qubits.</span><span class="sxs-lookup"><span data-stu-id="85c81-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="85c81-171">Ez magában foglalja a kölcsönzött qubits is.</span><span class="sxs-lookup"><span data-stu-id="85c81-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="85c81-172">Két működési mód támogatott.</span><span class="sxs-lookup"><span data-stu-id="85c81-172">Two modes of operation are supported.</span></span> <span data-ttu-id="85c81-173">A módot a QCTraceSimulatorConfiguration. OptimizeDepth beállítással választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="85c81-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="85c81-174">__OptimizeDepth = True:__ A QubitManager a qubit újrahasznosítása és az új qubit lefoglalása minden alkalommal, amikor a rendszer kéri a qubit.</span><span class="sxs-lookup"><span data-stu-id="85c81-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="85c81-175">A gyökérszintű művelet __mélysége__ a minimális mélység (alsó határ) lesz.</span><span class="sxs-lookup"><span data-stu-id="85c81-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="85c81-176">Ehhez a mélységhez (mindkettőt egyszerre lehet megvalósítani) kompatibilis __szélességet__ kell jelenteni.</span><span class="sxs-lookup"><span data-stu-id="85c81-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="85c81-177">Vegye figyelembe, hogy ez a szélesség valószínűleg nem lesz optimális a mélység miatt.</span><span class="sxs-lookup"><span data-stu-id="85c81-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="85c81-178">A __QubitCount__ alacsonyabb lehet a legfelső szintű műveletnél, mert az újrafelhasználást feltételezi.</span><span class="sxs-lookup"><span data-stu-id="85c81-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="85c81-179">__OptimizeDepth = FALSE:__ A QubitManager a qubits újrafelhasználását javasolta, és újból felhasználja a kiadott qubits az újak lefoglalása előtt.</span><span class="sxs-lookup"><span data-stu-id="85c81-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="85c81-180">A gyökérszintű művelet __szélessége__ a minimális szélesség (alsó határ) lesz.</span><span class="sxs-lookup"><span data-stu-id="85c81-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="85c81-181">A rendszer a kompatibilis __mélységet__ fogja jelenteni, amelyen elérhető.</span><span class="sxs-lookup"><span data-stu-id="85c81-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="85c81-182">A __QubitCount__ megegyeznek a gyökérszintű művelet __szélességével__ , feltéve, hogy nincs hitelfelvétel.</span><span class="sxs-lookup"><span data-stu-id="85c81-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="85c81-183">Mérési eredmények valószínűségének megadása</span><span class="sxs-lookup"><span data-stu-id="85c81-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="85c81-184"><xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>A <xref:Microsoft.Quantum.Diagnostics> névtérből való használatával információt adhat meg egy mérési művelet várható valószínűségéről.</span><span class="sxs-lookup"><span data-stu-id="85c81-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="85c81-185">További információ: [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="85c81-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="85c81-186">Lásd még</span><span class="sxs-lookup"><span data-stu-id="85c81-186">See also</span></span>

- [<span data-ttu-id="85c81-187">Quantum Trace Simulator</span><span class="sxs-lookup"><span data-stu-id="85c81-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="85c81-188">Toffoli-kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="85c81-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="85c81-189">Teljes körű funkciókkal rendelkező kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="85c81-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
