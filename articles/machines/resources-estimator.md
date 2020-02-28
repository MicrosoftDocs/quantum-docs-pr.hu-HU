---
title: A Quantum Development Kit erőforrásainak kalkulátora
description: 'Ismerje meg az erőforrások becslését, amely a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 37c901e5a861f0e8a10cdc911ad1d84ddd3e6e00
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907052"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="125d2-103">A ResourcesEstimator cél gépe</span><span class="sxs-lookup"><span data-stu-id="125d2-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="125d2-104">Ahogy a név is jelenti, a `ResourcesEstimator` a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.</span><span class="sxs-lookup"><span data-stu-id="125d2-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="125d2-105">Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Ebből kifolyólag megbecsülheti a Q # olyan műveleteinek erőforrásait, amelyek több ezer qubits használnak.</span><span class="sxs-lookup"><span data-stu-id="125d2-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="125d2-106">Használat</span><span class="sxs-lookup"><span data-stu-id="125d2-106">Usage</span></span>

<span data-ttu-id="125d2-107">A `ResourcesEstimator` csak egy másik típusú célszámítógép, így bármely Q # művelet futtatására is használható.</span><span class="sxs-lookup"><span data-stu-id="125d2-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="125d2-108">Más célszámítógépek esetén a C# gazdagépen való használathoz hozzon létre egy példányt, és adja át a művelet `Run` metódusának első paramétereként:</span><span class="sxs-lookup"><span data-stu-id="125d2-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="125d2-109">A példa azt mutatja, hogy a `ResourcesEstimator` `ToTSV()` módszert biztosít egy olyan tabulátorral elválasztott tábla létrehozásához, amely fájlba menthető, vagy elemzésre a konzolba.</span><span class="sxs-lookup"><span data-stu-id="125d2-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="125d2-110">A fenti program kimenetének a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="125d2-110">The output of the above program should look something like this:</span></span>

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
> <span data-ttu-id="125d2-111">A `ResourcesEstimator` nem állítja alaphelyzetbe a számításokat minden futtatáskor, ha ugyanazt a példányt egy másik művelet végrehajtásához használja, akkor a meglévő eredmények alapján megtartja az összesítési számlálást.</span><span class="sxs-lookup"><span data-stu-id="125d2-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="125d2-112">Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden végrehajtáshoz.</span><span class="sxs-lookup"><span data-stu-id="125d2-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="125d2-113">A becsült adatok programozott beolvasása</span><span class="sxs-lookup"><span data-stu-id="125d2-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="125d2-114">A TSV-táblázat mellett a becsült erőforrások programozott módon is beolvashatók a `ResourcesEstimator``Data` tulajdonságán keresztül.</span><span class="sxs-lookup"><span data-stu-id="125d2-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="125d2-115">a `Data` `System.DataTable` példányt biztosít két oszloppal: `Metric` és `Sum`, a metrikák nevei szerint indexelve.</span><span class="sxs-lookup"><span data-stu-id="125d2-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="125d2-116">A következő kód bemutatja, hogyan kérhető le és nyomtatható ki a Q # művelet által használt `QubitClifford`, `T` és `CNOT` Gates teljes száma:</span><span class="sxs-lookup"><span data-stu-id="125d2-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="125d2-117">Jelentett metrikák</span><span class="sxs-lookup"><span data-stu-id="125d2-117">Metrics Reported</span></span>

<span data-ttu-id="125d2-118">Az alábbi lista a `ResourcesEstimator`becsült mérőszámait sorolja fel:</span><span class="sxs-lookup"><span data-stu-id="125d2-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="125d2-119">__Cnem__: a cnem (más néven ellenőrzött Pauli X Gate) Gates száma.</span><span class="sxs-lookup"><span data-stu-id="125d2-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="125d2-120">__QubitClifford__: egy qubit-es Clifford-és Pauli-kapuk száma.</span><span class="sxs-lookup"><span data-stu-id="125d2-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="125d2-121">__Mérték__: a végrehajtott mérések száma.</span><span class="sxs-lookup"><span data-stu-id="125d2-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="125d2-122">__R__: a végrehajtott egyetlen qubit-forgatások száma, kivéve a T, Clifford és Pauli gateset.</span><span class="sxs-lookup"><span data-stu-id="125d2-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="125d2-123">__T__: a t-kapuk és a benne lévő konjugátumok száma, beleértve a t-kaput, T_x = H. T. h, valamint T_y = a (z). t. a.</span><span class="sxs-lookup"><span data-stu-id="125d2-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="125d2-124">__Mélység__: a Q # művelet által végrehajtott kvantum-áramkör mélysége.</span><span class="sxs-lookup"><span data-stu-id="125d2-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="125d2-125">Alapértelmezés szerint csak a T-Gates számítanak bele a mélységbe, a részletekért lásd a részletes [számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="125d2-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="125d2-126">__Szélesség__: a Q # művelet végrehajtása során lefoglalt qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="125d2-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="125d2-127">__BorrowedWidth__: a Q # műveletben kölcsönzött qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="125d2-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="125d2-128">Mérési eredmények valószínűségének biztosítása</span><span class="sxs-lookup"><span data-stu-id="125d2-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="125d2-129">a <xref:microsoft.quantum.intrinsic> névtérből származó <xref:microsoft.quantum.intrinsic.assertprob> használatával információt adhat meg egy mérték várható valószínűségéről a Q # program végrehajtásának elősegítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="125d2-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="125d2-130">A következő példa ezt illusztrálja:</span><span class="sxs-lookup"><span data-stu-id="125d2-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="125d2-131">Ha a `ResourcesEstimator` `AssertProb`, a rendszer rögzíti, hogy a mérési `PauliZ` a `source`, és `q` a 0,5-as valószínűségű `Zero` eredményét kell adni.</span><span class="sxs-lookup"><span data-stu-id="125d2-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="125d2-132">Amikor később végrehajtja `M`, megkeresi a kimeneteli valószínűségek rögzített értékeit, és `M` `Zero` vagy `One` értéket ad vissza a 0,5 valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="125d2-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="125d2-133">Lásd még</span><span class="sxs-lookup"><span data-stu-id="125d2-133">See also</span></span>

<span data-ttu-id="125d2-134">A `ResourcesEstimator` a kvantum-számítógép [nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a metrikák széles választékát biztosítja, a teljes hívási gráfban lévő mérőszámok jelentését, valamint az olyan funkciókat, mint a [különböző bemenet-ellenőrök](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , amelyek segítenek a hibák keresésében a Q # programokon.</span><span class="sxs-lookup"><span data-stu-id="125d2-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="125d2-135">További információért tekintse meg a [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="125d2-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

