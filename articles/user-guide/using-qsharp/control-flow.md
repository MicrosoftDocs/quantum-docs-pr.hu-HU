---
title: 'Vezérlési folyamat a Q-ban #'
description: Hurkok, feltételesség stb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 0cf62a128170bd0c28ff77f00fc23414567b1ea4
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415303"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="effcd-103">Vezérlési folyamat a Q-ban #</span><span class="sxs-lookup"><span data-stu-id="effcd-103">Control flow in Q#</span></span>

<span data-ttu-id="effcd-104">Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan más gyakori klasszikus nyelvekhez.</span><span class="sxs-lookup"><span data-stu-id="effcd-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="effcd-105">A vezérlés folyamatát azonban három különböző módon módosíthatja:</span><span class="sxs-lookup"><span data-stu-id="effcd-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="effcd-106">`if`nyilatkozatok</span><span class="sxs-lookup"><span data-stu-id="effcd-106">`if` statements</span></span>
* <span data-ttu-id="effcd-107">`for`hurkok</span><span class="sxs-lookup"><span data-stu-id="effcd-107">`for` loops</span></span>
* <span data-ttu-id="effcd-108">`repeat-until-success`hurkok</span><span class="sxs-lookup"><span data-stu-id="effcd-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="effcd-109">A `if` és a `for` vezérlési folyamat szerkezetét a klasszikus programozási nyelvek többsége ismeri.</span><span class="sxs-lookup"><span data-stu-id="effcd-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="effcd-110">[`Repeat-until-success`](#repeat-until-success-loop)a hurkokat a cikk későbbi részében tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="effcd-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="effcd-111">Fontos, hogy `for` a hurkok és `if` utasítások olyan műveletekben használhatók, amelyekben automatikusan létrejönnek a [specializációk](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="effcd-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="effcd-112">Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.</span><span class="sxs-lookup"><span data-stu-id="effcd-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="effcd-113">Ez a művelet a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat.</span><span class="sxs-lookup"><span data-stu-id="effcd-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="effcd-114">If, máskülönben</span><span class="sxs-lookup"><span data-stu-id="effcd-114">If, Else-if, Else</span></span>

<span data-ttu-id="effcd-115">Az `if` utasítás támogatja a feltételes végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="effcd-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="effcd-116">A kulcsszó `if` , a logikai kifejezés zárójelek között, valamint egy utasítás blokkja (az _akkori_ blokk).</span><span class="sxs-lookup"><span data-stu-id="effcd-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="effcd-117">Opcionálisan tetszőleges számú Else-if záradékot követhet, amelyek mindegyike egy kulcsszóból `elif` , egy zárójelben található logikai kifejezésből és egy utasításból álló blokkból áll (a _másik, ha_ blokk).</span><span class="sxs-lookup"><span data-stu-id="effcd-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="effcd-118">Végül az utasítás opcionálisan végződhet más záradékkal is, amely a kulcsszót, `else` majd egy másik utasítás blokkját (az _Else_ blokkot) tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="effcd-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="effcd-119">A rendszer `if` kiértékeli a feltételt, és ha az *then* értéke *igaz*, a rendszer futtatja a letiltást.</span><span class="sxs-lookup"><span data-stu-id="effcd-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="effcd-120">Ha a feltétel *hamis*, akkor az első más-if feltétel kiértékelése megtörténik. Ha ez igaz, akkor az *Else-if* blokk fut.</span><span class="sxs-lookup"><span data-stu-id="effcd-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="effcd-121">Ellenkező esetben a második, ha a blokk kiértékeli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.</span><span class="sxs-lookup"><span data-stu-id="effcd-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="effcd-122">Ha az eredeti *IF* feltétel és az összes Else-if záradék *Hamis értéket*ad vissza, akkor a *többi* blokk is fut, ha meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="effcd-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="effcd-123">Vegye figyelembe, hogy bármelyik blokk fut, a saját hatókörén belül fut.</span><span class="sxs-lookup"><span data-stu-id="effcd-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="effcd-124">`if`Az egy, `elif` , vagy blokkon belül végrehajtott kötések `else` nem láthatók a blokk vége után.</span><span class="sxs-lookup"><span data-stu-id="effcd-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="effcd-125">Példa:</span><span class="sxs-lookup"><span data-stu-id="effcd-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="effcd-126">vagy</span><span class="sxs-lookup"><span data-stu-id="effcd-126">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="effcd-127">Hurok esetén</span><span class="sxs-lookup"><span data-stu-id="effcd-127">For loop</span></span>

<span data-ttu-id="effcd-128">Az `for` utasítás támogatja az ismétlést egész tartományon vagy tömbön.</span><span class="sxs-lookup"><span data-stu-id="effcd-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="effcd-129">Az utasítás a kulcsszót `for` , majd egy szimbólum vagy egy szimbólumot, a kulcsszót `in` és egy Type `Range` vagy Array kifejezést, valamint az összes zárójelet és egy utasítás blokkját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="effcd-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="effcd-130">Az utasítás blokkja (a hurok törzse) ismétlődően fut, és a megadott szimbólummal (a hurok változóval) a tartomány vagy tömb minden értékéhez kötve van.</span><span class="sxs-lookup"><span data-stu-id="effcd-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="effcd-131">Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem fut.</span><span class="sxs-lookup"><span data-stu-id="effcd-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="effcd-132">A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és a hurok végrehajtása közben nem változik.</span><span class="sxs-lookup"><span data-stu-id="effcd-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="effcd-133">A hurok változó a hurok törzsének minden bejáratához van kötve, és a törzs végén van kötve.</span><span class="sxs-lookup"><span data-stu-id="effcd-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="effcd-134">A Loop változó nem kötődik a for ciklus befejeződése után.</span><span class="sxs-lookup"><span data-stu-id="effcd-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="effcd-135">A hurok változó kötése nem változtatható meg, és ugyanazokat a szabályokat követi, mint a többi változó kötése.</span><span class="sxs-lookup"><span data-stu-id="effcd-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="effcd-136">Ezekben a példákban `qubits` a qubits (pl. típus) regisztrálása `Qubit[]` ,</span><span class="sxs-lookup"><span data-stu-id="effcd-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="effcd-137">Vegye figyelembe, hogy a végén a számtani-SHIFT-Left bináris operátort használták `<<<` .</span><span class="sxs-lookup"><span data-stu-id="effcd-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="effcd-138">További információ: [numerikus kifejezések](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="effcd-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="effcd-139">REPEAT-ig-Success hurok</span><span class="sxs-lookup"><span data-stu-id="effcd-139">Repeat-until-success loop</span></span>

<span data-ttu-id="effcd-140">A Q # nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.</span><span class="sxs-lookup"><span data-stu-id="effcd-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="effcd-141">Ez a funkció lehetővé teszi, hogy a hatékony valószínűséggel rendelkező minialkalmazások megvalósításával csökkentse a unitaries megvalósításához szükséges számítási költségeket.</span><span class="sxs-lookup"><span data-stu-id="effcd-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="effcd-142">Ilyenek például a Q #-ban a *REPEAT-ig-Success* (RUS) minták.</span><span class="sxs-lookup"><span data-stu-id="effcd-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="effcd-143">Ezek az RUS-minták olyan valószínűségi programok, amelyek az alapvető kapuk szempontjából *várhatóan* alacsony költségeket mutatnak; a felmerülő költségek a tényleges futtatástól és a több lehetséges ág közötti összekapcsolástól függenek.</span><span class="sxs-lookup"><span data-stu-id="effcd-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="effcd-144">A REPEAT-ig-Success (RUS) minták megkönnyítése érdekében a Q # támogatja a szerkezeteket</span><span class="sxs-lookup"><span data-stu-id="effcd-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="effcd-145">ahol a `expression` bármely érvényes kifejezés, amely egy típusú értékre van kiértékelve `Bool` .</span><span class="sxs-lookup"><span data-stu-id="effcd-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="effcd-146">A hurok törzse fut, majd kiértékeli a feltételt.</span><span class="sxs-lookup"><span data-stu-id="effcd-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="effcd-147">Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a javítás lefut, és az utasítás ismét lefut, a hurok törzsének megfelelően.</span><span class="sxs-lookup"><span data-stu-id="effcd-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="effcd-148">Egy RUS-hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve az *egyes ismétlődésekhez*, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="effcd-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="effcd-149">A javítás végrehajtásának befejezése azonban befejezi a utasítás hatókörét, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődések során.</span><span class="sxs-lookup"><span data-stu-id="effcd-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="effcd-150">Az utasítás továbbá `fixup` gyakran hasznos, de nem mindig szükséges.</span><span class="sxs-lookup"><span data-stu-id="effcd-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="effcd-151">Abban az esetben, ha nincs rá szükség, a szerkezet</span><span class="sxs-lookup"><span data-stu-id="effcd-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="effcd-152">érvényes RUS-minta is.</span><span class="sxs-lookup"><span data-stu-id="effcd-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="effcd-153">További példákért és részletekért tekintse meg a jelen cikk [REPEAT-amíg-sikeres példáit](#repeat-until-success-examples) .</span><span class="sxs-lookup"><span data-stu-id="effcd-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="effcd-154">Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát.</span><span class="sxs-lookup"><span data-stu-id="effcd-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="effcd-155">Használja *a* hurkokat a függvények megfelelő funkcióinak megadásához.</span><span class="sxs-lookup"><span data-stu-id="effcd-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="effcd-156">Ciklus közben</span><span class="sxs-lookup"><span data-stu-id="effcd-156">While loop</span></span>

<span data-ttu-id="effcd-157">A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="effcd-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="effcd-158">Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi összeállítás Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="effcd-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="effcd-159">Azonban az olyan hurkok, amelyek egy adott feltétel alapján törnek át, és amelynek végrehajtási hosszát a fordítási időben nem ismeri, a rendszer a kvantum-futtatókörnyezetben különösen körültekintően kezeli.</span><span class="sxs-lookup"><span data-stu-id="effcd-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="effcd-160">Azonban a függvényeken belüli használatuk nem problémamentes, mivel ezek a hurkok csak a hagyományos (nem Quantum) hardveren futó kódokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="effcd-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="effcd-161">A Q # lehetővé teszi, hogy a csak a functions-ben lévő hurkokat használja.</span><span class="sxs-lookup"><span data-stu-id="effcd-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="effcd-162">Egy `while` utasítás a kulcsszóból `while` , egy logikai kifejezésből áll zárójelben, és egy utasítás blokkot.</span><span class="sxs-lookup"><span data-stu-id="effcd-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="effcd-163">Az utasítás blokkja (a hurok törzse) mindaddig fut, amíg a feltétel kiértékelése megtörténik `true` .</span><span class="sxs-lookup"><span data-stu-id="effcd-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="effcd-164">Visszatérési utasítás</span><span class="sxs-lookup"><span data-stu-id="effcd-164">Return Statement</span></span>

<span data-ttu-id="effcd-165">A Return utasítás egy művelet vagy függvény futtatását, és egy értéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="effcd-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="effcd-166">Ez a kulcsszóból áll `return` , majd a megfelelő típusú kifejezéssel, valamint egy megszakítási pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="effcd-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="effcd-167">Példa:</span><span class="sxs-lookup"><span data-stu-id="effcd-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="effcd-168">vagy</span><span class="sxs-lookup"><span data-stu-id="effcd-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="effcd-169">Egy üres rekordot visszaadó hívható, `()` nem igényel visszatérési utasítást.</span><span class="sxs-lookup"><span data-stu-id="effcd-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="effcd-170">A művelet vagy a függvény korai kilépésének megadásához használja a következőt: `return ();` .</span><span class="sxs-lookup"><span data-stu-id="effcd-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="effcd-171">A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.</span><span class="sxs-lookup"><span data-stu-id="effcd-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="effcd-172">Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.</span><span class="sxs-lookup"><span data-stu-id="effcd-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="effcd-173">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="effcd-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="effcd-174">Sikertelen utasítás</span><span class="sxs-lookup"><span data-stu-id="effcd-174">Fail statement</span></span>

<span data-ttu-id="effcd-175">A Fail utasítás egy művelet futtatásával végződik, és hibaértéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="effcd-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="effcd-176">A kulcsszót `fail` , majd egy karakterláncot és egy megszakítást tartalmazó pontosvesszőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="effcd-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="effcd-177">Az utasítás a klasszikus illesztőprogram sztringjét adja vissza hibaüzenetként.</span><span class="sxs-lookup"><span data-stu-id="effcd-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="effcd-178">A műveleteken belüli sikertelen utasítások száma nincs korlátozva.</span><span class="sxs-lookup"><span data-stu-id="effcd-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="effcd-179">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="effcd-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="effcd-180">Példa:</span><span class="sxs-lookup"><span data-stu-id="effcd-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="effcd-181">vagy [interpolált karakterláncok](xref:microsoft.quantum.guide.expressions#interpolated-strings)használatával</span><span class="sxs-lookup"><span data-stu-id="effcd-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="effcd-182">Ismételt sikeres példák</span><span class="sxs-lookup"><span data-stu-id="effcd-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="effcd-183">RUS-minta egyetlen qubit elforgatásához egy irracionális tengelyen</span><span class="sxs-lookup"><span data-stu-id="effcd-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="effcd-184">Egy tipikus használati eset esetében a következő Q # művelet végrehajt egy, az/\sqrt $ (I + 2i Z) és a Bloch gömb közötti irracionális tengely körüli rotációt {5} .</span><span class="sxs-lookup"><span data-stu-id="effcd-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="effcd-185">A megvalósítás egy ismert RUS mintát használ:</span><span class="sxs-lookup"><span data-stu-id="effcd-185">The implementation uses a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="effcd-186">RUS-hurok változtatható változóval a hatókörben</span><span class="sxs-lookup"><span data-stu-id="effcd-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="effcd-187">Ez a példa egy változtatható változó használatát mutatja be, `finished` amely a teljes REPEAT-ig-javítás hurok hatókörén belül van, és amely a hurok és a javítás lépésének frissítése előtt inicializálva lesz.</span><span class="sxs-lookup"><span data-stu-id="effcd-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="effcd-188">RUS nélkül`fixup`</span><span class="sxs-lookup"><span data-stu-id="effcd-188">RUS without `fixup`</span></span>

<span data-ttu-id="effcd-189">Ez a példa egy RUS-hurkot mutat be a javítási lépés nélkül.</span><span class="sxs-lookup"><span data-stu-id="effcd-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="effcd-190">A kód egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ a `H` és a Gates használatával `T` .</span><span class="sxs-lookup"><span data-stu-id="effcd-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="effcd-191">A hurok a $ \frac {8} {5} $ Ismétlődések átlagában leáll.</span><span class="sxs-lookup"><span data-stu-id="effcd-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="effcd-192">További részletekért lásd: egyszeres qubit unitaries (Petrovics és Svore, 2014) [*nem determinisztikus felbomlása*](https://arxiv.org/abs/1311.1074) .</span><span class="sxs-lookup"><span data-stu-id="effcd-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="effcd-193">RUS a kvantum-állapot előkészítéséhez</span><span class="sxs-lookup"><span data-stu-id="effcd-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="effcd-194">Végezetül Íme egy példa egy olyan RUS-mintázatra, amely a Quantum State $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket \right) $ előkészíti a $ {1} \ket{+} $ állapottól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="effcd-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="effcd-195">A műveletben bemutatott jelentős programozott funkciók a következők:</span><span class="sxs-lookup"><span data-stu-id="effcd-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="effcd-196">`fixup`A hurok összetettebb része, amely magában foglalja a kvantum-műveleteket.</span><span class="sxs-lookup"><span data-stu-id="effcd-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="effcd-197">Az utasítások használata `AssertProb` annak megállapítására, hogy a program bizonyos meghatározott pontjain a kvantum-állapot mérésének valószínűsége várható-e.</span><span class="sxs-lookup"><span data-stu-id="effcd-197">The use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="effcd-198">További információ a és a [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) műveletekről: [tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="effcd-198">For more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="effcd-199">További információkért lásd: [Unit Testing Sample a standard Library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="effcd-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="effcd-200">További lépések</span><span class="sxs-lookup"><span data-stu-id="effcd-200">Next steps</span></span>

<span data-ttu-id="effcd-201">A [tesztelés és a hibakeresés](xref:microsoft.quantum.guide.testingdebugging) megismertetése a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="effcd-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
