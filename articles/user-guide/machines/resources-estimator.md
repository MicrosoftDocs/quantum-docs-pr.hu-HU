---
title: Quantum erőforrás-kalkulátor – Quantum Development Kit
description: Ismerje meg a Microsoft QDK erőforrásainak kalkulátorát, amely a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg Q# .
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868185"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>A Quantum Development Kit (QDK) erőforrásainak kalkulátora

Ahogy a név is jelenti, az `ResourcesEstimator` osztály a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli Q# meg. Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Emiatt a Q# több ezer qubits-t használó műveletek erőforrásainak becslése, ha a kód klasszikus része ésszerű időn belül fut.

Az erőforrások becslése a [kvantum-nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a mérőszámok és eszközök sokoldalú készletét kínálja a programok hibakereséséhez Q# .

## <a name="invoking-and-running-the-resources-estimator"></a>Az erőforrás-kalkulátor meghívása és futtatása

Az erőforrás-kalkulátor használatával bármilyen Q# műveletet futtathat. További részletekért tekintse [meg a Q# programok futtatásának módjait](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>A C-ből származó erőforrások becslésének meghívása # 

Ahogy más célgépek esetében is, először a `ResourceEstimator` osztály egy példányát kell létrehoznia, majd azt kell megadnia a művelet `Run` metódusának első paramétereként.

Vegye figyelembe, hogy a `QuantumSimulator` osztálytól eltérően a `ResourceEstimator` osztály nem implementálja a <xref:System.IDisposable> felületet, így nem kell azt egy `using` utasításba belefoglalnia.

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

Használja az [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q# művelettel:

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

|Metrika|Leírás|
|----|----|
|__CNOT__    |A műveletek futtatási száma `CNOT` (más néven vezérelt Pauli X-műveletek).|
|__QubitClifford__ |Egyetlen qubit Clifford-és Pauli-művelet futtatási száma.|
|__mérték__    |A mérések futtatásának száma.  |
|__R__    |A qubit-Forgások futtatásának száma, kivéve a `T` Clifford és a Pauli műveletet.  |
|__T__    |A `T` műveletek és a konjugátumok futtatásának száma, beleértve a `T` műveleteket, a T_x = H. T. h és a T_y = a kifogyott. t. vízterületet.  |
|__Mélység__|A művelet által futtatott Quantum Circuit mélységének alsó határa Q# . Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja. További részletekért lásd a [részletes számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Szélesség__    |A művelet futtatása során lefoglalt qubits maximális számának alsó határa Q# . Előfordulhat, hogy a __mélység__ és a __szélesség__ alsó határa nem érhető el egyszerre.  |
|__BorrowedWidth__    |A műveleten belül kölcsönzött qubits maximális száma Q# .  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Mérési eredmények valószínűségének megadása

<xref:microsoft.quantum.diagnostics.assertmeasurementprobability>A <xref:microsoft.quantum.diagnostics> névtérből való használatával információt adhat meg egy mérési művelet várható valószínűségéről. További információ: [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>További információ

- [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Toffoli-kvantumszimulátor](xref:microsoft.quantum.machines.toffoli-simulator)
- [Teljes körű funkciókkal rendelkező kvantumszimulátor](xref:microsoft.quantum.machines.full-state-simulator) 