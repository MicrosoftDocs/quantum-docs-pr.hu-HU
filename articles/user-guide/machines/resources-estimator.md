---
title: Quantum erőforrás-kalkulátor – Quantum Development Kit
description: 'Ismerje meg a Microsoft QDK erőforrásainak kalkulátorát, amely a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870539"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>A Quantum Development Kit (QDK) erőforrásainak kalkulátora

Ahogy a név is jelzi, az `ResourcesEstimator` osztály a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg. Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Emiatt a Q # olyan műveleteinek erőforrásait becsüli meg, amelyek több ezer qubits használnak, ha a kód klasszikus része ésszerű időn belül fut.

Az erőforrások becslése a [kvantum-nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely számos mérőszámot és eszközt biztosít a Q # programok hibakereséséhez.

## <a name="invoking-and-running-the-resources-estimator"></a>Az erőforrás-kalkulátor meghívása és futtatása

Az erőforrás-kalkulátor használatával bármilyen Q # műveletet futtathat. További részleteket a [Q # program futtatásának módjai](xref:microsoft.quantum.guide.host-programs)című témakörben talál.

### <a name="invoking-the-resources-estimator-from-c"></a>A C-ből származó erőforrások becslésének meghívása # 

A többi célszámítógépen hasonlóan először létre kell hoznia a osztály egy példányát, `ResourceEstimator` majd át kell adni a művelet metódusának első paramétereként `Run` .

Vegye figyelembe, hogy az osztálytól eltérően `QuantumSimulator` az `ResourceEstimator` osztály nem valósítja <xref:System.IDisposable> meg a felületet, így nem kell azt egy utasításon belül csatolnia `using` .

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

Használja az [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) metódust a Python-könyvtárból az importált Q # művelettel:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Az erőforrás-kalkulátor meghívása a parancssorból

Ha Q # programot futtat a parancssorból, használja a **--Simulator** (vagy **-s** parancsikon) paramétert a célszámítógép megadásához `ResourcesEstimator` . A következő parancs egy programot futtat az erőforrás-kalkulátor használatával: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>A Juptyer-jegyzetfüzetek erőforrásainak becslése

A Q # művelet futtatásához használja az IQ # Magic Command [% Költségbecslés](xref:microsoft.quantum.iqsharp.magic-ref.simulate) parancsot.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>A becsült adatok programozott beolvasása

A TSV-táblázat mellett programozott módon is lekérheti a Futtatás során becsült erőforrásokat az erőforrások becslésének `Data` tulajdonságán keresztül. A `Data` tulajdonság egy olyan `System.DataTable` példányt biztosít, amelyben két oszlop szerepel: `Metric` és `Sum` a metrikák nevei vannak indexelve.

A következő kód bemutatja, hogyan lehet lekérdezni és kinyomtatni `QubitClifford` a `T` `CNOT` Q # művelet által használt teljes számát és műveleteit:

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
|__Mélység__|A Q # művelet által futtatott Quantum áramkör mélységének alsó határa. Alapértelmezés szerint a mélységi metrika csak a `T` gateset számolja. További részletekért lásd a [részletes számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Szélesség__    |A Q # művelet futtatása során lefoglalt qubits maximális számának alsó határa. Előfordulhat, hogy a __mélység__ és a __szélesség__ alsó határa nem érhető el egyszerre.  |
|__BorrowedWidth__    |A Q # műveletben kölcsönzött qubits maximális száma.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>A mérési eredmények valószínűségének megadása

<xref:microsoft.quantum.diagnostics.assertmeasurementprobability>A <xref:microsoft.quantum.diagnostics> névtérből való használatával információt adhat meg egy mérési művelet várható valószínűségéről. További információ: [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Lásd még

- [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Quantum Toffoli szimulátor](xref:microsoft.quantum.machines.toffoli-simulator)
- [Quantum teljes állapot szimulátor](xref:microsoft.quantum.machines.full-state-simulator) 