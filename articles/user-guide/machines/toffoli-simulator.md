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
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Quantum Development Kit (QDK) Toffoli szimulátor

A QDK Toffoli szimulátor egy speciális célú szimulátor, amely korlátozott hatókörű, és csak a `X` , `CNOT` és a többszörösen vezérelt `X` kvantum-műveleteket támogatja. Minden klasszikus logika és számítás elérhető.

Habár a Toffoli-szimulátor a [teljes állapotú szimulátornál](xref:microsoft.quantum.machines.full-state-simulator)szigorúbb működésre korlátozódik, az előnye, hogy sokkal több qubits szimulál. A Toffoli szimulátor több millió qubits is használható, míg a teljes állapotú szimulátor körülbelül 30 qubits-ra van korlátozva. Ez hasznos lehet például olyan Oracle-megoldásokkal, amelyek a logikai függvényeket értékelik ki – ezek a támogatott algoritmusok korlátozott készletével valósíthatók meg, és nagy számú qubits tesztelték.

## <a name="invoking-the-toffoli-simulator"></a>A Toffoli szimulátor meghívása

A Toffoli szimulátort a osztályon keresztül teheti elérhetővé `ToffoliSimulator` . További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>A Toffoli szimulátor meghívása a C-ből #

Ahogy más célgépek esetében is, először a `ToffoliSimulator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.

Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `ToffoliSimulator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>A Toffoli szimulátor meghívása a Pythonból

Használja az [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q# művelettel:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>A Toffoli szimulátor meghívása a parancssorból

Ha a Q# parancssorból futtat egy programot, a **--Simulator** (vagy a **-s** parancsikon) paraméterrel adhatja meg a Toffoli Simulator célszámítógép értékét. A következő parancs egy programot futtat az erőforrás-kalkulátor használatával: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>A Toffoli szimulátor meghívása a Juptyer-jegyzetfüzetekről

A Q# művelet futtatásához használja a [(z)% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) I Magic-parancsot Q# .

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Támogatott műveletek

A Toffoli Simulator a következőket támogatja:

* A Forgások és a exponentiated Paulis, `R` például `Exp` a és a, ha az eredményül kapott művelet egyenlő `X` vagy az Identity Matrix.
* Mérési és [érvényesítési](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) műveletek, de csak a Pauli `Z` alapján. Vegye figyelembe, hogy a mérési művelet valószínűsége mindig **0** vagy **1**; nincs véletlenszerűség a Toffoli-szimulátorban.
* `DumpMachine` és `DumpRegister` függvények.
Mindkét függvény az `Z` egyes qubit aktuális állapotának kimenetét adja eredményül, soronként egy qubit.

## <a name="specifying-the-number-of-qubits"></a>A qubits számának meghatározása

Alapértelmezés szerint a `ToffoliSimulator` példány lemezterületet foglal le a 65 536 qubits.
Ha az algoritmus ennél több qubits igényel, akkor megadhatja a qubit darabszámot úgy, hogy megadja a `qubitCount` paraméter értékét a konstruktornak.
Minden további qubit csak egy bájt memóriát igényel, így nincs jelentős ár a szükséges qubits számának túlbecsléséhez.

Például:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Lásd még

- [Quantum-erőforrások kalkulátora](xref:microsoft.quantum.machines.resources-estimator)
- [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Quantum teljes állapot szimulátor](xref:microsoft.quantum.machines.full-state-simulator) 