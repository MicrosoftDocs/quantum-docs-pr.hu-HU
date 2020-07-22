---
title: Quantum Toffoli Simulator – Quantum Development Kit
description: Ismerje meg a Microsoft QDK Toffoli szimulátort, amely egy speciális célú kvantum-szimulátor, amely több millió qubits is használható.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870617"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="b6c30-103">Quantum Development Kit (QDK) Toffoli szimulátor</span><span class="sxs-lookup"><span data-stu-id="b6c30-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="b6c30-104">A QDK Toffoli szimulátor egy speciális célú szimulátor, amely korlátozott hatókörű, és csak a `X` , `CNOT` és a többszörösen vezérelt `X` kvantum-műveleteket támogatja.</span><span class="sxs-lookup"><span data-stu-id="b6c30-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="b6c30-105">Minden klasszikus logika és számítás elérhető.</span><span class="sxs-lookup"><span data-stu-id="b6c30-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="b6c30-106">Habár a Toffoli-szimulátor a [teljes állapotú szimulátornál](xref:microsoft.quantum.machines.full-state-simulator)szigorúbb működésre korlátozódik, az előnye, hogy sokkal több qubits szimulál.</span><span class="sxs-lookup"><span data-stu-id="b6c30-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="b6c30-107">A Toffoli szimulátor több millió qubits is használható, míg a teljes állapotú szimulátor körülbelül 30 qubits-ra van korlátozva.</span><span class="sxs-lookup"><span data-stu-id="b6c30-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="b6c30-108">Ez hasznos lehet például olyan Oracle-megoldásokkal, amelyek a logikai függvényeket értékelik ki – ezek a támogatott algoritmusok korlátozott készletével valósíthatók meg, és nagy számú qubits tesztelték.</span><span class="sxs-lookup"><span data-stu-id="b6c30-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="b6c30-109">A Toffoli szimulátor meghívása</span><span class="sxs-lookup"><span data-stu-id="b6c30-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="b6c30-110">A Toffoli szimulátort a osztályon keresztül teheti elérhetővé `ToffoliSimulator` .</span><span class="sxs-lookup"><span data-stu-id="b6c30-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="b6c30-111">További részleteket a [Q # program futtatásának módjai](xref:microsoft.quantum.guide.host-programs)című témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="b6c30-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="b6c30-112">A Toffoli szimulátor meghívása a C-ből #</span><span class="sxs-lookup"><span data-stu-id="b6c30-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="b6c30-113">A többi célszámítógépen hasonlóan először létre kell hoznia a osztály egy példányát, `ToffoliSimulator` majd át kell adni a művelet metódusának első paramétereként `Run` .</span><span class="sxs-lookup"><span data-stu-id="b6c30-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b6c30-114">Vegye figyelembe, hogy az osztálytól eltérően `QuantumSimulator` az `ToffoliSimulator` osztály nem valósítja <xref:System.IDisposable> meg a felületet, így nem kell azt egy utasításon belül csatolnia `using` .</span><span class="sxs-lookup"><span data-stu-id="b6c30-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="b6c30-115">A Toffoli szimulátor meghívása a Pythonból</span><span class="sxs-lookup"><span data-stu-id="b6c30-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="b6c30-116">Használja az [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q # művelettel:</span><span class="sxs-lookup"><span data-stu-id="b6c30-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="b6c30-117">A Toffoli szimulátor meghívása a parancssorból</span><span class="sxs-lookup"><span data-stu-id="b6c30-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="b6c30-118">Ha Q # programot futtat a parancssorból, a **--Simulator** (vagy **-s** parancsikon) paraméterrel adhatja meg a Toffoli Simulator célszámítógép értékét.</span><span class="sxs-lookup"><span data-stu-id="b6c30-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="b6c30-119">A következő parancs egy programot futtat az erőforrás-kalkulátor használatával:</span><span class="sxs-lookup"><span data-stu-id="b6c30-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="b6c30-120">A Toffoli szimulátor meghívása a Juptyer-jegyzetfüzetekről</span><span class="sxs-lookup"><span data-stu-id="b6c30-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="b6c30-121">A Q # művelet futtatásához használja a [(z)% TOFFOLI](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) IQ # Magic-parancsot.</span><span class="sxs-lookup"><span data-stu-id="b6c30-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="b6c30-122">Támogatott műveletek</span><span class="sxs-lookup"><span data-stu-id="b6c30-122">Supported operations</span></span>

<span data-ttu-id="b6c30-123">A Toffoli Simulator a következőket támogatja:</span><span class="sxs-lookup"><span data-stu-id="b6c30-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="b6c30-124">A Forgások és a exponentiated Paulis, `R` például `Exp` a és a, ha az eredményül kapott művelet egyenlő `X` vagy az Identity Matrix.</span><span class="sxs-lookup"><span data-stu-id="b6c30-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="b6c30-125">Mérési és [érvényesítési](xref:microsoft.quantum.diagnostics.assertmeasurement) műveletek, de csak a Pauli `Z` alapján.</span><span class="sxs-lookup"><span data-stu-id="b6c30-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="b6c30-126">Vegye figyelembe, hogy a mérési művelet valószínűsége mindig **0** vagy **1**; nincs véletlenszerűség a Toffoli-szimulátorban.</span><span class="sxs-lookup"><span data-stu-id="b6c30-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="b6c30-127">`DumpMachine`és `DumpRegister` függvények.</span><span class="sxs-lookup"><span data-stu-id="b6c30-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="b6c30-128">Mindkét függvény az `Z` egyes qubit aktuális állapotának kimenetét adja eredményül, soronként egy qubit.</span><span class="sxs-lookup"><span data-stu-id="b6c30-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="b6c30-129">A qubits számának meghatározása</span><span class="sxs-lookup"><span data-stu-id="b6c30-129">Specifying the number of qubits</span></span>

<span data-ttu-id="b6c30-130">Alapértelmezés szerint a `ToffoliSimulator` példány lemezterületet foglal le a 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="b6c30-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="b6c30-131">Ha az algoritmus ennél több qubits igényel, akkor megadhatja a qubit darabszámot úgy, hogy megadja a `qubitCount` paraméter értékét a konstruktornak.</span><span class="sxs-lookup"><span data-stu-id="b6c30-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="b6c30-132">Minden további qubit csak egy bájt memóriát igényel, így nincs jelentős ár a szükséges qubits számának túlbecsléséhez.</span><span class="sxs-lookup"><span data-stu-id="b6c30-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="b6c30-133">Például:</span><span class="sxs-lookup"><span data-stu-id="b6c30-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="b6c30-134">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b6c30-134">See also</span></span>

- [<span data-ttu-id="b6c30-135">Quantum-erőforrások kalkulátora</span><span class="sxs-lookup"><span data-stu-id="b6c30-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="b6c30-136">Quantum Trace Simulator</span><span class="sxs-lookup"><span data-stu-id="b6c30-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="b6c30-137">Quantum teljes állapot szimulátor</span><span class="sxs-lookup"><span data-stu-id="b6c30-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 