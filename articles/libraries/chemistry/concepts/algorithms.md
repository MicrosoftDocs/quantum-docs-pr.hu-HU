---
title: Hamilton Dynamics szimulálása
description: Ismerje meg, hogyan használható a Trotter-Suzuki-képletek és-qubitization a Hamilton-szimulációkkal való együttműködéshez.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320707"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="91c68-103">Hamilton Dynamics szimulálása</span><span class="sxs-lookup"><span data-stu-id="91c68-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="91c68-104">Ha a Hamilton az elemi operátorok összegeként van kifejezve, a Dynamics a jól ismert módszerek egyikének használatával lefordítható az alapvető kapu műveleteibe.</span><span class="sxs-lookup"><span data-stu-id="91c68-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="91c68-105">Három hatékony megközelítés: Trotter – Suzuki-képletek, unitaries lineáris kombinációi és qubitization.</span><span class="sxs-lookup"><span data-stu-id="91c68-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="91c68-106">Ismertetjük az alábbi három megközelítést, és konkrét Q # példákat adunk arra, hogyan valósíthatók meg ezek a módszerek a Hamilton szimulációs kódtár használatával.</span><span class="sxs-lookup"><span data-stu-id="91c68-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="91c68-107">Trotter – Suzuki-képletek</span><span class="sxs-lookup"><span data-stu-id="91c68-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="91c68-108">A Trotter mögötti ötlet – a Suzuki-képletek egyszerűek: fejezze be a Hamilton, amely egy könnyen szimulálható Hamiltonians, majd a teljes evolúció megközelíthető az egyszerűbb fejlesztések sorrendjében.</span><span class="sxs-lookup"><span data-stu-id="91c68-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="91c68-109">Különösen $H = \ sum_ {j = 1} ^ m H_j $ legyen a Hamilton.</span><span class="sxs-lookup"><span data-stu-id="91c68-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="91c68-110">Ezután $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, ami azt jelenti, hogy ha $t \ll $1, akkor a közelítésben szereplő hiba elhanyagolható lesz.</span><span class="sxs-lookup"><span data-stu-id="91c68-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="91c68-111">Vegye figyelembe, hogy ha $e ^ {-i H t} $ volt, akkor a közelítésben szereplő hiba nem lesz $O (m ^ 2 t ^ 2) $: nulla lenne.</span><span class="sxs-lookup"><span data-stu-id="91c68-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="91c68-112">Ez a hiba azért fordul elő, mert $e ^ {-iHt} $ egy operátor exponenciális, és ennek eredményeként hiba történt a képlet használatakor, mert a $H _j $ feltételek nem ingázik (*azaz*$H _j H_k \ne H_k H_j $-t).</span><span class="sxs-lookup"><span data-stu-id="91c68-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="91c68-113">Ha $t $ nagy, a Trotter – Suzuki-képletek továbbra is használhatók a dinamika pontos szimulálása érdekében, ha a rövid időre lépésekre bontja a folyamatot.</span><span class="sxs-lookup"><span data-stu-id="91c68-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="91c68-114">$R $ legyen az időbeli evolúció lépéseinek száma, így minden alkalommal, amikor az/r $ $t időt futtat.</span><span class="sxs-lookup"><span data-stu-id="91c68-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="91c68-115">Ezután a $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t $ $, ami azt jelenti, hogy ha $r $ skála $m ^ 2 t ^ 2/\ epszilon $, akkor a hiba a legfeljebb $ \epsilon $ értékre tehető bármely $ \epsilon > 0 $ esetében.</span><span class="sxs-lookup"><span data-stu-id="91c68-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="91c68-116">A pontosabb közelítések úgy hozhatók létre, hogy az operátorok egy sorozatot állítanak össze, így a hibák megszakadnak.</span><span class="sxs-lookup"><span data-stu-id="91c68-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="91c68-117">A legegyszerűbb ilyen képlet, a második sorrend Trotter-Suzuki képlete, az űrlap $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2r} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ a hiba, amelynek elvégzése a $ \epsilon $-nál kevesebb, mint $ \epsilon > 0 $, ha $r $ értéket kíván méretezni a következővel: $m ^ {3/2} t ^ {3/2}/\sqrt {\ epszilon} $.</span><span class="sxs-lookup"><span data-stu-id="91c68-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="91c68-118">Még magasabb rendű képletek, pontosabban ($ 2k $) a $k > 0 $ megrendelése is kiépíthető rekurzív módon: $ $ U_ {2k} (t) = [U_ {2k-2} (s_k\~ t)] ^ 2 U_ {2k-2} ([1-4s_k] t) [U_ {2k-2} (s_k\~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2k + 1}/r ^ {2k}), $ $, ahol $s _k = (4 – 4 ^ {1/(2k-1)}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="91c68-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="91c68-119">A legegyszerűbb a következő negyedik Order ($k = $2) képlet, amelyet eredetileg a Suzuki: $ $ U_4 (t) = [U_2 (s_2\~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2\~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5T ^ 5/r ^ 4), $ $, ahol $s _2 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="91c68-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="91c68-120">Általánosságban elmondható, hogy az önkényesen magas rendű képletek hasonlóan összeállíthatók; azonban a bonyolultabb integrátorok használata során felmerülő költségek gyakran meghaladják a legtöbb gyakorlati probléma esetén a negyedik sorrendet meghaladó előnyöket.</span><span class="sxs-lookup"><span data-stu-id="91c68-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="91c68-121">Ahhoz, hogy a fenti stratégiák működjenek, meg kell adni egy metódust a $e ^ {-iH_j t} $ széles osztályának szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="91c68-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="91c68-122">A Hamiltonians legegyszerűbb családja, és vitathatatlanul a leghasznosabb, hogy az itt található Pauli-operátorok is használhatók.</span><span class="sxs-lookup"><span data-stu-id="91c68-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="91c68-123">A Pauli-operátorok könnyen szimulálható, mert a Clifford-műveletekkel (amelyek standard szintű kapuk a kvantum-számítástechnikai szolgáltatásokban) elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="91c68-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="91c68-124">Ha a rendszer ezt követően is elvégezte a eigenvalues, a rendszer az általuk használt qubits paritását is megtalálhatja.</span><span class="sxs-lookup"><span data-stu-id="91c68-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="91c68-125">Például $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $, ahol $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="91c68-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="91c68-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="91c68-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="91c68-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="91c68-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="91c68-128">0 & 0 & 0 & e ^ {-it} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="91c68-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="91c68-129">$ $ Itt, $e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ és $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$, amely közvetlenül látható annak következményeként, hogy a $0 $ $ érték paritása az $0 $, míg a kis-és nagybetűs karakterlánc $1 $ értéke $1 $.</span><span class="sxs-lookup"><span data-stu-id="91c68-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="91c68-130">A Pauli-operátorok exponenciálisan valósíthatók meg közvetlenül a Q # használatával a <xref:microsoft.quantum.intrinsic.exp> művelettel:</span><span class="sxs-lookup"><span data-stu-id="91c68-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="91c68-131">A Fermionic Hamiltonians esetében a [Jordan – Wigner elbomlása](xref:microsoft.quantum.chemistry.concepts.jordanwigner) kényelmesen leképezi a Hamilton-t a Pauli-operátorok összegére.</span><span class="sxs-lookup"><span data-stu-id="91c68-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="91c68-132">Ez azt jelenti, hogy a fenti megközelítés könnyen módosítható a kémia szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="91c68-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="91c68-133">Az alábbiakban egy egyszerű példa arra, hogy az ilyen szimulációkat hogyan lehet a kémián belül végrehajtani a Jordan-Wigner ábrázolásban, és nem kell manuálisan összevetnie az összes Pauli kifejezéssel.</span><span class="sxs-lookup"><span data-stu-id="91c68-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="91c68-134">A kiindulási pont a Fermionic Hamilton [Jordánia – Wigner kódolása](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , amely kód formájában szerepel a `JordanWignerEncoding` osztály példányaiban.</span><span class="sxs-lookup"><span data-stu-id="91c68-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="91c68-135">A Wigner a Q # szimulációs algoritmusok által fogyasztott formátuma a felhasználó által definiált `JordanWignerEncodingData`típus.</span><span class="sxs-lookup"><span data-stu-id="91c68-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="91c68-136">A Q # esetében ezt a formátumot egy kényelmi függvénynek adja át `TrotterStepOracle` amely egy operátort ad vissza a Trotter – Suzuki integrátor használatával, a végrehajtásához szükséges egyéb paraméterek mellett.</span><span class="sxs-lookup"><span data-stu-id="91c68-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

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

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="91c68-137">Fontos, hogy ez a megvalósítás bizonyos optimalizálásokat alkalmaz, amelyek a Quantum [Computers használatával Hamiltonians az elektronikus struktúrák szimulációjában](https://arxiv.org/abs/1001.3855) , és javítják a kvantum- [kémia kvantum-algoritmusait](https://arxiv.org/abs/1403.1539) , hogy minimálisra csökkentsék a szükséges qubit-elforgatások számát, valamint a szimulációs hibákat.</span><span class="sxs-lookup"><span data-stu-id="91c68-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="91c68-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="91c68-138">Qubitization</span></span>

<span data-ttu-id="91c68-139">A Qubitization egy alternatív módszer a szimulációra, amely a Quantum walks ötleteit használja a kvantum-dinamika szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="91c68-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="91c68-140">Míg a qubitization több qubits igényel, mint a Trotter-képletek, a metódus optimális skálázást ígér az evolúciós idővel és a hibatűréssel.</span><span class="sxs-lookup"><span data-stu-id="91c68-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="91c68-141">Ezen okok miatt a Hamilton Dynamics általános szimulálása, valamint az elektronikus szerkezettel kapcsolatos probléma megoldására szolgáló előnyben részesített módszer lett.</span><span class="sxs-lookup"><span data-stu-id="91c68-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="91c68-142">A qubitization magas szinten a következő lépésekkel valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="91c68-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="91c68-143">Először is legyen $H = \ sum_j h_j H_j $ az egységes és Hermitian $H _j $ és $h _j \ge $0.</span><span class="sxs-lookup"><span data-stu-id="91c68-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="91c68-144">Egy pár reflexiók elvégzésével a qubitization olyan operátort valósít meg, amely egyenértékű a következővel: $ $W = e ^ {\pm i \cos ^{-1}(H/| H | _1)}, $ $ where $ | H | _1 = \ sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="91c68-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="91c68-145">A következő lépés magában foglalja a Walk operátor eigenvalues átalakítását $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, ahol $E _k $ eigenvalues $H $ és $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="91c68-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="91c68-146">Ez számos, a kvantumok számának különböző átalakítási módszerének használatával érhető el, beleértve a [kvantum-jelek feldolgozását](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)is.</span><span class="sxs-lookup"><span data-stu-id="91c68-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="91c68-147">Azt is megteheti, hogy csak a statikus mennyiségeket kívánja használni (például a Hamilton alapvető állapotát), és a [fázis-becslést](xref:microsoft.quantum.libraries.characterization) közvetlenül $W $ értékre alkalmazza, hogy megbecsülje a terepi állapotot az eredményből az eredmény koszinuszának kiszámításával.</span><span class="sxs-lookup"><span data-stu-id="91c68-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="91c68-148">Ez azért fontos, mert lehetővé teszi, hogy a spektrális átalakítás klasszikusan legyen elvégezhető, és ne használjon kvantum-szám értékű átalakítási módszert.</span><span class="sxs-lookup"><span data-stu-id="91c68-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="91c68-149">Részletesebb szinten a qubitization megvalósítása két olyan alrutint igényel, amelyek biztosítják a Hamilton interfészeit.</span><span class="sxs-lookup"><span data-stu-id="91c68-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="91c68-150">A Trotter – Suzuki metódusokkal ellentétben ezek az alrutinok nem klasszikusok, és a megvalósításuk szükségessé teszi a logaritmikusan több qubits használatát, mint a Trotter-alapú szimulációk esetében.</span><span class="sxs-lookup"><span data-stu-id="91c68-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="91c68-151">A qubitization által használt első kvantum-alrutin neve $ \operatorname{Select} $, és a rendszer megígérte, hogy \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation}, ahol minden $H _j $ feltételezi Hermitian és egységes.</span><span class="sxs-lookup"><span data-stu-id="91c68-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="91c68-152">Habár ez úgy tűnhet, hogy korlátozónak tűnik, a Pauli-operátorok Hermitian és egységesek, így az olyan alkalmazások, mint a Quantum kémia szimuláció, természetesen ebbe a keretrendszerbe tartoznak.</span><span class="sxs-lookup"><span data-stu-id="91c68-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="91c68-153">A $ \operatorname{Select} $ művelet, ami talán meglepő, valójában egy reflexiós művelet.</span><span class="sxs-lookup"><span data-stu-id="91c68-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="91c68-154">Ez azt jelentheti, hogy a $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $, mivel minden $H _j $ egységes és Hermitian, így eigenvalues $ \pm $1.</span><span class="sxs-lookup"><span data-stu-id="91c68-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="91c68-155">A második alrutin neve $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="91c68-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="91c68-156">Míg a Select művelet lehetővé teszi, hogy koherens módon hozzáférhessen a Hamilton egyes használati feltételeihez $H _j $ a felkészülési alrutin lehetővé teszi az együtthatók elérését $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="91c68-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="91c68-157">Ezt követően a \end{Equation} egy szorzás vezérelt fázisú kaput használva láthatjuk, hogy $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="91c68-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="91c68-158">\ket{x} & \text{otherwise} \end{Cases}.</span><span class="sxs-lookup"><span data-stu-id="91c68-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="91c68-159">A $ \operatorname{Prepare} $ művelet nem használható közvetlenül a qubitization-ben, hanem olyan állapottal kapcsolatos reflexió megvalósítására szolgál, amely a $ \operatorname{Prepare} $ létrehoz $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="91c68-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="91c68-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="91c68-160">\end{align} $$</span></span>

<span data-ttu-id="91c68-161">A Walk operátor ($W $) a $ \operatorname{Select} $ és a $R $ műveletekben kifejezhető a $ $ W = \operatorname{Select} R, $ $ értékkel, amely ismét látható egy olyan operátor megvalósításához, amely egyenértékű (legfeljebb egy isometry) $e ^ {\pm i \cos ^{-1}(H/| H | _1)} $.</span><span class="sxs-lookup"><span data-stu-id="91c68-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="91c68-162">Ezek az alrutinok egyszerűen beállíthatók a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="91c68-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="91c68-163">Vegyük például az egyszerű qubit keresztirányú-Ising Hamilton, ahol a $H = X_1 + X_2 + Z_1 Z_2 $ értéket.</span><span class="sxs-lookup"><span data-stu-id="91c68-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="91c68-164">Ebben az esetben a $ \operatorname{Select} $ művelet megvalósítására szolgáló Q # kódot a <xref:microsoft.quantum.canon.multiplexoperations>hívja meg, míg a $ \operatorname{Prepare} $ művelet a <xref:microsoft.quantum.preparation.preparearbitrarystate>használatával valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="91c68-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="91c68-165">A Hubbard-modell szimulálása például [Q # mintaként](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)is megtalálható.</span><span class="sxs-lookup"><span data-stu-id="91c68-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="91c68-166">Ha manuálisan szeretné megadni ezeket a lépéseket az önkényes kémiai problémákhoz, nagy erőfeszítést igényel, ami elkerülhető a kémiai könyvtár használatával.</span><span class="sxs-lookup"><span data-stu-id="91c68-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="91c68-167">A fenti Trotter – Suzuki szimulációs algoritmushoz hasonlóan a `JordanWignerEncodingData` át lesz adva a kényelmi `QubitizationOracle` függvénynek, amely visszaadja a Walk-operátort, a végrehajtáshoz szükséges egyéb paraméterek mellett.</span><span class="sxs-lookup"><span data-stu-id="91c68-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="91c68-168">Fontos, hogy a megvalósítási <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> a Pauli-karakterláncok lineáris kombinációjával megadott tetszőleges Hamiltonians érvényesek.</span><span class="sxs-lookup"><span data-stu-id="91c68-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="91c68-169">A kémia-szimulációra optimalizált verzió a <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>használatával hívható meg.</span><span class="sxs-lookup"><span data-stu-id="91c68-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="91c68-170">Ez a verzió úgy van optimalizálva, hogy csökkentse a T-kapuk számát a [kvantum-áramkörökben lévő, lineáris T komplexitású elektronikus spektrumok kódolásával](https://arxiv.org/abs/1805.03662)tárgyalt technikák használatával.</span><span class="sxs-lookup"><span data-stu-id="91c68-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
