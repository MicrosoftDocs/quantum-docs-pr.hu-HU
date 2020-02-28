---
title: Hartree – Fock elmélet
description: Ismerje meg a Hartree – Fock elméletet, amely egy egyszerű módszer a Quantum Systems kezdeti állapotának összeállításához.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904451"
---
# <a name="hartreefock-theory"></a>Hartree – Fock elmélet

A Quantum kémia szimulációjának legfontosabb mennyisége a legjelentősebb mennyiség, amely a Hamilton mátrix minimális energiafogyasztási eigenvector.
Ennek az az oka, hogy a legtöbb, a szobahőmérsékleten lévő molekulák, például a reagálási arányok a kvantum-állapotok közötti szabad energia-eltérések, amelyek leírják a lépés kezdetét és végét a reagálási útvonalon, illetve a szobahőmérsékleten, például a közbenső az állapot általában az Államokban gyökerezik.
Bár a terepi állapot általában túl nehéz megtanulni (még a kvantum-számítógéppel is), mivel ez egy exponenciálisan nagy számú konfiguráció eloszlása.
A mennyiségeket, például a terepi állapotot, megtudhatja.
Ha például a $ \ket{\psi} $ értéke tiszta Quantum állapot, akkor a \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} megadja azt a középértéket, amelyet a rendszer adott állapotban tartalmaz.
A terület állapota ezután az az állapot, amely a legkisebb értéket adja meg. Ennek eredményeképpen egy olyan állapotot kell kiválasztania, amely a lehető legpontosabban van a valódi alapállapothoz képest, és a közvetlen (a variációs eigensolvers-ben végzett) vagy a fázis becslése alapján alapvetően fontos az energia becsléséhez.

Hartree – a Fock elmélete egyszerű módszert kínál a kvantum-rendszerek kezdeti állapotának összeállítására. Egyetlen Slater-meghatározó megközelítést eredményez a kvantumrendszer állapotának meghatározásához. Ebből a célból megtalál egy rotációs területet a Fock belül, amely lekicsinyíti a terepi állapotot. $N $ elektronok rendszeréhez a metódus végrehajtja az elforgatási \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket{0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket{0}\defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket{0}, \end{Equation} egy Hermitian (azaz $u =-u ^ \dagger $) mátrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $. Érdemes megjegyezni, hogy a $u $ mátrix az orbitális forgásokat jelöli, a $ \widetilde{a} ^ \ dagger_j $ és a $ \widetilde{a} _j $ érték pedig a Hartree – Fock molekuláris spin-orbits típusú elektronok létrehozási és megsemmisítési operátorait jelöli.


Ezt követően a mátrix $u $ értékre van optimalizálva, hogy csökkentse a várt energia \bra{0} \ prod_ {j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket{0}$. Habár előfordulhat, hogy az ilyen optimalizálási problémák általánosságban nehézkesek, a gyakorlatban a Hartree – Fock algoritmus igyekszik gyorsan konvergálni az optimalizálási probléma közel optimális megoldásához, különösen az egyensúlyi geometriákban lévő zárt rendszerhéjú molekulák esetében. Ezeket az állapotokat a `FermionWavefunction` objektum példányának is megadhatjuk. Például a következő állapot $a ^ \ dagger_{1}^ \ dagger_{2}egy ^ \ dagger_{6}\ket{0}$ példánya a kémiai könyvtárban a következőképpen történik.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
A Wave functions `SpinOrbital` indexekkel is indexelhető, majd a következőképpen konvertálhatja ezeket az indexeket egész számmá.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

A Hartree – Fock elmélet legszembetűnőbb funkciója, hogy olyan kvantum-állapotot eredményez, amely nem rendelkezik felakadás az elektronok között.
Ez azt jelenti, hogy gyakran megfelelő minőségi leírást biztosít a molekuláris rendszerek tulajdonságairól. 

A Hartree-Fock állapot az alábbi módon is újraépíthető a `FermionHamiltonian`ból.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Azonban a pontos eredmények beszerzése – különösen az erősen korrelált rendszerek esetében – olyan kvantum-állapotokat követel meg, amelyek túlmutatnak a Hartree – Fock elméleten.
