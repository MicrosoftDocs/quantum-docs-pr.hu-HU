---
title: Hartree – Fock elmélet
description: Ismerje meg a Hartree – Fock elméletet, amely egy egyszerű módszer a Quantum Systems kezdeti állapotának összeállításához.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275111"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="bba67-103">Hartree – Fock elmélet</span><span class="sxs-lookup"><span data-stu-id="bba67-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="bba67-104">A Quantum kémia szimulációjának legfontosabb mennyisége a legjelentősebb mennyiség, amely a Hamilton mátrix minimális energiafogyasztási eigenvector.</span><span class="sxs-lookup"><span data-stu-id="bba67-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="bba67-105">Ennek az az oka, hogy a legtöbb, a szobahőmérsékleten lévő molekulák, például a reagálási arányok a kvantum-állapotok közötti szabad energia-eltérések, amelyek leírják a lépés kezdetét és végét a reakció útvonalán és a szobahőmérsékleten, például a közbenső állapot általában az állam.</span><span class="sxs-lookup"><span data-stu-id="bba67-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="bba67-106">Bár a terepi állapot általában túl nehéz megtanulni (még a kvantum-számítógéppel is), mivel ez egy exponenciálisan nagy számú konfiguráció eloszlása.</span><span class="sxs-lookup"><span data-stu-id="bba67-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="bba67-107">A mennyiségeket, például a terepi állapotot, megtudhatja.</span><span class="sxs-lookup"><span data-stu-id="bba67-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="bba67-108">Ha például a $ \ket{\psi} $ értéke tiszta Quantum állapot, akkor a \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} megadja azt a középértéket, amelyet a rendszer adott állapotban tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="bba67-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="bba67-109">A terület állapota ezután az az állapot, amely a legkisebb értéket adja meg.</span><span class="sxs-lookup"><span data-stu-id="bba67-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="bba67-110">Ennek eredményeképpen egy olyan állapotot kell kiválasztania, amely a lehető legpontosabban van a valódi alapállapothoz képest, és a közvetlen (a variációs eigensolvers-ben végzett) vagy a fázis becslése alapján alapvetően fontos az energia becsléséhez.</span><span class="sxs-lookup"><span data-stu-id="bba67-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="bba67-111">Hartree – a Fock elmélete egyszerű módszert kínál a kvantum-rendszerek kezdeti állapotának összeállítására.</span><span class="sxs-lookup"><span data-stu-id="bba67-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="bba67-112">Egyetlen Slater-meghatározó megközelítést eredményez a kvantumrendszer állapotának meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="bba67-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="bba67-113">Ebből a célból megtalál egy rotációs területet a Fock belül, amely lekicsinyíti a terepi állapotot.</span><span class="sxs-lookup"><span data-stu-id="bba67-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="bba67-114">Különösen $N $ elektronok rendszeréhez a metódus végrehajtja az elforgatási \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {n-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} egy Hermitian (azaz $u =-u ^ \dagger $) mátrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="bba67-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="bba67-115">Érdemes megjegyezni, hogy a $u $ mátrix az orbitális forgásokat jelöli, a $ \widetilde{a} ^ \ dagger_j $ és a $ \widetilde{a} _j $ érték pedig a Hartree – Fock molekuláris spin-orbits típusú elektronok létrehozási és megsemmisítési operátorait jelöli.</span><span class="sxs-lookup"><span data-stu-id="bba67-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="bba67-116">A mátrix $u $-t a rendszer a várt energia minimalizálására optimalizálta. \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="bba67-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="bba67-117">Habár előfordulhat, hogy az ilyen optimalizálási problémák általánosságban nehézkesek, a gyakorlatban a Hartree – Fock algoritmus igyekszik gyorsan konvergálni az optimalizálási probléma közel optimális megoldásához, különösen az egyensúlyi geometriákban lévő zárt rendszerhéjú molekulák esetében.</span><span class="sxs-lookup"><span data-stu-id="bba67-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="bba67-118">Ezeket az állapotokat az objektum egy példánya is megadhatjuk `FermionWavefunction` .</span><span class="sxs-lookup"><span data-stu-id="bba67-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="bba67-119">Például a következő állapotot $a ^ \ dagger_ {1} egy ^ \ dagger_ {2} egy ^ \ dagger_ {6} \ket {0} $ példányt a kémiai könyvtárban a következőképpen kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="bba67-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="bba67-120">Az indexekkel is indexelheti a Wave függvényeket `SpinOrbital` , majd a következőképpen konvertálhatja ezeket az indexeket egész számmá.</span><span class="sxs-lookup"><span data-stu-id="bba67-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="bba67-121">A Hartree – Fock elmélet legszembetűnőbb funkciója, hogy olyan kvantum-állapotot eredményez, amely nem rendelkezik felakadás az elektronok között.</span><span class="sxs-lookup"><span data-stu-id="bba67-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="bba67-122">Ez azt jelenti, hogy gyakran megfelelő minőségi leírást biztosít a molekuláris rendszerek tulajdonságairól.</span><span class="sxs-lookup"><span data-stu-id="bba67-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="bba67-123">A Hartree-Fock állapot a következőből is újraépíthető `FermionHamiltonian` .</span><span class="sxs-lookup"><span data-stu-id="bba67-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="bba67-124">Azonban a pontos eredmények beszerzése – különösen az erősen korrelált rendszerek esetében – olyan kvantum-állapotokat követel meg, amelyek túlmutatnak a Hartree – Fock elméleten.</span><span class="sxs-lookup"><span data-stu-id="bba67-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
