---
title: 'Q # standard könyvtárak – diagnosztika | Microsoft Docs'
description: 'Q # standard könyvtárak – diagnosztika'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 67ec6780d8cbbda7223d46026a9df97cebc92b33
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820980"
---
# <a name="diagnostics"></a>Diagnosztika #

A klasszikus fejlesztéshez hasonlóan fontos, hogy képes legyen diagnosztizálni a kvantum-programok hibáit és hibáit.
A Q # standard szintű kódtárak számos különböző módszert biztosítanak a kvantum-programok helyességének biztosításához a <xref:microsoft.quantum.techniques.testing-and-debugging>részletezve.
Ez a támogatás nagyrészt olyan függvények és műveletek formájában érhető el, amelyek vagy a célszámítógép elutasításával további diagnosztikai adatokat biztosítanak a gazda programnak vagy fejlesztőknek, vagy kikényszerítik a feltételek és az invariánsok helyességét. a függvény vagy a művelet hívásával.

## <a name="machine-diagnostics"></a>Gépi diagnosztika ##

A klasszikus értékekkel kapcsolatos diagnosztika a <xref:microsoft.quantum.intrinsic.message> függvénnyel végezhető el, amely a gép által függő módon naplóz egy üzenetet.
Alapértelmezés szerint ez a karakterláncot írja a konzolra.
Az interpolált karakterláncokkal együtt használt <xref:microsoft.quantum.intrinsic.message> megkönnyíti a klasszikus értékekkel kapcsolatos diagnosztikai információk jelentését:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` rendelkezik aláírással `(String -> Unit)`, amely azt jelenti, hogy a hibakeresési naplót kibocsátó üzenet nem figyelhető meg a Q #-on belül.

A <xref:microsoft.quantum.diagnostics.dumpmachine> és <xref:microsoft.quantum.diagnostics.dumpregister> callables arra utasítja a célszámítógépeken, hogy diagnosztikai információkat biztosítson az összes jelenleg lefoglalt qubits, illetve a qubits egy adott regiszteréről.
Az egyes célszámítógépeken eltérő diagnosztikai információk szerepelnek a dump utasításra adott válaszban.
A [teljes körű állapot-szimulátor](xref:microsoft.quantum.machines.full-state-simulator) célszámítógép, például biztosítja a gazdagép programját a belső használatú állapot-vektor alapján, hogy az qubits regisztráljon.
Összehasonlításképpen a [Toffoli Simulator](xref:microsoft.quantum.machines.toffoli-simulator) célszámítógép egyetlen klasszikus bitet biztosít minden qubit.

 Ha többet szeretne megtudni a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` kimenetéről, tekintse meg a [tesztelési és hibakeresési cikk](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)dump functions című szakaszát.


## <a name="facts-and-assertions"></a>Tények és kijelentések ##

Ahogy azt a [tesztelési és hibakeresési](xref:microsoft.quantum.techniques.testing-and-debugging)művelettel tárgyaljuk, az aláírással `Unit -> Unit` vagy `Unit => Unit`tal rendelkező függvények vagy műveletek *egységként*is jelölhetők.
Az egyes egységek tesztelése általában egy kis kvantum-programból áll, valamint egy vagy több, a program helyességét ellenőrző feltételt.
Ezek a feltételek akár _tények_formájában is megtekinthetők, amelyek bemutatják a bemenetek vagy a _bejelentések_értékeit, amelyek egy vagy több, bemenetként átadott qubits állapotának ellenőrzését jelzik.

`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` például az a matematikai tény, hogy a $1 + 1 = $2, míg a `AssertQubit(One, qubit)` azt a feltételt jelöli, hogy a `qubit` mérési `One` bizonyossággal fog visszaadni.
Az előző esetben ellenőrizhető, hogy a feltétel helyes értéke csak az értékekre vonatkozik-e, míg az utóbbiban tudnia kell valamit a qubit állapotáról az érvényesítés kiértékelése érdekében.

A Q # standard könyvtárak számos különböző funkciót biztosítanak a tények ábrázolásához, többek között:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Qubit állapotának tesztelése ###

A gyakorlatban az állítások arra utalnak, hogy a kvantummechanika klasszikus szimulációinak nem kell megtartaniuk a [klónozás nélküli adattételt](https://arxiv.org/abs/quant-ph/9607018), így nem lehet fizikai méréseket és kijelentéseket készíteni, ha szimulátort használunk a célszámítógép számára.
Így a hardverre való üzembe helyezés előtt tesztelheti az egyes műveleteket a klasszikus szimulátoron.
Azokon a célszámítógépeken, amelyek nem engedélyezik az állítások kiértékelését, nyugodtan figyelmen kívül hagyhatják a <xref:microsoft.quantum.intrinsic.assert> hívásokat.

Általánosabb értelemben a <xref:microsoft.quantum.intrinsic.assert> művelet azt állítja be, hogy az adott qubits mérése az adott Pauli-alapon mindig a megadott eredménnyel jár.
Ha az állítás sikertelen, a végrehajtás az adott üzenettel `fail` meghívásával végződik.
Alapértelmezés szerint ez a művelet nincs implementálva; a-t támogató szimulátoroknak olyan implementációt kell biztosítaniuk, amely a futtatókörnyezet ellenőrzését végzi.
`Assert` aláírása `((Pauli[], Qubit[], Result, String) -> ())`.
Mivel a `Assert` egy üres rekordból álló függvény, amelynek kimeneti típusa, a rendszer nem eredményezte, hogy a Q # programon belül a `Assert` megfigyelhetők.

A <xref:microsoft.quantum.intrinsic.assertprob> Operation függvény azt állítja be, hogy a megadott qubits a megadott Pauli-alapon való mérése a megadott valószínűséggel fog rendelkezni, bizonyos tűréshatáron belül.
A tolerancia adalékanyag (például `abs(expected-actual) < tol`).
Ha az állítás sikertelen, a végrehajtás az adott üzenettel `fail` meghívásával végződik.
Alapértelmezés szerint ez a művelet nincs implementálva; a-t támogató szimulátoroknak olyan implementációt kell biztosítaniuk, amely a futtatókörnyezet ellenőrzését végzi.
`AssertProb` aláírása `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`. Az első `Double` paraméter megadja az eredmény kívánt valószínűségét, a második pedig a tűréshatárt.

Több, mint egy olyan mérést végzünk, amely a szimulátor által a qubit belső állapotának jelzésére használt klasszikus információkat a másolásra alkalmasnak tekinti, így nem kell mérést végeznie az állítás teszteléséhez.
Ez különösen azt eredményezi, hogy a nem *kompatibilis* mérések oka a tényleges hardverek esetében nem lehetséges.

Tegyük fel, hogy `P : Qubit => Unit` egy művelet, amelynek célja, hogy előkészítse a $ \ket{\psi} $ állapotot, ha a bemenete a $ \ket{0}$ állapotú.
A $ \ket{\psi '} $ értéket a `P`által készített tényleges állapotnak kell lennie.
Ezt követően a $ \ket{\psi} = \ket{\psi '} $ értéket, ha és csak akkor, ha a $ \ket{\psi} $ által leírt tengelyen a $ \ket{\psi '} $ érték mérése mindig `Zero`.
Ez a következő: \begin{align} \ket{\psi} = \ket{\psi '} \text{IF és only if} \braket{\psi | \psi '} = 1.
a Prelude-ben definiált primitív műveletek \end{align} közvetlenül olyan mérést végezhetünk, amely visszaadja `Zero`, ha a $ \ket{\psi} $ a Pauli-operátorok egyikének eigenstate.


A művelet <xref:microsoft.quantum.diagnostics.assertqubit> különösen hasznos rövidítést biztosít erre az esetre, ha tesztelni szeretné a $ \ket{\psi} = \ket{0}$ állítást.
Ez például akkor fordul elő, ha kiszámítjuk a kiszámítást, hogy a Ancilla qubits a $ \ket{0}$ értéket adja vissza a felszabadítás előtt.
A $ \ket{0}$-re való állítás akkor is hasznos, ha azt szeretnénk, hogy két állapot-előkészítési `P` és `Q` művelet is előkészítse ugyanazt az állapotot, és ha a `Q` támogatja `Adjoint`.
Különösen a

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Általánosságban azonban előfordulhat, hogy nem férnek hozzá olyan állapotokra vonatkozó kijelentésekhez, amelyek nem egyeznek a Pauli-operátorok eigenstates.
Például a $ \ket{\psi} = (\ket{0} + e ^ {i \pi/8} \ket{1})/\sqrt{2}$ nem eigenstate a Pauli operátorok egyike sem, így a <xref:microsoft.quantum.intrinsic.assertprob> nem tudjuk egyedileg meghatározni, hogy a $ \ket{\psi '} $ $ \ket{\psi} $ értékkel egyenlő.
Ehelyett fel kell bontani a $ \ket{\psi '} = \ket{\psi} $ metódust olyan feltételezésekre, amelyeket közvetlenül a szimulátor által támogatott primitívek használatával lehet tesztelni.
Ehhez tegye a $ \ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ értéket a következő összetett számoknál: $ \alpha = a\_r + a\_i $ és $ \beta $.
Vegye figyelembe, hogy ehhez a kifejezéshez négy valós számot kell megadnia: $\{a\_r, egy\_i, b\_r, b\_i\}$ a megadásához, mivel az egyes összetett számok egy valós és egy képzeletbeli rész összegének megfelelőek lehetnek.
A globális fázis miatt azonban választhatjuk, $a\_i = $0, így csak három valós számra van szükségünk, hogy egyedi módon qubit állapotot adjon meg.

Ezért három olyan állítást kell megadnia, amelyek egymástól függetlenek, hogy az elvárt állapotot érvényesítsék.
Ezt úgy teheti meg, hogy megkeresi a `Zero` megtartásának valószínűségét a $ \alpha $ és $ \beta $ értékkel megadott Pauli-mérések esetében, és mindegyiket egymástól függetlenül érvényesíti.
A $x $, $y $, és a $z $ `Result` értékeket a Pauli $X $, $Y $ és $Z $ mérések esetében.
Ezután használja a valószínűségi függvényt a kvantum-mérésekhez, \begin{align} \Pr (x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr (y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_^ 2 \right).
\end{align}

A <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> művelet a következő típusú állításokat valósítja meg: $ \alpha $ és $ \beta $, <xref:microsoft.quantum.math.complex>típusú értékekként.
Ez akkor hasznos, ha a várt állapotot matematikailag lehet kiszámítani.

### <a name="asserting-equality-of-quantum-operations"></a>A kvantum-műveletek egyenlőségének érvényesítése ###

Eddig olyan tesztelési műveletekkel foglalkozunk, amelyek bizonyos állapotok előkészítésére szolgálnak.
Gyakran azonban arra is Kíváncsiak vagyunk, hogy egy adott művelet nem egyetlen rögzített bemenet helyett a tetszőleges bemenetek esetében is működik.
Tegyük fel például, hogy egy olyan `U : ((Double, Qubit[]) => () : Adjoint)` műveletet hozott létre, amely egy egységes operátorok (t) $ $U (t) $ nevű családnak felel meg, és a `adjoint auto`használata helyett explicit `adjoint` blokkot adott meg.
Előfordulhat, hogy a rendszer azt állítja be, hogy $U ^ \dagger (t) = U (-t) $, ahogy az a várt érték, ha $t $ egy evolúciós időt jelöl.

Általánosságban elmondható, hogy két különböző stratégia van, amelyet követve az állítás szerint két művelet `U` és `V` azonos módon működnek.
Először is ellenőrizhető, hogy `U(target); (Adjoint V)(target);` megőrzi-e az egyes állapotokat egy adott alapon.
Másodszor, azt is megtehetjük, hogy egy kusza állapot felén eljáró `U(target); (Adjoint V)(target);` megőrzi a felakadás.
Ezeket a stratégiákat a Canon Operations <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> és <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>implementálja.

> [!NOTE]
> A fent tárgyalt hivatkozott állítás a [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), egy matematikai keretrendszer alapján működik, amely a (z) $n $ qubits műveleteit a $2n $ qubits-ben összekevert állapotokra kapcsolja.
> Különösen a $n $ qubits azonosító műveletét a rendszer a (z) $ \ket{\ beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})/\sqrt{2}$ $n $ másolatával jelképezi.
> A művelet <xref:microsoft.quantum.preparation.preparechoistate> implementálja ezt a isomorphism, és előkészít egy olyan állapotot, amely egy adott műveletet jelöl.

Nagyjából ezeket a stratégiákat az idő – Space kompromisszum különbözteti meg.
Az egyes bemeneti állapotok közelítése további időt vesz igénybe, míg a felakadás használata során további qubits kell tárolnia.
Azokban az esetekben, amikor egy művelet egy megfordítható klasszikus műveletet valósít meg, így csak a számítási alapon alapuló állapotokra érdeklik, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> a korlátozott adatbevitelek esetében az esélyegyenlőségi teszteket.

> [!TIP]
> A bemeneti állapotokra vonatkozó iterációt a számbavételi műveletek <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> és <xref:microsoft.quantum.canon.iteratethroughcartesianpower>kezelik.
> Ezek a műveletek általánosságban hasznosak lehetnek ahhoz, hogy a Descartes-féle termék minden elemére a két vagy több készlet között alkalmazza a műveletet.

Még ennél is fontosabb, hogy a két módszer a vizsgálat alatt álló műveletek különböző tulajdonságait teszteli.
Mivel a helyben történő bejelentések többször is meghívja az egyes műveleteket, az egyes bemeneti állapotokhoz egyszer, minden véletlenszerű döntés és mérési eredmény változhat a hívások között.
Ezzel szemben a hivatkozott állítás pontosan egyszer hívja meg az egyes műveleteket, például ellenőrzi, hogy a műveletek *egyetlen lövéssel*egyenlőek-e.
Mindkét teszt hasznos a kvantum-programok helyességének biztosításához.


## <a name="further-reading"></a>További olvasnivalók ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
