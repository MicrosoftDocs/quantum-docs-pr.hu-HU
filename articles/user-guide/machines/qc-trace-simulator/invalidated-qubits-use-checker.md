---
title: Érvénytelenített qubithasználat ellenőrzője
description: 'Ismerje meg a Microsoft QDK érvénytelenített qubits használatát ellenőrző eszközt, amely ellenőrzi a Q # kódját a potenciálisan érvénytelen qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274900"
---
# <a name="invalidated-qubits-use-checker"></a>Érvénytelenített qubits-ellenőrző használata

A a `Invalidated Qubits Use Checker` Quantum Computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) része, amely a kódban rejlő esetleges hibák észlelésére szolgál. Vegye figyelembe a következő Q #-kódrészletet, hogy bemutassa a által észlelt problémákat `Invalidated Qubits Use Checker` .

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Ha a `H` alkalmazás rá van alkalmazva, `q[0]` egy már kiadott qubit mutat. Ez nem definiált viselkedést okozhat. Ha a `Invalidated Qubits Use Checker` beállítás engedélyezve van, a kivétel akkor kerül megadásra, `InvalidatedQubitsUseCheckerException` Ha egy művelet már megjelent qubit van alkalmazva. További részletekért tekintse meg a [INVALIDATEDQUBITSUSECHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) API-dokumentációját.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Az érvénytelenített qubits használata a C# programban

A következőkben egy példa a C# illesztőprogram-kódra, amely lehetővé teszi a kvantum-számítógép használatát az `Trace
Simulator` `Invalidated Qubits Use Checker` engedélyezve: 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Az osztály `QCTraceSimulatorConfiguration` tárolja a kvantum-számítógép nyomkövetési szimulátor konfigurációját, és a konstruktor argumentumként is elérhető `QCTraceSimulator` . Ha `useInvalidatedQubitsUseChecker` a értéke TRUE (igaz `Invalidated Qubits Use Checker` ), akkor az engedélyezve van. További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) API-dokumentációját.

## <a name="see-also"></a>Lásd még ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
