---
title: Különálló bemenet-ellenőrzési
description: 'Ismerje meg a Microsoft QDK DISTINCT Inputs-ellenőrzőt, amely a Q # kódját ellenőrzi a megosztott qubits lehetséges ütközések esetén.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274930"
---
# <a name="distinct-inputs-checker"></a>Különálló bemenet-ellenőrzési

A a `Distinct Inputs Checker` Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezi. Ez a kód a lehetséges hibák észlelésére szolgál. A csomag által észlelt problémák szemléltetéséhez vegye figyelembe az alábbi Q #-kódot:

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

Amikor a felhasználó megkeresi a programot, feltételezi, hogy a `op1` és a `op2` hívási sorrend nem számít, mert `q1` és különböző `q2` qubits és műveletek különböző qubits-feladatokkal működnek. Most Vegyünk példaként egy példát, ahol ezt a műveletet használják:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Most `op1` és `op2` mindkettőt részleges alkalmazás használatával szerezték be, és megosztanak egy qubit. Ha a felhasználó a `ApplyBoth` fenti példában meghívja a művelet eredményét, a és a belső sorrendtől `op1` függ `op2` `ApplyBoth` . Ez biztosan nem az, amit a felhasználó elvár. A az `Distinct Inputs Checker` ilyen helyzeteket fogja felderíteni, ha engedélyezve van, és a rendszer kidobja `DistinctInputsCheckerException` . További részletekért tekintse meg a [DISTINCTINPUTSCHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) API-dokumentációját.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>A különböző input-ellenőrök használata a C# programban

Az alábbi példa egy C#-illesztőprogram-kódra mutat be, amely a Quantum Computer Trace Simulator használatát teszi `Distinct Inputs Checker` lehetővé:

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

Az osztály `QCTraceSimulatorConfiguration` tárolja a kvantum-számítógép nyomkövetési szimulátor konfigurációját, és a konstruktor argumentumként is elérhető `QCTraceSimulator` . Ha `useDistinctInputsChecker` a értéke TRUE (igaz `Distinct Inputs Checker` ), akkor az engedélyezve van. További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) API-dokumentációját.

## <a name="see-also"></a>Lásd még

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
