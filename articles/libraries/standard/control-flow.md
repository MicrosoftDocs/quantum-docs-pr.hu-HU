---
title: 'Q # standard könyvtárak – vezérlés és folyamat | Microsoft Docs'
description: 'Q # standard könyvtárak – vezérlés és folyamat'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185647"
---
# <a name="higher-order-control-flow"></a>Magasabb rendű vezérlési folyamat #

A standard szintű kódtár egyik elsődleges szerepköre, hogy könnyebb legyen a [kvantum-programok](https://en.wikipedia.org/wiki/Quantum_programming)segítségével kifejezni a magas szintű algoritmusos ötleteket.
Így a Q # Canon számos különböző Flow Control-szerkezetet biztosít, amelyek mindegyike a függvények és műveletek részleges alkalmazásával valósítható meg.
Tekintse át azonnal a példát, és vegye figyelembe, hogy az egyik "CNEM-létrát" szeretné létrehozni egy regiszteren:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Ezt a mintát iterációs és `for` hurkok használatával lehet kifejezni:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

A <xref:microsoft.quantum.canon.applytoeachca> és a tömb manipulációs funkciói, például a <xref:microsoft.quantum.arrays.zip>esetében azonban sokkal rövidebb és könnyebben olvasható:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

A szakasz további részében számos példát ismertetünk arra, hogy miként használhatók a Canon által nyújtott különféle flow-vezérlési műveletek és függvények a kvantum-programok tömörítéséhez.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Műveletek és függvények alkalmazása tömbökön és tartományokon keresztül ##

A Canon által biztosított elsődleges absztrakciók egyike az iteráció.
Vegyünk például egy egységes formát, $U \otimes U \otimes \cdots \otimes U $-t egyetlen qubit egységes $U $-ra.
A Q #-ban használhatjuk a <xref:microsoft.quantum.arrays.indexrange>t, hogy ezt `for` hurokként adja meg a regiszterben:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

Ezt követően ezt az új műveletet `HAll(register)`ként is használhatja $H \otimes H \otimes \cdots \otimes H $-re való alkalmazásához.

Ez azonban nehézkes, különösen egy nagyobb algoritmusban.
Emellett ez a megközelítés arra az adott műveletre specializálódott, amelyet az egyes qubit alkalmazni szeretnénk.
Azt is felhasználhatjuk, hogy a műveletek első osztályúak legyenek explicit módon kifejezni ezt az algoritmikus koncepciót:

```qsharp
ApplyToEachCA(H, register);
```

Itt az utótag `CA` azt jelzi, hogy a `ApplyToEach` meghívása maga is adjointable és ellenőrizhető.
Így ha `U` támogatja a `Adjoint` és a `Controlled`, a következő sorok egyenértékűek:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Ez azt jelenti, hogy a `ApplyToEachCA` meghívása olyan műveletekben jelenhet meg, amelyek esetében a adjoint-specializáció automatikusan létrejön.
Hasonlóképpen, <xref:microsoft.quantum.canon.applytoeachindex> hasznos lehet az űrlap `U(0, targets[0]); U(1, targets[1]); ...`mintázatának ábrázolásához, és a bemenet által támogatott összes-kombinációhoz biztosít verziókat.

> [!TIP]
> a `ApplyToEach` Type-paraméteres, így olyan műveletekkel használható, amelyek nem `Qubit`.
> Tegyük fel például, hogy `codeBlocks` a <xref:microsoft.quantum.errorcorrection.logicalregister> értékek tömbje, amelyet helyre kell állítani.
> Ezután a `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` a hibajavítási kódot `code` és a helyreállítási függvényt is alkalmazza, `recoveryFn` az egyes blokkokra egymástól függetlenül.
> Ez a klasszikus adatbevitelek esetében is megőrzi a következőket: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` a $ \pi/$2-es rotációt alkalmazza a $X $ értékre, amelyet $pi/$3 $Y $ értékkel való elforgatása követ.

A Q # Canon Emellett támogatja a funkcionális programozáshoz ismert klasszikus enumerálási mintákat is.
Például a <xref:microsoft.quantum.arrays.fold> implementálja a mintát $f (f (f (s\_{\text{Initial}}, x\_0), x\_1), \dots) $, hogy csökkentse a függvények listáját.
Ez a minta összegek, termékek, minimumok, Maxima és más hasonló függvények megvalósítására használható:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Hasonlóképpen, a <xref:microsoft.quantum.arrays.mapped> és <xref:microsoft.quantum.arrays.mappedbyindex> függvények is használhatók a funkcionális programozási fogalmak kifejezésére a Q #-ban.

## <a name="composing-operations-and-functions"></a>Műveletek és függvények összeállítása ##

A Canon által kínált vezérlési folyamatokat a rendszer bemenetként használja fel, így hasznos lehet több művelet vagy funkció egyetlen hívható számára való összeállítására.
Például a "^ {\dagger} $ $UVU minta rendkívül gyakori a kvantum-programozásban – úgy, hogy a Canon a műveletet <xref:microsoft.quantum.canon.applywith> a minta absztrakciója adja meg.
Ez az absztrakció azt is lehetővé teszi, hogy hatékonyabb Compliation legyenek a áramkörök, mivel a sorozatban `U(qubit); V(qubit); Adjoint U(qubit);` nem kell az egyes `U`okra `Controlled`.
Ha ezt szeretné látni, hagyja, hogy $c (U) $ legyen az egységes képviselő `Controlled U([control], target)`, és hagyja, hogy a $c (V) $ azonos módon legyen definiálva.
Ezután egy tetszőleges állapothoz $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ ket{1} \otimes \ket{\psi}.
a \end{align} a `Controlled`definíciója szerint.
Másrészről a \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.
a \end{align} lineárisan következtetünk arra, hogy az összes bemeneti állapothoz így $U $-t is fel lehet venni.
Vagyis $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Mivel a vezérlési műveletek általában költségesek lehetnek, az ellenőrzött változatok (például a `WithC` és a `WithCA`) segítségével csökkentheti az alkalmazandó vezérlő-kezelők számát.

> [!NOTE]
> A $U $ kiszámításának egyik másik következménye, hogy még nem kell tudnia, hogyan kell alkalmazni a `Controlled`-munkafolyamatot `U`re.
> `ApplyWithCA` ezért a vártnál gyengébb aláírással rendelkezik:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Hasonlóképpen <xref:microsoft.quantum.canon.bind> olyan műveleteket hoz létre, amelyek más műveletek sorozatot alkalmaznak.
Például a következők egyenértékűek:

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

Az iterációs minták kombinálásával ez különösen hasznos lehet:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Idősorba rendezett összeállítás ###

Továbbra is folytathatja a flow-szabályozást a részleges alkalmazás-és klasszikus függvények szempontjából, és a klasszikus folyamatok szabályozása szempontjából is elég kifinomult kvantum-fogalmakat modellez.
Ez az analógia pontosan az a felismerés, hogy az egységes operátorok pontosan megfelelnek a hívási műveletek mellékhatásának, így az egységes operátorok bármely más, az egységes operátorok által meghatározott bontása megfelel egy adott adat létrehozásának. olyan klasszikus alrutinok hívási sorrendje, amelyek az adott egységes operátorként való műveletre vonatkozó utasításokat bocsátanak ki.
Ebben a nézetben a `Bind` pontosan a mátrix termékének ábrázolását mutatja, mivel a `Bind([A, B])(target)` egyenértékű a `A(target); B(target);`, ami viszont a $BA $ értéknek megfelelő hívási sorrend.

Kifinomultabb példa a [Trotter – Suzuki bővítése](https://arxiv.org/abs/math-ph/0506007v1).
Ahogy azt az [adatstruktúrák](xref:microsoft.quantum.libraries.data-structures)dinamikus generátoros ábrázolási szakasza is tárgyalja, a Trotter – Suzuki terjeszkedés különösen hasznos módszert kínál a mátrixok exponenciális kifejezésére.
Például, ha a legalacsonyabb sorrendben alkalmazza a terjeszkedést, hogy minden operátornál $A $ és $B $, hogy $A = A ^ \dagger $ és $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i A t/n) \exp (i B t/n ) \right) ^ n.
\end{align}, ez azt mondja, hogy a $A + B $ alatti állapotot hozzávetőlegesen $A $ és $B $ alatt fejlesztjük.
Ha a $A $ alatt lévő evolúciót jelöli egy `A : (Double, Qubit[]) => Unit`, amely a következőt alkalmazza: $e ^ {i t A} $, akkor a Trotter – a Suzuki bővítése a hívási folyamatok átrendezése szempontjából egyértelművé válik.
Konkrétan, egy olyan művelet `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl`, amely `A = U(0, _, _)` és `B = U(1, _, _)`egy olyan új műveletet határozhat meg, amely az űrlap `U` $t

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Ezen a ponton most már a Trotter – Suzuki kiterjesztésre is hivatkozhatunk, *anélkül, hogy a kvantum-mechanikara*lenne szükség.
A bővítés gyakorlatilag egy nagyon különleges iterációs minta, amelyet a $ \eqref{EQ: Trotter-Suzuki-0} $ alapján motiválnak.
Ezt az iterációs mintát a <xref:microsoft.quantum.canon.decomposeintotimestepsca>implementálja:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

`DecomposeIntoTimeStepsCA` aláírása a Q #-ban közös mintát követ, ahol a tömbök vagy a menetben lévő elemeket olyan gyűjtemények képviselik, amelyek az első `Int` elemeknek a hosszát jelző rekordok jelölik.

## <a name="putting-it-together-controlling-operations"></a>Összerakva: vezérlési műveletek ##

Végül a Canon a `Controlled`-üzemben is felépíthető, ha további lehetőségeket biztosít a kvantum-műveletek feltételéhez.
Gyakori – különösen a Quantum aritmetika esetében – a \ket{0\cdots 0} $-től eltérő számítási alapon végrehajtott műveletek feltétele.
A fentiekben bemutatott vezérlési műveletek és függvények használatával egyetlen utasításban több általános kvantum-feltétel is megadható.
Ugorjunk a <xref:microsoft.quantum.canon.controlledonbitstring> működésének módjára (Sans Type Parameters), majd a darabokat egyenként fogjuk bontani.
Az első dolog, hogy meg kell határoznia egy olyan műveletet, amely valójában a vezérlő tetszőleges számítási alapon történő megvalósításának jelentős mértékű feloldását végzi.
Ezt a műveletet nem hívjuk közvetlenül, és így a név elejéhez hozzáadunk `_`, hogy azt jelezze, hogy egy másik szerkezet implementációja máshol.

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

Vegye figyelembe, hogy egy `Bool` tömbként jelölt bitet használunk, amellyel megadhatjuk, hogy milyen feltételt kívánunk alkalmazni az általunk megadott művelet `oracle`.
Mivel ez a művelet ténylegesen az alkalmazást közvetlenül végzi el, a vezérlő és a cél regisztereket is el kell végezni, mindkettőt `Qubit[]`ként ábrázoljuk.

Ezt követően vegye figyelembe, hogy a következő számítási állapotot kell megadnia: $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ a $ \vec{s} $ értékre való átalakításával a $ \ket{\vec{s}} $-t $ \ket{0\cdots 0} $ értékre alakíthatja át.
Különösen a $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.
Mivel $X ^ {\dagger} = X $, ez azt jelenti, hogy a $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.
Ezért alkalmazhatjuk $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, alkalmazza `Controlled oracle`, és alakítsa vissza a $ \vec{s} $ értékre.
Ez az építés pontosan `ApplyWith`, ezért az új művelet törzsét ennek megfelelően írjuk:

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Itt a <xref:microsoft.quantum.canon.applypaulifrombitstring> alkalmazta a $P $ használatára, részlegesen alkalmazva a célt a `ApplyWith`használatával való használatra.
Vegye figyelembe azonban, hogy a *vezérlő* regisztrációját át kell alakítani a kívánt űrlapra, ezért részben alkalmazzuk a *cél*belső műveletét `(Controlled oracle)`.
Ezzel a `ApplyWith` úgy viselkedik, hogy a vezérlési regisztert $P $, pontosan a kívánt módon regisztrálja.

Ezen a ponton megtehetjük, de valahogy nem teljesül, hogy az új művelet nem "érzi", mint a `Controlled`-felhasználó alkalmazás alkalmazása.
Így az új vezérlési folyamat fogalmának meghatározása egy olyan függvény megírásával történik, amely az Oracle felügyeletét végzi, és új műveletet ad vissza.
Így úgy tűnik, hogy az új függvény nagyon hasonlít a `Controlled`ra, és bemutatjuk, hogy könnyen definiáljuk a Q # és a Canon együttes használatával a hatékony új vezérlési folyamat szerkezetét:

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
