---
title: A Quantum Development Kit erőforrásainak kalkulátora
description: 'Ismerje meg az erőforrások becslését, amely a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274887"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="4b654-103">Az erőforrások kalkulátor cél gépe</span><span class="sxs-lookup"><span data-stu-id="4b654-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="4b654-104">Ahogy a név is jelenti, a `ResourcesEstimator` becslések szerint a Q # művelet egy adott példányának futtatásához szükséges erőforrások a kvantum-számítógépen.</span><span class="sxs-lookup"><span data-stu-id="4b654-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="4b654-105">Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Emiatt megbecsülheti a Q # olyan műveleteinek erőforrásait, amelyek több ezer qubits használnak, ha a kód klasszikus része ésszerű időn belül futtatható.</span><span class="sxs-lookup"><span data-stu-id="4b654-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="4b654-106">Használat</span><span class="sxs-lookup"><span data-stu-id="4b654-106">Usage</span></span>

<span data-ttu-id="4b654-107">A `ResourcesEstimator` csak egy másik típusú célszámítógép, így bármilyen Q # művelet futtatására is használható.</span><span class="sxs-lookup"><span data-stu-id="4b654-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="4b654-108">Más célszámítógépként a C#-gazdagépen való használathoz hozzon létre egy példányt, és adja át a művelet metódusának első paramétereként `Run` :</span><span class="sxs-lookup"><span data-stu-id="4b654-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="4b654-109">A példa azt mutatja, `ResourcesEstimator` hogy a lehetővé teszi egy olyan `ToTSV()` tábla létrehozását, amely tabulátorral elválasztott értékeket (TSV) tartalmaz, amelyek fájlba menthetők, vagy a konzolba való beírással elemezhetők.</span><span class="sxs-lookup"><span data-stu-id="4b654-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="4b654-110">A fenti program kimenetének a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="4b654-110">The output of the above program should look something like this:</span></span>

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
> <span data-ttu-id="4b654-111">A `ResourcesEstimator` nem állítja alaphelyzetbe a számításokat minden futtatáskor, ha ugyanazt a példányt egy másik művelet végrehajtásához használja, a meglévő eredmények alapján megtartja az összesítést.</span><span class="sxs-lookup"><span data-stu-id="4b654-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="4b654-112">Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden végrehajtáshoz.</span><span class="sxs-lookup"><span data-stu-id="4b654-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="4b654-113">A becsült adatok programozott beolvasása</span><span class="sxs-lookup"><span data-stu-id="4b654-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="4b654-114">A TSV-táblázat mellett a becsült erőforrások programozott módon is beolvashatók a `ResourcesEstimator` `Data` tulajdonságán keresztül.</span><span class="sxs-lookup"><span data-stu-id="4b654-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="4b654-115">`Data``System.DataTable`két oszloppal rendelkező példányt biztosít: `Metric` és `Sum` a metrikák nevei szerint indexelve.</span><span class="sxs-lookup"><span data-stu-id="4b654-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="4b654-116">A következő kód azt mutatja be, hogyan lehet lekérdezni és kinyomtatni a `QubitClifford` `T` `CNOT` Q # művelet által használt teljes számát és kapuit:</span><span class="sxs-lookup"><span data-stu-id="4b654-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="4b654-117">Jelentett metrikák</span><span class="sxs-lookup"><span data-stu-id="4b654-117">Metrics Reported</span></span>

<span data-ttu-id="4b654-118">Az alábbi lista a becsült mérőszámokat sorolja fel `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="4b654-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="4b654-119">__Cnem__: a cnem (más néven ellenőrzött Pauli X Gate) Gates száma.</span><span class="sxs-lookup"><span data-stu-id="4b654-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="4b654-120">__QubitClifford__: egy qubit-es Clifford-és Pauli-kapuk száma.</span><span class="sxs-lookup"><span data-stu-id="4b654-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="4b654-121">__Mérték__: a végrehajtott mérések száma.</span><span class="sxs-lookup"><span data-stu-id="4b654-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="4b654-122">__R__: a végrehajtott egyetlen qubit-forgatások száma, kivéve a T, Clifford és Pauli gateset.</span><span class="sxs-lookup"><span data-stu-id="4b654-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="4b654-123">__T__: a t-kapuk és a benne lévő konjugátumok száma, beleértve a t-kaput, T_x = H. T. h, valamint T_y = a (z). t. a.</span><span class="sxs-lookup"><span data-stu-id="4b654-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="4b654-124">__Mélység__: a Q # művelet által végrehajtott kvantum-áramkör mélysége.</span><span class="sxs-lookup"><span data-stu-id="4b654-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="4b654-125">Alapértelmezés szerint csak a T-Gates számítanak bele a mélységbe, a részletekért lásd a részletes [számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="4b654-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="4b654-126">__Szélesség__: a Q # művelet végrehajtása során lefoglalt qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="4b654-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="4b654-127">__BorrowedWidth__: a Q # műveletben kölcsönzött qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="4b654-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="4b654-128">Mérési eredmények valószínűségének biztosítása</span><span class="sxs-lookup"><span data-stu-id="4b654-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="4b654-129"><xref:microsoft.quantum.intrinsic.assertprob>a névtérből megadható <xref:microsoft.quantum.intrinsic> , hogy milyen valószínűséggel kell megadnia egy mérés várható valószínűségét a Q # program végrehajtásának elősegítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b654-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="4b654-130">A következő példa ezt illusztrálja:</span><span class="sxs-lookup"><span data-stu-id="4b654-130">The following example illustrates this:</span></span>

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

<span data-ttu-id="4b654-131">Amikor a `ResourcesEstimator` `AssertProb` rendszer megkezdi a mérést `PauliZ` , `source` és a 0,5-as `q` `Zero` valószínűséggel a következő eredményt kapja:.</span><span class="sxs-lookup"><span data-stu-id="4b654-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="4b654-132">Amikor később végrehajtja `M` , a rendszer megkeresi a kimeneteli valószínűségek rögzített értékeit, és `M` visszaküldi `Zero` vagy `One` a 0,5-es valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="4b654-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="4b654-133">Lásd még</span><span class="sxs-lookup"><span data-stu-id="4b654-133">See also</span></span>

<span data-ttu-id="4b654-134">A a `ResourcesEstimator` kvantum-számítógép [nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a metrikák széles választékát biztosítja, a teljes hívás – gráf mérőszámait és a különböző funkciókat (például a [DISTINCT Inputs-ellenőröket](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) ) a Q # programok hibáinak megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="4b654-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="4b654-135">További információért tekintse meg a [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="4b654-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

