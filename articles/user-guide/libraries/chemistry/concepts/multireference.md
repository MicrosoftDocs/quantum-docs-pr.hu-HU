---
title: Korrelált hullámfüggvények
description: Ismerje meg a wavefunctions dinamikus és nem dinamikus korrelációit a Microsoft Quantum kémia Library használatával.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275095"
---
# <a name="correlated-wavefunctions"></a>Korrelált hullámfüggvények

Számos rendszer esetében, különösen az egyensúlyi geometria közelében, a [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) Theory a molekuláris tulajdonságok minőségi leírását egy egytényezős hivatkozási állapottal biztosítja. A mennyiségi pontosság elérése érdekében azonban az egyiknek a korrelációs hatásokat is figyelembe kell vennie. 

Ebben a kontextusban fontos, hogy dinstinguish a dinamikus és a nem dinamikus korrelációk között.
A dinamikus összefüggések abból erednek, hogy az elektronok hajlamosak egymástól távol maradni, például az elektronikus hajtás miatt. Ez a hatás úgy modellezhető, hogy az elektronok izgatják a hivatkozási állapotot. Nem dinamikus korrelációk akkor jelentkeznek, ha a wavefunction két vagy több konfiguráció uralja nulladik sorrendben, még akkor is, ha csak a rendszer minőségi leírását szeretné elérni.
Ez szükségessé teszi a meghatározó tényezők felhelyezését, és példát mutat a Többhivatkozásos wavefunction.

A kémiai könyvtár lehetővé teszi, hogy megadják a nulladik Order wavefunction a Többhivatkozásos probléma számára, amely meghatározza a meghatározó tényezőket. Ez a megközelítés, amely ritka Többhivatkozásos wavefunctions hív meg, akkor lép életbe, amikor csak néhány összetevő elegendő a Felfekvés megadásához. A függvénytár egy olyan módszert is biztosít, amely dinamikus korrelációkat tartalmaz egy, az általánosított, különálló fürtön keresztüli Ansatz. Emellett olyan kvantum-áramköröket is létrehoz, amelyek létrehozza ezeket az állapotokat a kvantum-számítógépeken. Ezek az állapotok a [Broombridge sémában](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)adhatók meg, és ezen állapotok manuális megadására is lehetőséget biztosítunk a kémia könyvtárán keresztül.

## <a name="sparse-multi-reference-wavefunction"></a>Ritka multi-Reference wavefunction
A többszörös hivatkozási állapot $ \ket{\ psi_ {\rm {MCSCF}}} $ lehet explicit módon megadható $N $-Electron Slater determininants lineáris kombinációjával.
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .
\end{align} például a következő állapotot: $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 egy ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ a kémiai könyvtárban a következőképpen adható meg.
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
Ha csak néhány összetevőt kell megadnia, akkor ez a feltételhez tartozó összetevők explicit ábrázolása is érvényes. Az egyiknek kerülnie kell ezt az ábrázolást, ha sok összetevő szükséges a kívánt állapot pontos rögzítéséhez. Ennek az az oka, hogy ez az állapot a kvantum-számítógépeken felkészíti a Quantum Circuit-t, amely legalább lineárisan méretezi a Felskálázási összetevők számát, és a legtöbb esetben a többhelyes amplitúdók egy-egy normáját.

## <a name="unitary-coupled-cluster-wavefunction"></a>Egyszintű – fürt wavefunction
A kémikusi függvénytár használatával a psi_ \ket{\ {\rm {UCC}}} $ wavefunction is megadható. Ebben az esetben egyetlen meghatározó hivatkozási állapottal rendelkezünk, mondjuk: $ \ket{\ psi_ {\rm{SCF}}} $. Az egységes és a fürt wavefunction összetevői implicit módon vannak megadva a hivatkozási állapotot kezelő egységes operátoron keresztül.
Ez az egységes operátor általában $e ^ {T-T ^ \dagger} $ néven íródott, ahol a $T-T ^ \dagger $ a Hermitian-fürt operátora. Így \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

Az is gyakori, hogy a $T = T_1 + T_2 + \cdots $ csomópontot részekre darabolják, ahol minden rész $T _j $ tartalmaz $j $-Body kifejezést. Az általánosított és a fürtök elméletében az egytörzsű fürt operátora (Singles) \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

a kéttörzsű fürt operátora (Double) a következő: \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.
\end{align}

A magasabb rendű feltételek (triplák, négyszeresek stb.) lehetségesek, de a kémia könyvtára jelenleg nem támogatja őket.

Tegyük fel például, hogy $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $, és hagyja $T = 0,123 a ^ \ dagger_0 a_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $. Ezt az állapotot az alábbi módon hozza létre a kémiai könyvtárban.
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

A spin convervation explicit módon is elvégezhető, ha `SpinOrbital` az indexeket a Integer indexek helyett megadhatja. Tegyük fel például, hogy $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $, és hagyjuk $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ be spin convserving. Ezt az állapotot az alábbi módon hozza létre a kémiai könyvtárban.
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Olyan kényelmi funkciót is biztosítunk, amely az összes olyan spin-beszélgetést végző fürt operátorát tartalmazza, amely megsemmisíti a csak megszállt spin-pályákat, és izgatja a nem foglalt spin-pályákat.
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
