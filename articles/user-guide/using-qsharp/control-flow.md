---
title: 'Folyamat vezérlése :::no-loc(Q#):::'
description: Hurkok, feltételesség stb.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: eca37202e5fe9b48dcfdec4eeb4ba6cafaac8723
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691095"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="46dc1-103">Folyamat vezérlése :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="46dc1-103">Control flow in :::no-loc(Q#):::</span></span>

<span data-ttu-id="46dc1-104">Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan más gyakori klasszikus nyelvekhez.</span><span class="sxs-lookup"><span data-stu-id="46dc1-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="46dc1-105">A vezérlés folyamatát azonban három különböző módon módosíthatja:</span><span class="sxs-lookup"><span data-stu-id="46dc1-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="46dc1-106">`if` nyilatkozatok</span><span class="sxs-lookup"><span data-stu-id="46dc1-106">`if` statements</span></span>
* <span data-ttu-id="46dc1-107">`for` hurkok</span><span class="sxs-lookup"><span data-stu-id="46dc1-107">`for` loops</span></span>
* <span data-ttu-id="46dc1-108">`repeat-until-success` hurkok</span><span class="sxs-lookup"><span data-stu-id="46dc1-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="46dc1-109">conjugations ( `apply-within` utasítások)</span><span class="sxs-lookup"><span data-stu-id="46dc1-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="46dc1-110">A `if` és a `for` vezérlési folyamat szerkezetét a klasszikus programozási nyelvek többsége ismeri.</span><span class="sxs-lookup"><span data-stu-id="46dc1-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="46dc1-111">[`Repeat-until-success`](#repeat-until-success-loop) a hurkokat és a [conjugations](#conjugations) a cikk későbbi részében tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="46dc1-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="46dc1-112">Fontos, hogy `for` a hurkok és `if` utasítások olyan műveletekben használhatók, amelyekben automatikusan létrejönnek a [specializációk](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="46dc1-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="46dc1-113">Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.</span><span class="sxs-lookup"><span data-stu-id="46dc1-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="46dc1-114">Ez a művelet a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat.</span><span class="sxs-lookup"><span data-stu-id="46dc1-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="46dc1-115">If, máskülönben</span><span class="sxs-lookup"><span data-stu-id="46dc1-115">If, Else-if, Else</span></span>

<span data-ttu-id="46dc1-116">Az `if` utasítás támogatja a feltételes feldolgozást.</span><span class="sxs-lookup"><span data-stu-id="46dc1-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="46dc1-117">A kulcsszó `if` , a logikai kifejezés zárójelek között, valamint egy utasítás blokkja (az _akkori_ blokk).</span><span class="sxs-lookup"><span data-stu-id="46dc1-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="46dc1-118">Opcionálisan tetszőleges számú Else-if záradékot követhet, amelyek mindegyike egy kulcsszóból `elif` , egy zárójelben található logikai kifejezésből és egy utasításból álló blokkból áll (a _másik, ha_ blokk).</span><span class="sxs-lookup"><span data-stu-id="46dc1-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="46dc1-119">Végül az utasítás opcionálisan végződhet más záradékkal is, amely a kulcsszót, `else` majd egy másik utasítás blokkját (az _Else_ blokkot) tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="46dc1-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="46dc1-120">A rendszer `if` kiértékeli a feltételt, és ha az *then* értéke *igaz* , a rendszer futtatja a letiltást.</span><span class="sxs-lookup"><span data-stu-id="46dc1-120">The `if` condition is evaluated, and if it is *true* , the *then* block is run.</span></span>
<span data-ttu-id="46dc1-121">Ha a feltétel *hamis* , akkor az első más-if feltétel kiértékelése megtörténik. Ha ez igaz, akkor az *Else-if* blokk fut.</span><span class="sxs-lookup"><span data-stu-id="46dc1-121">If the condition is *false* , then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="46dc1-122">Ellenkező esetben a második, ha a blokk kiértékeli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.</span><span class="sxs-lookup"><span data-stu-id="46dc1-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="46dc1-123">Ha az eredeti *IF* feltétel és az összes Else-if záradék *Hamis értéket* ad vissza, akkor a *többi* blokk is fut, ha meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="46dc1-123">If the original *if* condition and all the else-if clauses evaluate to *false* , the *else* block is run, if provided.</span></span>

<span data-ttu-id="46dc1-124">Vegye figyelembe, hogy bármelyik blokk fut, a saját hatókörén belül fut.</span><span class="sxs-lookup"><span data-stu-id="46dc1-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="46dc1-125">`if`Az egy, `elif` , vagy blokkon belül végrehajtott kötések `else` nem láthatók a blokk vége után.</span><span class="sxs-lookup"><span data-stu-id="46dc1-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="46dc1-126">Például:</span><span class="sxs-lookup"><span data-stu-id="46dc1-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="46dc1-127">vagy</span><span class="sxs-lookup"><span data-stu-id="46dc1-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="46dc1-128">A for hurok</span><span class="sxs-lookup"><span data-stu-id="46dc1-128">For loop</span></span>

<span data-ttu-id="46dc1-129">Az `for` utasítás támogatja az ismétlést egész tartományon vagy tömbön.</span><span class="sxs-lookup"><span data-stu-id="46dc1-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="46dc1-130">Az utasítás a kulcsszót `for` , majd egy szimbólum vagy egy szimbólumot, a kulcsszót `in` és egy Type `Range` vagy Array kifejezést, valamint az összes zárójelet és egy utasítás blokkját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="46dc1-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="46dc1-131">Az utasítás blokkja (a hurok törzse) ismétlődően fut, és a megadott szimbólummal (a hurok változóval) a tartomány vagy tömb minden értékéhez kötve van.</span><span class="sxs-lookup"><span data-stu-id="46dc1-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="46dc1-132">Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem fut.</span><span class="sxs-lookup"><span data-stu-id="46dc1-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="46dc1-133">A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és nem változik, amíg a hurok fut.</span><span class="sxs-lookup"><span data-stu-id="46dc1-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="46dc1-134">A hurok változó a hurok törzsének minden bejáratához van kötve, és a törzs végén van kötve.</span><span class="sxs-lookup"><span data-stu-id="46dc1-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="46dc1-135">A Loop változó nem kötődik a for ciklus befejeződése után.</span><span class="sxs-lookup"><span data-stu-id="46dc1-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="46dc1-136">A hurok változó kötése nem változtatható meg, és ugyanazokat a szabályokat követi, mint a többi változó kötése.</span><span class="sxs-lookup"><span data-stu-id="46dc1-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="46dc1-137">Ezekben a példákban `qubits` a qubits (pl. típus) regisztrálása `Qubit[]` ,</span><span class="sxs-lookup"><span data-stu-id="46dc1-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="46dc1-138">Vegye figyelembe, hogy a végén a számtani-SHIFT-Left bináris operátort használták `<<<` .</span><span class="sxs-lookup"><span data-stu-id="46dc1-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="46dc1-139">További információ: [numerikus kifejezések](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="46dc1-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="46dc1-140">REPEAT-ig-Success hurok</span><span class="sxs-lookup"><span data-stu-id="46dc1-140">Repeat-until-success loop</span></span>

<span data-ttu-id="46dc1-141">A :::no-loc(Q#)::: nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.</span><span class="sxs-lookup"><span data-stu-id="46dc1-141">The :::no-loc(Q#)::: language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="46dc1-142">Ez a funkció lehetővé teszi, hogy a hatékony valószínűséggel rendelkező minialkalmazások megvalósításával csökkentse a unitaries megvalósításához szükséges számítási költségeket.</span><span class="sxs-lookup"><span data-stu-id="46dc1-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="46dc1-143">Ilyenek például a *REPEAT-ig-Success* (RUS) minták a alkalmazásban :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="46dc1-143">Examples of this are the *repeat-until-success* (RUS) patterns in :::no-loc(Q#):::.</span></span>
<span data-ttu-id="46dc1-144">Ezek az RUS-minták olyan valószínűségi programok, amelyek az alapvető kapuk szempontjából *várhatóan* alacsony költségeket mutatnak; a felmerülő költségek a tényleges futtatástól és a több lehetséges ág közötti összekapcsolástól függenek.</span><span class="sxs-lookup"><span data-stu-id="46dc1-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="46dc1-145">A sikeres ismétléses (RUS) minták megkönnyítése érdekében :::no-loc(Q#)::: támogatja a szerkezeteket</span><span class="sxs-lookup"><span data-stu-id="46dc1-145">To facilitate repeat-until-success (RUS) patterns, :::no-loc(Q#)::: supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="46dc1-146">ahol a `expression` bármely érvényes kifejezés, amely egy típusú értékre van kiértékelve `Bool` .</span><span class="sxs-lookup"><span data-stu-id="46dc1-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="46dc1-147">A hurok törzse fut, majd kiértékeli a feltételt.</span><span class="sxs-lookup"><span data-stu-id="46dc1-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="46dc1-148">Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a javítás lefut, és az utasítás ismét lefut, a hurok törzsének megfelelően.</span><span class="sxs-lookup"><span data-stu-id="46dc1-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="46dc1-149">Egy RUS-hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve az *egyes ismétlődésekhez* , így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="46dc1-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition* , so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="46dc1-150">A javítás futtatása azonban véget ér a utasítás hatókörével, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődésekben.</span><span class="sxs-lookup"><span data-stu-id="46dc1-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="46dc1-151">Az utasítás továbbá `fixup` gyakran hasznos, de nem mindig szükséges.</span><span class="sxs-lookup"><span data-stu-id="46dc1-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="46dc1-152">Abban az esetben, ha nincs rá szükség, a szerkezet</span><span class="sxs-lookup"><span data-stu-id="46dc1-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="46dc1-153">érvényes RUS-minta is.</span><span class="sxs-lookup"><span data-stu-id="46dc1-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="46dc1-154">További példákért és részletekért tekintse meg a jelen cikk [REPEAT-amíg-sikeres példáit](#repeat-until-success-examples) .</span><span class="sxs-lookup"><span data-stu-id="46dc1-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="46dc1-155">Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát.</span><span class="sxs-lookup"><span data-stu-id="46dc1-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="46dc1-156">Használja *a* hurkokat a függvények megfelelő funkcióinak megadásához.</span><span class="sxs-lookup"><span data-stu-id="46dc1-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="46dc1-157">A while hurok</span><span class="sxs-lookup"><span data-stu-id="46dc1-157">While loop</span></span>

<span data-ttu-id="46dc1-158">A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="46dc1-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="46dc1-159">Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi konstrukciója :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="46dc1-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in :::no-loc(Q#):::.</span></span> <span data-ttu-id="46dc1-160">Azonban az olyan hurkok, amelyek egy adott feltétel alapján szakítják meg a futási időtartamot, és így a futtatási hossz nem ismert a fordítási időben, a rendszer a kvantum-futtatókörnyezetben különös gondossággal kezeli.</span><span class="sxs-lookup"><span data-stu-id="46dc1-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="46dc1-161">Azonban a függvényeken belüli használatuk nem problémamentes, mivel ezek a hurkok csak a hagyományos (nem Quantum) hardveren futó kódokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="46dc1-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="46dc1-162">:::no-loc(Q#):::Ezért a csak a functions-ben lévő hurkok használatát támogatja.</span><span class="sxs-lookup"><span data-stu-id="46dc1-162">:::no-loc(Q#):::, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="46dc1-163">Egy `while` utasítás a kulcsszóból `while` , egy logikai kifejezésből áll zárójelben, és egy utasítás blokkot.</span><span class="sxs-lookup"><span data-stu-id="46dc1-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="46dc1-164">Az utasítás blokkja (a hurok törzse) mindaddig fut, amíg a feltétel kiértékelése megtörténik `true` .</span><span class="sxs-lookup"><span data-stu-id="46dc1-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="46dc1-165">Conjugations</span><span class="sxs-lookup"><span data-stu-id="46dc1-165">Conjugations</span></span>

<span data-ttu-id="46dc1-166">A klasszikus BITS-vel szemben a kvantum-memória felszabadítása valamivel nagyobb mértékben történik, mivel a qubits vakon alaphelyzetbe állítása nem kívánt hatással lehet a fennmaradó számításra, ha a qubits továbbra is összefonódik.</span><span class="sxs-lookup"><span data-stu-id="46dc1-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="46dc1-167">Ezek a hatások elkerülhetők a memória felszabadítása előtt végrehajtott számítások megfelelő "visszavonása" esetén.</span><span class="sxs-lookup"><span data-stu-id="46dc1-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="46dc1-168">A kvantum-számítástechnika általános mintája a következő:</span><span class="sxs-lookup"><span data-stu-id="46dc1-168">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="46dc1-169">:::no-loc(Q#)::: a támogatja az előző transzformációt megvalósító ragozó utasítást.</span><span class="sxs-lookup"><span data-stu-id="46dc1-169">:::no-loc(Q#)::: supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="46dc1-170">Az utasítás használatával a művelet a `ApplyWith` következő módon valósítható meg:</span><span class="sxs-lookup"><span data-stu-id="46dc1-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="46dc1-171">Ha a külső és belső átalakítások nem állnak rendelkezésre könnyen elérhető műveletként, akkor az ilyen típusú ragozás akkor válik hasznosnak, ha egy blokk több utasításból áll.</span><span class="sxs-lookup"><span data-stu-id="46dc1-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="46dc1-172">A blokkon belül definiált utasítások inverz átalakítását a fordító automatikusan hozza létre, és az Apply-Block befejeződése után fut.</span><span class="sxs-lookup"><span data-stu-id="46dc1-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="46dc1-173">Mivel a blokk részeként használt változó változók nem használhatók fel az alkalmazás-blokkban, a generált transzformáció garantált, hogy a adjoint a blokkon belül.</span><span class="sxs-lookup"><span data-stu-id="46dc1-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="46dc1-174">Visszatérési utasítás</span><span class="sxs-lookup"><span data-stu-id="46dc1-174">Return Statement</span></span>

<span data-ttu-id="46dc1-175">A Return utasítás egy művelet vagy függvény futtatását, és egy értéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="46dc1-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="46dc1-176">Ez a kulcsszóból áll `return` , majd a megfelelő típusú kifejezéssel, valamint egy megszakítási pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="46dc1-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="46dc1-177">Például:</span><span class="sxs-lookup"><span data-stu-id="46dc1-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="46dc1-178">vagy</span><span class="sxs-lookup"><span data-stu-id="46dc1-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="46dc1-179">Egy üres rekordot visszaadó hívható, `()` nem igényel visszatérési utasítást.</span><span class="sxs-lookup"><span data-stu-id="46dc1-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="46dc1-180">A művelet vagy a függvény korai kilépésének megadásához használja a következőt: `return ();` .</span><span class="sxs-lookup"><span data-stu-id="46dc1-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="46dc1-181">A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.</span><span class="sxs-lookup"><span data-stu-id="46dc1-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="46dc1-182">Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.</span><span class="sxs-lookup"><span data-stu-id="46dc1-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="46dc1-183">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="46dc1-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="46dc1-184">Sikertelen utasítás</span><span class="sxs-lookup"><span data-stu-id="46dc1-184">Fail statement</span></span>

<span data-ttu-id="46dc1-185">A Fail utasítás egy művelet futtatásával végződik, és hibaértéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="46dc1-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="46dc1-186">A kulcsszót `fail` , majd egy karakterláncot és egy megszakítást tartalmazó pontosvesszőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="46dc1-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="46dc1-187">Az utasítás a klasszikus illesztőprogram sztringjét adja vissza hibaüzenetként.</span><span class="sxs-lookup"><span data-stu-id="46dc1-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="46dc1-188">A műveleteken belüli sikertelen utasítások száma nincs korlátozva.</span><span class="sxs-lookup"><span data-stu-id="46dc1-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="46dc1-189">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="46dc1-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="46dc1-190">Például:</span><span class="sxs-lookup"><span data-stu-id="46dc1-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="46dc1-191">vagy [interpolált karakterláncok](xref:microsoft.quantum.guide.expressions#interpolated-strings)használatával</span><span class="sxs-lookup"><span data-stu-id="46dc1-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="46dc1-192">Ismételt sikeres példák</span><span class="sxs-lookup"><span data-stu-id="46dc1-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="46dc1-193">RUS-minta egyetlen qubit elforgatásához egy irracionális tengelyen</span><span class="sxs-lookup"><span data-stu-id="46dc1-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="46dc1-194">Tipikus használati eset esetén a következő művelet a :::no-loc(Q#)::: (Z) $ (I + 2i Z)/\sqrt $, a Bloch szférán belüli irracionális tengely körüli rotációt valósít {5} meg.</span><span class="sxs-lookup"><span data-stu-id="46dc1-194">In a typical use case, the following :::no-loc(Q#)::: operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="46dc1-195">A megvalósítás egy ismert RUS mintát használ:</span><span class="sxs-lookup"><span data-stu-id="46dc1-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="46dc1-196">RUS-hurok változtatható változóval a hatókörben</span><span class="sxs-lookup"><span data-stu-id="46dc1-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="46dc1-197">Ez a példa egy változtatható változó használatát mutatja be, `finished` amely a teljes REPEAT-ig-javítás hurok hatókörén belül van, és amely a hurok és a javítás lépésének frissítése előtt inicializálva lesz.</span><span class="sxs-lookup"><span data-stu-id="46dc1-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="46dc1-198">RUS nélkül `fixup`</span><span class="sxs-lookup"><span data-stu-id="46dc1-198">RUS without `fixup`</span></span>

<span data-ttu-id="46dc1-199">Ez a példa egy RUS-hurkot mutat be a javítási lépés nélkül.</span><span class="sxs-lookup"><span data-stu-id="46dc1-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="46dc1-200">A kód egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ a `H` és a Gates használatával `T` .</span><span class="sxs-lookup"><span data-stu-id="46dc1-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="46dc1-201">A hurok a $ \frac {8} {5} $ Ismétlődések átlagában leáll.</span><span class="sxs-lookup"><span data-stu-id="46dc1-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="46dc1-202">További részletekért lásd: egyszeres qubit unitaries (Petrovics és Svore, 2014) [*nem determinisztikus felbomlása*](https://arxiv.org/abs/1311.1074) .</span><span class="sxs-lookup"><span data-stu-id="46dc1-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="46dc1-203">RUS a kvantum-állapot előkészítéséhez</span><span class="sxs-lookup"><span data-stu-id="46dc1-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="46dc1-204">Végezetül Íme egy példa egy olyan RUS-mintázatra, amely a Quantum State $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket \right) $ előkészíti a $ {1} \ket{+} $ állapottól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="46dc1-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="46dc1-205">A műveletben bemutatott jelentős programozott funkciók a következők:</span><span class="sxs-lookup"><span data-stu-id="46dc1-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="46dc1-206">`fixup`A hurok összetettebb része, amely magában foglalja a kvantum-műveleteket.</span><span class="sxs-lookup"><span data-stu-id="46dc1-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="46dc1-207">Az utasítások használata `AssertMeasurementProbability` annak megállapítására, hogy a program bizonyos meghatározott pontjain a kvantum-állapot mérésének valószínűsége várható-e.</span><span class="sxs-lookup"><span data-stu-id="46dc1-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="46dc1-208">További információ a és a [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) műveletekről: [tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="46dc1-208">For more information about the [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="46dc1-209">További információkért lásd: [Unit Testing Sample a standard Library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="46dc1-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="46dc1-210">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="46dc1-210">Next steps</span></span>

<span data-ttu-id="46dc1-211">További információ a [teszteléséről és hibakereséséről](xref:microsoft.quantum.guide.testingdebugging) :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="46dc1-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in :::no-loc(Q#):::.</span></span>
