---
title: Energiaszint-becslések lekérése
description: A Q# molekuláris hidrogén energiagazdálkodási szintjeinek becslésére szolgáló minta program végigvezeti.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 05506f4099de754cd02d81fbd9200f2de091e37e
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759732"
---
# <a name="obtaining-energy-level-estimates"></a>Energiaszint-becslések lekérése
Az energia szintjeinek becslése a Quantum kémiájának egyik fő alkalmazása. Ez a cikk ismerteti, hogyan hajthatja végre ezt a molekuláris hidrogén kanonikus példáján. Az ebben a szakaszban hivatkozott minta a [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) kémia Samples repositoryban található. Egy több vizualizációs példa, amely a kimenetet ábrázolja a [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) bemutatóban.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>A molekuláris hidrogén energia értékének becslése

Első lépésként a molekuláris hidrogént képviselő Hamilton kell létrehozni. Bár ezt a NWChem eszközzel is létrehozhatja, a rövidség kedvéért ez a példa manuálisan hozzáadja a Hamilton kifejezéseket.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

A Hamilton szimulálása szükséges a Fermion-operátorok qubit-operátorokra való átalakításához. Ezt a konverziót a Jordan-Wigner kódolással hajtja végre a következőképpen:

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

A következő, pass `qSharpData` , amely a Hamilton jelöli a `TrotterStepOracle` függvényhez. `TrotterStepOracle` egy olyan kvantum-műveletet ad vissza, amely a Hamilton valós idejű alakulását közelíti meg. További információ: a [Hamilton Dynamics szimulálása](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

Ezen a ponton a standard könyvtár [fázisának becslési algoritmusait](xref:microsoft.quantum.libraries.characterization) használva megismerheti az előző szimulációt használó alapvető állapotú energiát. Ehhez jó közelítést kell készíteni a kvantum-állapothoz. Az ilyen közelítésekre vonatkozó javaslatokat a sémában kell megadnia [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) . A javaslatok hiányában azonban az alapértelmezett megközelítés számos elektronot ad hozzá, `hamiltonian.NElectrons` hogy mohón a legkisebb átlós, egyelektronos adatmennyiséget. A fázis-becslési függvények és műveletek DocFX-jelöléssel vannak megadva a [Microsoft. Quantum. jellemzési](xref:microsoft.quantum.characterization) névtérben.

A következő kódrészlet azt mutatja be, hogyan integrálható a kémia-szimulációs könyvtár valós idejű evolúciós eredményei a Quantum Phase-becsléssel.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

Most meghívhatja a Q# kódot a gazda programból. A következő C#-kód egy teljes állapotú szimulátort hoz létre `GetEnergyByTrotterization` , amely a terepi állapot megszerzéséhez szükséges.

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

A művelet két paramétert ad vissza: 

- `energyEst` a az állapot becsült állapota, és az `-1.137` átlaghoz közeledik. 
- `phaseEst` a fázis-becslési algoritmus által visszaadott nyers fázis. Ez hasznos lehet az aliasok diagnosztizálásához, ha az egy `trotterStep` túl nagy értékű érték miatt fordul elő.
