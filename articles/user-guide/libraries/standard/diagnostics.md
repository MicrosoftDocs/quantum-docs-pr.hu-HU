---
title: Diagnosztika a Q# standard könyvtárakban
description: A Q# kvantum-programokban a hibák és hibák észleléséhez használt standard könyvtárak diagnosztikai funkcióinak és műveleteinek megismerése.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ab9b77c7536a1860064110810371d3a68e95b40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690853"
---
# <a name="diagnostics"></a>Diagnosztika #

A klasszikus fejlesztéshez hasonlóan fontos, hogy képes legyen diagnosztizálni a kvantum-programok hibáit és hibáit.
A Q# standard szintű kódtárak számos különböző módszert biztosítanak a kvantum-programok helyességének biztosításához <xref:microsoft.quantum.guide.testingdebugging> .
Ez a támogatás nagyrészt olyan függvények és műveletek formájában érhető el, amelyek a célszámítógép számára arra utasítja a további diagnosztikai adatokat, hogy a gazda programhoz vagy a fejlesztőhöz, vagy a függvény vagy a művelet hívása által kifejezett feltételek és invariánsok helyességét érvényesítsék.

## <a name="machine-diagnostics"></a>Gépi diagnosztika ##

A klasszikus értékekkel kapcsolatos diagnosztika megszerzéséhez a <xref:Microsoft.Quantum.Intrinsic.Message> függvény használatával kell naplózni egy üzenetet a gépen függő módon.
Alapértelmezés szerint ez a karakterláncot írja a konzolra.
Az interpolált karakterláncokkal együtt használva <xref:Microsoft.Quantum.Intrinsic.Message> könnyedén jelenthet diagnosztikai adatokat a klasszikus értékekről:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` rendelkezik aláírással `(String -> Unit)` , amely azt jelenti, hogy a hibakeresési napló üzenetének kibocsátása nem figyelhető meg a belülről Q# .

A <xref:Microsoft.Quantum.Diagnostics.DumpMachine> és a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables utasíthatja a megcélzott gépeket arra, hogy diagnosztikai adatokat szolgáltassanak a jelenleg lefoglalt qubits vagy a qubits egy adott regiszteréről.
Az egyes célszámítógépeken eltérő diagnosztikai információk szerepelnek a dump utasításra adott válaszban.
A [teljes körű állapot-szimulátor](xref:microsoft.quantum.machines.full-state-simulator) célszámítógép, például biztosítja a gazdagép programját a belső használatú állapot-vektor alapján, hogy az qubits regisztráljon.
Összehasonlításképpen a [Toffoli Simulator](xref:microsoft.quantum.machines.toffoli-simulator) célszámítógép egyetlen klasszikus bitet biztosít minden qubit.

 Ha többet szeretne megtudni a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` kimenetéről, tekintse meg a [tesztelési és hibakeresési cikk](xref:microsoft.quantum.guide.testingdebugging#dump-functions)dump functions című szakaszát.


## <a name="facts-and-assertions"></a>Tények és kijelentések ##

Ahogy azt a [tesztelési és hibakeresési](xref:microsoft.quantum.guide.testingdebugging)művelet, az aláírással `Unit -> Unit` vagy a használatával végzett műveletek `Unit => Unit` is megadhatók *egységként* .
Az egyes egységek tesztelése általában egy kis kvantum-programból áll, valamint egy vagy több, a program helyességét ellenőrző feltételt.
Ezek a feltételek akár _tények_ formájában is megtekinthetők, amelyek bemutatják a bemenetek vagy a _bejelentések_ értékeit, amelyek egy vagy több, bemenetként átadott qubits állapotának ellenőrzését jelzik.

Például `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` az a matematikai tény, hogy a $1 + 1 = $2, míg `AssertQubit(One, qubit)` a mérési feltételt jelzi, hogy a mérés `qubit` visszaadja a megfelelő `One` bizonyosságot.
Az előző esetben ellenőrizhető, hogy a feltétel helyes értéke csak az értékekre vonatkozik-e, míg az utóbbiban tudnia kell valamit a qubit állapotáról az érvényesítés kiértékelése érdekében.

A Q# standard könyvtárak számos különböző funkciót biztosítanak a tények ábrázolásához, többek között a következőket:

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a>Qubit állapotának tesztelése ###

A gyakorlatban az állítások arra utalnak, hogy a kvantummechanika klasszikus szimulációinak nem kell megtartaniuk a [klónozás nélküli adattételt](https://arxiv.org/abs/quant-ph/9607018), így nem lehet fizikai méréseket és kijelentéseket készíteni, ha szimulátort használunk a célszámítógép számára.
Így a hardverre való üzembe helyezés előtt tesztelheti az egyes műveleteket a klasszikus szimulátoron.
Azokon a célszámítógépeken, amelyek nem engedélyezik az állítások kiértékelését, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> nyugodtan figyelmen kívül hagyhatják a hívásokat.

Általánosságban a <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> művelet azt állítja be, hogy a megadott Pauli-alapú qubits mérése mindig a megadott eredménnyel jár.
Ha az állítás sikertelen, a Futtatás az adott üzenettel meghívásával végződik `fail` .
Alapértelmezés szerint ez a művelet nincs implementálva; a-t támogató szimulátoroknak olyan implementációt kell biztosítaniuk, amely a futtatókörnyezet ellenőrzését végzi.
`AssertMeasurement` aláírással rendelkezik `((Pauli[], Qubit[], Result, String) -> ())` .
Mivel a `AssertMeasurement` függvény egy üres rekordot tartalmaz a kimeneti típusként, a rendszer semmilyen hatást sem `AssertMeasurement` figyel a Q# programon belül.

A <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> Operation függvény azt állítja be, hogy a megadott Pauli-alapú qubits mérése a megadott valószínűséggel az adott tűréshatáron belül megtörténik.
A tolerancia adalékanyag (például: `abs(expected-actual) < tol` ).
Ha az állítás sikertelen, a Futtatás az adott üzenettel meghívásával végződik `fail` .
Alapértelmezés szerint ez a művelet nincs implementálva; a-t támogató szimulátoroknak olyan implementációt kell biztosítaniuk, amely a futtatókörnyezet ellenőrzését végzi.
`AssertMeasurementProbability` aláírással rendelkezik `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` . Az első `Double` paraméter megadja az eredmény kívánt valószínűségét, a második pedig a tűréshatárt.

Több, mint egy olyan mérést végzünk, amely a szimulátor által a qubit belső állapotának jelzésére használt klasszikus információkat a másolásra alkalmasnak tekinti, így nem kell mérést végeznie az állítás teszteléséhez.
Ez különösen azt eredményezi, hogy a nem *kompatibilis* mérések oka a tényleges hardverek esetében nem lehetséges.

Tegyük fel, hogy `P : Qubit => Unit` egy olyan művelet, amely a $ \ket{\psi} $ állapot előkészítésére szolgál, ha a bemenete a $ \ket $ állapotú {0} .
A $ \ket{\psi '} $ értéket kell a tényleges állapotra felkészíteni `P` .
Ezt követően a $ \ket{\psi} = \ket{\psi '} $ értéket, ha pedig csak akkor, ha a $ \ket{\psi} $ által ismertetett tengelyen a $ \ket{\psi '} $ érték mérése után a rendszer csak a $ `Zero`
Ez a következő: \begin{align} \ket{\psi} = \ket{\psi '} \text{IF és only if} \braket{\psi | \psi '} = 1.
a bevezetés során definiált primitív műveletek \end{align} közvetlenül olyan mérést végezhetünk, amely visszaadja a $ \ket{\psi} $ értéket, amely a `Zero` Pauli-operátorok egyikének eigenstate.


A művelet <xref:Microsoft.Quantum.Diagnostics.AssertQubit> különösen hasznos rövidítést biztosít erre az esetre, ha tesztelni szeretné a $ \ket{\psi} = \ket {0} $ állítását.
Ez például akkor fordul elő, ha nem számítottuk ki, hogy Ancilla qubits vissza $ \ket $ értékre, {0} mielőtt felszabadítja őket.
A $ \ket $-re {0} való állítás akkor is hasznos, ha azt szeretnénk, hogy a két állapot előkészítését `P` és `Q` műveleteit egyaránt készítse elő, és ha `Q` támogatja `Adjoint` .
Különösen a

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Általánosságban azonban előfordulhat, hogy nem férnek hozzá olyan állapotokra vonatkozó kijelentésekhez, amelyek nem egyeznek a Pauli-operátorok eigenstates.
Például a $ \ket{\psi} = (\ket {0} + e ^ {i \pi/8} \ket {1} )/\sqrt {2} $ nem eigenstate a Pauli operátorok egyike sem, így nem tudjuk <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> egyedileg meghatározni, hogy a $ \ket{\psi '} $ érték egyenlő a $ \ket{\psi} $ értékkel.
Ehelyett fel kell bontani a $ \ket{\psi '} = \ket{\psi} $ metódust olyan feltételezésekre, amelyeket közvetlenül a szimulátor által támogatott primitívek használatával lehet tesztelni.
Ehhez tegye a $ \ket{\psi} = \alpha \ket {0} + \beta \ket $ értéket {1} a következő összetett számok esetében: $ \alpha = a \_ r + a \_ i i $ és $ \beta $.
Vegye figyelembe, hogy ehhez a kifejezéshez négy valós számot kell \{ \_ megadnia: $ a r, \_ i, b \_ r, b \_ i \} $, hogy megadják, mivel minden összetett szám egy valós és egy képzeletbeli rész összegével fejezhető ki.
A globális fázis miatt azonban választhatjuk $a \_ i = $0, így csak három valós számra van szükségünk, hogy egyedi módon qubit állapotot adjon meg.

Ezért három olyan állítást kell megadnia, amelyek egymástól függetlenek, hogy az elvárt állapotot érvényesítsék.
Ezt úgy teheti meg `Zero` , hogy megkeresi az egyes, a $ \alpha $ és a $ \beta $ értékkel megadott Pauli-mérések valószínűségét, és mindegyiket egymástól függetlenül érvényesíti.
$X $, $y $, és $z $ érték adható `Result` meg a Pauli $X $, $Y $ és a $Z $ mérésekhez.
Ezt követően a \begin{align} \Pr (x = \texttt{Zero} | \alpha) a valószínűség függvény használatával \beta) & = \frac12 + a \_ r b \_ r + a \_ i b i \_ \\ \\ \Pr (y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2 \right).
\end{align}

A <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> művelet végrehajtja ezeket az állításokat a $ \alpha $ és a $ \beta $ értékkel megadott típusú értékek formájában <xref:Microsoft.Quantum.Math.Complex> .
Ez akkor hasznos, ha a várt állapotot matematikailag lehet kiszámítani.

### <a name="asserting-equality-of-quantum-operations"></a>A kvantum-műveletek egyenlőségének érvényesítése ###

Eddig olyan tesztelési műveletekkel foglalkozunk, amelyek bizonyos állapotok előkészítésére szolgálnak.
Gyakran azonban arra is Kíváncsiak vagyunk, hogy egy adott művelet nem egyetlen rögzített bemenet helyett a tetszőleges bemenetek esetében is működik.
Tegyük fel például, hogy megvalósított egy olyan műveletet, amely `U : ((Double, Qubit[]) => () : Adjoint)` egy egységes operátorok családja $U (t) $, és a `adjoint` használata helyett explicit blokkot adott meg `adjoint auto` .
Előfordulhat, hogy a rendszer azt állítja be, hogy $U ^ \dagger (t) = U (-t) $, ahogy az a várt érték, ha $t $ egy evolúciós időt jelöl.

Általánosságban elmondható, hogy két különböző stratégia van, amelyet követve elvégezheti az állítást, hogy két művelet `U` és `V` azonos módon járjon el.
Először is megvizsgálhatja, hogy az `U(target); (Adjoint V)(target);` egyes állapotok megtalálhatók-e egy adott alapon.
Másodszor, azt is megtehetjük, hogy `U(target); (Adjoint V)(target);` egy kusza állapot felén eljáró műveletek megőrzik a felakadás.
Ezeket a stratégiákat a Canon-műveletek, illetve a rendszerek implementálják <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> .

> [!NOTE]
> A fent tárgyalt hivatkozott állítás a [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), egy matematikai keretrendszer alapján működik, amely a (z) $n $ qubits műveleteit a $2n $ qubits-ben összekevert állapotokra kapcsolja.
> Különösen a $n $ qubits azonosító műveletét a rendszer a (z) $ \ket{\ beta_ {00} } \mathrel{: =} (\ket {00} + \ket {11} )/\sqrt $ összefoglalt állapot $n $ példányával jelöli {2} .
> A művelet <xref:Microsoft.Quantum.Preparation.PrepareChoiState> végrehajtja ezt a isomorphism, és előkészít egy olyan állapotot, amely egy adott műveletet jelöl.

Nagyjából ezeket a stratégiákat az idő – Space kompromisszum különbözteti meg.
Az egyes bemeneti állapotok közelítése további időt vesz igénybe, míg a felakadás használata során további qubits kell tárolnia.
Azokban az esetekben, amikor egy művelet egy megfordítható klasszikus műveletet valósít meg, így csak a számítási alapon működő állapotokkal kapcsolatos viselkedésre van szükség, a <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> korlátozott adatbevitelek esetében az egyenlőséget ellenőrzi.

> [!TIP]
> A bemeneti állapotokra való iterációt a számbavételi műveletek és a <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> .
> Ezek a műveletek általánosságban hasznosak lehetnek ahhoz, hogy a Descartes-féle termék minden elemére a két vagy több készlet között alkalmazza a műveletet.

Még ennél is fontosabb, hogy a két módszer a vizsgálat alatt álló műveletek különböző tulajdonságait teszteli.
Mivel a helyben történő bejelentések többször is meghívja az egyes műveleteket, az egyes bemeneti állapotokhoz egyszer, minden véletlenszerű döntés és mérési eredmény változhat a hívások között.
Ezzel szemben a hivatkozott állítás pontosan egyszer hívja meg az egyes műveleteket, például ellenőrzi, hogy a műveletek *egyetlen lövéssel* egyenlőek-e.
Mindkét teszt hasznos a kvantum-programok helyességének biztosításához.


## <a name="further-reading"></a>További információ ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>
