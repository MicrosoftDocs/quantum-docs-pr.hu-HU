---
title: Korrelált hullámfüggvények
description: Ismerje meg a wavefunctions dinamikus és nem dinamikus korrelációit a Microsoft Quantum kémia Library használatával.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: ab3d90d79c7c14a1ef5b3aa833df49be186f3dd7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856275"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="f9e4f-103">Korrelált hullámfüggvények</span><span class="sxs-lookup"><span data-stu-id="f9e4f-103">Correlated wavefunctions</span></span>

<span data-ttu-id="f9e4f-104">Számos rendszer esetében, különösen az egyensúlyi geometria közelében, a [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) Theory a molekuláris tulajdonságok minőségi leírását egy egytényezős hivatkozási állapottal biztosítja.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="f9e4f-105">A mennyiségi pontosság elérése érdekében azonban az egyiknek a korrelációs hatásokat is figyelembe kell vennie.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="f9e4f-106">Ebben a kontextusban fontos, hogy dinstinguish a dinamikus és a nem dinamikus korrelációk között.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="f9e4f-107">A dinamikus összefüggések abból erednek, hogy az elektronok hajlamosak egymástól távol maradni, például az elektronikus hajtás miatt.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="f9e4f-108">Ez a hatás úgy modellezhető, hogy az elektronok izgatják a hivatkozási állapotot.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="f9e4f-109">Nem dinamikus korrelációk akkor jelentkeznek, ha a wavefunction két vagy több konfiguráció uralja nulladik sorrendben, még akkor is, ha csak a rendszer minőségi leírását szeretné elérni.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="f9e4f-110">Ez szükségessé teszi a meghatározó tényezők felhelyezését, és példát mutat a Többhivatkozásos wavefunction.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="f9e4f-111">A kémiai könyvtár lehetővé teszi, hogy megadják a nulladik Order wavefunction a Többhivatkozásos probléma számára, amely meghatározza a meghatározó tényezőket.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="f9e4f-112">Ez a megközelítés, amely ritka Többhivatkozásos wavefunctions hív meg, akkor lép életbe, amikor csak néhány összetevő elegendő a Felfekvés megadásához.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="f9e4f-113">A függvénytár egy olyan módszert is biztosít, amely dinamikus korrelációkat tartalmaz egy, az általánosított, különálló fürtön keresztüli Ansatz.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="f9e4f-114">Emellett olyan kvantum-áramköröket is létrehoz, amelyek létrehozza ezeket az állapotokat a kvantum-számítógépeken.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="f9e4f-115">Ezek az állapotok a [Broombridge sémában](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)adhatók meg, és ezen állapotok manuális megadására is lehetőséget biztosítunk a kémia könyvtárán keresztül.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="f9e4f-116">Ritka multi-Reference wavefunction</span><span class="sxs-lookup"><span data-stu-id="f9e4f-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="f9e4f-117">A többszörös hivatkozási állapot $ \ket{\ psi_ {\rm {MCSCF}}} $ lehet explicit módon megadható $N $-Electron Slater determininants lineáris kombinációjával.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="f9e4f-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="f9e4f-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="f9e4f-119">\end{align} például a következő állapotot: $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 egy ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ a kémiai könyvtárban a következőképpen adható meg.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
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
<span data-ttu-id="f9e4f-120">Ha csak néhány összetevőt kell megadnia, akkor ez a feltételhez tartozó összetevők explicit ábrázolása is érvényes.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="f9e4f-121">Az egyiknek kerülnie kell ezt az ábrázolást, ha sok összetevő szükséges a kívánt állapot pontos rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="f9e4f-122">Ennek az az oka, hogy ez az állapot a kvantum-számítógépeken felkészíti a Quantum Circuit-t, amely legalább lineárisan méretezi a Felskálázási összetevők számát, és a legtöbb esetben a többhelyes amplitúdók egy-egy normáját.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="f9e4f-123">Egyszintű – fürt wavefunction</span><span class="sxs-lookup"><span data-stu-id="f9e4f-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="f9e4f-124">A kémikusi függvénytár használatával a psi_ \ket{\ {\rm {UCC}}} $ wavefunction is megadható.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="f9e4f-125">Ebben az esetben egyetlen meghatározó hivatkozási állapottal rendelkezünk, mondjuk: $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="f9e4f-126">Az egységes és a fürt wavefunction összetevői implicit módon vannak megadva a hivatkozási állapotot kezelő egységes operátoron keresztül.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="f9e4f-127">Ez az egységes operátor általában $e ^ {T-T ^ \dagger} $ néven íródott, ahol a $T-T ^ \dagger $ a Hermitian-fürt operátora.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="f9e4f-128">Így \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="f9e4f-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f9e4f-129">\end{align}</span></span>

<span data-ttu-id="f9e4f-130">Az is gyakori, hogy a $T = T_1 + T_2 + \cdots $ csomópontot részekre darabolják, ahol minden rész $T _j $ tartalmaz $j $-Body kifejezést.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="f9e4f-131">Az általánosított és a fürtök elméletében az egytörzsű fürt operátora (Singles) \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="f9e4f-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="f9e4f-132">a kéttörzsű fürt operátora (Double) a következő: \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="f9e4f-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f9e4f-133">\end{align}</span></span>

<span data-ttu-id="f9e4f-134">A magasabb rendű feltételek (triplák, négyszeresek stb.) lehetségesek, de a kémia könyvtára jelenleg nem támogatja őket.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="f9e4f-135">Tegyük fel például, hogy $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $, és hagyja $T = 0,123 a ^ \ dagger_0 a_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="f9e4f-136">Ezt az állapotot az alábbi módon hozza létre a kémiai könyvtárban.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-136">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="f9e4f-137">A spin convervation explicit módon is elvégezhető, ha `SpinOrbital` az indexeket a Integer indexek helyett megadhatja.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="f9e4f-138">Tegyük fel például, hogy $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $, és hagyjuk $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ be spin convserving.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="f9e4f-139">Ezt az állapotot az alábbi módon hozza létre a kémiai könyvtárban.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-139">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="f9e4f-140">Olyan kényelmi funkciót is biztosítunk, amely az összes olyan spin-beszélgetést végző fürt operátorát tartalmazza, amely megsemmisíti a csak megszállt spin-pályákat, és izgatja a nem foglalt spin-pályákat.</span><span class="sxs-lookup"><span data-stu-id="f9e4f-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
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
