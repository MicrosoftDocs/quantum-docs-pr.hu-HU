---
title: 'Vezérlési folyamat a Q-ban #'
description: Hurkok, feltételesség stb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326540"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="1d4f3-103">Vezérlési folyamat a Q-ban #</span><span class="sxs-lookup"><span data-stu-id="1d4f3-103">Control Flow in Q#</span></span>

<span data-ttu-id="1d4f3-104">Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan a leggyakoribb klasszikus nyelvekhez.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="1d4f3-105">Ez a vezérlési folyamat azonban három különböző módon módosítható:</span><span class="sxs-lookup"><span data-stu-id="1d4f3-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="1d4f3-106">`if`nyilatkozatok</span><span class="sxs-lookup"><span data-stu-id="1d4f3-106">`if` statements</span></span>
- <span data-ttu-id="1d4f3-107">`for`hurkok</span><span class="sxs-lookup"><span data-stu-id="1d4f3-107">`for` loops</span></span>
- <span data-ttu-id="1d4f3-108">`repeat`-`until`hurkok</span><span class="sxs-lookup"><span data-stu-id="1d4f3-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="1d4f3-109">Az utóbbival kapcsolatos vitát elhalasztjuk [alább](#repeat-until-success-loop).</span><span class="sxs-lookup"><span data-stu-id="1d4f3-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="1d4f3-110">A `if` és a `for` vezérlés folyamata azonban a klasszikus programozási nyelvek többsége számára jól ismert.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="1d4f3-111">Fontos, hogy `for` a hurkok és `if` utasítások olyan műveletekben is használhatók, amelyekhez a rendszer automatikusan létrehozza a specializációkat.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="1d4f3-112">Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="1d4f3-113">Ez a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="1d4f3-114">Határozottan kevésbé jól működik, ha a cipőjét továbbra is ki szeretné próbálni.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="1d4f3-115">If, máskülönben</span><span class="sxs-lookup"><span data-stu-id="1d4f3-115">If, Else-if, Else</span></span>

<span data-ttu-id="1d4f3-116">Az `if` utasítás támogatja a feltételes végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="1d4f3-117">A kulcsszóból `if` , egy nyitó zárójelből `(` , egy logikai kifejezésből, egy záró zárójelből `)` és egy utasításból álló blokkból áll (ez a blokk). _then_</span><span class="sxs-lookup"><span data-stu-id="1d4f3-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="1d4f3-118">Ezt követheti tetszőleges számú Else-if záradék, amelyek mindegyike egy kulcsszóból `elif` , egy nyitó zárójelből `(` , egy logikai kifejezésből, egy záró zárójelből `)` és egy utasításból álló blokkból áll (ez a _másik_ blokk).</span><span class="sxs-lookup"><span data-stu-id="1d4f3-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="1d4f3-119">Végül az utasítás opcionálisan végződhet más záradékkal is, amely a kulcsszót, `else` majd egy másik utasítás blokkját (az _Else_ blokkot) tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="1d4f3-120">A rendszer `if` kiértékeli a feltételt, és ha az értéke igaz, a rendszer végrehajtja a letiltást.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="1d4f3-121">Ha a feltétel hamis, akkor az első más-if feltétel kiértékelése megtörténik. Ha az értéke igaz, akkor ez a másik a blokkolás végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="1d4f3-122">Ellenkező esetben a második, ha a blokkot teszteli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="1d4f3-123">Ha az eredeti if feltétel és az összes más-if záradék hamis értéket ad vissza, akkor a rendszer a másik blokkot hajtja végre, ha meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="1d4f3-124">Vegye figyelembe, hogy a rendszer bármelyik blokkot a saját hatókörében hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="1d4f3-125">Az egy `if` , `elif` , vagy blokkon belül végrehajtott kötések `else` nem láthatók a vége után.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="1d4f3-126">Példa:</span><span class="sxs-lookup"><span data-stu-id="1d4f3-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="1d4f3-127">vagy</span><span class="sxs-lookup"><span data-stu-id="1d4f3-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="1d4f3-128">Hurok esetén</span><span class="sxs-lookup"><span data-stu-id="1d4f3-128">For Loop</span></span>

<span data-ttu-id="1d4f3-129">Az `for` utasítás egy egész tartományon vagy egy tömbön keresztül támogatja az ismétlést.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="1d4f3-130">Az utasítás a kulcsszóból `for` , egy nyitott zárójelből `(` , egy szimbólum vagy egy szimbólum, egy `in` tömbből, egy típusú vagy egy tömbből álló kifejezésből, `Range` egy záró zárójelből `)` és egy utasításból áll.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="1d4f3-131">A rendszer az utasítás blokkját (a hurok törzsét) többször hajtja végre, és a definiált szimbólum (ok) (a hurok változói) a tartomány vagy tömb egyes értékeihez van kötve.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="1d4f3-132">Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem lesz végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="1d4f3-133">A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és a hurok végrehajtása közben nem változik.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="1d4f3-134">A hurok változó a hurok törzsének minden bejáratánál, a törzs végén pedig nem köthető.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="1d4f3-135">A Loop változó nem kötődik a for ciklus befejeződése után.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="1d4f3-136">A deklarált szimbólum (ok) kötése nem módosítható, és ugyanazokat a szabályokat követi, mint a többi változó kötése.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="1d4f3-137">Néhány példa arra, hogy `qubits` a qubits (azaz típus) regisztrálása a következő: `Qubit[]`</span><span class="sxs-lookup"><span data-stu-id="1d4f3-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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
<span data-ttu-id="1d4f3-138">Vegye figyelembe, hogy a végén a számtani-SHIFT-Left bináris operátort használták, `<<<` amely részletesen megtalálhatja a [numerikus kifejezéseket](xref:microsoft.quantum.guide.expressions#numeric-expressions) .</span><span class="sxs-lookup"><span data-stu-id="1d4f3-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="1d4f3-139">REPEAT-ig-Success hurok</span><span class="sxs-lookup"><span data-stu-id="1d4f3-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="1d4f3-140">A Q # nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="1d4f3-141">Ez a funkció lehetővé teszi a hatékony valószínűségi minialkalmazások megvalósítását, ami csökkentheti a számítási költségeket a unitaries megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="1d4f3-142">A Q #-ban például könnyen megvalósítható az úgynevezett *REPEAT-ig-Success* (RUS) mintázat.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="1d4f3-143">Ezek az RUS-minták olyan valószínűségi programok, amelyek a *vártnál* alacsonyabb költségeket mutatnak az elemi kapuk szempontjából, de a valódi díjak a tényleges futtatástól és a különböző lehetséges elágazások tényleges elhagyása függnek.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="1d4f3-144">A REPEAT-ig-Success (RUS) minták megkönnyítése érdekében a Q # támogatja a szerkezeteket</span><span class="sxs-lookup"><span data-stu-id="1d4f3-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="1d4f3-145">ahol a `expression` bármely érvényes kifejezés, amely egy típusú értékre van kiértékelve `Bool` .</span><span class="sxs-lookup"><span data-stu-id="1d4f3-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="1d4f3-146">A rendszer végrehajtja a hurok törzsét, majd kiértékeli a feltételt.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="1d4f3-147">Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a rendszer végrehajtja a javítást, és az utasítást a hurok törzsének megfelelően újra végrehajtja.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="1d4f3-148">Az Ismétlési/a hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve az *egyes ismétlődésekhez*, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="1d4f3-149">A javítás végrehajtásának befejezése azonban befejezi az utasítás hatókörét, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődések során.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="1d4f3-150">Az utasítás továbbá `fixup` gyakran hasznos, de nem mindig szükséges.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="1d4f3-151">Abban az esetben, ha nincs rá szükség, a szerkezet</span><span class="sxs-lookup"><span data-stu-id="1d4f3-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="1d4f3-152">érvényes RUS-minta is.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="1d4f3-153">A lap alján az [RUS-hurkok néhány példáját](#repeat-until-success-examples)mutatjuk be.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="1d4f3-154">Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="1d4f3-155">A kapcsolódó funkciókat a függvények hurkoi is biztosítják.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="1d4f3-156">Ciklus közben</span><span class="sxs-lookup"><span data-stu-id="1d4f3-156">While Loop</span></span>

<span data-ttu-id="1d4f3-157">A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="1d4f3-158">Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi összeállítás Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="1d4f3-159">Azonban az olyan hurkok, amelyek feltételen alapulnak, és amelynek végrehajtási hosszát a fordítási időn belül ismeretlennek kell lenniük, a kvantum-futtatókörnyezetben különös gondossággal kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="1d4f3-160">A függvényeken belüli használatuk azonban nem problémamentes, mivel ezek csak a hagyományos (nem Quantum) hardveren végrehajtandó kódokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="1d4f3-161">A Q # ezért a csak functions-ben lévő hurkok használatát támogatja.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="1d4f3-162">Egy `while` utasítás a kulcsszóból `while` , egy nyitó zárójelből `(` , egy feltétellel (például logikai kifejezésből), egy záró zárójelből `)` és egy utasításból áll.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="1d4f3-163">A rendszer az utasítás blokkját (a hurok törzsét) hajtja végre, amíg a feltétel kiértékelése megtörténik `true` .</span><span class="sxs-lookup"><span data-stu-id="1d4f3-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="1d4f3-164">Visszatérési utasítás</span><span class="sxs-lookup"><span data-stu-id="1d4f3-164">Return Statement</span></span>

<span data-ttu-id="1d4f3-165">A Return utasítás egy művelet vagy függvény végrehajtását hajtja végre, és egy értéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="1d4f3-166">Ez a kulcsszóból áll `return` , majd a megfelelő típusú kifejezéssel, valamint egy megszakítási pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="1d4f3-167">Egy üres rekordot visszaadó hívható, `()` nem igényel visszatérési utasítást.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="1d4f3-168">Ha korai kilépés szükséges, `return ()` akkor ebben az esetben is használható.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="1d4f3-169">A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="1d4f3-170">Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="1d4f3-171">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="1d4f3-172">Példa:</span><span class="sxs-lookup"><span data-stu-id="1d4f3-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="1d4f3-173">vagy</span><span class="sxs-lookup"><span data-stu-id="1d4f3-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="1d4f3-174">vagy</span><span class="sxs-lookup"><span data-stu-id="1d4f3-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="1d4f3-175">Sikertelen utasítás</span><span class="sxs-lookup"><span data-stu-id="1d4f3-175">Fail Statement</span></span>

<span data-ttu-id="1d4f3-176">A Fail utasítás befejezi a művelet végrehajtását, és hibaértéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="1d4f3-177">A kulcsszót `fail` , majd egy karakterláncot és egy megszakítást tartalmazó pontosvesszőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="1d4f3-178">A rendszer a karakterláncot a klasszikus illesztőprogramnak adja vissza hibaüzenetként.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="1d4f3-179">A műveleteken belüli sikertelen utasítások száma nincs korlátozva.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="1d4f3-180">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="1d4f3-181">Példa:</span><span class="sxs-lookup"><span data-stu-id="1d4f3-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="1d4f3-182">vagy [interpolált karakterláncok](xref:microsoft.quantum.guide.expressions#interpolated-strings)használatával</span><span class="sxs-lookup"><span data-stu-id="1d4f3-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="1d4f3-183">Ismételt sikeres példák</span><span class="sxs-lookup"><span data-stu-id="1d4f3-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="1d4f3-184">RUS-minta egyetlen qubit elforgatásához egy irracionális tengelyen</span><span class="sxs-lookup"><span data-stu-id="1d4f3-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="1d4f3-185">Egy tipikus használati eset esetében a következő Q # művelet végrehajt egy, az/\sqrt $ (I + 2i Z) és a Bloch gömb közötti irracionális tengely körüli rotációt {5} .</span><span class="sxs-lookup"><span data-stu-id="1d4f3-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="1d4f3-186">Ez egy ismert RUS-minta használatával valósítható meg:</span><span class="sxs-lookup"><span data-stu-id="1d4f3-186">This is accomplished by using a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="1d4f3-187">RUS-hurok változtatható változóval a hatókörben</span><span class="sxs-lookup"><span data-stu-id="1d4f3-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="1d4f3-188">Ez a példa egy változtatható változó használatát mutatja be, `finished` amely a teljes REPEAT-ig-javítás hurok hatókörében van, és amely a hurok és a javítás lépésének frissítése előtt inicializálva lesz.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="1d4f3-189">RUS nélkül`fixup`</span><span class="sxs-lookup"><span data-stu-id="1d4f3-189">RUS without `fixup`</span></span>

<span data-ttu-id="1d4f3-190">A következő kód például egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ a `H` és a Gates használatával `T` .</span><span class="sxs-lookup"><span data-stu-id="1d4f3-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="1d4f3-191">A hurok a $ \frac {8} {5} $ Ismétlődések átlagában leáll.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="1d4f3-192">További részletekért lásd: egyszeres qubit unitaries (Petrovics és Svore, 2014) [*nem determinisztikus felbomlása*](https://arxiv.org/abs/1311.1074) .</span><span class="sxs-lookup"><span data-stu-id="1d4f3-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="1d4f3-193">RUS a kvantum-állapot előkészítéséhez</span><span class="sxs-lookup"><span data-stu-id="1d4f3-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="1d4f3-194">Végül egy olyan RUS-mintát mutatunk be, amely az $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $ értéket, a $ \ket{+} $ állapottól kezdődően előkészíti a kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="1d4f3-195">Lásd még: a [standard könyvtárhoz megadott Unit Testing minta](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="1d4f3-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

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

<span data-ttu-id="1d4f3-196">Az ebben a műveletben bemutatott jelentős programozott funkciók a hurok összetettebb `fixup` részét képezik, amely magában foglalja a kvantum-műveleteket, valamint az `AssertProb` utasítások használatát annak megállapítására, hogy a program bizonyos meghatározott pontjain a kvantum-állapot mérésének valószínűsége várható-e.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="1d4f3-197">Lásd még: [tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging) , további információ a [`Assert`](xref:microsoft.quantum.intrinsic.assert) és a [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) műveletekről.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="1d4f3-198">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="1d4f3-198">Next steps</span></span>

<span data-ttu-id="1d4f3-199">A [tesztelés és a hibakeresés](xref:microsoft.quantum.guide.testingdebugging) megismertetése a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="1d4f3-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>