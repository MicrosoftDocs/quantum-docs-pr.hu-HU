---
title: Második kvantálás
description: Ismerkedjen meg a második kvantálási megközelítéssel az elektronikus struktúrák modellezéséhez a kvantum-programozásban.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: e17c97767b05395af46a82c4035337406c7e3218
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907341"
---
# <a name="second-quantization"></a>Második kvantálás

A második kvantálás az elektronikus struktúra egy másik lencsén keresztüli problémáját vizsgálja.
Ahelyett, hogy az egyes $N _e $ elektronokat egy adott állapothoz (vagy orbitális) rendelje, a második kvantálás nyomon követi az egyes orbitális útvonalakat, és tárolja, hogy van-e egy elektron az egyes helyeken, és egyidejűleg automatikusan biztosítja a szimmetria-tulajdonságokat a hozzá tartozó Wave függvény.
Ez azért fontos, mert lehetővé teszi a kvantum-kémia modelljeinek megadását anélkül, hogy aggódnia kellene a bemeneti állapot symmetrizing (ahogy az a fermions esetében szükséges), és azért is, mert a második kvantálás lehetővé teszi, hogy az ilyen modellek kis kvantum használatával legyenek szimulálva számítógépek.

Példa a második kvantálás működésére: tegyük fel, hogy a $ \ psi_0 \cdots \ psi_ {N-1} $ a térbeli orbitális orthonormal készlete.
Ezek az időkeretek úgy vannak kiválasztva, hogy a lehető legpontosabban képviseljék a rendszernek a figyelembe vett, meghatározott módon.
Ilyen orbitális példák olyan atomi pályák, amelyek a hidrogén atom eigenbasis alkotják.
Mivel az elektronok két spin-állapottal rendelkeznek, két elektron is beépíthető az egyes térbeli keringésbe.
Ez azt jelenti, hogy az érvényes állapotok a következők: $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $, ahol $ \uparrow $ és $ \downarrow $ olyan címkék, amelyek meghatározzák a spin foka két eigenstates. Szabadságfok.
Ez a $ (j, \sigma) $ \sigma \in \{\uparrow, \downarrow\}$ összesített indexe spin-orbitális, mivel a térbeli és a spin szintű szabadságot is tárolja.
A kémia könyvtárában a spin-orbits egy `SpinOrbital` adatstruktúrában tárolódik, és a következőképpen jön létre.

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

Ez azt jelenti, hogy a Wave-függvény spin-és térbeli részének alapja a $ \ psi_{0} \cdots \ psi_ {2N-1} $ $, ahol az egyes indexek mostantól egy $ (j, \sigma) $ enumerálást alkotnak.
Az egyik lehetséges enumerálás $g (j, \sigma) = j + N\sigma ' $.
Egy másik lehetséges enumerálás $h (j, \sigma) = 2 * j + \sigma $.
A Quantum kémia könyvtára használhatja ezeket az egyezményeket, és az ilyen kódolású pörgetések az alábbiak szerint hozhatók létre.

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

A fermionic rendszerek esetében a Pauli kizárási elv megakadályozza, hogy egynél több elektron legyen elérhető a spin-orbitális környezetekben egy időben.
Ez azt jelenti, hogy a $ \ psi_1 $ \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket{0}_1 & \text{if $ \ psi_1 $ nem foglalt el,} \\\
\ket{1}_1 & \text{if $ \ psi_1 $ foglalt.} \end{Cases} \end{Equation} ez a kódolás nagy a kvantum-számítógépek esetében, mivel ez azt jelenti, hogy az elektronikus foglalkozást egyetlen kvantum-bit-ként tudjuk tárolni.

A $2N $ spin-pályák megfoglalkozási állapota hasonló lehet a $2N $ qubits-ben.
Példa: Ha $N = $2, akkor az állapot $ $ \ket{0} \ket{1} \ket{1} \ket{0}, $ $

a spin-pályák $1 $ és $2 $ értékűek maradnak.
Hasonlóképpen, az állapot $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $ $

nincsenek elektronok, és a "vákuum állapot" néven ismertek.

A második kvantálás gyönyörű mellékhatása, hogy már nem kell explicit módon nyomon követni a kvantum-állapotot.
Ennek az az oka, hogy amint látni fogjuk, az állapot-szimmetria önmagában a spin-pályák elektronikus foglalkozásait létrehozó és megsemmisítő operátorok ingázási szabályait képviseli.

## <a name="fermionic-operators"></a>Fermionic-operátorok

A második kvantálási vektorok által létrehozott két alapvető operátor a létrehozási és a megsemmisítő operátor.
Ezek az operátorok egy adott helyen helyezik el vagy semmisítik meg az elektronokat.
Ezek a következők: $a ^ \ dagger_j $ és $a _j $.

Például \begin{align} a ^ \ dagger_1 \ket{0}_1 = \ket{1}_1, \quad a ^ \ dagger_1 \ket{1}_1 = 0, \quad a_1 \ket{0}_1 = 0, \quad a_1 \ket{1}_1 = \ket{0}_1.
\end{align} vegye figyelembe, hogy itt $a ^ \ dagger_1 \ket{1}_1 = 0 $ és $a _1 \ket{0}_1 $ hozam a Zero-Vector not $ \ket{0}_1 $.
Ilyen operátorok tehát nem Hermitian és nem egységesek.
Az általános létrehozási és megsemmisítési operátorokat a <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> típus használatával jelöljük.
Egyetlen létrehozási operátor például az alábbiak szerint jelenik meg.

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

Az ilyen operátorokat is használhatjuk, a $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}^ {\otimes 4}.
$ $ Az operátorok ezen sorozata a Hamilton szimulációs könyvtárában a fentiekben ismertetett egyszeres pörgetési esethez hasonló C# kóddal lett kiépítve:
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

$K $ Fermions rendszer esetén a második kvantálás a létrehozási operátor műveletét $a ^ \ dagger_i $ értéket adja meg $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $ $ és $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $, ahol $S _i = \ sum_ {j < i} a ^ \ dagger_j a_j $ a Fermions teljes számát méri, amely egyetlen részecske állapotában van, és amelynek van indexe $j < i $.

A második kvantálást is használják egy harmadik operátor.
Ezt az operátort a Number operátornak nevezzük, és a \begin{Equation} n_i = a ^ \ dagger_i a_i határozza meg.
\end{Equation} ez az operátor Megszámolja egy adott spin-orbitális foglalkozását, ami azt jelenti, hogy \begin{align} n_i \ket{0}_i & = 0 \ számú\\\
n_i \ket{1}_i & = \ket{1}_i.
a fenti `FermionTerm`-példákhoz hasonló \end{align} az alábbiak szerint kell kiépíteni.
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

A ravaszság azonban akkor is fennáll, ha a fermionic-rendszerekben létrehozási vagy megsemmisítő operátorokat használ.
Szükség van arra, hogy bármely érvényes kvantum-állapot a címkék cseréje nélkül legyen szimmetrikus.
Ez azt jelenti, hogy a $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket{0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}.
$ $ Ilyen operátorok azt mondják, hogy az "anti-ingázás", és általánosságban minden $i, j $, hogy \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
a \end{align} így a következő két <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> példány nem megfelelőnek minősül
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

Annak a követelménye, hogy az egyes létrehozási operátorok által felhasználható adatingázás azt jelenti, hogy egy második kvantálási ábrázolás használatával elkerülhetők a Fermions-k szimmetria által felmerülő kihívások.
Ehelyett a kihívás újra kiemelkedik a létrehozási operátorok definíciójában. 

Az anti-ingázási szabályok segítségével egyes `LadderSequence` példányok ténylegesen ugyanahhoz a fermionic-operátorhoz tartoznak, esetenként akár egy mínusz előjel is.
Vegyük például a Hamilton $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.
Ez motiválja, hogy minden `FermionTerm`kanonikus sorrendet határozzon meg.
A rendszer minden `FermionTerm` automatikusan kanonikus sorrendbe helyezi az alábbiak szerint.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Második-Kvantálásos Fermionic Hamilton

Valószínűleg nem meglepő, hogy az [elektronikus rendszerek](xref:microsoft.quantum.chemistry.concepts.quantummodels) Hamilton a létrehozási és a megsemmisítési operátorok alapján írhatók.
Különösen, ha a $ \psi\_j $ a spin-pályák, amelyek az alapot alkotják

\begin{Equation} \hat{H} = \sum\_{pq} H\_{pq} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_p a ^ \dagger\_q a\_ra\_s + H\_{\textrm NUC}, \label{EQ: totalHam} \end{Equation}, ahol a $h\_{\textrm NUC} $ a nukleáris energia (amely a Born-Oppenheimer közelítés alatt állandó), és

\begin{align} h\_{pq} & = \int\_{-\infty} ^ \infty \psi ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \right) \psi\_q (x\_1) \mathrm{d} ^ 3x\_1, \end{align}

ahol a $V (x) $ a Mean-Field potenciál, és

\begin{align} h\_{pqrs} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \right) \psi\_r (x\_2) \psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ címke {EQ : integrálja} \end{align}

A ($h\_{pq} $ kifejezéshez tartozó feltételek a következők: egy elektronos egység, mert az összes ilyen kifejezés csak egyetlen elektront érint, és hasonlóképpen $h\_{pqrs} $ a kételektronos szerves egység.
Ezek az adatok szerves részét képezik, mert az ilyen együtthatók értékeinek beszámításához szerves értékre van szükség.
Az egyetlen elektron-kifejezés az egyes elektronok mozgási energiáját és azok interakcióját írja le az atommagok elektromos mezőivel.
A kételektronos, másrészt az elektronok közötti interakciók leírása.

Az ezekkel a feltételekkel kapcsolatos intuíció a létrehozási és a megsemmisítési operátorokból származhat, amelyek magukban foglalják ezeket.
Például $h _ {pq} a ^ \ dagger_p a_q $ a spin orbitális $q $ és a spin orbitális $p $ közötti elektron-átugrást írja le.
Hasonlóképpen, $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (a DISTINCT $p, a q, az r, s $) kifejezésben két elektront ismertet a spin orbits $r $ és $s $ szétszóródásával, és végül a spin orbits $p $ és $q $ alatt végződik.
Ha $r = q $ és $p = s $, $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ megadja a két elektronhoz kapcsolódó energiaadó, de nem írja le a dinamikus folyamatot.

Ezt a Hamiltonians a `FermionHamiltonian` osztály használatával lehet képviselni, amely lényegében a kívánt `FermionTerm` példányokat tartalmazó lista.
Mivel a Hamiltonians a definíciók szerint vannak Hermitian, a kifejezéseket a specializált `HermitianFermionTerm` típusnak megfelelően indexeljük, amely Hermitian-szimmetriát is használ, ha ellenőrzi, hogy a feltételek egyenértékűek-e.

Hozzunk létre néhány szemléltető példát.
Vegye fontolóra a Hamilton $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $ értéket.
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
Egyszerűsítheti ezt az építkezést, hogy a Hamilton-operátorok Hermitian-operátorok.
Ha `Add`használatával adja hozzá a feltételeket a Hamilton, akkor a nem Hermitian kifejezéseket, például a `fermionTerm0` a rendszer a Hermitian konjugátummal párosítja.
Így az alábbi kódrészlet is ugyanazt a Hamilton jelöli:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Az anti-ingázási szabályok használatával a Hamilton egyes `FermionTerm` példányai valójában ugyanahhoz a fermionic-operátorhoz tartoznak, esetenként akár egy mínusz előjel is.
Vegyük például a Hamilton $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, amely a fentiekben összefoglalt feltételek összege.
Előfordulhat, hogy a felhasználó számára nem mindig egyértelmű, hogy ezek egyenértékű feltételek, és így külön is felvehetők a Hamilton.
Azt is megteheti, hogy a Hamilton már meglévő kifejezéseket is szeretne módosítani.
Ezekben az esetekben az alábbi módon kombinálhatók az egyenértékű feltételekkel.
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
Az egyenértékű kifejezések együtthatóinak kombinálásával a Hamilton lévő feltételek teljes számát csökkenti.
A későbbiekben ez csökkenti a Hamilton szimulálásához szükséges kvantum-kapuk számát.

### <a name="internal-representation"></a>Belső ábrázolás

Egy-és kéttörzsű kapcsolattal rendelkező fermionic-Hamilton a második kvantálási jelöléssel

$ $ \begin{align} H = \sum\_{pq} H\_{pq} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s}.
\end{align} $ $

Ebben a jelölésben a legtöbb $N ^ 2 + N ^ 4 $ együtthatóval rendelkezik.
Azonban ezek az együtthatók sok esetben összegyűjthetők, mivel azok ugyanahhoz a kezelőhöz tartoznak.
Például abban az esetben, ha $p, q, r az s $ különálló indexek, a nem-ingázási szabályok segítségével megjelenítheti a következőt: $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r} a\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q}\_{s} a\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{s} a\_{r}.
$$

Továbbá, mivel $H $ Hermitian, minden nem Hermitian fermionic-kezelő, mondjuk $h\_{pqrs} ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $ Hermitian konjugátumot tartalmaz, amely $H $-ben is megtalálható. Ezen symmetries alapján egyedi módon indexelheti a kifejezéseket, és az indexek esetében definiálunk egy kanonikus sorrendet (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) $ $n + m $ fermionic-operátorok tetszőleges sorozatából $a ^ \dagger\_{i\_1} \cdots a ^ \dagger\_{i\_n} a\_{j\_1} \cdots a\_{j\_m} $as követi :
-   Minden létrehozási operátor $a ^ \dagger\_{i\_\cdot} $ az összes megsemmisítő operátor $a\_{j\_\cdot} $.
-   Az összes létrehozási operátor indexe növekvő sorrendbe van rendezve, azaz $i\_1 < i\_2 < \cdots < i\_n $.
-   Az összes megsemmisítési operátor indexe csökkenő sorrendbe van rendezve, azaz $j\_1 > j\_2 \cdots > j\_m $.
-   A bal szélső index kisebb vagy egyenlő, mint a jobb szélső index, azaz $i\_1 \ le j\_m $.

Ossza meg velünk a kanonikus módon rendezett indexek készletét $ $ \begin{align} (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) \in S\_{n, m}.
\end{align} $ $

Ezzel a kanonikus sorrendtel a fermionic Hamilton $ $ \begin{align} H = \sum\_{(p, q) \in S\_{1,1}} H "\_{pq} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{p}}{2}+ \sum\_{(p, q, r, s) \in S\_{2,2}} H '\_{pqrs} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{S} + a ^ \dagger\_{S} a ^ \ tőr\_{r} a\_{q} a\_{p}}{2}, \end{align} $ $, megfelelően igazított egy-és két elektronos belső $h "\_{pq} $ és $h"\_{pqrs} $.

