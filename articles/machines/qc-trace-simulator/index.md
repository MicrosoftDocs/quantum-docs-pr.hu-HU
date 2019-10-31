---
title: Kvantumszámítógép nyomkövetési szimulátora | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035139"
---
# <a name="quantum-trace-simulator"></a>Kvantum-nyomkövetési szimulátor

A Microsoft kvantumszámítógépekhez való nyomkövetési szimulátora egy kvantumprogramot hajt végre a kvantumszámítógép állapotának tényleges szimulálása nélkül.  Emiatt a nyomkövetési szimulátor olyan kvantumprogramokat is futtathat, amelyek több ezer qubitet használnak.  Ez két főbb okból lehet hasznos: 

* Olyan klasszikus kódok hibakeresésekor, amelyek egy kvantumprogram részei. 
* Annak a megbecsléséhez, mennyi erőforrásra van szükség a kvantumprogramok egy adott példányának a kvantumszámítógépen való futtatásához.

A nyomkövetési szimulátor a felhasználó által a mérések végrehajtásakor megadandó további információkra támaszkodik. További részletekért tekintse meg a [mérési eredmények valószínűségének biztosításával](#providing-the-probability-of-measurement-outcomes) foglalkozó témakört. 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Mérési eredmények valószínűségének biztosítása

A kvantumalgoritmusokban kétféle mérték szerepel. Az első kiegészítő szerepet tölt be, mert a felhasználó általában ismeri a kimenetel valószínűségét. Ebben az esetben a felhasználó beírhat egy <xref:microsoft.quantum.primitive.assertprob> műveletet a <xref:microsoft.quantum.primitive> névtérből, hogy kifejezze a birtokában lévő tudást. A következő példa ezt illusztrálja:

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

Amikor a nyomkövetési szimulátor végrehajtja az `AssertProb` műveletet, rögzíti, hogy a `PauliZ` mérése a `source` és az `ancilla` esetében 0,5-ös valószínűséggel `Zero` eredményt ad. Ha a szimulátor később végrehajtja az `M` műveletet, megtalálja a kimeneti valószínűséghez rögzített értékeket, és az `M` 0,5-ös valószínűséggel `Zero` vagy `One` eredményt ad ki. Ha ugyanazt a kódot egy olyan szimulátoron hajtja végre, amely nyomon követi a kvantumállapotot, a szimulátor ellenőrizni fogja, hogy az `AssertProb` megadott valószínűségei helyesek-e.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Program futtatása a kvantumszámítógép nyomkövetési szimulátorával 

A kvantumszámítógép nyomkövetési szimulátora tekinthető úgy, mint egy másik célszámítógép. A használatára szolgáló C#-illesztő nagyon hasonló a bármelyik másik kvantumszimulátorhoz használthoz: 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Figyelje meg, hogy ha legalább egy mérést nem látott el jegyzettel az `AssertProb` használatával, a szimulátor `UnconstrainedMeasurementException` kivételt ad vissza a `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` névtérből. További részleteket az [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) API-dokumentációban találhat.

A kvantumprogramok futtatása mellett a nyomkövetési szimulátor öt olyan összetevővel is rendelkezik, amelyek képesek a kvantumprogramok hibáinak észlelésére és erőforrás-becsléseinek végrehajtására: 

* [Eltérő bemenetek ellenőrzője](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Érvénytelenített qubithasználat ellenőrzője](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Primitív műveletek számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Kvantumkörök mélységének számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Kvantumkörök szélességének számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Ezek az összetevők a megfelelő jelzők beállításával engedélyezhetők a `QCTraceSimulatorConfiguration` elemnél. Az egyes összetevők használatáról további részleteket a megfelelő referenciafájlokban talál. A részletekért tekintse meg a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) API-dokumentációját.

## <a name="see-also"></a>Lásd még
A kvantumszámítógép [nyomkövetési szimulátorának](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C#-referenciája 

