---
title: Quantum Development Kit Toffoli szimulátor
description: Ismerje meg a Microsoft QDK Toffoli szimulátort, amely egy speciális célú kvantum-szimulátor, amely több millió qubits is használható.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907018"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Quantum Development Kit Toffoli szimulátor

A Quantum Development Kit egy Toffoli szimulátort biztosít, amely egy speciális célú szimulátor, amely képes szimulálni az X, a CNEM és a többszörösen vezérelt X Quantum műveletekre korlátozott kvantum-algoritmusokat (az összes klasszikus logika és számítás elérhető).

Habár a Toffoli-szimulátor sokkal nagyobb mértékben korlátozott a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)működésében, sokkal több qubits szimulálhat.
A Toffoli szimulátor több millió qubits is használható, míg a teljes állapotú szimulátor általában körülbelül 30-ra van korlátozva.
Végrehajthat és hibakeresést végezhet a számítógépen Q #-ban írt kvantum-algoritmusok korlátozott készletén. a logikai függvényeket kiértékelő Oracle-példányok például a következő kapuk használatával valósíthatók meg, így a szimulátor használatával változó nagy mennyiségű qubits is tesztelték.

Ez a Quantum Simulator a `ToffoliSimulator` osztályon keresztül érhető el.
A szimulátor használatához egyszerűen hozza létre ennek az osztálynak egy példányát, és adja át a végrehajtani kívánt kvantum-művelet `Run` metódusának a többi paraméterrel együtt:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Egyéb műveletek

A `ToffoliSimulator` támogatja a rotációs és exponentiated Paulis, például a `R` és a `Exp`használatát, ha az eredményül kapott művelet `X` vagy az identitásnak felel meg.

A mérés és a érvényesítés támogatott, de csak a Pauli `Z` alapján.
Vegye figyelembe, hogy bizonyos mérték valószínűsége mindig 0 vagy 1; nincs véletlenszerűség a Toffoli-szimulátorban.

a `DumpMachine` és a `DumpRegister` támogatottak.
Mindkettő az egyes qubit aktuális `Z`-alapú állapotát adja eredményül, soronként egy qubit.

## <a name="qubitcount"></a>QubitCount

Alapértelmezés szerint a `ToffoliSimulator` tárterületet foglal le a 65 536 qubits számára.
Ha az algoritmus ennél többre van szüksége, a qubit megváltoztatásához adja meg a `qubitCount` paraméter értékét a konstruktor számára.
Minden további qubit további memóriát igényel, így nincs jelentős ár a szükséges qubits számának túlbecsléséhez.

Például:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
