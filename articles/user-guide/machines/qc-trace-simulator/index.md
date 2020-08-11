---
title: Kvantum-nyomkövetési szimulátor – Quantum Development Kit
description: Ismerje meg, hogyan használható a Microsoft kvantumszámítógépekhez való nyomkövetési szimulátora klasszikus kódok hibakereséséhez, illetve Q#-programok erőforrásigényeinek becsléséhez.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d5efef037ff236bd040dfd88e94f7f3dd331aef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868219"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Microsoft Quantum Development Kit (QDK) – Kvantum-nyomkövetési szimulátor

A QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> osztály kvantumprogramot futtat a kvantumszámítógép állapotának tényleges szimulálása nélkül. Emiatt a kvantum-nyomkövetési szimulátor olyan kvantumprogramokat is futtathat, amelyek több ezer qubitet használnak.  Ez két főbb okból lehet hasznos: 

* Olyan klasszikus kódok hibakeresésekor, amelyek egy kvantumprogram részei. 
* Annak a megbecsléséhez, mennyi erőforrásra van szükség a kvantumprogramok egy adott példányának a kvantumszámítógépen való futtatásához. Az [Erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator), amely metrikák korlátozottabb készletét biztosítja, valójában a nyomkövetési szimulátorra épül.

## <a name="invoking-the-quantum-trace-simulator"></a>A kvantum-nyomkövetési szimulátor meghívása

A kvantum-nyomkövetési szimulátorral bármilyen Q#-művelet futtatható.

Ahogy más célgépek esetében is, először a `QCTraceSimulator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.

Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `QCTraceSimulator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Mérési eredmények valószínűségének megadása

Mivel a kvantum-nyomkövetési szimulátor nem szimulálja a tényleges kvantumállapotot, ezért nem tudja kiszámolni a mérési eredmények valószínűségét egy műveletben. 

Ezért ha a művelet méréseket tartalmaz, a valószínűségeket explicit módon kell megadnia a <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> művelettel a <xref:microsoft.quantum.diagnostics> névtérből. A következő példa ezt illusztrálja:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Amikor a kvantum-nyomkövetési szimulátor végrehajtja az `AssertMeasurementProbability` műveletet, rögzíti, hogy a `PauliZ` mérése a `source` és a `q` esetében **0,5**-ös valószínűséggel `Zero` eredményt ad. Ha később futtatja az `M` műveletet, megkeresi a kimeneti valószínűségek rögzített értékeit, és az `M` **0,5**-ös valószínűséggel `Zero` vagy `One` eredményt ad. Ha ugyanazt a kódot egy olyan szimulátoron futtatja, amely nyomon követi a kvantumállapotot, a szimulátor ellenőrzi, hogy az `AssertMeasurementProbability` megadott valószínűségei helyesek-e.

Ügyeljen arra, hogy ha van legalább egy olyan mérési művelet, amely nem lett jegyzettel ellátva az `AssertMeasurementProbability` használatával, a szimulátor [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception) kivételt ad vissza.

## <a name="quantum-trace-simulator-tools"></a>Kvantum-nyomkövetési szimulátor – Eszközök

A QDK öt olyan, a kvantum-nyomkövetési szimulátorral használható eszközt foglal magába, amelyekkel észlelhetők a programok hibái és végrehajthatók a kvantumprogramok erőforrás-becslései: 

|Eszköz | Leírás |
|-----| -----|
|[Eltérő bemenetek ellenőrzője](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |A közös qubitek lehetséges ütközéseit ellenőrzi |
|[Érvénytelenített qubithasználat ellenőrzője](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Ellenőrzi, hogy a program alkalmaz-e műveletet egy már kiadott qubitre |
|[Primitív műveletek számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Megszámlálja a kvantumprogramban meghívott összes művelet által használt primitív végrehajtásokat  |
|[Mélységszámláló](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Összegyűjti a kvantumprogramban meghívott összes művelet mélysége alsó határértékei darabszámát   |
|[Szélességszámláló](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Megszámlálja a kvantumprogram egyes műveletei által lefoglalt és kölcsönzött qubiteket |

Az eszközök engedélyezéséhez be kell állítani a megfelelő jelzőt a `QCTraceSimulatorConfiguration` elemnél, majd meg kell adni a konfigurációt a `QCTraceSimulator` deklarációhoz. Az eszközök használatával kapcsolatos információk az előző listában lévő hivatkozásokon érhetők el. További információk a `QCTraceSimulator` konfigurálásáról: [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>A QCTraceSimulator metódusai

A `QCTraceSimulator` többféle beépített metódussal rendelkezik a kvantumművelet során nyomon követett metrikák értékeinek lekéréséhez. A [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) és a [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) metódusokra a [Primitív műveletek számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), a [Mélységszámláló](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) és a [Szélességszámláló](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) cikkekben talál példákat. Az összes elérhető metódusról a Q# API-referencia [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) szakaszában talál további információkat.  

## <a name="see-also"></a>Lásd még

- [Kvantumerőforrás-becslő](xref:microsoft.quantum.machines.resources-estimator)
- [Toffoli-kvantumszimulátor](xref:microsoft.quantum.machines.toffoli-simulator)
- [Teljes körű funkciókkal rendelkező kvantumszimulátor](xref:microsoft.quantum.machines.full-state-simulator) 