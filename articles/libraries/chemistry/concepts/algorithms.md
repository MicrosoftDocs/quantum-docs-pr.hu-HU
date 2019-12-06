---
title: Hamilton Dynamics szimulálása | Microsoft Docs
description: Hamilton Dynamics fogalmi docs szimulálása
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 4d1924386eadb427e8f53bc0a177453a341f185f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864457"
---
# <a name="simulating-hamiltonian-dynamics"></a>Hamilton Dynamics szimulálása

Ha a Hamilton az elemi operátorok összegeként van kifejezve, a Dynamics a jól ismert módszerek egyikének használatával lefordítható az alapvető kapu műveleteibe.
Három hatékony megközelítés: Trotter – Suzuki-képletek, unitaries lineáris kombinációi és qubitization.
Ismertetjük az alábbi három megközelítést, és konkrét Q # példákat adunk arra, hogyan valósíthatók meg ezek a módszerek a Hamilton szimulációs kódtár használatával.


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki-képletek
A Trotter mögötti ötlet – a Suzuki-képletek egyszerűek: fejezze be a Hamilton, amely egy könnyen szimulálható Hamiltonians, majd a teljes evolúció megközelíthető az egyszerűbb fejlesztések sorrendjében.
Különösen $H = \ sum_ {j = 1} ^ m H_j $ legyen a Hamilton.
Ezután $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, ami azt jelenti, hogy ha $t \ll $1, akkor a közelítésben szereplő hiba elhanyagolható lesz.
Vegye figyelembe, hogy ha $e ^ {-i H t} $ volt, akkor a közelítésben szereplő hiba nem lesz $O (m ^ 2 t ^ 2) $: nulla lenne.
Ez a hiba azért fordul elő, mert $e ^ {-iHt} $ egy operátor exponenciális, és ennek eredményeként hiba történt a képlet használatakor, mert a $H _j $ feltételek nem ingázik (*azaz*$H _j H_k \ne H_k H_j $-t).

Ha $t $ nagy, a Trotter – Suzuki-képletek továbbra is használhatók a dinamika pontos szimulálása érdekében, ha a rövid időre lépésekre bontja a folyamatot.
$R $ legyen az időbeli evolúció lépéseinek száma.
Ezután a $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t $ $, ami azt jelenti, hogy ha $r $ skála $m ^ 2 t ^ 2/\ epszilon $, akkor a hiba a legfeljebb $ \epsilon $ értékre tehető bármely $ \epsilon > 0 $ esetében.

A pontosabb közelítések úgy hozhatók létre, hogy az operátorok egy sorozatot állítanak össze, így a hibák megszakadnak.
A legegyszerűbb ilyen képlet, a szimmetrikus Trotter-képlet vagy a furcsa felosztása a következő formát veszi: $ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3) $ $, amely a $ \epsilon $-nál kevesebbet tehet elérhetővé bármely $ \epsilon > 0 $ értékre, ha a $r $ értéket szeretné méretezni a következővel: $m ^ {3/2} t ^ {3/2}/\sqrt {\ epszilon} $.

A magasabb rendű Trotter képletek a $U _1 $ alapján is létrehozhatók.
A legegyszerűbb a következő negyedik sorrendi képlet, eredetileg a Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $, ahol $s _1 = (4-4 ^ {1/3}) ^{-1}$.
Általánosságban elmondható, hogy az önkényesen magas rendű képletek hasonlóan összeállíthatók; azonban a bonyolultabb integrátorok használata során felmerülő költségek gyakran meghaladják a legtöbb gyakorlati probléma esetén a negyedik sorrendet meghaladó előnyöket.

Ahhoz, hogy a fenti stratégiák működjenek, meg kell adni egy metódust a $e ^ {-iH_j t} $ széles osztályának szimulálása érdekében.
A Hamiltonians legegyszerűbb családja, és vitathatatlanul a leghasznosabb, hogy az itt található Pauli-operátorok is használhatók.
A Pauli-operátorok könnyen szimulálható, mert a Clifford-műveletekkel (amelyek standard szintű kapuk a kvantum-számítástechnikai szolgáltatásokban) elhelyezhetők.
Ha a rendszer ezt követően is elvégezte a eigenvalues, a rendszer az általuk használt qubits paritását is megtalálhatja.

Például $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $, ahol $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {IT} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}.
$ $ Itt, $e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ és $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$, amely közvetlenül látható annak következményeként, hogy a $0 $ $ érték paritása az $0 $, míg a kis-és nagybetűs karakterlánc $1 $ értéke $1 $.

A Pauli-operátorok exponenciálisan valósíthatók meg közvetlenül a Q # használatával a <xref:microsoft.quantum.primitive.exp> művelettel:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

A Fermionic Hamiltonians esetében a [Jordan – Wigner elbomlása](xref:microsoft.quantum.chemistry.concepts.jordanwigner) kényelmesen leképezi a Hamilton-t a Pauli-operátorok összegére.
Ez azt jelenti, hogy a fenti megközelítés könnyen módosítható a kémia szimulálása érdekében.
Az alábbiakban egy egyszerű példa arra, hogy az ilyen szimulációkat hogyan lehet a kémián belül végrehajtani a Jordan-Wigner ábrázolásban, és nem kell manuálisan összevetnie az összes Pauli kifejezéssel.
A kiindulási pont a Fermionic Hamilton [Jordánia – Wigner kódolása](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , amely kód formájában szerepel a `JordanWignerEncoding` osztály példányaiban.

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

A Wigner a Q # szimulációs algoritmusok által fogyasztott formátuma a felhasználó által definiált `JordanWignerEncodingData`típus.
A Q # esetében ezt a formátumot egy kényelmi függvénynek adja át `TrotterStepOracle` amely egy operátort ad vissza a Trotter – Suzuki integrátor használatával, a végrehajtásához szükséges egyéb paraméterek mellett.

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

Fontos, hogy ez a megvalósítás bizonyos optimalizálásokat alkalmaz, amelyek a Quantum [Computers használatával Hamiltonians az elektronikus struktúrák szimulációjában](https://arxiv.org/abs/1001.3855) , és javítják a kvantum- [kémia kvantum-algoritmusait](https://arxiv.org/abs/1403.1539) , hogy minimálisra csökkentsék a szükséges qubit-elforgatások számát, valamint a szimulációs hibákat.

## <a name="qubitization"></a>Qubitization

A Qubitization egy alternatív módszer a szimulációra, amely a Quantum walks ötleteit használja a kvantum-dinamika szimulálása érdekében.
Míg a qubitization több qubits igényel, mint a Trotter-képletek, a metódus optimális skálázást ígér az evolúciós idővel és a hibatűréssel.
Ezen okok miatt a Hamilton Dynamics általános szimulálása, valamint az elektronikus szerkezettel kapcsolatos probléma megoldására szolgáló előnyben részesített módszer lett.

A qubitization magas szinten a következő lépésekkel valósítható meg.
Először is legyen $H = \ sum_j h_j H_j $ az egységes és Hermitian $H _j $ és $h _j \ge $0.
Egy pár reflexiók elvégzésével a qubitization olyan operátort valósít meg, amely egyenértékű a következővel: $ $W = e ^ {\pm i \cos ^{-1}(H/| H | _1)}, $ $ where $ | H | _1 = \ sum_j | h_j | $.
A következő lépés magában foglalja a Walk operátor eigenvalues átalakítását $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, ahol $E _k $ eigenvalues $H $ és $e ^ {-iE_k t} $.
Ez számos, a kvantumok számának különböző átalakítási módszerének használatával érhető el, beleértve a [kvantum-jelek feldolgozását](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)is.

Azt is megteheti, hogy csak a statikus mennyiségeket kívánja használni (például a Hamilton alapvető állapotát), és a [fázis-becslést](xref:microsoft.quantum.libraries.characterization) közvetlenül $W $ értékre alkalmazza, hogy megbecsülje a terepi állapotot az eredményből az eredmény koszinuszának kiszámításával.
Ez azért fontos, mert lehetővé teszi, hogy a spektrális átalakítás klasszikusan legyen elvégezhető, és ne használjon kvantum-szám értékű átalakítási módszert.

Részletesebb szinten a qubitization megvalósítása két olyan alrutint igényel, amelyek biztosítják a Hamilton interfészeit.
A Trotter – Suzuki metódusokkal ellentétben ezek az alrutinok nem klasszikusok, és a megvalósításuk szükségessé teszi a logaritmikusan több qubits használatát, mint a Trotter-alapú szimulációk esetében.

A qubitization által használt első kvantum-alrutin neve $ \operatorname{Select} $, és a rendszer megígérte, hogy \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation}, ahol minden $H _j $ feltételezi Hermitian és egységes.
Habár ez úgy tűnhet, hogy korlátozónak tűnik, a Pauli-operátorok Hermitian és egységesek, így az olyan alkalmazások, mint a Quantum kémia szimuláció, természetesen ebbe a keretrendszerbe tartoznak.
A $ \operatorname{Select} $ művelet, ami talán meglepő, valójában egy reflexiós művelet.
Ez azt jelentheti, hogy a $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $, mivel minden $H _j $ egységes és Hermitian, így eigenvalues $ \pm $1.

A második alrutin neve $ \operatorname{Prepare} $.
Míg a Select művelet lehetővé teszi, hogy koherens módon hozzáférhessen a Hamilton egyes használati feltételeihez $H _j $ a felkészülési alrutin lehetővé teszi az együtthatók elérését $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
Ezt követően a \end{Equation} egy szorzás vezérelt fázisú kaput használva láthatjuk, hogy $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \text{if} x = 0 \\\
        \ket{x} & \text{otherwise} \end{Cases}.
$$

A $ \operatorname{Prepare} $ művelet nem használható közvetlenül a qubitization-ben, hanem olyan állapottal kapcsolatos reflexió megvalósítására szolgál, amely a $ \operatorname{Prepare} $ létrehoz $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.
\end{align} $ $

A Walk operátor ($W $) a $ \operatorname{Select} $ és a $R $ műveletekben kifejezhető a $ $ W = \operatorname{Select} R, $ $ értékkel, amely ismét látható egy olyan operátor megvalósításához, amely egyenértékű (legfeljebb egy isometry) $e ^ {\pm i \cos ^{-1}(H/| H | _1)} $.

Ezek az alrutinok egyszerűen beállíthatók a Q #-ban.
Vegyük például az egyszerű qubit keresztirányú-Ising Hamilton, ahol a $H = X_1 + X_2 + Z_1 Z_2 $ értéket.
Ebben az esetben a $ \operatorname{Select} $ művelet megvalósítására szolgáló Q # kódot a <xref:microsoft.quantum.canon.multiplexoperations>hívja meg, míg a $ \operatorname{Prepare} $ művelet a <xref:microsoft.quantum.preparation.preparearbitrarystate>használatával valósítható meg.
A Hubbard-modell szimulálása például [Q # mintaként](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)is megtalálható.

Ha manuálisan szeretné megadni ezeket a lépéseket az önkényes kémiai problémákhoz, nagy erőfeszítést igényel, ami elkerülhető a kémiai könyvtár használatával.
A fenti Trotter – Suzuki szimulációs algoritmushoz hasonlóan a `JordanWignerEncodingData` át lesz adva a kényelmi `QubitizationOracle` függvénynek, amely visszaadja a Walk-operátort, a végrehajtáshoz szükséges egyéb paraméterek mellett.

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

Fontos, hogy a megvalósítási <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> a Pauli-karakterláncok lineáris kombinációjával megadott tetszőleges Hamiltonians érvényesek.
A kémia-szimulációra optimalizált verzió a <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>használatával hívható meg.
Ez a verzió úgy van optimalizálva, hogy csökkentse a T-kapuk számát a [kvantum-áramkörökben lévő, lineáris T komplexitású elektronikus spektrumok kódolásával](https://arxiv.org/abs/1805.03662)tárgyalt technikák használatával.
