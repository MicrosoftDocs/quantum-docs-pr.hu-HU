---
title: A Quantum Development Kit erőforrásainak kalkulátora | Microsoft Docs
description: A Microsoft Quantum Development Kit-erőforrások kalkulátorának áttekintése
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184984"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="e7b15-103">A ResourcesEstimator cél gépe</span><span class="sxs-lookup"><span data-stu-id="e7b15-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="e7b15-104">Ahogy a név is jelenti, a `ResourcesEstimator` a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.</span><span class="sxs-lookup"><span data-stu-id="e7b15-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="e7b15-105">Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Ebből kifolyólag megbecsülheti a Q # olyan műveleteinek erőforrásait, amelyek több ezer qubits használnak.</span><span class="sxs-lookup"><span data-stu-id="e7b15-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="e7b15-106">Használat</span><span class="sxs-lookup"><span data-stu-id="e7b15-106">Usage</span></span>

<span data-ttu-id="e7b15-107">A `ResourcesEstimator` csak egy másik típusú célszámítógép, így bármely Q # művelet futtatására is használható.</span><span class="sxs-lookup"><span data-stu-id="e7b15-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="e7b15-108">Más célszámítógépek esetén a C# gazdagépen való használathoz hozzon létre egy példányt, és adja át a művelet `Run` metódusának első paramétereként:</span><span class="sxs-lookup"><span data-stu-id="e7b15-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="e7b15-109">A példa azt mutatja, hogy a `ResourcesEstimator` `ToTSV()` módszert biztosít egy olyan tabulátorral elválasztott tábla létrehozásához, amely fájlba menthető, vagy elemzésre a konzolba.</span><span class="sxs-lookup"><span data-stu-id="e7b15-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="e7b15-110">A fenti program kimenetének a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="e7b15-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="e7b15-111">A `ResourcesEstimator` nem állítja alaphelyzetbe a számításokat minden futtatáskor, ha ugyanazt a példányt egy másik művelet végrehajtásához használja, akkor a meglévő eredmények alapján megtartja az összesítési számlálást.</span><span class="sxs-lookup"><span data-stu-id="e7b15-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="e7b15-112">Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden végrehajtáshoz.</span><span class="sxs-lookup"><span data-stu-id="e7b15-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="e7b15-113">A becsült adatok programozott beolvasása</span><span class="sxs-lookup"><span data-stu-id="e7b15-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="e7b15-114">A TSV-táblázat mellett a becsült erőforrások programozott módon is beolvashatók a `ResourcesEstimator``Data` tulajdonságán keresztül.</span><span class="sxs-lookup"><span data-stu-id="e7b15-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="e7b15-115">a `Data` `System.DataTable` példányt biztosít két oszloppal: `Metric` és `Sum`, a metrikák nevei szerint indexelve.</span><span class="sxs-lookup"><span data-stu-id="e7b15-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="e7b15-116">A következő kód bemutatja, hogyan kérhető le és nyomtatható ki a Q # művelet által használt `QubitClifford`, `T` és `CNOT` Gates teljes száma:</span><span class="sxs-lookup"><span data-stu-id="e7b15-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="e7b15-117">Jelentett metrikák</span><span class="sxs-lookup"><span data-stu-id="e7b15-117">Metrics Reported</span></span>

<span data-ttu-id="e7b15-118">Az alábbi lista a `ResourcesEstimator`becsült mérőszámait sorolja fel:</span><span class="sxs-lookup"><span data-stu-id="e7b15-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="e7b15-119">__Cnem__: a cnem (más néven ellenőrzött Pauli X Gate) Gates száma.</span><span class="sxs-lookup"><span data-stu-id="e7b15-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="e7b15-120">__QubitClifford__: egy qubit-es Clifford-és Pauli-kapuk száma.</span><span class="sxs-lookup"><span data-stu-id="e7b15-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="e7b15-121">__Mérték__: a végrehajtott mérések száma.</span><span class="sxs-lookup"><span data-stu-id="e7b15-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="e7b15-122">__R__: a végrehajtott egyetlen qubit-forgatások száma, kivéve a T, Clifford és Pauli gateset.</span><span class="sxs-lookup"><span data-stu-id="e7b15-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="e7b15-123">__T__: a t-kapuk és a benne lévő konjugátumok száma, beleértve a t-kaput, a T_x = h. T. h és a T_y = a (z). t. a.</span><span class="sxs-lookup"><span data-stu-id="e7b15-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="e7b15-124">__Mélység__: a Q # művelet által végrehajtott kvantum-áramkör mélysége.</span><span class="sxs-lookup"><span data-stu-id="e7b15-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="e7b15-125">Alapértelmezés szerint csak a T-Gates számítanak bele a mélységbe, a részletekért lásd a részletes [számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="e7b15-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="e7b15-126">__Szélesség__: a Q # művelet végrehajtása során lefoglalt qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="e7b15-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="e7b15-127">__BorrowedWidth__: a Q # műveletben kölcsönzött qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="e7b15-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="e7b15-128">A mérési eredmények valószínűségének megadása</span><span class="sxs-lookup"><span data-stu-id="e7b15-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="e7b15-129">a <xref:microsoft.quantum.primitive> névtérből származó <xref:microsoft.quantum.primitive.assertprob> használatával információt adhat meg egy mérték várható valószínűségéről a Q # program végrehajtásának elősegítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="e7b15-129"><xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="e7b15-130">A következő példa ezt szemlélteti:</span><span class="sxs-lookup"><span data-stu-id="e7b15-130">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="e7b15-131">Ha a `ResourcesEstimator` `AssertProb`, a rendszer rögzíti, hogy a mérési `PauliZ` a `source`, és `ancilla` a 0,5-as valószínűségű `Zero` eredményét kell adni.</span><span class="sxs-lookup"><span data-stu-id="e7b15-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="e7b15-132">Amikor később végrehajtja `M`, megkeresi a kimeneteli valószínűségek rögzített értékeit, és `M` `Zero` vagy `One` értéket ad vissza a 0,5 valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="e7b15-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="e7b15-133">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e7b15-133">See also</span></span>

<span data-ttu-id="e7b15-134">A `ResourcesEstimator` a kvantum-számítógép [nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a metrikák széles választékát biztosítja, a teljes hívási gráfban lévő mérőszámok jelentését, valamint az olyan funkciókat, mint a [különböző bemenet-ellenőrök](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , amelyek segítenek a hibák keresésében a Q # programokon.</span><span class="sxs-lookup"><span data-stu-id="e7b15-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="e7b15-135">További információért tekintse meg a [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="e7b15-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

