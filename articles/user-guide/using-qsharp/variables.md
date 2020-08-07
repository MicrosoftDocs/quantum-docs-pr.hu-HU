---
title: Változók a-benQ#
description: Kitöltés leírása
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: 00af0989cd5a1f9ccc7d9f2545acd0d256bc7eb9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867845"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="ba14b-103">Változók a-benQ#</span><span class="sxs-lookup"><span data-stu-id="ba14b-103">Variables in Q#</span></span>

<span data-ttu-id="ba14b-104">Q#megkülönbözteti a változókat és a nem módosítható szimbólumokat, illetve a kifejezésekhez hozzárendelt vagy hozzájuk rendelt *változókat*.</span><span class="sxs-lookup"><span data-stu-id="ba14b-104">Q# distinguishes between mutable and immutable symbols, or *variables*, which are bound/assigned to expressions.</span></span>
<span data-ttu-id="ba14b-105">Általánosságban a nem módosítható szimbólumok használata javasolt, mivel lehetővé teszi, hogy a fordító több optimalizációt végezzen.</span><span class="sxs-lookup"><span data-stu-id="ba14b-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="ba14b-106">A kötés bal oldali oldala egy szimbólum és egy kifejezés jobb oldalán áll.</span><span class="sxs-lookup"><span data-stu-id="ba14b-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="ba14b-107">Megváltoztathatatlan változók</span><span class="sxs-lookup"><span data-stu-id="ba14b-107">Immutable Variables</span></span>

<span data-ttu-id="ba14b-108">A kulcsszó használatával bármilyen típusú értéket hozzárendelhet Q# egy változóhoz egy műveleten vagy függvényen belüli újrafelhasználáshoz `let` .</span><span class="sxs-lookup"><span data-stu-id="ba14b-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="ba14b-109">Egy nem módosítható kötés a kulcsszóból `let` , majd egy szimbólum vagy egy szimbólum, egy egyenlőségjel, egy egyenlőségjelet, egy kifejezés, amely `=` a szimbólum (oka) t és egy lezáró pontosvesszőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ba14b-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="ba14b-110">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="ba14b-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="ba14b-111">Ez a Pauli-operátorok egy adott tömbjét rendeli hozzá a változó nevéhez (vagy "szimbólum") `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="ba14b-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="ba14b-112">Az előző példában nem kell explicit módon megadnia az új változó típusát, mivel az utasítás jobb oldalán lévő kifejezés nem `let` egyértelmű, és a fordító kikövetkezteti a megfelelő típust.</span><span class="sxs-lookup"><span data-stu-id="ba14b-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="ba14b-113">A használatával definiált változók `let` nem *változtathatók*meg, ami azt jelenti, hogy a meghatározása után a továbbiakban nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="ba14b-113">Variables defined using `let` are *immutable*, meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="ba14b-114">Ez számos hasznos optimalizálást tesz lehetővé, többek között a klasszikus logika optimalizálását, amely a változókat a művelet változatának átrendezésére fogja alkalmazni `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="ba14b-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="ba14b-115">Változtatható változók</span><span class="sxs-lookup"><span data-stu-id="ba14b-115">Mutable Variables</span></span>

<span data-ttu-id="ba14b-116">Egy változónak a használatával való létrehozásának alternatívájaként `let` a `mutable` kulcsszó egy változtatható változót hoz létre, amely a kulcsszóval való első létrehozás után újrakötésre *képes* `set` .</span><span class="sxs-lookup"><span data-stu-id="ba14b-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="ba14b-117">Egy utasítás részeként deklarált és kötött szimbólumokat a `mutable` kód későbbi részében egy másik értékre lehet visszakötni.</span><span class="sxs-lookup"><span data-stu-id="ba14b-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="ba14b-118">Ha egy szimbólum később van kötve a kódban, a típusa nem változik, és az újonnan kötött értéknek kompatibilisnek kell lennie az adott típussal.</span><span class="sxs-lookup"><span data-stu-id="ba14b-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="ba14b-119">Változtatható szimbólumok újrakötése</span><span class="sxs-lookup"><span data-stu-id="ba14b-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="ba14b-120">Egy megváltoztathatatlan változót egy utasítás használatával lehet újra kötni `set` .</span><span class="sxs-lookup"><span data-stu-id="ba14b-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="ba14b-121">Egy ilyen újrakötés a kulcsszóból, egy szimbólum vagy egy szimbólum, egy egyenlőségjelet, egy `set` egyenlőségjel, egy kifejezés, amely a `=` szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.</span><span class="sxs-lookup"><span data-stu-id="ba14b-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="ba14b-122">Az alábbiakban néhány példát talál az újrakötési utasításokra vonatkozó eljárásokra.</span><span class="sxs-lookup"><span data-stu-id="ba14b-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="ba14b-123">Utasítások alkalmazása és újbóli társítása</span><span class="sxs-lookup"><span data-stu-id="ba14b-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="ba14b-124">Egy adott típusú `set` utasítás, az *Apply-and-reassign* utasítás kényelmes módot biztosít az Összefűzésre, ha a jobb oldal egy bináris operátor alkalmazásából áll, és az eredmény az operátorhoz a bal argumentumhoz lesz kötve.</span><span class="sxs-lookup"><span data-stu-id="ba14b-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="ba14b-125">Például:</span><span class="sxs-lookup"><span data-stu-id="ba14b-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="ba14b-126">növeli a számláló értékét a `counter` hurok minden egyes iterációjában `for` .</span><span class="sxs-lookup"><span data-stu-id="ba14b-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="ba14b-127">Az előző kód egyenértékű a következővel</span><span class="sxs-lookup"><span data-stu-id="ba14b-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="ba14b-128">Hasonló utasítások érhetők el minden olyan bináris operátor esetében, amelyben a bal oldali oldal típusa megegyezik a kifejezés típusával.</span><span class="sxs-lookup"><span data-stu-id="ba14b-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="ba14b-129">Ezek az utasítások az értékek összegyűjtésének kényelmes módját biztosítják.</span><span class="sxs-lookup"><span data-stu-id="ba14b-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="ba14b-130">Tegyük fel például, hogy `qubits` a qubits egy regisztrálása:</span><span class="sxs-lookup"><span data-stu-id="ba14b-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="ba14b-131">Utasítások frissítése és újbóli társítása</span><span class="sxs-lookup"><span data-stu-id="ba14b-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="ba14b-132">Hasonló Összefűzés található a jobb oldali [másolási és frissítési kifejezésekhez](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .</span><span class="sxs-lookup"><span data-stu-id="ba14b-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="ba14b-133">Ennek megfelelően a rendszer a felhasználó által definiált típusokban és a *tömbökben*lévő *megnevezett elemek* esetében is tartalmazza a *frissítés és az ismételt hozzárendelés* utasításait.</span><span class="sxs-lookup"><span data-stu-id="ba14b-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

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

<span data-ttu-id="ba14b-134">Tömbök esetén a [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Q# standard szintű függvénytárban a szükséges eszközök számos gyakran használt tömb inicializálási és manipulációs igényeihez szükségesek, így elkerülhető, hogy a tömb elemeit az első helyen frissítse.</span><span class="sxs-lookup"><span data-stu-id="ba14b-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="ba14b-135">Az Update-and-reassign utasítások szükség esetén alternatív megoldást nyújtanak:</span><span class="sxs-lookup"><span data-stu-id="ba14b-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="ba14b-136">A-ben megadott tár-eszközök használatával [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) például egyszerűen meghatározhat egy olyan függvényt, amely egy olyan típusú tömböt ad vissza, `Pauli` amelyben az indexben található elem `i` egy adott értéket vesz igénybe `Pauli` , és az összes többi bejegyzés az Identity ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="ba14b-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="ba14b-137">Íme egy ilyen függvény két definíciója, a második pedig kihasználja a rendelkezésére álló eszközöket.</span><span class="sxs-lookup"><span data-stu-id="ba14b-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="ba14b-138">Ahelyett, hogy megismétli a tömbben lévő egyes indexeket, és feltételesen Beállítja azt a `PauliI` vagy a megadott `pauli` `ConstantArray` értékre, a from paranccsal [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) létrehozhat egy tömb típusú tömböt `PauliI` , majd egyszerűen visszaállíthat egy olyan másolási és frissítési kifejezést, amelyben módosította az adott értéket az indexnél `location` :</span><span class="sxs-lookup"><span data-stu-id="ba14b-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="ba14b-139">Rekord kiépítése</span><span class="sxs-lookup"><span data-stu-id="ba14b-139">Tuple Deconstruction</span></span>

<span data-ttu-id="ba14b-140">Egyetlen változó hozzárendelésén kívül használhatja a `let` és a `mutable` kulcsszavakat is, vagy bármely más kötési összeállítást, például a `set` -t egy [rekord típusú](xref:microsoft.quantum.guide.types#tuple-types)tartalom kicsomagolásához.</span><span class="sxs-lookup"><span data-stu-id="ba14b-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="ba14b-141">Az űrlap kiosztása a rekord elemeinek *kiépítése* .</span><span class="sxs-lookup"><span data-stu-id="ba14b-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="ba14b-142">Ha a kötés jobb oldalán egy rekord található, akkor a hozzárendelés után visszaállíthatja ezt a rekordot.</span><span class="sxs-lookup"><span data-stu-id="ba14b-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="ba14b-143">Ezek a dekonstrukciók beágyazott rekordok is tartalmazhatnak, és a teljes vagy részleges kiépítés akkor érvényes, ha a jobb oldalon lévő rekord alakja kompatibilis a Symbol rekord alakzatával.</span><span class="sxs-lookup"><span data-stu-id="ba14b-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="ba14b-144">Például:</span><span class="sxs-lookup"><span data-stu-id="ba14b-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="ba14b-145">Kötési hatókörök</span><span class="sxs-lookup"><span data-stu-id="ba14b-145">Binding Scopes</span></span>

<span data-ttu-id="ba14b-146">Általánosságban elmondható, hogy a szimbólumokra vonatkozó kötések kikerülnek a hatókörből, és a blokk végén nem válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="ba14b-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="ba14b-147">A szabálynak két kivétele van:</span><span class="sxs-lookup"><span data-stu-id="ba14b-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="ba14b-148">Egy hurok hurok-változójának kötése `for` hatókörben van a for ciklus törzséhez, de a hurok vége után nem.</span><span class="sxs-lookup"><span data-stu-id="ba14b-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="ba14b-149">A ciklus mindhárom része `repeat` / `until` (a törzs, a teszt és a javítás) egyetlen hatókörként működik, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="ba14b-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="ba14b-150">Mindkét típusú hurok esetében a hurok továbbítása a saját hatókörében történik, így a korábbi pass-kötések nem érhetők el egy későbbi menetben.</span><span class="sxs-lookup"><span data-stu-id="ba14b-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="ba14b-151">További információ ezekről a hurkokkal kapcsolatban: [vezérlési folyamat](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="ba14b-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="ba14b-152">A belső blokkok öröklik a szimbólum-kötéseket a külső blokkokból.</span><span class="sxs-lookup"><span data-stu-id="ba14b-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="ba14b-153">Blokkon keresztül csak egyszer köthető szimbólum. nem engedélyezett olyan szimbólumot definiálni, amelynek a neve megegyezik a hatókörön belüli másik szimbólummal (nincs "árnyék").</span><span class="sxs-lookup"><span data-stu-id="ba14b-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="ba14b-154">A következő szakaszokban jogi információk szerepelnek:</span><span class="sxs-lookup"><span data-stu-id="ba14b-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="ba14b-155">és</span><span class="sxs-lookup"><span data-stu-id="ba14b-155">and</span></span>

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

<span data-ttu-id="ba14b-156">Ez azonban nem engedélyezett:</span><span class="sxs-lookup"><span data-stu-id="ba14b-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="ba14b-157">például:</span><span class="sxs-lookup"><span data-stu-id="ba14b-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="ba14b-158">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="ba14b-158">Next steps</span></span>

<span data-ttu-id="ba14b-159">Ismerje meg, hogyan [dolgozhat a qubits](xref:microsoft.quantum.guide.qubits) a alkalmazásban Q# .</span><span class="sxs-lookup"><span data-stu-id="ba14b-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>