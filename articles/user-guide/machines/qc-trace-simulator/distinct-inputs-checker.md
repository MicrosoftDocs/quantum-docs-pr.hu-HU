---
title: DISTINCT Inputs-Dámajáték – Quantum Development Kit
description: 'Ismerje meg a Microsoft QDK DISTINCT input-ellenőrzését, amely a Quantum Trace Simulator használatával vizsgálja meg a Q # kódját a megosztott qubits lehetséges ütközések esetén.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871144"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Quantum Trace Simulator: különálló bemenet-ellenőrzési

A DISTINCT input-ellenőrök a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részét képezik. A használatával észlelheti a programkódban előforduló esetleges hibákat a megosztott qubits ütközései miatt. 

## <a name="conflicts-with-shared-qubits"></a>Ütközés megosztott qubits

Vegye figyelembe a következő Q #-kódrészletet a különböző input-ellenőrök által észlelt problémák szemléltetése érdekében:

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

Ha megtekinti ezt a programot, feltételezheti, hogy a meghívása `op1` és a `op2` nem számít, mivel a `q1` és a különböző `q2` qubits és műveletek különböző qubits-feladatokkal működnek. 

Most gondolja át a következő példát:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Vegye figyelembe, hogy `op1` `op2` mindkettő részleges alkalmazás használatával és a qubit megosztásával is beszerezhető. Ha ezt a `ApplyBoth` példát hívja meg, a művelet eredménye a és a belső sorrendtől függ, `op1` és nem az, `op2` `ApplyBoth` ami várható. Ha engedélyezi a különböző bemenet-ellenőröket, az észleli az ilyen helyzeteket, és eldönti a `DistinctInputsCheckerException` . További információ: a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q # API Library.

## <a name="invoking-the-distinct-inputs-checker"></a>A különböző bemenet-ellenőrök meghívása

Ha a kvantum-nyomkövetési szimulátort a DISTINCT Inputs-előfizetési lehetőséggel szeretné futtatni, létre kell hoznia egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, állítsa a `UseDistinctInputsChecker` tulajdonságot **igaz**értékre, majd hozzon létre egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>A különböző input-ellenőrök használata C#-gazdagép programban

A következőkben egy példa látható a C#-alapú gazdagépre, amely a kvantum-nyomkövetési szimulátort használja a különböző bemenet-ellenőrzési lehetőségekkel:

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Lásd még

- A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API-hivatkozás.
