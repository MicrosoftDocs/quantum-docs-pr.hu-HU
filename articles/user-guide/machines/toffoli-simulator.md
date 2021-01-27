---
title: Quantum Toffoli Simulator – Quantum Development Kit
description: Ismerje meg a Microsoft QDK Toffoli szimulátort, amely egy speciális célú kvantum-szimulátor, amely több millió qubits is használható.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 84b958912ab5116a3181c8eff4f331fc8394604c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858567"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="88b05-103">Quantum Development Kit (QDK) Toffoli szimulátor</span><span class="sxs-lookup"><span data-stu-id="88b05-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="88b05-104">A QDK Toffoli szimulátor egy speciális célú szimulátor, amely korlátozott hatókörű, és csak a `X` , `CNOT` és a többszörösen vezérelt `X` kvantum-műveleteket támogatja.</span><span class="sxs-lookup"><span data-stu-id="88b05-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="88b05-105">Minden klasszikus logika és számítás elérhető.</span><span class="sxs-lookup"><span data-stu-id="88b05-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="88b05-106">Habár a Toffoli-szimulátor a [teljes állapotú szimulátornál](xref:microsoft.quantum.machines.full-state-simulator)szigorúbb működésre korlátozódik, az előnye, hogy sokkal több qubits szimulál.</span><span class="sxs-lookup"><span data-stu-id="88b05-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="88b05-107">A Toffoli szimulátor több millió qubits is használható, míg a teljes állapotú szimulátor körülbelül 30 qubits-ra van korlátozva.</span><span class="sxs-lookup"><span data-stu-id="88b05-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="88b05-108">Ez hasznos lehet például olyan Oracle-megoldásokkal, amelyek a logikai függvényeket értékelik ki – ezek a támogatott algoritmusok korlátozott készletével valósíthatók meg, és nagy számú qubits tesztelték.</span><span class="sxs-lookup"><span data-stu-id="88b05-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="88b05-109">A Toffoli szimulátor meghívása</span><span class="sxs-lookup"><span data-stu-id="88b05-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="88b05-110">A Toffoli szimulátort a osztályon keresztül teheti elérhetővé `ToffoliSimulator` .</span><span class="sxs-lookup"><span data-stu-id="88b05-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="88b05-111">További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="88b05-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="88b05-112">A Toffoli szimulátor meghívása a C-ből #</span><span class="sxs-lookup"><span data-stu-id="88b05-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="88b05-113">Ahogy más célgépek esetében is, először a `ToffoliSimulator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.</span><span class="sxs-lookup"><span data-stu-id="88b05-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="88b05-114">Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `ToffoliSimulator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.</span><span class="sxs-lookup"><span data-stu-id="88b05-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="88b05-115">A Toffoli szimulátor meghívása a Pythonból</span><span class="sxs-lookup"><span data-stu-id="88b05-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="88b05-116">Használja az [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q# művelettel:</span><span class="sxs-lookup"><span data-stu-id="88b05-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="88b05-117">A Toffoli szimulátor meghívása a parancssorból</span><span class="sxs-lookup"><span data-stu-id="88b05-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="88b05-118">Ha a Q# parancssorból futtat egy programot, a **--Simulator** (vagy a **-s** parancsikon) paraméterrel adhatja meg a Toffoli Simulator célszámítógép értékét.</span><span class="sxs-lookup"><span data-stu-id="88b05-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="88b05-119">A következő parancs egy programot futtat az erőforrás-kalkulátor használatával:</span><span class="sxs-lookup"><span data-stu-id="88b05-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="88b05-120">A Toffoli szimulátor meghívása a Juptyer-jegyzetfüzetekről</span><span class="sxs-lookup"><span data-stu-id="88b05-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="88b05-121">A Q# művelet futtatásához használja a [(z)% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) I Magic-parancsot Q# .</span><span class="sxs-lookup"><span data-stu-id="88b05-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="88b05-122">Támogatott műveletek</span><span class="sxs-lookup"><span data-stu-id="88b05-122">Supported operations</span></span>

<span data-ttu-id="88b05-123">A Toffoli Simulator a következőket támogatja:</span><span class="sxs-lookup"><span data-stu-id="88b05-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="88b05-124">A Forgások és a exponentiated Paulis, `R` például `Exp` a és a, ha az eredményül kapott művelet egyenlő `X` vagy az Identity Matrix.</span><span class="sxs-lookup"><span data-stu-id="88b05-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="88b05-125">Mérési és [érvényesítési](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) műveletek, de csak a Pauli `Z` alapján.</span><span class="sxs-lookup"><span data-stu-id="88b05-125">Measurement and [assert](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="88b05-126">Vegye figyelembe, hogy a mérési művelet valószínűsége mindig **0** vagy **1**; nincs véletlenszerűség a Toffoli-szimulátorban.</span><span class="sxs-lookup"><span data-stu-id="88b05-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="88b05-127">`DumpMachine` és `DumpRegister` függvények.</span><span class="sxs-lookup"><span data-stu-id="88b05-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="88b05-128">Mindkét függvény az `Z` egyes qubit aktuális állapotának kimenetét adja eredményül, soronként egy qubit.</span><span class="sxs-lookup"><span data-stu-id="88b05-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="88b05-129">A qubits számának meghatározása</span><span class="sxs-lookup"><span data-stu-id="88b05-129">Specifying the number of qubits</span></span>

<span data-ttu-id="88b05-130">Alapértelmezés szerint a `ToffoliSimulator` példány lemezterületet foglal le a 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="88b05-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="88b05-131">Ha az algoritmus ennél több qubits igényel, akkor megadhatja a qubit darabszámot úgy, hogy megadja a `qubitCount` paraméter értékét a konstruktornak.</span><span class="sxs-lookup"><span data-stu-id="88b05-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="88b05-132">Minden további qubit csak egy bájt memóriát igényel, így nincs jelentős ár a szükséges qubits számának túlbecsléséhez.</span><span class="sxs-lookup"><span data-stu-id="88b05-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="88b05-133">Például:</span><span class="sxs-lookup"><span data-stu-id="88b05-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="88b05-134">Lásd még</span><span class="sxs-lookup"><span data-stu-id="88b05-134">See also</span></span>

- [<span data-ttu-id="88b05-135">Quantum-erőforrások kalkulátora</span><span class="sxs-lookup"><span data-stu-id="88b05-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="88b05-136">Quantum Trace Simulator</span><span class="sxs-lookup"><span data-stu-id="88b05-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="88b05-137">Quantum teljes állapot szimulátor</span><span class="sxs-lookup"><span data-stu-id="88b05-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 