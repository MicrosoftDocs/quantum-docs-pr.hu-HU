---
title: Érvénytelenített qubits-használat ellenőrzője – Quantum Development Kit
description: Ismerkedjen meg a Microsoft QDK által érvénytelenített qubits-ellenőrzővel, amely a Quantum Trace Simulator használatával ellenőrzi, hogy a Q# kód esetleg érvénytelen qubits-e.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868287"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Quantum Trace Simulator: érvénytelenített qubits-ellenőrző használata

A nem érvényesített qubits használja az ellenőrzőt a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részeként. Felhasználhatja a kódban az érvénytelen qubits által okozott lehetséges hibák észlelésére. 

## <a name="invalid-qubits"></a>Érvénytelen qubits

Vegye figyelembe a következő Q# kódrészletet a nem érvényesített qubits-ellenőrző által észlelt problémák szemléltetéséhez:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Amikor alkalmazza a műveletet a alkalmazásra `H` `q[0]` , az egy már kiadott qubit mutat, amely nem definiált viselkedést okozhat. Ha a érvénytelenített qubits használata ellenőrző engedélyezve van, akkor a kivételt képez, `InvalidatedQubitsUseCheckerException` Ha a program egy már kiadott qubit alkalmazza a műveletet. További információ: <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>A érvénytelenített qubits használatának ellenőrzése

Ha a kvantum-nyomkövetési szimulátort a érvénytelenítve qubits használatával szeretné futtatni, hozzon létre egy <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> példányt, állítsa a `UseInvalidatedQubitsUseChecker` tulajdonságot **true (igaz**) értékre, majd hozzon létre egy új <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> példányt `QCTraceSimulatorConfiguration` a paraméterrel. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>A devalidated qubits használata a C# gazdagép programban

A következőkben egy példa látható a C#-alapú gazdagépekre, amelyek a kvantum-nyomkövetési szimulátort használják a nem érvényesített qubits-használati ellenőrző használatával: 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>További információ

- A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API-hivatkozás.