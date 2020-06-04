---
title: 'Változók a Q-ban #'
description: Kitöltés leírása
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 456c05d4ca66a747e0cc514a30c6bbb33610f481
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327781"
---
# <a name="variables-in-q"></a><span data-ttu-id="dc463-103">Változók a Q-ban #</span><span class="sxs-lookup"><span data-stu-id="dc463-103">Variables in Q#</span></span>

<span data-ttu-id="dc463-104">A Q # különbséget tesz a változó és a nem módosítható szimbólumok, vagy a "változók" között, amelyek a kifejezésekhez vannak kötve/társítva.</span><span class="sxs-lookup"><span data-stu-id="dc463-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="dc463-105">Általánosságban a nem módosítható szimbólumok használata javasolt, mivel lehetővé teszi, hogy a fordító több optimalizációt végezzen.</span><span class="sxs-lookup"><span data-stu-id="dc463-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="dc463-106">A kötés bal oldali lapja egy szimbólumból álló rekordból és egy kifejezés jobb oldaláról áll.</span><span class="sxs-lookup"><span data-stu-id="dc463-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="dc463-107">Megváltoztathatatlan változók</span><span class="sxs-lookup"><span data-stu-id="dc463-107">Immutable Variables</span></span>

<span data-ttu-id="dc463-108">A Q # bármelyik típusának értéke hozzárendelhető egy változóhoz egy műveleten vagy függvényen belül a `let` kulcsszó használatával.</span><span class="sxs-lookup"><span data-stu-id="dc463-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="dc463-109">Egy nem módosítható kötés a kulcsszóból `let` , majd egy szimbólum vagy egy szimbólum, egy egyenlőségjel, egy egyenlőségjelet, egy kifejezés, amely `=` a szimbólum (oka) t és egy lezáró pontosvesszőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="dc463-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="dc463-110">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="dc463-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="dc463-111">Ez a Pauli-operátorok egy adott tömbjét rendeli hozzá a változó nevéhez (vagy "szimbólum") `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="dc463-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="dc463-112">Nem kell explicit módon megadnia az új változó típusát, mert az utasítás jobb oldalán lévő kifejezés nem `let` egyértelmű, és a típust a fordító következteti ki.</span><span class="sxs-lookup"><span data-stu-id="dc463-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="dc463-113">A használatával definiált változók nem `let` *változtathatók*meg, ami azt jelenti, hogy ha már definiálva van, akkor az már nem módosítható semmilyen módon.</span><span class="sxs-lookup"><span data-stu-id="dc463-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="dc463-114">Ez számos hasznos optimalizálást tesz lehetővé, beleértve a változókra alkalmazott klasszikus logika optimalizálását a `Adjoint` művelet változatának átrendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="dc463-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="dc463-115">Változtatható változók</span><span class="sxs-lookup"><span data-stu-id="dc463-115">Mutable Variables</span></span>

<span data-ttu-id="dc463-116">Egy változónak a használatával való létrehozásának alternatívájaként `let` a `mutable` kulcsszó egy változtatható változót hoz létre, *can* amely újra köthető, miután a kulcsszóval létrehozta azt `set` .</span><span class="sxs-lookup"><span data-stu-id="dc463-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="dc463-117">A deklarált és az utasítás részeként kötött szimbólumok `mutable` a kód későbbi részében más értékre is visszaköthetők.</span><span class="sxs-lookup"><span data-stu-id="dc463-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="dc463-118">Ha a kódban később egy szimbólum van kötve, a típusa nem változik, és az újonnan kötött értéknek kompatibilisnek kell lennie az adott típussal.</span><span class="sxs-lookup"><span data-stu-id="dc463-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="dc463-119">Változtatható szimbólumok újrakötése</span><span class="sxs-lookup"><span data-stu-id="dc463-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="dc463-120">Egy változtatható változót egy utasítás használatával lehet visszakötni `set` .</span><span class="sxs-lookup"><span data-stu-id="dc463-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="dc463-121">Egy ilyen újrakötés a kulcsszóból, egy szimbólum vagy egy szimbólum, egy egyenlőségjelet, egy `set` egyenlőségjel, egy kifejezés, amely a `=` szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.</span><span class="sxs-lookup"><span data-stu-id="dc463-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="dc463-122">Íme néhány lehetséges példa az újrakötési utasítási technikákra</span><span class="sxs-lookup"><span data-stu-id="dc463-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="dc463-123">Utasítások alkalmazása és újbóli társítása</span><span class="sxs-lookup"><span data-stu-id="dc463-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="dc463-124">Egy adott típusú `set` -utasításra hivatkozunk, mint az *alkalmazásra és az ismételt hozzárendelésre* vonatkozó utasítás, amely kényelmes megoldást kínál az Összefűzésre, ha a jobb oldalon egy bináris operátor alkalmazásából áll, és az eredmény a kezelőhöz a bal argumentumhoz lesz kötve.</span><span class="sxs-lookup"><span data-stu-id="dc463-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="dc463-125">Példa:</span><span class="sxs-lookup"><span data-stu-id="dc463-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="dc463-126">növeli a számláló értékét a `counter` hurok minden egyes iterációjában `for` .</span><span class="sxs-lookup"><span data-stu-id="dc463-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="dc463-127">A fenti kód egyenértékű a következővel</span><span class="sxs-lookup"><span data-stu-id="dc463-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="dc463-128">Hasonló utasítások érhetők el minden olyan bináris operátor esetében, amelyben a bal oldali oldal típusa megegyezik a kifejezés típusával.</span><span class="sxs-lookup"><span data-stu-id="dc463-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="dc463-129">Ez például egy kényelmes módszer az értékek összegyűjtéséhez.</span><span class="sxs-lookup"><span data-stu-id="dc463-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="dc463-130">Tegyük fel például, hogy `qubits` a qubits egy regsiter:</span><span class="sxs-lookup"><span data-stu-id="dc463-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="dc463-131">Utasítások frissítése és újbóli társítása</span><span class="sxs-lookup"><span data-stu-id="dc463-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="dc463-132">Hasonló Összefűzés található a jobb oldali [másolási és frissítési kifejezésekhez](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .</span><span class="sxs-lookup"><span data-stu-id="dc463-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="dc463-133">Ennek megfelelően a rendszer a felhasználó által definiált típusokban és a *tömbökben*lévő *megnevezett elemek* esetében is tartalmazza a *frissítés és az ismételt hozzárendelés* utasításait.</span><span class="sxs-lookup"><span data-stu-id="dc463-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="dc463-134">Tömbök esetén a [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) standard könyvtárakban számos gyakori tömb-inicializálási és-manipulációs igényt biztosítunk, így elkerülhető, hogy a tömb elemeit az első helyen frissítse.</span><span class="sxs-lookup"><span data-stu-id="dc463-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="dc463-135">Az Update-and-reassign utasítások szükség esetén alternatív megoldást nyújtanak:</span><span class="sxs-lookup"><span data-stu-id="dc463-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="dc463-136">A-ben megadott tár-eszközök használatával [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) például egyszerűen meghatározhat egy olyan függvényt, amely Paulis tömböt ad vissza, ahol a Pauli at indexben a `i` megadott érték és az összes többi bejegyzés az identitás.</span><span class="sxs-lookup"><span data-stu-id="dc463-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="dc463-137">Íme egy ilyen függvény két definíciója, a második pedig kihasználja a rendelkezésére álló eszközöket.</span><span class="sxs-lookup"><span data-stu-id="dc463-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="dc463-138">Ahelyett, hogy megismétli a tömbben lévő egyes indexeket, és feltételesen beállítja a `PauliI` vagy a `Pauli` rendszerre, ehelyett a `ConstantArray` következővel lehet [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) létrehozni egy tömböt `PauliI` :, majd egyszerűen egy másolási és frissítési kifejezést ad vissza, amelyben módosítottuk a különös értéket az indexnél `location`</span><span class="sxs-lookup"><span data-stu-id="dc463-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="dc463-139">Rekord kiépítése</span><span class="sxs-lookup"><span data-stu-id="dc463-139">Tuple Deconstruction</span></span>

<span data-ttu-id="dc463-140">Egyetlen változó kiosztása mellett a `let` és a `mutable` kulcsszavak---vagy valójában bármilyen más kötési szerkezet, például `set` (lásd alább)---is lehetővé teszi, hogy kicsomagolja a [rekord típusú](xref:microsoft.quantum.guide.types#tuple-types)tartalmat.</span><span class="sxs-lookup"><span data-stu-id="dc463-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="dc463-141">Az űrlap kiosztása a rekord elemeinek *kiépítése* .</span><span class="sxs-lookup"><span data-stu-id="dc463-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="dc463-142">Ha a kötés jobb oldalán egy rekord található, akkor a rekord a hozzárendelés után kiépíthető.</span><span class="sxs-lookup"><span data-stu-id="dc463-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="dc463-143">Ezek a dekonstrukciók beágyazott rekordok tartalmazhatnak, és a teljes vagy részleges kiépítés akkor érvényes, ha a jobb oldalon lévő rekord alakja kompatibilis a szimbólum rekordjának formájával.</span><span class="sxs-lookup"><span data-stu-id="dc463-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="dc463-144">Például:</span><span class="sxs-lookup"><span data-stu-id="dc463-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="dc463-145">Kötési hatókörök</span><span class="sxs-lookup"><span data-stu-id="dc463-145">Binding Scopes</span></span>

<span data-ttu-id="dc463-146">Általánosságban elmondható, hogy a szimbólumokra vonatkozó kötések kikerülnek a hatókörből, és a blokk végén nem válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="dc463-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="dc463-147">A szabálynak két kivétele van:</span><span class="sxs-lookup"><span data-stu-id="dc463-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="dc463-148">Egy hurok hurok-változójának kötése `for` hatókörben van a for ciklus törzséhez, de a hurok vége után nem.</span><span class="sxs-lookup"><span data-stu-id="dc463-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="dc463-149">A `repeat` / `until` hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="dc463-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="dc463-150">Mindkét típusú hurok esetében a hurok továbbítása a saját hatókörében történik, így a korábbi pass-kötések nem érhetők el egy későbbi menetben.</span><span class="sxs-lookup"><span data-stu-id="dc463-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="dc463-151">Ezekről a hurkok részletei a [vezérlés folyamatában](xref:microsoft.quantum.guide.controlflow)találhatók.</span><span class="sxs-lookup"><span data-stu-id="dc463-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="dc463-152">A külső blokkokból származó szimbólum-kötéseket belső blokkok öröklik.</span><span class="sxs-lookup"><span data-stu-id="dc463-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="dc463-153">Egy szimbólum csak egyszer köthető egy blokkban; nem engedélyezett olyan szimbólumot definiálni, amelynek a neve megegyezik a hatókörön belüli másik szimbólummal (nincs "árnyék").</span><span class="sxs-lookup"><span data-stu-id="dc463-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="dc463-154">A következő szakaszokban lenne jogi:</span><span class="sxs-lookup"><span data-stu-id="dc463-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="dc463-155">és</span><span class="sxs-lookup"><span data-stu-id="dc463-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="dc463-156">Ez azonban nem engedélyezett:</span><span class="sxs-lookup"><span data-stu-id="dc463-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="dc463-157">például:</span><span class="sxs-lookup"><span data-stu-id="dc463-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="dc463-158">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="dc463-158">Next steps</span></span>

<span data-ttu-id="dc463-159">További információ a [qubits](xref:microsoft.quantum.guide.qubits) használatáról a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="dc463-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>