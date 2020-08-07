---
title: Symmetries
description: Tudnivalók a OrbitalIntegral típus használatáról a Q# molekuláris symmetries számbavételéhez.
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1f71c0ac8e2cd2781c0bc7b23d6c9222f3b9d18a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869443"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="05328-103">Symmetries</span><span class="sxs-lookup"><span data-stu-id="05328-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="05328-104">A Coulomb-Hamilton, amely az [elektronikus rendszerek kvantum-modelljeiben](xref:microsoft.quantum.chemistry.concepts.quantummodels)megadott Hamilton, amely az egymással és az atommagokkal együttesen kommunikáló elektronokat mutatja be, számos olyan symmetries eredményez, amely felhasználható a Hamilton feltételeinek tömörítésére.</span><span class="sxs-lookup"><span data-stu-id="05328-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="05328-105">Általánosságban elmondható, hogy a "$ \ psi_j $" függvényre vonatkozó további feltételezések nem teljesülnek, ezért csak a \begin{Equation} h_ {pqrs} = h_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation}, amely az [elektronikus rendszerek kvantum-modelljeinek](xref:microsoft.quantum.chemistry.concepts.quantummodels) szerves részéből azonnal megtekinthető, hogy az értékek megegyeznek abban az esetben, ha a $p, a q $ és a $r, s $ nem változik.</span><span class="sxs-lookup"><span data-stu-id="05328-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="05328-106">Ha feltételezzük, hogy a spin-orbits valós értékű (mint a Gauss orbitális alapértékek esetében), akkor a \begin{Equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation} adott feltételezések esetében a fenti symmetries használatával csökkentheti a Hamilton mátrix-elemeinek a $8 $ értékkel való tárolásához szükséges adatokat. Bár ez így is lehetővé teszi az adatimportálást, valamivel nagyobb kihívást jelent.</span><span class="sxs-lookup"><span data-stu-id="05328-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="05328-107">Szerencsére a Hamilton szimulációs függvénytár olyan alrutinokkal rendelkezik, amelyek az [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) vagy közvetlenül a [NWChem](http://www.nwchem-sw.org/index.php/Main_Page)-ből származó integrált fájlok importálására használhatók.</span><span class="sxs-lookup"><span data-stu-id="05328-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="05328-108">A molekuláris orbitális integrálása (azaz a $h \_ {pq} $ és a $h \_ {pqrs} $ kifejezések), például ezek a típus alapján jelennek `OrbitalIntegral` meg, amely számos hasznos funkciót biztosít a szimmetria kiértékeléséhez.</span><span class="sxs-lookup"><span data-stu-id="05328-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
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

<span data-ttu-id="05328-109">A numerikusan megegyező összes orbitális egység számbavétele mellett az alábbi módon hozhatók létre a Hamilton által jelzett összes spin-orbitális index listája `OrbitalIntegral` .</span><span class="sxs-lookup"><span data-stu-id="05328-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="05328-110">Fermionic-Hamiltonians létrehozása a molekuláris szerves részéből</span><span class="sxs-lookup"><span data-stu-id="05328-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="05328-111">Ahelyett, hogy a Fermionic-Hamilton az s használatával hozza létre `FermionTerm` , az egyes orbitális szerves elemeknek megfelelő összes kifejezést automatikusan hozzá lehet adni.</span><span class="sxs-lookup"><span data-stu-id="05328-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="05328-112">Például a következő kód automatikusan enumerálja az összes permutációs symmetries, és megrendeli a feltételeket a kanonikus sorrendben:</span><span class="sxs-lookup"><span data-stu-id="05328-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
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
