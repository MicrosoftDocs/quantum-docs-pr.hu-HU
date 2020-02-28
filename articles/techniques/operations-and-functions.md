---
title: 'Q # műveletek és függvények'
description: 'Ismerje meg a Q # műveleteit és funkcióit, valamint azt, hogy ezek hogyan lesznek alkalmazva a Quantum programban.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907664"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="1ce86-103">Q # műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="1ce86-103">Q# Operations and Functions</span></span>

<span data-ttu-id="1ce86-104">A Q # programok egy vagy több olyan *műveletből* állnak, amelyek leírják a kvantum-műveleteket a Quantum-adatokon, és egy vagy több olyan *függvényt* , amely engedélyezi a klasszikus adatok módosítását.</span><span class="sxs-lookup"><span data-stu-id="1ce86-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="1ce86-105">A műveletekkel szemben a függvények a tisztán klasszikus viselkedés leírására szolgálnak, és nem gyakorolnak semmilyen hatást a klasszikus számítástechnikai értékek mellett.</span><span class="sxs-lookup"><span data-stu-id="1ce86-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="1ce86-106">A Q # által meghatározott minden művelet hívhat meg tetszőleges számú egyéb műveletet, beleértve a nyelv által meghatározott beépített belső műveleteket is.</span><span class="sxs-lookup"><span data-stu-id="1ce86-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="1ce86-107">A belső műveletek meghatározásának konkrét módja a célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="1ce86-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="1ce86-108">A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.</span><span class="sxs-lookup"><span data-stu-id="1ce86-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="1ce86-109">Új műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="1ce86-109">Defining New Operations</span></span>

<span data-ttu-id="1ce86-110">A fentiekben leírtak szerint egy, a Q #-ban írt kvantum-program legalapvetőbb építőeleme egy *művelet*, amely hívható a klasszikus .NET-alkalmazásokból, például szimulátor használatával vagy más, a q #-on belüli műveletekkel.</span><span class="sxs-lookup"><span data-stu-id="1ce86-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="1ce86-111">Mindegyik művelet egy bemenetet hoz létre, kimenetet állít elő, és meghatározza egy vagy több műveleti specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="1ce86-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="1ce86-112">A következő művelet például csak az alapértelmezett szövegtörzset definiálja, és egyetlen qubit fogad hozzá bemenetként, majd meghívja a beépített `X` műveletet az adott bemeneten:</span><span class="sxs-lookup"><span data-stu-id="1ce86-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="1ce86-113">A kulcsszó `operation` megkezdi a művelet definícióját, és ezt a nevet követi; Itt `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="1ce86-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="1ce86-114">Ezután a bemenet típusa `Qubit`ként van definiálva, valamint egy név `target`, amely az új műveletben lévő bemenetre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="1ce86-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="1ce86-115">Hasonlóképpen, a `Unit` azt is meghatározza, hogy a művelet kimenete üres.</span><span class="sxs-lookup"><span data-stu-id="1ce86-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="1ce86-116">Ezt ugyanúgy használják, mint a C# és más, a `void` és más hasznos nyelveken, valamint F# a `unit` és más funkcionális nyelvek esetében.</span><span class="sxs-lookup"><span data-stu-id="1ce86-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="1ce86-117">Ezt részletesebben is megvizsgáljuk, de a Q # minden művelete pontosan egy bemenetet vesz fel, és pontosan egy kimenetet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="1ce86-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="1ce86-118">Ezután több bemenet és kimenet is képviselteti magát a *rekordok*használatával, amely egyszerre több értéket gyűjt össze egyetlen értékkel.</span><span class="sxs-lookup"><span data-stu-id="1ce86-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="1ce86-119">Informálisan azt mondjuk, hogy a Q # egy "rekordos kijelentkezés" nyelv.</span><span class="sxs-lookup"><span data-stu-id="1ce86-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="1ce86-120">Ezt a fogalmat követve a `()` az "üres" rekordként kell olvasni, amelynek típusa `Unit`.</span><span class="sxs-lookup"><span data-stu-id="1ce86-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="1ce86-121">Az új műveleten belül a megvalósítás közvetlenül a deklarációban adható meg, ha csak az alapértelmezett szövegtörzs-specializáció megvalósítását explicit módon kell megadni.</span><span class="sxs-lookup"><span data-stu-id="1ce86-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="1ce86-122">Emellett lehetséges a megvalósítások definiálása, például egy vagy több `functor` művelet, az alábbi módon:</span><span class="sxs-lookup"><span data-stu-id="1ce86-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="1ce86-123">A fenti példában az egyetlen utasítás a beépített Q # művelet <xref:microsoft.quantum.intrinsic.x>meghívása.</span><span class="sxs-lookup"><span data-stu-id="1ce86-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="1ce86-124">A műveletek több érdekes típust is visszaadhatnak, mint a `Unit`.</span><span class="sxs-lookup"><span data-stu-id="1ce86-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="1ce86-125">A <xref:microsoft.quantum.intrinsic.m> művelet például `Result`típusú kimenetet ad vissza, amely a mérés végrehajtásával jár.</span><span class="sxs-lookup"><span data-stu-id="1ce86-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="1ce86-126">Egy művelet kimenetét átadhatja egy másik műveletnek, vagy használhatja a `let` kulcsszóval egy új változó definiálásához.</span><span class="sxs-lookup"><span data-stu-id="1ce86-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="1ce86-127">Ez lehetővé teszi a klasszikus számításokat, amelyek alacsony szinten működnek a kvantum-műveletekkel, például a sűrűbb kódolásban:</span><span class="sxs-lookup"><span data-stu-id="1ce86-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="1ce86-128">Adjoint és vezérelt</span><span class="sxs-lookup"><span data-stu-id="1ce86-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="1ce86-129">Ha egy művelet egy egységes átalakítást valósít meg, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen.</span><span class="sxs-lookup"><span data-stu-id="1ce86-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="1ce86-130">Egy művelet adjoint megadásával megadható, hogy a hogyan működik, amikor fordított állapotban van, míg a szabályozott specializáció meghatározza, hogy a művelet hogyan viselkedik, ha a rendszer a kvantum-regiszter állapotára alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="1ce86-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="1ce86-131">Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható: `is Adj + Ctl` a következő példában.</span><span class="sxs-lookup"><span data-stu-id="1ce86-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="1ce86-132">Ezután a fordító létrehozza a megfelelő implementációt minden ilyen implicit módon deklarált specializációhoz.</span><span class="sxs-lookup"><span data-stu-id="1ce86-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="1ce86-133">A Q # számos művelete egységes kapukat képvisel.</span><span class="sxs-lookup"><span data-stu-id="1ce86-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="1ce86-134">Ha $U $ a művelet `U`által reprezentált egységes kapu, akkor `Adjoint U` az egységes kaput jelöli $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="1ce86-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="1ce86-135">Abban az esetben, ha a fordító nem tudja létrehozni a megvalósítást, explicit módon megadható.</span><span class="sxs-lookup"><span data-stu-id="1ce86-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="1ce86-136">Az ilyen explicit specializációs nyilatkozatok megfelelő generációs irányelvből vagy felhasználó által definiált implementációból állhatnak.</span><span class="sxs-lookup"><span data-stu-id="1ce86-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="1ce86-137">A fenti `PrepareEntangledPair` található kód például az alábbi kóddal egyenértékű, explicit specializációs deklarációkat tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="1ce86-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="1ce86-138">A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan hozhatja ki a specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="1ce86-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="1ce86-139">Ha a fordító nem tud automatikusan előállítani egy bizonyos specializáció megvalósítását, vagy ha hatékonyabb megvalósításra van lehetőség, akkor a megvalósítás manuálisan is megadható.</span><span class="sxs-lookup"><span data-stu-id="1ce86-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="1ce86-140">A fenti példában a `adjoint invert;` azt jelzi, hogy a adjoint specializációt a törzs megvalósításának visszafordításával kell létrehozni, és a `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint specializációt úgy kell létrehozni, hogy a vezérelt specializáció adott implementációját visszaállítja.</span><span class="sxs-lookup"><span data-stu-id="1ce86-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="1ce86-141">Ennek további példáit láthatjuk a [magasabb rendű vezérlési folyamatokban](xref:microsoft.quantum.concepts.control-flow).</span><span class="sxs-lookup"><span data-stu-id="1ce86-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="1ce86-142">Egy művelet specializációjának meghívásához használja a `Adjoint` vagy `Controlled` kulcsszavakat.</span><span class="sxs-lookup"><span data-stu-id="1ce86-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="1ce86-143">Például a fenti kondenzátor-kódolási példa az `PrepareEntangledPair` adjoint használatával tömören írható, hogy a kusza állapotot visszaalakítsa egy nem összeillesztett qubits:</span><span class="sxs-lookup"><span data-stu-id="1ce86-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="1ce86-144">Számos fontos korlátozást kell figyelembe venni, amikor a rendszer megtervezi, hogy milyen műveleteket végeznek az üzemben.</span><span class="sxs-lookup"><span data-stu-id="1ce86-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="1ce86-145">A legtöbb kritikus jelentőséggel bír, ha egy olyan műveletre specializálódott, amely bármely más művelet kimeneti értékét használja, nem lehet automatikusan generálni a fordítótól, mert nem egyértelmű, hogy az ilyen műveletekben szereplő utasítások hogyan rendezhetők át ugyanezen hatás megszerzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="1ce86-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="1ce86-146">Új függvények definiálása</span><span class="sxs-lookup"><span data-stu-id="1ce86-146">Defining New Functions</span></span>

<span data-ttu-id="1ce86-147">A Q # Emellett lehetővé teszi a *függvények*definiálását is, amelyek nem azonosak a kimeneti érték kiszámításának következményeivel.</span><span class="sxs-lookup"><span data-stu-id="1ce86-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="1ce86-148">A függvények nem hívhatják meg a műveleteket, a qubits, a véletlenszerű számú mintákat, vagy más módon a bemeneti értéken kívüli állapottól függenek.</span><span class="sxs-lookup"><span data-stu-id="1ce86-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="1ce86-149">Ennek következményeként a Q # függvények *tisztán*vannak rendelve, hogy mindig ugyanazokat a bemeneti értékeket rendelik ugyanahhoz a kimeneti értékekhez.</span><span class="sxs-lookup"><span data-stu-id="1ce86-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="1ce86-150">Így a Q # fordító biztonságosan átrendezheti, hogyan és mikor hívja meg a függvényeket a műveleti specializációk létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="1ce86-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="1ce86-151">A függvények definiálása hasonlóan működik a művelet definiálásához, azzal a kivétellel, hogy egy függvényhez nem lehet adjoint vagy vezérelt specializációt meghatározni.</span><span class="sxs-lookup"><span data-stu-id="1ce86-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="1ce86-152">Például:</span><span class="sxs-lookup"><span data-stu-id="1ce86-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="1ce86-153">Ha ezt megteheti, hasznos lehet a klasszikus logikát kiírni a függvények helyett, hogy azok a műveletek során könnyebben használhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="1ce86-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="1ce86-154">Ha például egy műveletként írt `Square`, akkor a fordító nem tudta volna garantálni, hogy ugyanazt a bemenetet ugyanazzal a kimenettel fogja megszólítani.</span><span class="sxs-lookup"><span data-stu-id="1ce86-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="1ce86-155">A függvények és a műveletek közötti különbség kihangsúlyozása érdekében vegye figyelembe, hogy egy véletlenszerűen kiválasztott számnak a Q #-műveletből való klasszikus mintavételezési problémája:</span><span class="sxs-lookup"><span data-stu-id="1ce86-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="1ce86-156">Minden alkalommal, amikor a `U` meghívása megtörtént, a `target`egy másik művelettel fog rendelkezni.</span><span class="sxs-lookup"><span data-stu-id="1ce86-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="1ce86-157">A fordító nem tudja garantálni, hogy ha `adjoint auto` specializációs nyilatkozatot adott hozzá `U`hoz, akkor `U(target); Adjoint U(target);` identitásként viselkedik (azaz nem op).</span><span class="sxs-lookup"><span data-stu-id="1ce86-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="1ce86-158">Ez sérti a [vektorokban és mátrixokban](xref:microsoft.quantum.concepts.vectors)megjelenő adjoint definícióját, amely lehetővé teszi, hogy egy adjoint-specializációt egy olyan műveletben engedélyezzen, amelyben az általunk használt művelet <xref:microsoft.quantum.math.randomreal> a fordító által biztosított garanciák megbomlásával. <xref:microsoft.quantum.math.randomreal> olyan művelet, amelynek nem létezik adjoint vagy vezérelt verziója.</span><span class="sxs-lookup"><span data-stu-id="1ce86-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="1ce86-159">Másfelől lehetővé teszi, hogy a függvényhívás, például a `Square` biztonságos legyen, abban az esetben, ha a fordító biztos lehet abban, hogy csak a bemenetet kell megőriznie `Square` a kimenet stabilitásának megőrzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="1ce86-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="1ce86-160">Így a lehető legtöbb klasszikus logikát elkülönítheti a functions szolgáltatásban, így a logika más funkciókban és műveletekben is felhasználható.</span><span class="sxs-lookup"><span data-stu-id="1ce86-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="1ce86-161">Átvitelvezérlés</span><span class="sxs-lookup"><span data-stu-id="1ce86-161">Control Flow</span></span>

<span data-ttu-id="1ce86-162">Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan a leggyakoribb klasszikus nyelvekhez.</span><span class="sxs-lookup"><span data-stu-id="1ce86-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="1ce86-163">Ez a vezérlési folyamat azonban három különböző módon módosítható:</span><span class="sxs-lookup"><span data-stu-id="1ce86-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="1ce86-164">`if` utasítások</span><span class="sxs-lookup"><span data-stu-id="1ce86-164">`if` Statements</span></span>
- <span data-ttu-id="1ce86-165">`for` hurkok</span><span class="sxs-lookup"><span data-stu-id="1ce86-165">`for` Loops</span></span>
- <span data-ttu-id="1ce86-166">`repeat`-`until` hurkok</span><span class="sxs-lookup"><span data-stu-id="1ce86-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="1ce86-167">Addig elhalasztjuk a vitát, amíg meg nem vitatjuk a [sikeres (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) áramköröket.</span><span class="sxs-lookup"><span data-stu-id="1ce86-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="1ce86-168">A `if` és `for` Control flow szerkezetek azonban a klasszikus programozási nyelvek többségében jól ismertek.</span><span class="sxs-lookup"><span data-stu-id="1ce86-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="1ce86-169">Egy `if` utasítás egy feltételt is igénybe vehet, amelyet egy vagy több `elif` utasítás követ, és a `else`is végződhet:</span><span class="sxs-lookup"><span data-stu-id="1ce86-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="1ce86-170">Hasonlóképpen, `for` hurkok több egész szám vagy egy tömb elemeinek megismétlését jelölik:</span><span class="sxs-lookup"><span data-stu-id="1ce86-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="1ce86-171">Fontos, hogy `for` hurkokat és `if` utasításokat olyan műveletekben is felhasználhatjuk, amelyekben automatikusan létrejönnek a specializációk.</span><span class="sxs-lookup"><span data-stu-id="1ce86-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="1ce86-172">Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.</span><span class="sxs-lookup"><span data-stu-id="1ce86-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="1ce86-173">Ez a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat.</span><span class="sxs-lookup"><span data-stu-id="1ce86-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="1ce86-174">Határozottan kevésbé jól működik, ha a cipőjét továbbra is ki szeretné próbálni.</span><span class="sxs-lookup"><span data-stu-id="1ce86-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="1ce86-175">Műveletek és függvények első osztályú értékként</span><span class="sxs-lookup"><span data-stu-id="1ce86-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="1ce86-176">Az egyik kritikus módszer, amellyel a vezérlési folyamat és a klasszikus logika a függvények helyett functions használatával történik, hogy a Q # *első osztályú*műveleteit és funkcióit használják.</span><span class="sxs-lookup"><span data-stu-id="1ce86-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="1ce86-177">Ez azt eredményezi, hogy a nyelv minden értéke a saját jobb oldalán van.</span><span class="sxs-lookup"><span data-stu-id="1ce86-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="1ce86-178">Például a következőkben teljesen érvényes Q # kód van, ha egy kicsit indirekt:</span><span class="sxs-lookup"><span data-stu-id="1ce86-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="1ce86-179">A fenti kódrészletben `ourH` változó értéke a művelet <xref:microsoft.quantum.intrinsic.h>, így például bármely más művelethez hasonlóan hívhatjuk ezt az értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce86-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="1ce86-180">Ez lehetővé teszi olyan műveletek írását, amelyek a bemenetük részeként végzik a műveleteket, és a magasabb rendű vezérlési folyamatokra vonatkozó fogalmakat képeznek.</span><span class="sxs-lookup"><span data-stu-id="1ce86-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="1ce86-181">Tegyük fel például, hogy a "Square" műveletet úgy képzeli el, hogy kétszer ugyanazt a cél qubit alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="1ce86-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="1ce86-182">Ebben a példában a `(Qubit => Unit)` típusban megjelenő `=>` nyíl azt jelzi, hogy a beviteli mező `op` egy olyan művelet, amely a `Qubit` típusként adja meg a bemenetet, és a kimenetként üres rekordot hoz létre.</span><span class="sxs-lookup"><span data-stu-id="1ce86-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="1ce86-183">Ezen túlmenően a művelet típusának jellemzőit is megadjuk, amely tartalmazza azokat az információkat, amelyek támogatottak.</span><span class="sxs-lookup"><span data-stu-id="1ce86-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="1ce86-184">Egy `(Qubit => Unit)` típusú művelet sem a `Adjoint`, sem a `Controlled`-kezelőt is támogatja.</span><span class="sxs-lookup"><span data-stu-id="1ce86-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="1ce86-185">Ha azt szeretnénk jelezni, hogy az adott típusú műveletnek támogatnia kell például az `Adjoint`-t, akkor azt adjointable kell bejelenteni.</span><span class="sxs-lookup"><span data-stu-id="1ce86-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="1ce86-186">Ez a típushoz tartozó jegyzet `is Adj` használatával végezhető el.</span><span class="sxs-lookup"><span data-stu-id="1ce86-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="1ce86-187">Hasonlóképpen `(Qubit => Unit is Ctl)` azt is jelzi, hogy az adott típusú művelet támogatja a `Controlled`-munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="1ce86-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="1ce86-188">Ezt tovább fogjuk feltárni, amikor [a Q #](xref:microsoft.quantum.language.type-model) általánosabban tárgyalt típusokról beszélünk.</span><span class="sxs-lookup"><span data-stu-id="1ce86-188">We will explore this further when we discuss [types in Q#](xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="1ce86-189">Most Kiemeljük, hogy a kimenetek részeként is visszaadhatjuk a műveleteket, így a klasszikus feltételes logika valamilyen módon elkülöníthető klasszikus függvényként, amely egy művelet formájában egy kvantum-program leírását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="1ce86-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="1ce86-190">Egyszerű példaként tekintse meg a teleportálás példáját, amelyben a kétbites klasszikus üzenetet fogadó fél az üzenetet arra használja, hogy dekódolja a qubit a megfelelő teleportált állapotba.</span><span class="sxs-lookup"><span data-stu-id="1ce86-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="1ce86-191">Ezt egy olyan függvényben írhatjuk, amely a két klasszikus bitet veszi át, és visszaadja a megfelelő dekódolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="1ce86-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="1ce86-192">Ez az új függvény valóban egy függvény, abban az esetben, ha a `hereBit` és `thereBit`megegyező értékekkel hívjuk, mindig ugyanezt a műveletet fogjuk visszakapni.</span><span class="sxs-lookup"><span data-stu-id="1ce86-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="1ce86-193">Így a dekóder biztonságosan futtatható a műveletekben anélkül, hogy meg kellene indokolnia, hogy a dekódolási logika hogyan működjön együtt a különböző műveleti szakosodások definícióinak használatával.</span><span class="sxs-lookup"><span data-stu-id="1ce86-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="1ce86-194">Ez azt is megteheti, hogy elszigetelte a klasszikus logikát egy függvényen belül, garantálva azt a fordítót, hogy a függvény hívása büntetlenül rendezhető, feltéve, hogy a bevitel megmarad.</span><span class="sxs-lookup"><span data-stu-id="1ce86-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="1ce86-195">A függvényeket az első osztályú értékekként is kezelhetjük, mivel a [műveletekről és a függvények típusairól](#operations-and-functions-as-first-class-values)részletesebben is tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="1ce86-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="1ce86-196">A műveletek és függvények részleges alkalmazása</span><span class="sxs-lookup"><span data-stu-id="1ce86-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="1ce86-197">A műveleteknek a *részleges alkalmazás*használatával történő visszaadását lehetővé tehetjük, amelyekben a bemenet egy vagy több részének megadásával egy függvénynek vagy műveletnek a tényleges hívása nélkül is megadható.</span><span class="sxs-lookup"><span data-stu-id="1ce86-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="1ce86-198">Ha például visszahívja a fenti `ApplyTwice` példát, jelezheti, hogy nem szeretnénk megadni, azonnal, hogy a bemeneti művelet melyik qubit vonatkozzon:</span><span class="sxs-lookup"><span data-stu-id="1ce86-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="1ce86-199">Ebben az esetben a helyi változó `twiceOp` a részlegesen alkalmazott művelet `ApplyTwice(op, _)`, ahol a bemenetben még nem megadott részek szerepelnek `_`.</span><span class="sxs-lookup"><span data-stu-id="1ce86-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="1ce86-200">Ha a következő sorban ténylegesen meghívja a `twiceOp`t, akkor a bemenetnek a részlegesen alkalmazott művelethez adja át az eredeti művelet összes fennmaradó részét.</span><span class="sxs-lookup"><span data-stu-id="1ce86-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="1ce86-201">Így a fenti kódrészlet gyakorlatilag azonos ahhoz, hogy `ApplyTwice(op, target)` közvetlenül meghívja őket, mentse, hogy egy új helyi változót vezettünk be, amely lehetővé teszi számunkra, hogy késleltetjük a hívást, miközben a bemenet egyes részeit biztosítjuk.</span><span class="sxs-lookup"><span data-stu-id="1ce86-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="1ce86-202">Mivel egy részlegesen alkalmazott művelet valójában nem lett meghívva, amíg a teljes adatbevitel meg nem történt, akkor a függvényekből is biztonságosan részben alkalmazhatjuk a műveleteket.</span><span class="sxs-lookup"><span data-stu-id="1ce86-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="1ce86-203">Elvileg a `SquareOperation`on belüli klasszikus logika sokkal több résztvevő lehet, de továbbra is el van különítve a többi művelettől, mert az garantálja, hogy a fordító a functions szolgáltatással kapcsolatban tud nyújtani.</span><span class="sxs-lookup"><span data-stu-id="1ce86-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="1ce86-204">Ezt a megközelítést fogja használni a Q # standard könyvtárban a klasszikus vezérlési folyamat kifejezésére, amely a kvantum-programokban könnyen használható.</span><span class="sxs-lookup"><span data-stu-id="1ce86-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
