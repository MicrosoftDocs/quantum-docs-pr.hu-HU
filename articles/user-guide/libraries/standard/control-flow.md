---
title: A standard libararies a flow-vezérlők Q#
description: Ismerje meg a Flow Control műveleteit és funkcióit a Microsoft Q# standard Library-ben.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: a440f1ef2b901b18593816ca27aeadf7ab827104
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868576"
---
# <a name="higher-order-control-flow"></a>Magasabb rendű vezérlési folyamat #

A standard szintű kódtár egyik elsődleges szerepköre, hogy könnyebb legyen a [kvantum-programok](https://en.wikipedia.org/wiki/Quantum_programming)segítségével kifejezni a magas szintű algoritmusos ötleteket.
Így a Q# Canon számos különböző flow-vezérlési szerkezetet biztosít, amelyek mindegyike a függvények és műveletek részleges alkalmazásával valósítható meg.
Tekintse át azonnal a példát, és vegye figyelembe, hogy az egyik "CNEM-létrát" szeretné létrehozni egy regiszteren:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Ezt a mintát iteráció és hurkok használatával lehet kifejezni `for` :

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

A <xref:microsoft.quantum.canon.applytoeachca> és a tömbben kifejezett manipulációs függvények, például a <xref:microsoft.quantum.arrays.zip> , ez sokkal rövidebb és könnyebben olvasható:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

A szakasz további részében számos példát ismertetünk arra, hogy miként használhatók a Canon által nyújtott különféle flow-vezérlési műveletek és függvények a kvantum-programok tömörítéséhez.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Műveletek és függvények alkalmazása tömbökön és tartományokon keresztül ##

A Canon által biztosított elsődleges absztrakciók egyike az iteráció.
Vegyünk például egy egységes formát, $U \otimes U \otimes \cdots \otimes U $-t egyetlen qubit egységes $U $-ra.
A-ben a Q# következő módon lehet ezt a lehetőséget használni a <xref:microsoft.quantum.arrays.indexrange> `for` regisztrálási hurokként:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

Ezt követően ezt az új műveletet úgy használhatja, `HAll(register)` hogy alkalmazza $H \Otimes h \otimes \cdots \Otimes h $-t.

Ez azonban nehézkes, különösen egy nagyobb algoritmusban.
Emellett ez a megközelítés arra az adott műveletre specializálódott, amelyet az egyes qubit alkalmazni szeretnénk.
Azt is felhasználhatjuk, hogy a műveletek első osztályúak legyenek explicit módon kifejezni ezt az algoritmikus koncepciót:

```qsharp
ApplyToEachCA(H, register);
```

Itt az utótag `CA` azt jelzi, hogy a hívása `ApplyToEach` maga is adjointable és ellenőrizhető.
Így ha `U` a támogatja `Adjoint` és `Controlled` a-t, a következő sorok egyenértékűek:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Ez azt jelenti, hogy a `ApplyToEachCA` megjelenő hívások olyan műveletekben jelenhetnek meg, amelyeknél a adjoint-specializáció automatikusan létrejön.
Hasonlóképpen, az <xref:microsoft.quantum.canon.applytoeachindex> űrlap mintázatának ábrázolására is hasznos, `U(0, targets[0]); U(1, targets[1]); ...` és a bemenetek által támogatott összes-kombinációhoz biztosít verziókat.

> [!TIP]
> `ApplyToEach`a Type-paraméter úgy van megadva, hogy olyan műveletekkel is használható legyen, amelyek nem a (z) értéket használják `Qubit` .
> Tegyük fel például, hogy a `codeBlocks` <xref:microsoft.quantum.errorcorrection.logicalregister> helyreállításhoz szükséges értékek tömbje.
> Ezután `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` alkalmazza a hiba – a kód és a `code` helyreállítási függvényt az `recoveryFn` egyes blokkokra egymástól függetlenül.
> Ez a klasszikus bemenetek esetében is `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` érvényes: a $ \pi/$2 rotációját alkalmazza a $X $ értékre, amelyet a $PI/$3 $Y $ értékkel való elforgatása követ.

A Q# Canon Emellett támogatja a funkcionális programozáshoz ismert klasszikus enumerálási mintákat is.
Például <xref:microsoft.quantum.arrays.fold> implementálja a mintát $f (f (f (s \_ {\text{Initial}}, x \_ 0), x \_ 1), \dots) $, hogy csökkentse a függvények listáját.
Ez a minta összegek, termékek, minimumok, Maxima és más hasonló függvények megvalósítására használható:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Hasonlóképpen, a (z <xref:microsoft.quantum.arrays.mapped> ) és a függvények <xref:microsoft.quantum.arrays.mappedbyindex> is használhatók a funkcionális programozási fogalmak kifejezésére a alkalmazásban Q# .

## <a name="composing-operations-and-functions"></a>Műveletek és függvények összeállítása ##

A Canon által kínált vezérlési folyamatokat a rendszer bemenetként használja fel, így hasznos lehet több művelet vagy funkció egyetlen hívható számára való összeállítására.
Például a "^ {\dagger} $ $UVU minta rendkívül gyakori a kvantum-programozásban – úgy, hogy a Canon a műveletet <xref:microsoft.quantum.canon.applywith> absztraktként adja meg ehhez a mintához.
Ez az absztrakció azt is lehetővé teszi, hogy a folyamatok hatékonyabb Compliation legyenek, ahogy `Controlled` a sorozatot illetően `U(qubit); V(qubit); Adjoint U(qubit);` nem kell mindegyikre hatnia `U` .
Ha ezt szeretné látni, hagyja, hogy $c (U) $ legyen az egységes képviselő, `Controlled U([control], target)` és hagyja, hogy a $c (V) $ azonos módon legyen definiálva.
Ezután egy tetszőleges állapothoz $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (UVU ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\psi}.
a \end{align} a definíciója szerint `Controlled` .
Másrészről a \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes u) (c (v)) (\boldone \otimes u ^ \dagger) \ket {0} \otimes \ket{\psi}.
a \end{align} lineárisan következtetünk arra, hogy az összes bemeneti állapothoz így $U $-t is fel lehet venni.
Vagyis $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Mivel a vezérlési műveletek általában költségesek lehetnek, az ellenőrzött változatok, például a `WithC` és `WithCA` a segítségével csökkentheti az alkalmazandó vezérlő-kezelők számát.

> [!NOTE]
> A $U $ kiszámításának egyik másik következménye, hogy nem kell még azt is tudnia, hogy hogyan kell alkalmazni az üzemben lévőket `Controlled` `U` .
> `ApplyWithCA`Ezért a vártnál gyengébb aláírással rendelkezik:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Hasonlóképpen <xref:microsoft.quantum.canon.bound> olyan műveleteket állít elő, amelyek más műveletek sorozatot alkalmaznak.
Például a következők egyenértékűek:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

Az iterációs minták kombinálásával ez különösen hasznos lehet:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Idősorba rendezett összeállítás ###

Továbbra is folytathatja a flow-szabályozást a részleges alkalmazás-és klasszikus függvények szempontjából, és a klasszikus folyamatok szabályozása szempontjából is elég kifinomult kvantum-fogalmakat modellez.
Ez az analógia pontosan az a felismerés, hogy az egységes operátorok pontosan megegyeznek a hívási műveletek mellékhatásával, így az egységes operátorok más, az egységes operátorok általi lebomlása megfelel egy adott hívási sorrend létrehozásához a klasszikus alrutinok számára, amelyek olyan utasításokat bocsátanak ki, amelyek adott egységes operátorként működnek.
Ebben a nézetben `Bound` pontosan a mátrix termék ábrázolása, mivel az `Bound([A, B])(target)` egyenértékű a következővel, `A(target); B(target);` amely viszont a $ba $ értéknek megfelelő hívási sorrend.

Kifinomultabb példa a [Trotter – Suzuki bővítése](https://arxiv.org/abs/math-ph/0506007v1).
Ahogy azt az [adatstruktúrák](xref:microsoft.quantum.libraries.data-structures)dinamikus generátoros ábrázolási szakasza is tárgyalja, a Trotter – Suzuki terjeszkedés különösen hasznos módszert kínál a mátrixok exponenciális kifejezésére.
Például, ha a legalacsonyabb sorrendben alkalmazza a terjeszkedést, az olyan operátorok esetében, $A $ és $B $, hogy $A = A ^ \dagger $ és $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i A t/n) \exp (i B t/n) \right) ^ n.
\end{align}, ez azt mondja, hogy a $A + B $ alatti állapotot hozzávetőlegesen $A $ és $B $ alatt fejlesztjük.
Ha a $A $ alatti evolúciót jelöli egy olyan művelettel, amely a következőt `A : (Double, Qubit[]) => Unit` alkalmazza: $e ^ {i t A} $, akkor a Trotter – Suzuki terjeszkedés a hívási folyamatok átrendezése szempontjából egyértelművé válik.
Konkrétan egy művelet, `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` amely egy olyan műveletet `A = U(0, _, _)` `B = U(1, _, _)` határoz meg, amely a `U` (z) $t $ időpontban való integrálása melletti új műveletet is definiálhat az űrlap létrehozásával

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Ezen a ponton most már a Trotter – Suzuki kiterjesztésre is hivatkozhatunk, *anélkül, hogy a kvantum-mechanikara*lenne szükség.
A bővítés gyakorlatilag egy nagyon különleges iterációs minta, amelyet a $ \eqref{EQ: Trotter-Suzuki-0} $ alapján motiválnak.
Ezt az iterációs mintát a következő implementálja <xref:microsoft.quantum.canon.decomposeintotimestepsca> :

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

Az aláírás a `DecomposeIntoTimeStepsCA` következő általános mintát követi Q# , ahol olyan gyűjtemények szerepelnek, amelyekben tömbök vagy a menet közbeni elemek is lehetnek, amelyek az első elemek a rekordok jelölik `Int` .

## <a name="putting-it-together-controlling-operations"></a>Összerakva: vezérlési műveletek ##

Végül a Canon a `Controlled` feltételhez további lehetőségeket biztosít a kvantum-műveletek megkötésére.
Gyakori – különösen a Quantum aritmetika esetében – a \ket{0\cdots 0} $-től eltérő számítási alapon végrehajtott műveletek feltétele.
A fentiekben bemutatott vezérlési műveletek és függvények használatával egyetlen utasításban több általános kvantum-feltétel is megadható.
Ismerkedjen meg a <xref:microsoft.quantum.canon.controlledonbitstring> következővel: Hogyan (Sans Type Parameters), majd a darabokat eggyel bontják le.
Az első dolog, hogy meg kell határoznia egy olyan műveletet, amely valójában a vezérlő tetszőleges számítási alapon történő megvalósításának jelentős mértékű feloldását végzi.
Ezt a műveletet nem hívjuk közvetlenül, és így a név elejéhez hozzáadjuk azt, `_` hogy jelezze, hogy egy másik szerkezet implementációja máshol.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Vegye figyelembe, hogy egy tömbként jelölt BITS-karakterláncot `Bool` használunk, amellyel megadhatjuk, hogy milyen feltételt szeretnénk alkalmazni a megadott művelethez `oracle` .
Mivel ez a művelet ténylegesen az alkalmazást közvetlenül végzi el, a vezérlő és a cél regisztereket is el kell végeznie, mindkettőt pedig a következőként ábrázoljuk `Qubit[]` .

Ezt követően vegye figyelembe, hogy a $ \ket{\vec{s}} $ értéknek a $ \ket{0\cdots $ értékre való átalakításával a $ \ket{\vec{s}} = \ket{s \_ 0 s 1 \dots s {n-1}} $ kiszámítási állapotának vezérlését a $ \_ \_ \vec{s} $ értékre konvertálva lehet megvalósítani.
Különösen a $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.
Mivel $X ^ {\dagger} = X $, ez azt jelenti, hogy a $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.
Ezért alkalmazhatjuk $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $, Apply `Controlled oracle` , és retransform to $ \vec{s} $.
Ez az építés pontosan működik `ApplyWith` , ezért az új művelet törzsét ennek megfelelően írjuk:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Itt <xref:microsoft.quantum.canon.applypaulifrombitstring> alkalmazta a $P $-t, részben alkalmazva azt a cél használatára a szolgáltatással való használatra `ApplyWith` .
Vegye figyelembe azonban, hogy a *vezérlő* regisztrációját át kell alakítani a kívánt űrlapra, ezért részben alkalmazzuk a belső műveletet a `(Controlled oracle)` *célhelyen*.
Így `ApplyWith` a vezérlő regisztrálása a $P $ értékkel pontosan úgy működik, ahogy a kívánt módon.

Ezen a ponton megtehetjük, de valahogy nem teljesül, hogy az új műveletünk nem "érzi", mint az elmaradó alkalmazása `Controlled` .
Így az új vezérlési folyamat fogalmának meghatározása egy olyan függvény megírásával történik, amely az Oracle felügyeletét végzi, és új műveletet ad vissza.
Így úgy tűnik, hogy az új függvény nagyon hasonlít `Controlled` , és bemutatjuk, hogy könnyen definiáljuk a hatékony új vezérlési folyamatokat Q# a és a Canon együttes használatával:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
