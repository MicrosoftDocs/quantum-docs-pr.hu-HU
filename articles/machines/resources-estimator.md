---
title: A Quantum Development Kit erőforrásainak kalkulátora
description: 'Ismerje meg az erőforrások becslését, amely a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 51186134e9279727fec212cdce84f69493aaa656
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320810"
---
# <a name="the-resourcesestimator-target-machine"></a>A ResourcesEstimator cél gépe

Ahogy a név is jelenti, a `ResourcesEstimator` a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.
Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Emiatt megbecsülheti a Q # olyan műveleteinek erőforrásait, amelyek több ezer qubits használnak, ha a kód klasszikus része ésszerű időn belül futtatható.

## <a name="usage"></a>Használat

A `ResourcesEstimator` csak egy másik típusú célszámítógép, így bármely Q # művelet futtatására is használható. 

Más célszámítógépek esetén a C# gazdagépen való használathoz hozzon létre egy példányt, és adja át a művelet `Run` metódusának első paramétereként:

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

A példa azt mutatja, hogy a `ResourcesEstimator` `ToTSV()` módszert biztosít egy olyan tabulátorral elválasztott tábla létrehozásához, amely fájlba menthető, vagy elemzésre a konzolba. A fenti program kimenetének a következőhöz hasonlóan kell kinéznie:

```Output
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
> A `ResourcesEstimator` nem állítja alaphelyzetbe a számításokat minden futtatáskor, ha ugyanazt a példányt egy másik művelet végrehajtásához használja, akkor a meglévő eredmények alapján megtartja az összesítési számlálást.
> Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden végrehajtáshoz.


## <a name="programmatically-retrieving-the-estimated-data"></a>A becsült adatok programozott beolvasása

A TSV-táblázat mellett a becsült erőforrások programozott módon is beolvashatók a `ResourcesEstimator``Data` tulajdonságán keresztül. a `Data` `System.DataTable` példányt biztosít két oszloppal: `Metric` és `Sum`, a metrikák nevei szerint indexelve.

A következő kód bemutatja, hogyan kérhető le és nyomtatható ki a Q # művelet által használt `QubitClifford`, `T` és `CNOT` Gates teljes száma:

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

Az alábbi lista a `ResourcesEstimator`becsült mérőszámait sorolja fel:

* __Cnem__: a cnem (más néven ellenőrzött Pauli X Gate) Gates száma.
* __QubitClifford__: egy qubit-es Clifford-és Pauli-kapuk száma.
* __Mérték__: a végrehajtott mérések száma.
* __R__: a végrehajtott egyetlen qubit-forgatások száma, kivéve a T, Clifford és Pauli gateset.
* __T__: a t-kapuk és a benne lévő konjugátumok száma, beleértve a t-kaput, T_x = H. T. h, valamint T_y = a (z). t. a.
* __Mélység__: a Q # művelet által végrehajtott kvantum-áramkör mélysége. Alapértelmezés szerint csak a T-Gates számítanak bele a mélységbe, a részletekért lásd a részletes [számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Szélesség__: a Q # művelet végrehajtása során lefoglalt qubits maximális száma.
* __BorrowedWidth__: a Q # műveletben kölcsönzött qubits maximális száma.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Mérési eredmények valószínűségének biztosítása

a <xref:microsoft.quantum.intrinsic> névtérből származó <xref:microsoft.quantum.intrinsic.assertprob> használatával információt adhat meg egy mérték várható valószínűségéről a Q # program végrehajtásának elősegítése érdekében. A következő példa ezt illusztrálja:

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

Ha a `ResourcesEstimator` `AssertProb`, a rendszer rögzíti, hogy a mérési `PauliZ` a `source`, és `q` a 0,5-as valószínűségű `Zero` eredményét kell adni. Amikor később végrehajtja `M`, megkeresi a kimeneteli valószínűségek rögzített értékeit, és `M` `Zero` vagy `One` értéket ad vissza a 0,5 valószínűséggel.


## <a name="see-also"></a>Lásd még

A `ResourcesEstimator` a kvantum-számítógép [nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a metrikák széles választékát biztosítja, a teljes hívási gráfban lévő mérőszámok jelentését, valamint az olyan funkciókat, mint a [különböző bemenet-ellenőrök](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , amelyek segítenek a hibák keresésében a Q # programokon. További információért tekintse meg a [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) dokumentációját.

