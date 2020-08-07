---
title: Quantum erőforrás-kalkulátor – Quantum Development Kit
description: Ismerje meg a Microsoft QDK erőforrásainak kalkulátorát, amely a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg Q# .
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868185"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="b402c-103">A Quantum Development Kit (QDK) erőforrásainak kalkulátora</span><span class="sxs-lookup"><span data-stu-id="b402c-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="b402c-104">Ahogy a név is jelenti, az `ResourcesEstimator` osztály a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli Q# meg.</span><span class="sxs-lookup"><span data-stu-id="b402c-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="b402c-105">Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Emiatt a Q# több ezer qubits-t használó műveletek erőforrásainak becslése, ha a kód klasszikus része ésszerű időn belül fut.</span><span class="sxs-lookup"><span data-stu-id="b402c-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="b402c-106">Az erőforrások becslése a [kvantum-nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a mérőszámok és eszközök sokoldalú készletét kínálja a programok hibakereséséhez Q# .</span><span class="sxs-lookup"><span data-stu-id="b402c-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="b402c-107">Az erőforrás-kalkulátor meghívása és futtatása</span><span class="sxs-lookup"><span data-stu-id="b402c-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="b402c-108">Az erőforrás-kalkulátor használatával bármilyen Q# műveletet futtathat.</span><span class="sxs-lookup"><span data-stu-id="b402c-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="b402c-109">További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b402c-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="b402c-110">A C-ből származó erőforrások becslésének meghívása #</span><span class="sxs-lookup"><span data-stu-id="b402c-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="b402c-111">Ahogy más célgépek esetében is, először a `ResourceEstimator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.</span><span class="sxs-lookup"><span data-stu-id="b402c-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b402c-112">Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `ResourceEstimator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.</span><span class="sxs-lookup"><span data-stu-id="b402c-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="b402c-113">A példa bemutatja `ResourcesEstimator` a `ToTSV()` metódust, amely létrehoz egy tabulátorral tagolt értékeket (TSV) tartalmazó táblázatot.</span><span class="sxs-lookup"><span data-stu-id="b402c-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="b402c-114">Mentheti a táblázatot egy fájlba, vagy megjelenítheti a konzolon az elemzéshez.</span><span class="sxs-lookup"><span data-stu-id="b402c-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="b402c-115">Az alábbi példa az előző program kimenetét jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="b402c-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="b402c-116">A `ResourcesEstimator` példányok nem állítják alaphelyzetbe a számításokat minden futtatáskor.</span><span class="sxs-lookup"><span data-stu-id="b402c-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="b402c-117">Ha ugyanazt a példányt használja egy másik művelet futtatására, az új eredményeket összegzi a meglévő eredményekkel.</span><span class="sxs-lookup"><span data-stu-id="b402c-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="b402c-118">Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden futtatáshoz.</span><span class="sxs-lookup"><span data-stu-id="b402c-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="b402c-119">Az erőforrás-kalkulátor meghívása a Pythonból</span><span class="sxs-lookup"><span data-stu-id="b402c-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="b402c-120">Használja az [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q# művelettel:</span><span class="sxs-lookup"><span data-stu-id="b402c-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="b402c-121">Az erőforrás-kalkulátor meghívása a parancssorból</span><span class="sxs-lookup"><span data-stu-id="b402c-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="b402c-122">Ha a Q# parancssorból futtat egy programot, használja a **--Simulator** (vagy **-s** parancsikon) paramétert a célszámítógép megadásához `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="b402c-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="b402c-123">A következő parancs egy programot futtat az erőforrás-kalkulátor használatával:</span><span class="sxs-lookup"><span data-stu-id="b402c-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="b402c-124">A Juptyer-jegyzetfüzetek erőforrásainak becslése</span><span class="sxs-lookup"><span data-stu-id="b402c-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="b402c-125">A Q# művelet futtatásához használja a I Magic parancs [%-os becslését](xref:microsoft.quantum.iqsharp.magic-ref.simulate) Q# .</span><span class="sxs-lookup"><span data-stu-id="b402c-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="b402c-126">A becsült adatok programozott beolvasása</span><span class="sxs-lookup"><span data-stu-id="b402c-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="b402c-127">A TSV-táblázat mellett programozott módon is lekérheti a Futtatás során becsült erőforrásokat az erőforrások becslésének `Data` tulajdonságán keresztül.</span><span class="sxs-lookup"><span data-stu-id="b402c-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="b402c-128">A `Data` tulajdonság egy olyan `System.DataTable` példányt biztosít, amelyben két oszlop szerepel: `Metric` és `Sum` a metrikák nevei vannak indexelve.</span><span class="sxs-lookup"><span data-stu-id="b402c-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="b402c-129">A következő kód bemutatja, hogyan lehet lekérdezni és kinyomtatni a műveletek teljes számát `QubitClifford` `T` és a `CNOT` műveletek által használt műveleteket Q# :</span><span class="sxs-lookup"><span data-stu-id="b402c-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="b402c-130">Jelentett metrikák</span><span class="sxs-lookup"><span data-stu-id="b402c-130">Metrics Reported</span></span>

<span data-ttu-id="b402c-131">Az erőforrások becslése a következő metrikákat követi nyomon:</span><span class="sxs-lookup"><span data-stu-id="b402c-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="b402c-132">Metrika</span><span class="sxs-lookup"><span data-stu-id="b402c-132">Metric</span></span>|<span data-ttu-id="b402c-133">Leírás</span><span class="sxs-lookup"><span data-stu-id="b402c-133">Description</span></span>|
|----|----|
|<span data-ttu-id="b402c-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="b402c-134">__CNOT__</span></span>    |<span data-ttu-id="b402c-135">A műveletek futtatási száma `CNOT` (más néven vezérelt Pauli X-műveletek).</span><span class="sxs-lookup"><span data-stu-id="b402c-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="b402c-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="b402c-136">__QubitClifford__</span></span> |<span data-ttu-id="b402c-137">Egyetlen qubit Clifford-és Pauli-művelet futtatási száma.</span><span class="sxs-lookup"><span data-stu-id="b402c-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="b402c-138">__mérték__</span><span class="sxs-lookup"><span data-stu-id="b402c-138">__Measure__</span></span>    |<span data-ttu-id="b402c-139">A mérések futtatásának száma.</span><span class="sxs-lookup"><span data-stu-id="b402c-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="b402c-140">__R__</span><span class="sxs-lookup"><span data-stu-id="b402c-140">__R__</span></span>    |<span data-ttu-id="b402c-141">A qubit-Forgások futtatásának száma, kivéve a `T` Clifford és a Pauli műveletet.</span><span class="sxs-lookup"><span data-stu-id="b402c-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="b402c-142">__T__</span><span class="sxs-lookup"><span data-stu-id="b402c-142">__T__</span></span>    |<span data-ttu-id="b402c-143">A `T` műveletek és a konjugátumok futtatásának száma, beleértve a `T` műveleteket, a T_x = H. T. h és a T_y = a kifogyott. t. vízterületet.</span><span class="sxs-lookup"><span data-stu-id="b402c-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="b402c-144">__Mélység__</span><span class="sxs-lookup"><span data-stu-id="b402c-144">__Depth__</span></span>|<span data-ttu-id="b402c-145">A művelet által futtatott Quantum Circuit mélységének alsó határa Q# .</span><span class="sxs-lookup"><span data-stu-id="b402c-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="b402c-146">Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja.</span><span class="sxs-lookup"><span data-stu-id="b402c-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="b402c-147">További részletekért lásd a [részletes számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="b402c-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="b402c-148">__Szélesség__</span><span class="sxs-lookup"><span data-stu-id="b402c-148">__Width__</span></span>    |<span data-ttu-id="b402c-149">A művelet futtatása során lefoglalt qubits maximális számának alsó határa Q# .</span><span class="sxs-lookup"><span data-stu-id="b402c-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="b402c-150">Előfordulhat, hogy a __mélység__ és a __szélesség__ alsó határa nem érhető el egyszerre.</span><span class="sxs-lookup"><span data-stu-id="b402c-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="b402c-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="b402c-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="b402c-152">A műveleten belül kölcsönzött qubits maximális száma Q# .</span><span class="sxs-lookup"><span data-stu-id="b402c-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="b402c-153">Mérési eredmények valószínűségének megadása</span><span class="sxs-lookup"><span data-stu-id="b402c-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="b402c-154"><xref:microsoft.quantum.diagnostics.assertmeasurementprobability>A <xref:microsoft.quantum.diagnostics> névtérből való használatával információt adhat meg egy mérési művelet várható valószínűségéről.</span><span class="sxs-lookup"><span data-stu-id="b402c-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="b402c-155">További információ: [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="b402c-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="b402c-156">További információ</span><span class="sxs-lookup"><span data-stu-id="b402c-156">See also</span></span>

- [<span data-ttu-id="b402c-157">Quantum Trace Simulator</span><span class="sxs-lookup"><span data-stu-id="b402c-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="b402c-158">Toffoli-kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="b402c-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="b402c-159">Teljes körű funkciókkal rendelkező kvantumszimulátor</span><span class="sxs-lookup"><span data-stu-id="b402c-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 