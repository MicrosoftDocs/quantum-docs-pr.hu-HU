---
title: Érvénytelenített qubits-használat ellenőrzője – Quantum Development Kit
description: 'Ismerje meg a Microsoft QDK érvénytelenített qubits használatát ellenőrzőt, amely a Quantum Trace Simulator használatával ellenőrzi a Q # kódját a potenciálisan érvénytelen qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: fccf6d5784b587f4ad9b659e23027619acd06ffa
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871093"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Quantum Trace Simulator: érvénytelenített qubits-ellenőrző használata

A nem érvényesített qubits használja az ellenőrzőt a Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)részeként. Felhasználhatja a kódban az érvénytelen qubits által okozott lehetséges hibák észlelésére. 

## <a name="invalid-qubits"></a>Érvénytelen qubits

Vegye figyelembe a következő Q # Code-kódot, hogy bemutassa a invalidated qubits use ellenőrző által észlelt problémákat:

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

## <a name="see-also"></a>Lásd még

- A Quantum Development Kit [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) áttekintése.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API-hivatkozás.
- Az <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API-hivatkozás.