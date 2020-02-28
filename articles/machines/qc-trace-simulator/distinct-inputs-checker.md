---
title: Különálló bemenet-ellenőrzési
description: 'Ismerje meg a Microsoft QDK DISTINCT Inputs-ellenőrzőt, amely a Q # kódját ellenőrzi a megosztott qubits lehetséges ütközések esetén.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907103"
---
# <a name="distinct-inputs-checker"></a>Különálló bemenet-ellenőrzési

A `Distinct Inputs Checker` a Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi. Ez a kód a lehetséges hibák észlelésére szolgál. A csomag által észlelt problémák szemléltetéséhez vegye figyelembe az alábbi Q #-kódot:

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

Amikor a felhasználó megkeresi ezt a programot, feltételezi, hogy a `op1` és `op2` meghívásának sorrendje nem számít, mert a `q1` és a `q2` különböző qubits és a különböző qubits-feladatokkal működő műveletek. Most Vegyünk példaként egy példát, ahol ezt a műveletet használják:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Most `op1` és `op2` egyaránt a részleges alkalmazás használatával és a qubit megosztásával szerezhetők be. Ha a felhasználó a fenti példában meghívja a `ApplyBoth`t, akkor a művelet eredménye `op1` és `op2` sorrendtől függ `ApplyBoth`. Ez biztosan nem az, amit a felhasználó elvár. A `Distinct Inputs Checker` akkor fogja felderíteni az ilyen helyzeteket, ha az engedélyezve van, és `DistinctInputsCheckerException`fog dobni. További részletekért tekintse meg a [DISTINCTINPUTSCHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) API-dokumentációját.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>A különböző input-ellenőrök használata a C# programban

A következőkben egy példa C# látható a Quantum Computer Trace Simulator használatára a `Distinct Inputs Checker` engedélyezve:

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Az osztály `QCTraceSimulatorConfiguration` a kvantum-számítógép nyomkövetési szimulátorjának konfigurációját tárolja, és a `QCTraceSimulator` konstruktor argumentumként is elérhető. Ha a `useDistinctInputsChecker` értéke TRUE (igaz), akkor a `Distinct Inputs Checker` engedélyezve van. További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) API-dokumentációját.

## <a name="see-also"></a>Lásd még

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
