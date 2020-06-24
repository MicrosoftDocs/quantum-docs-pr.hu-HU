---
title: Quantum Development Kit Toffoli szimulátor
description: Ismerje meg a Microsoft QDK Toffoli szimulátort, amely egy speciális célú kvantum-szimulátor, amely több millió qubits is használható.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275144"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="d6605-103">Quantum Development Kit Toffoli szimulátor</span><span class="sxs-lookup"><span data-stu-id="d6605-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="d6605-104">A Quantum Development Kit egy Toffoli szimulátort biztosít, amely egy speciális célú szimulátor, amely képes szimulálni az X, a CNEM és a többszörösen vezérelt X Quantum műveletekre korlátozott kvantum-algoritmusokat (az összes klasszikus logika és számítás elérhető).</span><span class="sxs-lookup"><span data-stu-id="d6605-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="d6605-105">Habár a Toffoli-szimulátor sokkal nagyobb mértékben korlátozott a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)működésében, sokkal több qubits szimulálhat.</span><span class="sxs-lookup"><span data-stu-id="d6605-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="d6605-106">A Toffoli szimulátor több millió qubits is használható, míg a teljes állapotú szimulátor általában körülbelül 30-ra van korlátozva.</span><span class="sxs-lookup"><span data-stu-id="d6605-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="d6605-107">Végrehajthat és hibakeresést végezhet a számítógépen Q #-ban írt kvantum-algoritmusok korlátozott készletén. a logikai függvényeket kiértékelő Oracle-példányok például a következő kapuk használatával valósíthatók meg, így a szimulátor használatával változó nagy mennyiségű qubits is tesztelték.</span><span class="sxs-lookup"><span data-stu-id="d6605-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="d6605-108">Ezt a kvantum-szimulátort a osztályon keresztül teszi elérhetővé `ToffoliSimulator` .</span><span class="sxs-lookup"><span data-stu-id="d6605-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="d6605-109">A szimulátor használatához egyszerűen hozza létre az osztály egy példányát, és adja át a `Run` végrehajtani kívánt kvantum-művelet metódusának a többi paraméterrel együtt:</span><span class="sxs-lookup"><span data-stu-id="d6605-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="d6605-110">Egyéb műveletek</span><span class="sxs-lookup"><span data-stu-id="d6605-110">Other Operations</span></span>

<span data-ttu-id="d6605-111">A `ToffoliSimulator` támogatja a rotációs és a Exponentiated Paulis, például a és a használatát, `R` `Exp` Ha az eredményül kapott művelet egyenlő a `X` vagy az identitással.</span><span class="sxs-lookup"><span data-stu-id="d6605-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="d6605-112">A mérés és a érvényesítés támogatott, de csak a Pauli `Z` alapján.</span><span class="sxs-lookup"><span data-stu-id="d6605-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="d6605-113">Vegye figyelembe, hogy bizonyos mérték valószínűsége mindig 0 vagy 1; nincs véletlenszerűség a Toffoli-szimulátorban.</span><span class="sxs-lookup"><span data-stu-id="d6605-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="d6605-114">`DumpMachine`és `DumpRegister` támogatottak.</span><span class="sxs-lookup"><span data-stu-id="d6605-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="d6605-115">Mind az `Z` egyes qubit aktuális állapotának kimenetét jelentik, soronként egy qubit.</span><span class="sxs-lookup"><span data-stu-id="d6605-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="d6605-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="d6605-116">QubitCount</span></span>

<span data-ttu-id="d6605-117">Alapértelmezés szerint a `ToffoliSimulator` foglalt terület a 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="d6605-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="d6605-118">Ha az algoritmus ennél többre van szüksége, megváltoztathatja a qubit darabszámát úgy, hogy megadja a `qubitCount` paraméter értékét a konstruktornak.</span><span class="sxs-lookup"><span data-stu-id="d6605-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="d6605-119">Minden további qubit további memóriát igényel, így nincs jelentős ár a szükséges qubits számának túlbecsléséhez.</span><span class="sxs-lookup"><span data-stu-id="d6605-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="d6605-120">Például:</span><span class="sxs-lookup"><span data-stu-id="d6605-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
