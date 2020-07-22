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
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Quantum Development Kit (QDK) Toffoli szimulátor

A QDK Toffoli szimulátor egy speciális célú szimulátor, amely korlátozott hatókörű, és csak a `X` , `CNOT` és a többszörösen vezérelt `X` kvantum-műveleteket támogatja. Minden klasszikus logika és számítás elérhető.

Habár a Toffoli-szimulátor a [teljes állapotú szimulátornál](xref:microsoft.quantum.machines.full-state-simulator)szigorúbb működésre korlátozódik, az előnye, hogy sokkal több qubits szimulál. A Toffoli szimulátor több millió qubits is használható, míg a teljes állapotú szimulátor körülbelül 30 qubits-ra van korlátozva. Ez hasznos lehet például olyan Oracle-megoldásokkal, amelyek a logikai függvényeket értékelik ki – ezek a támogatott algoritmusok korlátozott készletével valósíthatók meg, és nagy számú qubits tesztelték.

## <a name="invoking-the-toffoli-simulator"></a>A Toffoli szimulátor meghívása

A Toffoli szimulátort a osztályon keresztül teheti elérhetővé `ToffoliSimulator` . További részleteket a [Q # program futtatásának módjai](xref:microsoft.quantum.guide.host-programs)című témakörben talál.

### <a name="invoking-the-toffoli-simulator-from-c"></a>A Toffoli szimulátor meghívása a C-ből #

A többi célszámítógépen hasonlóan először létre kell hoznia a osztály egy példányát, `ToffoliSimulator` majd át kell adni a művelet metódusának első paramétereként `Run` .

Vegye figyelembe, hogy az osztálytól eltérően `QuantumSimulator` az `ToffoliSimulator` osztály nem valósítja <xref:System.IDisposable> meg a felületet, így nem kell azt egy utasításon belül csatolnia `using` .

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>A Toffoli szimulátor meghívása a Pythonból

Használja az [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q # művelettel:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>A Toffoli szimulátor meghívása a parancssorból

Ha Q # programot futtat a parancssorból, a **--Simulator** (vagy **-s** parancsikon) paraméterrel adhatja meg a Toffoli Simulator célszámítógép értékét. A következő parancs egy programot futtat az erőforrás-kalkulátor használatával: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>A Toffoli szimulátor meghívása a Juptyer-jegyzetfüzetekről

A Q # művelet futtatásához használja a [(z)% TOFFOLI](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) IQ # Magic-parancsot.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Támogatott műveletek

A Toffoli Simulator a következőket támogatja:

* A Forgások és a exponentiated Paulis, `R` például `Exp` a és a, ha az eredményül kapott művelet egyenlő `X` vagy az Identity Matrix.
* Mérési és [érvényesítési](xref:microsoft.quantum.diagnostics.assertmeasurement) műveletek, de csak a Pauli `Z` alapján. Vegye figyelembe, hogy a mérési művelet valószínűsége mindig **0** vagy **1**; nincs véletlenszerűség a Toffoli-szimulátorban.
* `DumpMachine`és `DumpRegister` függvények.
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