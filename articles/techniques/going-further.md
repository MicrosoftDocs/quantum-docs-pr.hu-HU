---
title: 'Továbbiak – Q # technikák | Microsoft Docs'
description: 'Továbbiak – Q # technikák'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 41713827a93d2cc97e198fa4ad377012c846cf8b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036236"
---
# <a name="going-further"></a>Folytatás #

Most, hogy megismerte, hogyan írhat érdekes kvantum-programokat a Q #-ban, ez a szakasz továbbra is bevezet néhány fejlettebb témakört, amely hasznosnak bizonyulhat.


## <a name="generic-operations-and-functions"></a>Általános műveletek és függvények ##

> [!TIP]
> Ez a szakasz azt feltételezi, hogy alapszintű ismerettel rendelkezik az [általános C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), az [általános F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ a sablonok](https://docs.microsoft.com/cpp/cpp/templates-cpp)és a más nyelveken való metaprogramming hasonló megközelítésekben.

Számos olyan függvény és művelet, amelyet érdemes lehet meghatározni, valójában nem támaszkodik a bemenetek típusaira, hanem csak egy másik függvény vagy művelet segítségével implicit módon használják a saját típusait.
Tegyük fel például, hogy a *Térkép* fogalma számos funkcionális nyelvhez közös. az adott függvény $f (x) $ és Values $\{x_1, x_2, \dots, x_n\}$, a Map egy új gyűjteményt ad vissza,\{f (x_1), f (x_2), \dots, f (x_n)\}$.
Ha ezt a Q #-ban szeretné megvalósítani, kihasználhatjuk, hogy a függvények első osztályúak legyenek.
Tegyük fel, hogy egy gyors példát mutatunk a `Map`ra, ★ helyőrzőként használva, hogy milyen típusokra van szükségünk.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vegye figyelembe, hogy ez a függvény ugyanúgy néz ki, mint amit a tényleges típusok helyettesítenek.
Az egész számokból a Paulis-ra történő leképezések például a lebegőpontos számok és a karakterláncok közötti térképre hasonlítanak.

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Elvileg megírhatjuk a `Map` egy verzióját minden olyan típushoz, amelynél találkozhatunk, de ez számos problémát jelent.
Ha például hibát talál a `Map`ban, akkor biztosítani kell, hogy a javítás a `Map`összes verziójában egységesen legyen alkalmazva.
Továbbá, ha új rekordot vagy UDT hozunk létre, most új `Map` is létre kell majd lépnie az új típussal együtt.
Ez egy kis mennyiségű ilyen funkció esetében több és több olyan funkció összegyűjtése, mint a `Map`, az új típusok bevezetésének díja aránytalanul nagy lesz a meglehetősen rövid sorrendben.

A nehézségek nagy része azonban azt eredményezi, hogy a fordító nem kapott olyan információt, amely a `Map` különböző verzióival kapcsolatos információk felismeréséhez szükséges.
Gyakorlatilag azt szeretnénk, hogy a fordító a Q # *types* és a q # függvények esetében is kezelje a `Map`.
Ezt a fogalmat úgy kell megfogalmazni, hogy a functions és a Operations függvények *Type paramétereket*, valamint a szokásos rekord paramétereit is használják.
A fenti példákban azt szeretnénk, hogy a `Map` úgy gondolja, hogy az első esetben `Int, Pauli`, és a második esetben `Double, String`.
A legtöbb esetben ezek a típusú paraméterek a szokásos típusokként használhatók: paraméterek típusú értékeket használunk a tömbök és rekordok, a függvények és a műveletek hívásához, valamint a szokásos vagy változtatható változókhoz való hozzárendeléshez.

> [!NOTE]
> A közvetett függőség legszélsőségesebb esete a qubits, ahol a Q # program nem hivatkozhat közvetlenül a `Qubit` típusának struktúrájára, de ezeket a típusokat más műveletekre és funkciókra **kell** átadnia.

Ha visszatér a fenti példához, láthatjuk, hogy a Type paraméterrel `Map` van szükségünk, az egyik pedig az, hogy a bemenet `fn`, a másik pedig a `fn`kimenetét jelképezi.
A Q # utasításban ezt a szögletes zárójelek (`<>`azaz a brakets $ \braket{}$!) hozzáadása után kell megírni a deklarációjában szereplő függvények vagy műveletek neve után, valamint az egyes típusparaméter-paraméterek listázásával.
Az egyes típusparaméter-paraméterek nevének egy Tick `'`-vel kell kezdődnie, ami azt jelzi, hogy ez egy típusparaméter, nem pedig egy egyszerű típus (más néven *konkrét* típus).
A `Map`ezért a következőt írjuk:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vegye figyelembe, hogy a `Map<'Input, 'Output>` definíciója rendkívül hasonlít a korábban megírt verziókhoz.
Az egyetlen különbség, hogy kifejezetten tájékoztatta a fordítót arról, hogy `Map` nem függ közvetlenül attól, hogy milyen `'Input` és `'Output`, de két típust is használ, ha azokat közvetett módon `fn`on keresztül használja.
Ha már definiálta `Map<'Input, 'Output>` ilyen módon, meghívhatjuk, mintha egy szokványos függvény lenne:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Az általános függvények és műveletek írása egy olyan hely, ahol a "rekord-in rekord kijelentkezése" nagyon hasznos módszer a Q # függvények és műveletek gondolkodására.
> Mivel minden függvény pontosan egy bemenetet vesz fel, és pontosan egy kimenetet ad vissza, a `'T -> 'U` típusú bemenetek *bármilyen* Q # függvénynek felelnek meg.
> Hasonlóképpen, minden művelet átadható egy `'T => 'U`típusú bemenetnek.

Második példaként vegye figyelembe, hogy milyen kihívással kell elírnia egy olyan függvényt, amely két másik függvény összeállítását adja vissza:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Itt pontosan meg kell határozni, hogy milyen `A`, `B`és `C`, ezért szigorúan korlátozza az új `Compose` funkció segédprogramját.
Miután az összes, `Compose` csak `A`tól, `B`tól és `C`tól függ `innerFn` és `outerFn`*használatával* .
Alternatív megoldásként hozzáadhatunk olyan típusú paramétereket `Compose`, amelyek azt jelzik, hogy *bármely* `A`, `B`és `C`esetében működik, feltéve, hogy ezek a paraméterek megfelelnek a `innerFn` és `outerFn`által vártnak:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

A Q # standard kódtárak számos ilyen típusú paraméterrel rendelkező műveletet és funkciót biztosítanak, hogy a magasabb rendű vezérlési folyamat könnyebben kifejezhető legyen.
Ezeket a [Q # standard Library útmutatóban](xref:microsoft.quantum.libraries.standard.intro)tovább tárgyaljuk.

## <a name="borrowing-qubits"></a>Hitelfelvételi qubits ##

A hitelfelvételi mechanizmus lehetővé teszi az olyan qubits kiosztását, amelyek felhasználhatók a kiszámítások során felmerülő területként. Ezek a qubits általában nem tiszta állapotban vannak, azaz nem feltétlenül inicializálva vannak olyan ismert állapotokban, mint például a $ \ket{0}$. Az egyik a "piszkos" qubits is beszél, mert az állapotuk ismeretlen, és a kvantum-számítógép memóriájának más részeivel is összekeverhető. A piszkos qubits ismert használati esetei közül a több vezérelt CNEM-kapuk olyan implementációi, amelyek csak nagyon kevés qubits és a növekményes implementációt igénylik.

A Canon olyan példákat tartalmaz, amelyek a `borrowing` kulcsszót használják, például az alább meghatározott függvényt `MultiControlledXBorrow`.
Ha `controls` azt a vezérlő qubits jelöli, amelyet egy `X` művelethez kell hozzáadnia, akkor ez a megvalósítás teljes `Length(controls)-2` sok piszkos ancillas fog hozzáadni.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Vegye figyelembe, hogy a `With` combinator széles körű használata---a adjoint támogató műveletekre alkalmazható, például `WithA`---, amely a megfelelő programozási stílust eredményezi, mivel a vezérlést a `With`t érintő struktúrákhoz adja hozzá. További Megjegyzés: a művelet `body`án kívül a művelet `controlled` törzsének megvalósítását explicit módon adták meg, ahelyett, hogy egy `controlled auto` utasításhoz folyamodnak. Ennek az az oka, hogy tisztában vagyunk az áramkör struktúrájával, így egyszerűen hozzáadhat további vezérlőket, amelyek hasznosak a vezérlés hozzáadásához a `body`minden egyes kapuján. 

Ez a kód egy másik Canon-függvénnyel hasonlítható össze, `MultiControlledXClean`, amely ugyanazt a célt fogja elérni, mint egy szorzásra vezérelt `X` művelet megvalósítását, amely azonban több tiszta qubits használ a `using` mechanizmus használatával. 
