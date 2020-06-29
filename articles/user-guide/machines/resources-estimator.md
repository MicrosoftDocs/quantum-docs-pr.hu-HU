---
title: A Quantum Development Kit erőforrásainak kalkulátora
description: 'Ismerje meg az erőforrások becslését, amely a Q # művelet egy kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli meg.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: cbb1c274b64738cc4b47869563d7d02eb717afbc
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415257"
---
# <a name="the-resources-estimator-target-machine"></a>Az erőforrások kalkulátor cél gépe

Ahogy a név is jelenti, a `ResourcesEstimator` becslések szerint a Q # művelet egy adott példányának futtatásához szükséges erőforrások a kvantum-számítógépen.
Ezt úgy hajtja végre, hogy végrehajtja a kvantum-műveletet anélkül, hogy ténylegesen szimulálja a kvantum-számítógép állapotát; Emiatt megbecsülheti a Q # olyan műveleteinek erőforrásait, amelyek több ezer qubits használnak, ha a kód klasszikus része ésszerű időn belül futtatható.

## <a name="usage"></a>Használat

A `ResourcesEstimator` csak egy másik típusú célszámítógép, így bármilyen Q # művelet futtatására is használható. 

Más célszámítógépként a C#-gazdagépen való használathoz hozzon létre egy példányt, és adja át a művelet metódusának első paramétereként `Run` :

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

A példa azt mutatja, `ResourcesEstimator` hogy a lehetővé teszi egy olyan `ToTSV()` tábla létrehozását, amely tabulátorral elválasztott értékeket (TSV) tartalmaz, amelyek fájlba menthetők, vagy a konzolba való beírással elemezhetők. A fenti program kimenetének a következőhöz hasonlóan kell kinéznie:

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
> A `ResourcesEstimator` nem állítja alaphelyzetbe a számításokat minden futtatáskor, ha ugyanazt a példányt egy másik művelet végrehajtásához használja, a meglévő eredmények alapján megtartja az összesítést.
> Ha a futtatások közötti számításokat kell alaphelyzetbe állítani, hozzon létre egy új példányt minden végrehajtáshoz.


## <a name="programmatically-retrieving-the-estimated-data"></a>A becsült adatok programozott beolvasása

A TSV-táblázat mellett a becsült erőforrások programozott módon is beolvashatók a `ResourcesEstimator` `Data` tulajdonságán keresztül. `Data``System.DataTable`két oszloppal rendelkező példányt biztosít: `Metric` és `Sum` a metrikák nevei szerint indexelve.

A következő kód azt mutatja be, hogyan lehet lekérdezni és kinyomtatni a `QubitClifford` `T` `CNOT` Q # művelet által használt teljes számát és kapuit:

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

Az alábbi lista a becsült mérőszámokat sorolja fel `ResourcesEstimator` :

* __Cnem__: a cnem (más néven ellenőrzött Pauli X Gate) Gates száma.
* __QubitClifford__: egy qubit-es Clifford-és Pauli-kapuk száma.
* __Mérték__: a végrehajtott mérések száma.
* __R__: a végrehajtott egyetlen qubit-forgatások száma, kivéve a T, Clifford és Pauli gateset.
* __T__: a t-kapuk és a benne lévő konjugátumok száma, beleértve a t-kaput, T_x = H. T. h, valamint T_y = a (z). t. a.
* __Mélység__: a Q # művelet által végrehajtott kvantum-áramkör mélységének alsó határa. Alapértelmezés szerint csak a T-Gates számítanak bele a mélységbe, a részletekért lásd a részletes [számlálót](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width (szélesség__): a Q # művelet végrehajtása során lefoglalt qubits maximális számának alsó határa. Előfordulhat, hogy a __mélység__ és a __szélesség__ alsó határa nem érhető el egyszerre.
* __BorrowedWidth__: a Q # műveletben kölcsönzött qubits maximális száma.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Mérési eredmények valószínűségének biztosítása

<xref:microsoft.quantum.intrinsic.assertprob>a névtérből megadható <xref:microsoft.quantum.intrinsic> , hogy milyen valószínűséggel kell megadnia egy mérés várható valószínűségét a Q # program végrehajtásának elősegítése érdekében. A következő példa ezt illusztrálja:

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

Amikor a `ResourcesEstimator` `AssertProb` rendszer megkezdi a mérést `PauliZ` , `source` és a 0,5-as `q` `Zero` valószínűséggel a következő eredményt kapja:. Amikor később végrehajtja `M` , a rendszer megkeresi a kimeneteli valószínűségek rögzített értékeit, és `M` visszaküldi `Zero` vagy `One` a 0,5-es valószínűséggel.


## <a name="see-also"></a>Lásd még

A a `ResourcesEstimator` kvantum-számítógép [nyomkövetési szimulátorra](xref:microsoft.quantum.machines.qc-trace-simulator.intro)épül, amely a metrikák széles választékát biztosítja, a teljes hívás – gráf mérőszámait és a különböző funkciókat (például a [DISTINCT Inputs-ellenőröket](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) ) a Q # programok hibáinak megkereséséhez. További információért tekintse meg a [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) dokumentációját.

