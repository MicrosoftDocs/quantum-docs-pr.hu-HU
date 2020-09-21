---
title: Symmetries
description: Tudnivalók a OrbitalIntegral típus használatáról a Q# molekuláris symmetries számbavételéhez.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ebb8e9bda06967d3cfa002a7d074933d9135ada
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833815"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries

A Coulomb-Hamilton, amely az [elektronikus rendszerek kvantum-modelljeiben](xref:microsoft.quantum.chemistry.concepts.quantummodels)megadott Hamilton, amely az egymással és az atommagokkal együttesen kommunikáló elektronokat mutatja be, számos olyan symmetries eredményez, amely felhasználható a Hamilton feltételeinek tömörítésére.
Általánosságban elmondható, hogy a "$ \ psi_j $" függvényre vonatkozó további feltételezések nem teljesülnek, ezért csak a \begin{Equation} h_ {pqrs} = h_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation}, amely az [elektronikus rendszerek kvantum-modelljeinek](xref:microsoft.quantum.chemistry.concepts.quantummodels) szerves részéből azonnal megtekinthető, hogy az értékek megegyeznek abban az esetben, ha a $p, a q $ és a $r, s $ nem változik.

Ha feltételezzük, hogy a spin-orbits valós értékű (mint a Gauss orbitális alapértékek esetében), akkor a \begin{Equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation} adott feltételezések esetében a fenti symmetries használatával csökkentheti a Hamilton mátrix-elemeinek a $8 $ értékkel való tárolásához szükséges adatokat. Bár ez így is lehetővé teszi az adatimportálást, valamivel nagyobb kihívást jelent.
Szerencsére a Hamilton szimulációs függvénytár olyan alrutinokkal rendelkezik, amelyek az [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) vagy közvetlenül a [NWChem](http://www.nwchem-sw.org/index.php/Main_Page)-ből származó integrált fájlok importálására használhatók.

A molekuláris orbitális integrálása (azaz a $h \_ {pq} $ és a $h \_ {pqrs} $ kifejezések), például ezek a típus alapján jelennek `OrbitalIntegral` meg, amely számos hasznos funkciót biztosít a szimmetria kiértékeléséhez.
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

A numerikusan megegyező összes orbitális egység számbavétele mellett az alábbi módon hozhatók létre a Hamilton által jelzett összes spin-orbitális index listája `OrbitalIntegral` .
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Fermionic-Hamiltonians létrehozása a molekuláris szerves részéből

Ahelyett, hogy a Fermionic-Hamilton az s használatával hozza létre `FermionTerm` , az egyes orbitális szerves elemeknek megfelelő összes kifejezést automatikusan hozzá lehet adni.
Például a következő kód automatikusan enumerálja az összes permutációs symmetries, és megrendeli a feltételeket a kanonikus sorrendben: 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
