---
title: Erőforrásszámok lekérése
description: Megtudhatja, hogyan szerezhet be erőforrás-becslést a Quantum Trace Simulator használatával.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275080"
---
# <a name="obtaining-resource-counts"></a>Erőforrásszámok lekérése

A klasszikus számítógépeken a $n $ qubits szimulálása a $n $-val exponenciálisan méretezhető. Ez nagy mértékben korlátozza a kvantum-kémia szimulációt, amelyet a teljes állapotú szimulátorral lehet elvégezni. A kémia nagy példányai esetében is hasznos információkhoz juthat. Itt megvizsgáljuk, hogy az erőforrás-költségek, például a T-Gates vagy a CNEM-kapuk száma, a szimuláló kémia esetében a [nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro)használatával automatizált módon szerezhetők be. Ezek az információk arra utalnak minket, hogy ha a kvantum-számítógépek elég nagyok ahhoz, hogy ezeket a kvantum-kémiai algoritmusokat futtatni tudják. A hivatkozásokat lásd a megadott `GetGateCount` mintában.

Tegyük fel, hogy már van egy `FermionHamiltonian` példányunk, azaz betöltve a Broombridge-sémából, ahogy azt a [fájl betöltése a következő](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) példában tárgyaljuk. 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

Az erőforrás-becslések beszerzésének szintaxisa majdnem azonos az algoritmusnak a teljes állapotú szimulátoron való futtatásával. Egyszerűen válasszon másik célszámítógépet. Az erőforrás-becslések esetében elegendő az egyetlen Trotter-lépés vagy a Qubitization-módszer által létrehozott Quantum Walk-érték kiértékelése. Az algoritmusok meghívásához használt szöveg a következő.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Most a nyomkövetési szimulátort úgy konfiguráltuk, hogy nyomon kövessük a kívánt erőforrásokat. Ebben az esetben a primitív kvantum-műveleteket a jelölő értékre állításával számítjuk ki `usePrimitiveOperationsCounter` `true` . A technikai részleteket úgy kell `throwOnUnconstraintMeasurement` beállítani, `false` hogy elkerülje a kivételeket azokban az esetekben, amikor a Q # kód helytelenül állítja be a mérési eredmények valószínűségét, ha vannak ilyenek.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

Most a következő módon futtatjuk a Quantum algoritmust az illesztőprogram-programból.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```