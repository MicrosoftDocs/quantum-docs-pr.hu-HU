---
title: Második kvantálás
description: Ismerkedjen meg a második kvantálási megközelítéssel az elektronikus struktúrák modellezéséhez a kvantum-programozásban.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: a08e20d5b53aa97cb12ead0dc3a36069d0ec5df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858838"
---
# <a name="second-quantization"></a><span data-ttu-id="a1cea-103">Második kvantálás</span><span class="sxs-lookup"><span data-stu-id="a1cea-103">Second Quantization</span></span>

<span data-ttu-id="a1cea-104">A második kvantálás az elektronikus struktúra egy másik lencsén keresztüli problémáját vizsgálja.</span><span class="sxs-lookup"><span data-stu-id="a1cea-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="a1cea-105">Ahelyett, hogy a $N _e $ elektronokat egy adott állapothoz (vagy orbitális) rendeli hozzá, a második kvantálás nyomon követi az egyes orbitális útvonalakat, és tárolja, hogy van-e egy elektron az egyes helyeken, és egyidejűleg automatikusan biztosítja a megfelelő Wave-függvény szimmetria-tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="a1cea-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="a1cea-106">Ez azért fontos, mert lehetővé teszi a kvantum-kémia modelljeinek megadását anélkül, hogy aggódnia kellene a bemeneti állapot symmetrizing (ahogy az a fermions esetében szükséges), és azért is, mert a második kvantálás lehetővé teszi, hogy az ilyen modellek kis kvantum-számítógépek használatával legyenek szimulálva.</span><span class="sxs-lookup"><span data-stu-id="a1cea-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="a1cea-107">Példa a második kvantálás működésére: tegyük fel, hogy a $ \ psi_0 \cdots \ psi_ {N-1} $ a térbeli orbitális orthonormal készlete.</span><span class="sxs-lookup"><span data-stu-id="a1cea-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="a1cea-108">Ezek az időkeretek úgy vannak kiválasztva, hogy a lehető legpontosabban képviseljék a rendszernek a figyelembe vett, meghatározott módon.</span><span class="sxs-lookup"><span data-stu-id="a1cea-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="a1cea-109">Ilyen orbitális példák olyan atomi pályák, amelyek a hidrogén atom eigenbasis alkotják.</span><span class="sxs-lookup"><span data-stu-id="a1cea-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="a1cea-110">Mivel az elektronok két spin-állapottal rendelkeznek, két elektron is beépíthető az egyes térbeli keringésbe.</span><span class="sxs-lookup"><span data-stu-id="a1cea-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="a1cea-111">Ez azt jelenti, hogy az érvényes állapotok a következők: $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $, ahol a $ \uparrow $ és a $ \downarrow $ olyan címkék, amelyek meghatározzák a spin szintű szabadság két eigenstates.</span><span class="sxs-lookup"><span data-stu-id="a1cea-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="a1cea-112">A $ \sigma \in \uparrow, a \downarrow $, a $ (j, \sigma) $ összesített indexe a \{ \} spin-Orbital, mivel a térbeli és a spin szintű szabadságot is tárolja.</span><span class="sxs-lookup"><span data-stu-id="a1cea-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="a1cea-113">A kémia könyvtárában a spin-orbits egy `SpinOrbital` adatstruktúrában tárolódik, és a következőképpen jön létre.</span><span class="sxs-lookup"><span data-stu-id="a1cea-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="a1cea-114">Ez azt jelenti, hogy a Wave-függvény spin-és térbeli részének alapja a $ \ psi_ {0} \cdots \ psi_ {2n-1} $ $, ahol az egyes indexek mostantól egy $ (j, \sigma) $ enumerálást jelentenek.</span><span class="sxs-lookup"><span data-stu-id="a1cea-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="a1cea-115">Az egyik lehetséges enumerálás $g (j, \sigma) = j + N\sigma ' $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="a1cea-116">Egy másik lehetséges enumerálás $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="a1cea-117">A Quantum kémia könyvtára használhatja ezeket az egyezményeket, és az ilyen kódolású pörgetések az alábbiak szerint hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="a1cea-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="a1cea-118">A fermionic rendszerek esetében a Pauli kizárási elv megakadályozza, hogy egynél több elektron legyen elérhető a spin-orbitális környezetekben egy időben.</span><span class="sxs-lookup"><span data-stu-id="a1cea-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="a1cea-119">Ez azt jelenti, hogy megírhatjuk a $ \ psi_1 $ \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \text{if $ \ psi_1 $ nem foglalt jogi állapotot,} </span><span class="sxs-lookup"><span data-stu-id="a1cea-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="a1cea-120">{1}a \ket _1 & \text{if $ \ psi_1 $ foglalt.}</span><span class="sxs-lookup"><span data-stu-id="a1cea-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="a1cea-121">\end{Cases} \end{Equation} ez a kódolás nagy a kvantum-számítógépek esetében, mivel ez azt jelenti, hogy az elektronikus foglalkozást egyetlen kvantum-bit-ként tudjuk tárolni.</span><span class="sxs-lookup"><span data-stu-id="a1cea-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="a1cea-122">A $2N $ spin-pályák megfoglalkozási állapota hasonló lehet a $2N $ qubits-ben.</span><span class="sxs-lookup"><span data-stu-id="a1cea-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="a1cea-123">Példaként, ha $N = $2, akkor az állam $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="a1cea-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="a1cea-124">a spin-pályák $1 $ és $2 $ értékűek maradnak.</span><span class="sxs-lookup"><span data-stu-id="a1cea-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="a1cea-125">Hasonlóképpen, az állam $ $ \ket {0} \equiv \ket {0} _{0} \cdots \ket {0}_{N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="a1cea-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="a1cea-126">nincsenek elektronok, és a "vákuum állapot" néven ismertek.</span><span class="sxs-lookup"><span data-stu-id="a1cea-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="a1cea-127">A második kvantálás gyönyörű mellékhatása, hogy már nem kell explicit módon nyomon követni a kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="a1cea-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="a1cea-128">Ennek az az oka, hogy amint látni fogjuk, az állapot-szimmetria önmagában a spin-pályák elektronikus foglalkozásait létrehozó és megsemmisítő operátorok ingázási szabályait képviseli.</span><span class="sxs-lookup"><span data-stu-id="a1cea-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="a1cea-129">Fermionic-operátorok</span><span class="sxs-lookup"><span data-stu-id="a1cea-129">Fermionic operators</span></span>

<span data-ttu-id="a1cea-130">A második kvantálási vektorok által létrehozott két alapvető operátor a létrehozási és a megsemmisítő operátor.</span><span class="sxs-lookup"><span data-stu-id="a1cea-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="a1cea-131">Ezek az operátorok egy adott helyen helyezik el vagy semmisítik meg az elektronokat.</span><span class="sxs-lookup"><span data-stu-id="a1cea-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="a1cea-132">Ezek a következők: $a ^ \ dagger_j $ és $a _j $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="a1cea-133">Például \begin{align} a következőt: ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad a_1 \ket {0} _1 = 0, \quad a_1 \ket {1} _1 = \ket {0} _1.</span><span class="sxs-lookup"><span data-stu-id="a1cea-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="a1cea-134">\end{align} vegye figyelembe, hogy itt $a ^ \ dagger_1 \ket {1} _1 = 0 $ és $a _1 \ket {0} _1 $ hozam a nulla vektor nem $ \ket {0} _1 $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="a1cea-135">Ilyen operátorok tehát nem Hermitian és nem egységesek.</span><span class="sxs-lookup"><span data-stu-id="a1cea-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="a1cea-136">Az általános létrehozási és megsemmisítési operátorokat a <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> típus használatával jelölik.</span><span class="sxs-lookup"><span data-stu-id="a1cea-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="a1cea-137">Egyetlen létrehozási operátor például az alábbiak szerint jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a1cea-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="a1cea-138">Az ilyen operátorokat is használhatja, a $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="a1cea-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="a1cea-139">$ $ Az operátorok ezen sorozata a Hamilton szimulációs könyvtárban lett kiépítve a fentiekben ismertetett egyszeres pörgetési esethez hasonló C#-kód használatával:</span><span class="sxs-lookup"><span data-stu-id="a1cea-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="a1cea-140">$K $ Fermions rendszer esetén a második kvantálás a létrehozási operátor műveletét $a ^ \ dagger_i $ értéket adja meg $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ és $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $, ahol $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ a Fermions teljes számát méri, amely egyetlen részecske állapotában van, és amelynek indexe $j < $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="a1cea-141">A második kvantálást is használják egy harmadik operátor.</span><span class="sxs-lookup"><span data-stu-id="a1cea-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="a1cea-142">Ezt az operátort a Number operátornak nevezzük, és a \begin{Equation} n_i = a ^ \ dagger_i a_i határozza meg.</span><span class="sxs-lookup"><span data-stu-id="a1cea-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="a1cea-143">\end{Equation} ez az operátor Megszámolja egy adott spin-orbitális foglalkozását, azaz \begin{align} n_i \ket {0} _i &= 0 \ szám</span><span class="sxs-lookup"><span data-stu-id="a1cea-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="a1cea-144">n_i \ket {1} _i &= \ket {1} _i.</span><span class="sxs-lookup"><span data-stu-id="a1cea-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="a1cea-145">a fenti `FermionTerm` példákhoz hasonló \end{align} ez a szám operátor a következőképpen épül fel.</span><span class="sxs-lookup"><span data-stu-id="a1cea-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="a1cea-146">A ravaszság azonban akkor is fennáll, ha a fermionic-rendszerekben létrehozási vagy megsemmisítő operátorokat használ.</span><span class="sxs-lookup"><span data-stu-id="a1cea-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="a1cea-147">Szükség van arra, hogy bármely érvényes kvantum-állapot a címkék cseréje nélkül legyen szimmetrikus.</span><span class="sxs-lookup"><span data-stu-id="a1cea-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="a1cea-148">Ez azt jelenti, hogy a $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="a1cea-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="a1cea-149">$ $ Ilyen operátorok azt mondják, hogy az "anti-ingázás", és általánosságban minden $i, j $, hogy \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.</span><span class="sxs-lookup"><span data-stu-id="a1cea-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="a1cea-150">a \end{align} így a következő két <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> példány nem megfelelőnek minősül</span><span class="sxs-lookup"><span data-stu-id="a1cea-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="a1cea-151">Annak a követelménye, hogy az egyes létrehozási operátorok által felhasználható adatingázás azt jelenti, hogy egy második kvantálási ábrázolás használatával elkerülhetők a Fermions-k szimmetria által felmerülő kihívások.</span><span class="sxs-lookup"><span data-stu-id="a1cea-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="a1cea-152">Ehelyett a kihívás újra kiemelkedik a létrehozási operátorok definíciójában.</span><span class="sxs-lookup"><span data-stu-id="a1cea-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="a1cea-153">Az anti-ingázási szabályok segítségével egyes `LadderSequence` példányok ténylegesen ugyanahhoz a fermionic-operátorhoz tartoznak, esetenként akár egy mínusz előjel is.</span><span class="sxs-lookup"><span data-stu-id="a1cea-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="a1cea-154">Vegyük például a Hamilton $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="a1cea-155">Ez motiválja, hogy a rendszer mindenhez kanonikus sorrendet határozzon meg `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="a1cea-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="a1cea-156">A `FermionTerm` rendszer a következők szerint automatikusan kanonikus sorrendbe helyezi az összeset.</span><span class="sxs-lookup"><span data-stu-id="a1cea-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="a1cea-157">Second-Quantized Fermionic Hamilton</span><span class="sxs-lookup"><span data-stu-id="a1cea-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="a1cea-158">Valószínűleg nem meglepő, hogy az [elektronikus rendszerek](xref:microsoft.quantum.chemistry.concepts.quantummodels) Hamilton a létrehozási és a megsemmisítési operátorok alapján írhatók.</span><span class="sxs-lookup"><span data-stu-id="a1cea-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="a1cea-159">Különösen, ha a $ \psi \_ j $ a spin-pályák, amelyek az alapot alkotják</span><span class="sxs-lookup"><span data-stu-id="a1cea-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="a1cea-160">\begin{Equation} \hat{H} = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ ra \_ s + H \_ {\textrm NUC}, \label{EQ: totalHam} \end{Equation}, ahol a $h \_ {\textrm NUC} $ a nukleáris energia (amely állandó a Born-Oppenheimer közelítése alatt) és</span><span class="sxs-lookup"><span data-stu-id="a1cea-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="a1cea-161">\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="a1cea-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="a1cea-162">ahol a $V (x) $ a Mean-Field potenciál, és</span><span class="sxs-lookup"><span data-stu-id="a1cea-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="a1cea-163">\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ címke {EQ: integrál} \end{align}</span><span class="sxs-lookup"><span data-stu-id="a1cea-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="a1cea-164">A ($h \_ {pq} $ kifejezéseket nevezzük egyelektronos egységeknek, mivel az ilyen kifejezések csak egyetlen elektront érintenek, és hasonlóképpen $h \_ {pqrs} $ a két elektronos egység.</span><span class="sxs-lookup"><span data-stu-id="a1cea-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="a1cea-165">Ezek az adatok szerves részét képezik, mert az ilyen együtthatók értékeinek beszámításához szerves értékre van szükség.</span><span class="sxs-lookup"><span data-stu-id="a1cea-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="a1cea-166">Az egyetlen elektron-kifejezés az egyes elektronok mozgási energiáját és azok interakcióját írja le az atommagok elektromos mezőivel.</span><span class="sxs-lookup"><span data-stu-id="a1cea-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="a1cea-167">A kételektronos, másrészt az elektronok közötti interakciók leírása.</span><span class="sxs-lookup"><span data-stu-id="a1cea-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="a1cea-168">Az ezekkel a feltételekkel kapcsolatos intuíció a létrehozási és a megsemmisítési operátorokból származhat, amelyek magukban foglalják ezeket.</span><span class="sxs-lookup"><span data-stu-id="a1cea-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="a1cea-169">Például $h _ {pq} a ^ \ dagger_p a_q $ a spin orbitális $q $ és a spin orbitális $p $ közötti elektron-átugrást írja le.</span><span class="sxs-lookup"><span data-stu-id="a1cea-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="a1cea-170">Hasonlóképpen, $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (a DISTINCT $p, a q, az r, s $) kifejezésben két elektront ismertet a spin orbits $r $ és $s $ szétszóródásával, és végül a spin orbits $p $ és $q $ alatt végződik.</span><span class="sxs-lookup"><span data-stu-id="a1cea-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="a1cea-171">Ha $r = q $ és $p = s $, $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ megadja a két elektronhoz kapcsolódó energiaadó, de nem írja le a dinamikus folyamatot.</span><span class="sxs-lookup"><span data-stu-id="a1cea-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="a1cea-172">Ezt a Hamiltonians az osztály használatával lehet kijelölni `FermionHamiltonian` , amely lényegében az összes kívánt példányt tartalmazó lista `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="a1cea-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="a1cea-173">Mivel a Hamiltonians a Hermitian szerint vannak meghatározva, az olyan speciális típussal indexeljük a kifejezéseket, `HermitianFermionTerm` amely Hermitian-szimmetriát is használ, ha ellenőrzi, hogy a feltételek egyenértékűek.</span><span class="sxs-lookup"><span data-stu-id="a1cea-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="a1cea-174">Hozzunk létre néhány szemléltető példát.</span><span class="sxs-lookup"><span data-stu-id="a1cea-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="a1cea-175">Vegye fontolóra a Hamilton $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $ értéket.</span><span class="sxs-lookup"><span data-stu-id="a1cea-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="a1cea-176">Egyszerűsítheti ezt az építkezést, hogy a Hamilton-operátorok Hermitian-operátorok.</span><span class="sxs-lookup"><span data-stu-id="a1cea-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="a1cea-177">Ha a Hamilton a kifejezéseket a használatával adja hozzá `Add` , a nem Hermitian kifejezéseket, például `fermionTerm0` feltételezi, hogy párosítva van a Hermitian konjugátummal.</span><span class="sxs-lookup"><span data-stu-id="a1cea-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="a1cea-178">Így az alábbi kódrészlet is ugyanazt a Hamilton jelöli:</span><span class="sxs-lookup"><span data-stu-id="a1cea-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="a1cea-179">Az anti-ingázási szabályok használatával a `FermionTerm` Hamilton egyes példányai ténylegesen ugyanahhoz a fermionic-operátorhoz tartoznak, esetenként akár egy mínusz előjel is.</span><span class="sxs-lookup"><span data-stu-id="a1cea-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="a1cea-180">Vegyük például a Hamilton $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, amely a fentiekben összefoglalt feltételek összege.</span><span class="sxs-lookup"><span data-stu-id="a1cea-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="a1cea-181">Előfordulhat, hogy a felhasználó számára nem mindig egyértelmű, hogy ezek egyenértékű feltételek, és így külön is felvehetők a Hamilton.</span><span class="sxs-lookup"><span data-stu-id="a1cea-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="a1cea-182">Azt is megteheti, hogy a Hamilton már meglévő kifejezéseket is szeretne módosítani.</span><span class="sxs-lookup"><span data-stu-id="a1cea-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="a1cea-183">Ezekben az esetekben az alábbi módon kombinálhatók az egyenértékű feltételekkel.</span><span class="sxs-lookup"><span data-stu-id="a1cea-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="a1cea-184">Az egyenértékű kifejezések együtthatóinak kombinálásával a Hamilton lévő feltételek teljes számát csökkenti.</span><span class="sxs-lookup"><span data-stu-id="a1cea-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="a1cea-185">A későbbiekben ez csökkenti a Hamilton szimulálásához szükséges kvantum-kapuk számát.</span><span class="sxs-lookup"><span data-stu-id="a1cea-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="a1cea-186">Belső ábrázolás</span><span class="sxs-lookup"><span data-stu-id="a1cea-186">Internal Representation</span></span>

<span data-ttu-id="a1cea-187">Egy-és kéttörzsű kapcsolattal rendelkező fermionic-Hamilton a második kvantálási jelöléssel</span><span class="sxs-lookup"><span data-stu-id="a1cea-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="a1cea-188">$ $ \begin{align} H = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a { \_ s}.</span><span class="sxs-lookup"><span data-stu-id="a1cea-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="a1cea-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a1cea-189">\end{align} $$</span></span>

<span data-ttu-id="a1cea-190">Ebben a jelölésben a legtöbb $N ^ 2 + N ^ 4 $ együtthatóval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="a1cea-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="a1cea-191">Azonban ezek az együtthatók sok esetben összegyűjthetők, mivel azok ugyanahhoz a kezelőhöz tartoznak.</span><span class="sxs-lookup"><span data-stu-id="a1cea-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="a1cea-192">Például abban az esetben, ha $p, q, r az s $ különálló indexek, a nem-ingázási szabályok segítségével megjelenítheti a következőt: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger {p} a { \_ \_ r} a { \_ s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a {s} a {r \_ \_ } = a ^ \dagger \_ {q} a ^ \dagger \_ {p} \_ \_ a {s} a {r}.</span><span class="sxs-lookup"><span data-stu-id="a1cea-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="a1cea-193">Továbbá, ahogy $H $ is Hermitian, minden nem Hermitian fermionic operátor, mondjuk $h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s} $, rendelkezik egy Hermitian konjugátummal, amely szintén megtalálható a $H $-ban.</span><span class="sxs-lookup"><span data-stu-id="a1cea-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="a1cea-194">Az alábbi symmetries alapján egyedi módon indexelheti a kifejezéseket, definiálunk egy kanonikus sorrendet az indexek esetében (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ $n + m $ fermionic operátorok bármely sorozatából $a ^ \dagger \_ {i \_ 1} \cdots a (z) ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as a következő:</span><span class="sxs-lookup"><span data-stu-id="a1cea-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="a1cea-195">Minden létrehozási operátor $a ^ \dagger \_ {i \_ \cdot} $ a megsemmisítési operátorok $a \_ {j \_ \cdot} $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="a1cea-196">Az összes létrehozási operátor indexe növekvő sorrendben van rendezve, amely $i \_ 1< i \_ 2< \cdots < i \_ n $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="a1cea-197">A rendszer az összes megsemmisítési operátor indexét csökkenő sorrendbe rendezi, ez $j \_ 1> j \_ 2 \cdots > j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="a1cea-198">A bal szélső index kisebb vagy egyenlő, mint a jobb szélső index, azaz $i \_ 1 \ le j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="a1cea-199">Ossza meg velünk a kanonikus módon rendezett indexek készletét $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \in S \_ {n, m}.</span><span class="sxs-lookup"><span data-stu-id="a1cea-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="a1cea-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a1cea-200">\end{align} $$</span></span>

<span data-ttu-id="a1cea-201">Ezzel a kanonikus sorrendtel a fermionic Hamilton $ $ \begin{align} H = \sum \_ {(p, q) \In S \_ {1,1} } h ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a { \_ s} + a ^ \dagger \_ {s} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $, megfelelően igazított egy-és kételektronos integrált $h \_ {pq} $ és $h \_ {pqrs} $.</span><span class="sxs-lookup"><span data-stu-id="a1cea-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

