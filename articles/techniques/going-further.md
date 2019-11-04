---
title: 'Q # technikák – továbbiak | Microsoft Docs'
description: 'Q # technikák – folytatás'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183301"
---
# <a name="going-further"></a><span data-ttu-id="0bd2a-103">Folytatás</span><span class="sxs-lookup"><span data-stu-id="0bd2a-103">Going Further</span></span> #

<span data-ttu-id="0bd2a-104">Most, hogy megismerte, hogyan írhat érdekes kvantum-programokat a Q #-ban, ez a szakasz továbbra is bevezet néhány fejlettebb témakört, amely hasznosnak bizonyulhat.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a><span data-ttu-id="0bd2a-105">Általános műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="0bd2a-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="0bd2a-106">Ez a szakasz azt feltételezi, hogy alapszintű ismerettel rendelkezik az [általános C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), az [általános F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ a sablonok](https://docs.microsoft.com/cpp/cpp/templates-cpp)és a más nyelveken való metaprogramming hasonló megközelítésekben.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="0bd2a-107">Számos olyan függvény és művelet, amelyet érdemes lehet meghatározni, valójában nem támaszkodik a bemenetek típusaira, hanem csak egy másik függvény vagy művelet segítségével implicit módon használják a saját típusait.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="0bd2a-108">Tegyük fel például, hogy a *Térkép* fogalma számos funkcionális nyelvhez közös. a függvény $f (x) $, a $\{x_1, a x_2, a \dots, a x_n\}$, a Map pedig egy új gyűjteményt ad vissza a $\{f (x_1), f (x_2), \dots, f (x_n)\}$ értékkel.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="0bd2a-109">Ha ezt a Q #-ban szeretné megvalósítani, kihasználhatjuk, hogy a függvények első osztályúak legyenek.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="0bd2a-110">Tegyük fel, hogy egy gyors példát mutatunk a `Map`ra, ★ helyőrzőként használva, hogy milyen típusokra van szükségünk.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="0bd2a-111">Vegye figyelembe, hogy ez a függvény ugyanúgy néz ki, mint amit a tényleges típusok helyettesítenek.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="0bd2a-112">Az egész számokból a Paulis-ra történő leképezések például a lebegőpontos számok és a karakterláncok közötti térképre hasonlítanak.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="0bd2a-113">Elvileg megírhatjuk a `Map` egy verzióját minden olyan típushoz, amelynél találkozhatunk, de ez számos problémát jelent.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="0bd2a-114">Ha például hibát talál a `Map`ban, akkor biztosítani kell, hogy a javítás a `Map`összes verziójában egységesen legyen alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="0bd2a-115">Továbbá, ha új rekordot vagy UDT hozunk létre, most új `Map` is létre kell majd lépnie az új típussal együtt.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="0bd2a-116">Ez egy kis mennyiségű ilyen funkció esetében több és több olyan funkció összegyűjtése, mint a `Map`, az új típusok bevezetésének díja aránytalanul nagy lesz a meglehetősen rövid sorrendben.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="0bd2a-117">A nehézségek nagy része azonban azt eredményezi, hogy a fordító nem kapott olyan információt, amely a `Map` különböző verzióival kapcsolatos információk felismeréséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="0bd2a-118">Gyakorlatilag azt szeretnénk, hogy a fordító a Q # *types* és a q # függvények esetében is kezelje a `Map`.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="0bd2a-119">Ezt a fogalmat úgy kell megfogalmazni, hogy a functions és a Operations függvények *Type paramétereket*, valamint a szokásos rekord paramétereit is használják.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="0bd2a-120">A fenti példákban azt szeretnénk, hogy a `Map` úgy gondolja, hogy az első esetben `Int, Pauli`, és a második esetben `Double, String`.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="0bd2a-121">A legtöbb esetben ezek a típusú paraméterek a szokásos típusokként használhatók: paraméterek típusú értékeket használunk a tömbök és rekordok, a függvények és a műveletek hívásához, valamint a szokásos vagy változtatható változókhoz való hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd2a-122">A közvetett függőség legszélsőségesebb esete a qubits, ahol a Q # program nem hivatkozhat közvetlenül a `Qubit` típusának struktúrájára, de ezeket a típusokat más műveletekre és funkciókra **kell** átadnia.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="0bd2a-123">Ha visszatér a fenti példához, láthatjuk, hogy a Type paraméterrel `Map` van szükségünk, az egyik pedig az, hogy a bemenet `fn`, a másik pedig a `fn`kimenetét jelképezi.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="0bd2a-124">A Q # utasításban ezt a szögletes zárójelek (`<>`azaz a brakets $ \braket{}$!) hozzáadása után kell megírni a deklarációjában szereplő függvények vagy műveletek neve után, valamint az egyes típusparaméter-paraméterek listázásával.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="0bd2a-125">Az egyes típusparaméter-paraméterek nevének egy Tick `'`-vel kell kezdődnie, ami azt jelzi, hogy ez egy típusparaméter, nem pedig egy egyszerű típus (más néven *konkrét* típus).</span><span class="sxs-lookup"><span data-stu-id="0bd2a-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="0bd2a-126">A `Map`ezért a következőt írjuk:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="0bd2a-127">Vegye figyelembe, hogy a `Map<'Input, 'Output>` definíciója rendkívül hasonlít a korábban megírt verziókhoz.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="0bd2a-128">Az egyetlen különbség, hogy kifejezetten tájékoztatta a fordítót arról, hogy `Map` nem függ közvetlenül attól, hogy milyen `'Input` és `'Output`, de két típust is használ, ha azokat közvetett módon `fn`on keresztül használja.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="0bd2a-129">Ha már definiálta `Map<'Input, 'Output>` ilyen módon, meghívhatjuk, mintha egy szokványos függvény lenne:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="0bd2a-130">Az általános függvények és műveletek írása egy olyan hely, ahol a "rekord-in rekord kijelentkezése" nagyon hasznos módszer a Q # függvények és műveletek gondolkodására.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="0bd2a-131">Mivel minden függvény pontosan egy bemenetet vesz fel, és pontosan egy kimenetet ad vissza, a `'T -> 'U` típusú bemenetek *bármilyen* Q # függvénynek felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="0bd2a-132">Hasonlóképpen, minden művelet átadható egy `'T => 'U`típusú bemenetnek.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="0bd2a-133">Második példaként vegye figyelembe, hogy milyen kihívással kell elírnia egy olyan függvényt, amely két másik függvény összeállítását adja vissza:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="0bd2a-134">Itt pontosan meg kell határozni, hogy milyen `A`, `B`és `C`, ezért szigorúan korlátozza az új `Compose` funkció segédprogramját.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="0bd2a-135">Miután az összes, `Compose` csak `A`tól, `B`tól és `C`tól függ `innerFn` és `outerFn`*használatával* .</span><span class="sxs-lookup"><span data-stu-id="0bd2a-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="0bd2a-136">Alternatív megoldásként hozzáadhatunk olyan típusú paramétereket `Compose`, amelyek azt jelzik, hogy *bármely* `A`, `B`és `C`esetében működik, feltéve, hogy ezek a paraméterek megegyeznek `innerFn` és `outerFn`által várttal. :</span><span class="sxs-lookup"><span data-stu-id="0bd2a-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="0bd2a-137">A Q # standard kódtárak számos ilyen típusú paraméterrel rendelkező műveletet és funkciót biztosítanak, hogy a magasabb rendű vezérlési folyamat könnyebben kifejezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="0bd2a-138">Ezeket a [Q # standard Library útmutatóban](xref:microsoft.quantum.libraries.standard.intro)tovább tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="0bd2a-139">Hitelfelvételi qubits</span><span class="sxs-lookup"><span data-stu-id="0bd2a-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="0bd2a-140">A hitelfelvételi mechanizmus lehetővé teszi az olyan qubits kiosztását, amelyek felhasználhatók a kiszámítások során felmerülő területként.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="0bd2a-141">Ezek a qubits általában nem tiszta állapotban vannak, azaz nem feltétlenül inicializálva vannak olyan ismert állapotokban, mint például a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="0bd2a-142">Az egyik a "piszkos" qubits is beszél, mert az állapotuk ismeretlen, és a kvantum-számítógép memóriájának más részeivel is összekeverhető.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="0bd2a-143">A piszkos qubits ismert használati esetei közül a több vezérelt CNEM-kapuk olyan implementációi, amelyek csak nagyon kevés qubits és a növekményes implementációt igénylik.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="0bd2a-144">A Canon olyan példákat tartalmaz, amelyek a `borrowing` kulcsszót használják, például az alább meghatározott függvényt `MultiControlledXBorrow`.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="0bd2a-145">Ha `controls` azt a vezérlő qubits jelöli, amelyet egy `X` művelethez kell hozzáadnia, akkor ez a megvalósítás teljes `Length(controls)-2` sok piszkos ancillas fog hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="0bd2a-146">Vegye figyelembe, hogy a `With` combinator széles körben használható---a adjoint támogató műveletekre alkalmazható, például `WithA`---, amely a megfelelő programozási stílust eredményezi, mivel a vezérlőt csak `With`t érintő struktúrákhoz adja hozzá. továbbítja a vezérlést a belső műveletnek.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="0bd2a-147">További Megjegyzés: a művelet `body`án kívül a művelet `controlled` törzsének megvalósítását explicit módon adták meg, ahelyett, hogy egy `controlled auto` utasításhoz folyamodnak.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="0bd2a-148">Ennek az az oka, hogy tisztában vagyunk az áramkör struktúrájával, így egyszerűen hozzáadhat további vezérlőket, amelyek hasznosak a vezérlés hozzáadásához a `body`minden egyes kapuján.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="0bd2a-149">Ez a kód egy másik Canon-függvénnyel hasonlítható össze, `MultiControlledXClean`, amely ugyanazt a célt fogja elérni, mint egy szorzásra vezérelt `X` művelet megvalósítását, amely azonban több tiszta qubits használ a `using` mechanizmus használatával.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
