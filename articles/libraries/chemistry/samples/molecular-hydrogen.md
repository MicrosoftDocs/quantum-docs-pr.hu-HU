---
title: Az energia szintjére vonatkozó becslések beszerzése | Microsoft Docs
description: Az energia szintjének becslése – dokumentumok beszerzése
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 0fd457b152083af364d924502c18bc0813e34b83
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442574"
---
# <a name="obtaining-energy-level-estimates"></a>Energiaszint-becslések lekérése
Az energia szintjeinek becslése a Quantum kémiájának egyik fő alkalmazása. Itt felvázoljuk, hogy ez hogyan hajtható végre a molekuláris hidrogén kanonikus példáján. Az ebben a szakaszban hivatkozott minta `MolecularHydrogen` a kémia Samples repositoryban. A kimenetet ábrázoló vizualizációs példa a `MolecularHydrogenGUI` bemutató.

Első lépésként a molekuláris hidrogént képviselő Hamilton kell létrehozni. Bár ez a NWChem eszközzel is létrehozható, a rövid útmutatóhoz manuálisan is hozzáadhat Hamilton-kifejezéseket.

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

A Hamilton szimulálása megköveteli, hogy a Fermion-operátorokat qubit-operátoroknak alakítsa át. Ezt a konverziót a Jordan-Wigner kódolás hajtja végre az alábbiak szerint.

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Most átadjuk a Hamilton jelölő `qSharpData` a `TrotterStepOracle` függvénynek a [Hamilton Dynamics szimulálása](xref:microsoft.quantum.libraries.standard.algorithms)során. `TrotterStepOracle` egy olyan kvantum-műveletet ad vissza, amely a Hamilton valós idejű alakulását közelíti meg.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

Mostantól a standard könyvtár fázisának becslési algoritmusait használva megtudhatja, hogyan érheti el a fenti szimulációt a terepi állapottal. Ehhez jó közelítést kell készíteni a kvantum-állapothoz. Az ilyen közelítésekre vonatkozó javaslatokat a `Broombridge` sémában kell megadnia, de a javaslatok hiányában az alapértelmezett megközelítés számos `hamiltonian.NElectrons` elektronot ad hozzá, hogy mohón a legkisebb átlós, egyelektronos energiákat. A fázis-becslési függvények és műveletek a [Microsoft. Quantum. jellemzési névtérben](xref:microsoft.quantum.characterization in DocFX notation)találhatók.

A következő kódrészlet azt mutatja be, hogy a kémia szimulációs könyvtárának valós idejű fejlődése hogyan integrálható a kvantum fázis becslésével.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

Ez a Q # kód mostantól az illesztőprogram-programból is meghívható. A következő lépésekben létrehozunk egy teljes állapotú szimulátort, és `GetEnergyByTrotterization` futtatjuk az állami energia beszerzéséhez.

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

Vegye figyelembe, hogy a rendszer két paramétert ad vissza. a `energyEst` a terepi állapot becsült értéke, és átlagosan `-1.137` körül kell lennie. `phaseEst` a fázis-becslési algoritmus által visszaadott nyers fázis, és hasznos lehet diagnosztizálni, ha az alias egy túl nagy `trotterStep` miatt fordul elő.
