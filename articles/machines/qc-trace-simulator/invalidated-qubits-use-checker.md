---
title: Érvénytelenített qubits-használat ellenőrzője | Quantum Computer nyomkövetési szimulátor | Microsoft Docs
description: A kvantumszámítógép nyomkövetési szimulátorának áttekintése
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 283cc7d7d88f731f40fa396c38ae5ea8dd90537f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863180"
---
# <a name="invalidated-qubits-use-checker"></a>Érvénytelenített qubits-ellenőrző használata

A `Invalidated Qubits Use Checker` a Quantum Computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) azon része, amely a kódban rejlő esetleges hibák észlelésére szolgál. Vegye figyelembe a következő Q #-kódot a `Invalidated Qubits Use Checker`által észlelt problémák szemléltetése érdekében.

```qsharp
operation UseReleasedQubit () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Ha `H` van alkalmazva, `q[0]` egy már kiadott qubit mutat. Ez nem definiált viselkedést okozhat. Ha a `Invalidated Qubits Use Checker` engedélyezve van, akkor a kivétel `InvalidatedQubitsUseCheckerException` kerül, ha egy művelet egy már kiadott qubit van alkalmazva. További részletekért tekintse meg a [INVALIDATEDQUBITSUSECHECKEREXCEPTION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) API-dokumentációját.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Az érvénytelenített qubits használata a-ellenőrző használatával a C# programban

A következőkben egy példa látható C# arra az illesztőprogram-kódra, amely a quantum Computer `Trace
Simulator` használatát engedélyezi a `Invalidated Qubits Use Checker` engedélyezve: 

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

Az osztály `QCTraceSimulatorConfiguration` a kvantum-számítógép nyomkövetési szimulátorjának konfigurációját tárolja, és a `QCTraceSimulator` konstruktor argumentumként is elérhető. Ha a `useInvalidatedQubitsUseChecker` értéke TRUE (igaz), akkor a `Invalidated Qubits Use Checker` engedélyezve van. További részletekért tekintse meg a [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) és a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) API-dokumentációját.

## <a name="see-also"></a>Lásd még: ##

- A Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
