---
title: Hamilton-operátor betöltése fájlból
description: Ismerje meg, hogyan hozhatja automatikusan nagy Hamilton a Broombridge séma használatával.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57e25bf55009797b01695cef0f3d29b94662ccc0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869239"
---
# <a name="loading-a-hamiltonian-from-file"></a>Hamilton-operátor betöltése fájlból
Korábban a Hamiltonians az egyéni feltételek hozzáadásával alakítottuk ki. Habár ez a kis példák esetében is jó, a kvantum-kémia méretének Hamiltonians millió vagy több milliárd kifejezéssel kell rendelkeznie. A vegyipari csomagok, például a NWChem által generált Hamiltonians túl nagyok a kézzel történő importáláshoz. Ebben a példában bemutatjuk, hogyan lehet `FermionHamiltonian` automatikusan generálni egy példányt a [Broombridge séma](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)által jelölt molekula alapján. A hivatkozáshoz az egyik megvizsgálhatja a megadott `LithiumHydrideGUI` mintát vagy a `RunSimulation` mintát. Korlátozott támogatás is elérhető a [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)által felhasznált formátumból való importáláshoz.

Vegyük például a nitrogén molekula példáját, amelyet a `IntegralData/YAML` Samples adattár mappájában találhat. A séma betöltésének módszere `Broombridge` egyszerű.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

A Broombridge séma a kezdeti állapot előkészítésére vonatkozó javaslatokat is tartalmaz. Ezeknek az állapotoknak a címkéi (például vagy) a `"|G⟩"` `"|E1⟩"` fájl vizsgálatával is láthatók. A kezdeti állapotok előkészítéséhez a `qSharpData` Q# kvantum-algoritmusok által felhasznált érték az [előző szakaszhoz](xref:microsoft.quantum.chemistry.examples.energyestimate)hasonlóan történik, de egy további paraméterrel kiválaszthatja a kívánt kezdeti állapotot. Például:
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

A fenti lépéseket rövidítheti a megadott kényelmi módszerek alapján, az alábbiak szerint.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

Hamilton is betöltünk a LIQUi |> formátum, amely nagyon hasonló szintaxist használ. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Ha ezt a folyamatot a Broombridge bármely példányán, vagy bármely köztes lépésen követik, a kvantum-algoritmusok, például a kvantum-fázisok becslése a megadott elektronikus szerkezettel kapcsolatos probléma esetén is futtatható.
