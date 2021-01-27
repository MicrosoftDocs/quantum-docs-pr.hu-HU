---
title: Quantum erőforrás-kalkulátor – Quantum Development Kit
description: Ismerje meg a Microsoft QDK erőforrásainak kalkulátorát, amely a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg Q# .
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847464"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>A Quantum Development Kit (QDK) erőforrásainak kalkulátora

Ahogy a név is jelenti, az `ResourcesEstimator` osztály a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli Q# meg. Ezt a kvantum-művelet futtatásával hajtja végre, a kvantum-számítógép állapotának tényleges szimulálása nélkül. Emiatt a Q# több ezer qubits-t használó műveletek erőforrásainak becslése, ha a kód klasszikus része ésszerű időn belül fut.

Az erőforrások becslése a [kvantum-nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a mérőszámok és eszközök sokoldalú készletét kínálja a programok hibakereséséhez Q# .

## <a name="invoking-and-running-the-resources-estimator"></a>Az erőforrás-kalkulátor meghívása és futtatása

Az erőforrás-kalkulátor használatával bármilyen Q# műveletet futtathat. További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>A C-ből származó erőforrások becslésének meghívása # 

Ahogy más célgépek esetében is, először a `ResourcesEstimator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.

Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `ResourcesEstimator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.

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

A példa bemutatja `ResourcesEstimator` a `ToTSV()` metódust, amely létrehoz egy tabulátorral tagolt értékeket (TSV) tartalmazó táblázatot. Mentheti a táblázatot egy fájlba, vagy megjelenítheti a konzolon az elemzéshez. Az alábbi példa az előző program kimenetét jeleníti meg:

```output
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
> A `ResourcesEstimator` példányok nem állítják alaphelyzetbe a számításokat minden futtatáskor. Ha ugyanazt a példányt használja egy másik művelet futtatására, az új eredményeket összegzi a meglévő eredményekkel. Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden futtatáshoz.

### <a name="invoking-the-resources-estimator-from-python"></a>Az erőforrás-kalkulátor meghívása a Pythonból

Használja az [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q# művelettel:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Az erőforrás-kalkulátor meghívása a parancssorból

Ha a Q# parancssorból futtat egy programot, használja a **--Simulator** (vagy **-s** parancsikon) paramétert a célszámítógép megadásához `ResourcesEstimator` . A következő parancs egy programot futtat az erőforrás-kalkulátor használatával: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>A Juptyer-jegyzetfüzetek erőforrásainak becslése

A Q# művelet futtatásához használja a I Magic parancs [%-os becslését](xref:microsoft.quantum.iqsharp.magic-ref.simulate) Q# .

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>A becsült adatok programozott beolvasása

A TSV-táblázat mellett programozott módon is lekérheti a Futtatás során becsült erőforrásokat az erőforrások becslésének `Data` tulajdonságán keresztül. A `Data` tulajdonság egy olyan `System.DataTable` példányt biztosít, amelyben két oszlop szerepel: `Metric` és `Sum` a metrikák nevei vannak indexelve.

A következő kód bemutatja, hogyan lehet lekérdezni és kinyomtatni a műveletek teljes számát `QubitClifford` `T` és a `CNOT` műveletek által használt műveleteket Q# :

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

## <a name="metrics-reported"></a>Jelentett metrikák

Az erőforrások becslése a következő metrikákat követi nyomon:

|Metric|Leírás|
|----|----|
|__CNOT__    |A műveletek futtatási száma `CNOT` (más néven vezérelt Pauli X-műveletek).|
|__QubitClifford__ |Egyetlen qubit Clifford-és Pauli-művelet futtatási száma.|
|__Measure__    |A mérések futtatásának száma.  |
|__R__    |A qubit-Forgások futtatásának száma, kivéve a `T` Clifford és a Pauli műveletet.  |
|__T__    |A `T` műveletek és a konjugátumok futtatásának száma, beleértve a `T` műveleteket, a T_x = H. T. h és a T_y = a kifogyott. t. vízterületet.  |
|__Mélység__|A művelet által futtatott Quantum Circuit mélysége Q# (lásd [alább](#depth-width-and-qubitcount)). Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja. További részletekért lásd a [részletes számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Szélesség__|A művelet által futtatott kvantum-kör szélessége Q# (lásd [alább](#depth-width-and-qubitcount)). Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja. További részletek: a [szélesség számlálója](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).   |
|__QubitCount__    |A művelet futtatása során lefoglalt qubits maximális számának alsó határa Q# . Lehetséges, hogy ez a metrika nem kompatibilis a __mélységgel__ (lásd alább).  |
|__BorrowedWidth__    |A műveleten belül kölcsönzött qubits maximális száma Q# .  |


## <a name="depth-width-and-qubitcount"></a>Mélység, szélesség és QubitCount

A jelentett mélységi és szélességi becslések kompatibilisek egymással.
(Korábban mindkét szám elérhető volt, de a mélységhez és a szélességhez eltérő áramkörökre lenne szükség.) A párosban jelenleg mindkét metrikát ugyanazzal az áramkörrel lehet megvalósítani.

A következő metrikákat kell jelenteni:

__Mélység:__ A gyökérszintű művelethez – a konfigurált időpontok végrehajtásához szükséges idő.
A (z) vagy az azt követő műveletek – a művelet elején és végén a legutóbbi qubit rendelkezésre állási idő közötti különbség.

__Szélesség:__ A gyökérszintű művelethez – a ténylegesen a végrehajtáshoz használt qubits száma (és a művelet meghívása).
A vagy az azt követő műveletekhez – a művelet elején már használt qubits kívül még hány qubits használtak.

Vegye figyelembe, hogy az újrafelhasznált qubits nem járul hozzá ehhez a számhoz.
Ha azonban néhány qubits már megjelent a művelet elindítása előtt, és az A művelet által igényelt összes qubit (és az A-ból származó műveletek) a korábbi kiadási qubits újbóli használatával teljesültek, az A művelet szélességét 0-ra kell jelenteni. A qubits sikeres kölcsönzése nem járul hozzá a szélességhez.

__QubitCount:__ A gyökérszintű művelethez – a művelet végrehajtásához elégséges qubits minimális száma (és az általa meghívott műveletek).
A vagy az azt követő műveletek műveletekhez – a qubits minimális száma, amely elegendő lenne a művelet külön történő végrehajtásához. Ez a szám nem tartalmaz bemeneti qubits. Ez magában foglalja a kölcsönzött qubits is.

Két működési mód támogatott. A módot a QCTraceSimulatorConfiguration. OptimizeDepth beállítással választhatja ki.

__OptimizeDepth = FALSE:__ Ez az alapértelmezett mód. A QubitManager a qubits újrafelhasználását javasolta, és újból felhasználja a kiadott qubits az újak lefoglalása előtt. A gyökérszintű művelet __szélessége__ a minimális szélesség (alsó határ) lesz. A rendszer a kompatibilis __mélységet__ fogja jelenteni, amelyen elérhető. A __QubitCount__ megegyeznek a gyökérszintű művelet __szélességével__ , feltéve, hogy nincs hitelfelvétel.

__OptimizeDepth = True:__ A QubitManager a qubit újrafelhasználását, valamint a qubit újrafelhasználásának heurisztikus optimalizálását a végrehajtás során és után hajtja végre a rendszer. A gyökérszintű művelet __mélysége__ a minimális mélység (alsó határ) lesz. Ehhez a mélységhez (mindkettőt egyszerre lehet megvalósítani) kompatibilis __szélességet__ kell jelenteni. A szélesség optimalizálása érdekében a program későbbi szakaszaiban található Gates ütemezése ütemezhető, mielőtt a program korábban megtalálta a kapukat, de a qubits úgy ütemezik újra, hogy a mélység továbbra is minimális maradjon. Mivel a qubits az időértékek alapján újra felhasználják, azt javasoljuk, hogy a Gate-időpontok egész értékként legyenek konfigurálva. A __szélesség__ nem garantáltan optimális. További információ a következő témakörben található: tanulmány [szélessége és mélysége a nyomjelzőben](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).

## <a name="providing-the-probability-of-measurement-outcomes"></a>Mérési eredmények valószínűségének megadása

<xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>A <xref:Microsoft.Quantum.Diagnostics> névtérből való használatával információt adhat meg egy mérési művelet várható valószínűségéről. További információ: [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Lásd még

- [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Toffoli-kvantumszimulátor](xref:microsoft.quantum.machines.toffoli-simulator)
- [Teljes körű funkciókkal rendelkező kvantumszimulátor](xref:microsoft.quantum.machines.full-state-simulator) 
