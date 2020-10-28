---
title: Energiaszint-becslések lekérése
description: 'A :::no-loc(Q#)::: molekuláris hidrogén energiagazdálkodási szintjeinek becslésére szolgáló minta program végigvezeti.'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691535"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="b87b8-103">Energiaszint-becslések lekérése</span><span class="sxs-lookup"><span data-stu-id="b87b8-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="b87b8-104">Az energia szintjeinek becslése a Quantum kémiájának egyik fő alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="b87b8-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="b87b8-105">Ez a cikk ismerteti, hogyan hajthatja végre ezt a molekuláris hidrogén kanonikus példáján.</span><span class="sxs-lookup"><span data-stu-id="b87b8-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="b87b8-106">Az ebben a szakaszban hivatkozott minta a [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) kémia Samples repositoryban található.</span><span class="sxs-lookup"><span data-stu-id="b87b8-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="b87b8-107">Egy több vizualizációs példa, amely a kimenetet ábrázolja a [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) bemutatóban.</span><span class="sxs-lookup"><span data-stu-id="b87b8-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="b87b8-108">A molekuláris hidrogén energia értékének becslése</span><span class="sxs-lookup"><span data-stu-id="b87b8-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="b87b8-109">Első lépésként a molekuláris hidrogént képviselő Hamilton kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="b87b8-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="b87b8-110">Bár ezt a NWChem eszközzel is létrehozhatja, a rövidség kedvéért ez a példa manuálisan hozzáadja a Hamilton kifejezéseket.</span><span class="sxs-lookup"><span data-stu-id="b87b8-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="b87b8-111">A Hamilton szimulálása szükséges a Fermion-operátorok qubit-operátorokra való átalakításához.</span><span class="sxs-lookup"><span data-stu-id="b87b8-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="b87b8-112">Ezt a konverziót a Jordan-Wigner kódolás hajtja végre a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="b87b8-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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
    // of the Hamiltonian and wavefunction made for consumption by the :::no-loc(Q#)::: operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="b87b8-113">A következő, pass `qSharpData` , amely a Hamilton jelöli a `TrotterStepOracle` függvényhez.</span><span class="sxs-lookup"><span data-stu-id="b87b8-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="b87b8-114">`TrotterStepOracle` egy olyan kvantum-műveletet ad vissza, amely a Hamilton valós idejű alakulását közelíti meg.</span><span class="sxs-lookup"><span data-stu-id="b87b8-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="b87b8-115">További információ: a [Hamilton Dynamics szimulálása](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="b87b8-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="b87b8-116">Ezen a ponton a standard könyvtár [fázisának becslési algoritmusait](xref:microsoft.quantum.libraries.characterization) használva megismerheti az előző szimulációt használó alapvető állapotú energiát.</span><span class="sxs-lookup"><span data-stu-id="b87b8-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="b87b8-117">Ehhez jó közelítést kell készíteni a kvantum-állapothoz.</span><span class="sxs-lookup"><span data-stu-id="b87b8-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="b87b8-118">Az ilyen közelítésekre vonatkozó javaslatokat a sémában kell megadnia [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) .</span><span class="sxs-lookup"><span data-stu-id="b87b8-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="b87b8-119">A javaslatok hiányában azonban az alapértelmezett megközelítés számos elektronot ad hozzá, `hamiltonian.NElectrons` hogy mohón a legkisebb átlós, egyelektronos adatmennyiséget.</span><span class="sxs-lookup"><span data-stu-id="b87b8-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="b87b8-120">A fázis-becslési függvények és műveletek DocFX-jelöléssel vannak megadva a [Microsoft. Quantum. jellemzési](xref:Microsoft.Quantum.Characterization) névtérben.</span><span class="sxs-lookup"><span data-stu-id="b87b8-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="b87b8-121">A következő kódrészlet azt mutatja be, hogyan integrálható a kémia-szimulációs könyvtár valós idejű evolúciós eredményei a Quantum Phase-becsléssel.</span><span class="sxs-lookup"><span data-stu-id="b87b8-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="b87b8-122">Most meghívhatja a :::no-loc(Q#)::: kódot a gazda programból.</span><span class="sxs-lookup"><span data-stu-id="b87b8-122">You can now invoke the :::no-loc(Q#)::: code from the host program.</span></span> <span data-ttu-id="b87b8-123">A következő C#-kód egy teljes állapotú szimulátort hoz létre `GetEnergyByTrotterization` , amely a terepi állapot megszerzéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="b87b8-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="b87b8-124">A művelet két paramétert ad vissza:</span><span class="sxs-lookup"><span data-stu-id="b87b8-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="b87b8-125">`energyEst` a az állapot becsült állapota, és az `-1.137` átlaghoz közeledik.</span><span class="sxs-lookup"><span data-stu-id="b87b8-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="b87b8-126">`phaseEst` a fázis-becslési algoritmus által visszaadott nyers fázis.</span><span class="sxs-lookup"><span data-stu-id="b87b8-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="b87b8-127">Ez hasznos lehet az aliasok diagnosztizálásához, ha az egy `trotterStep` túl nagy értékű érték miatt fordul elő.</span><span class="sxs-lookup"><span data-stu-id="b87b8-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
