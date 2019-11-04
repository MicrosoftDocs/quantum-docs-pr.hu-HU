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
# <a name="higher-order-control-flow"></a><span data-ttu-id="153f1-103">Magasabb rendű vezérlési folyamat</span><span class="sxs-lookup"><span data-stu-id="153f1-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="153f1-104">A standard szintű kódtár egyik elsődleges szerepköre, hogy könnyebb legyen a [kvantum-programok](https://en.wikipedia.org/wiki/Quantum_programming)segítségével kifejezni a magas szintű algoritmusos ötleteket.</span><span class="sxs-lookup"><span data-stu-id="153f1-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="153f1-105">Így a Q # Canon számos különböző Flow Control-szerkezetet biztosít, amelyek mindegyike a függvények és műveletek részleges alkalmazásával valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="153f1-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="153f1-106">Tekintse át azonnal a példát, és vegye figyelembe, hogy az egyik "CNEM-létrát" szeretné létrehozni egy regiszteren:</span><span class="sxs-lookup"><span data-stu-id="153f1-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="153f1-107">Ezt a mintát iterációs és `for` hurkok használatával lehet kifejezni:</span><span class="sxs-lookup"><span data-stu-id="153f1-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="153f1-108">A <xref:microsoft.quantum.canon.applytoeachca> és a tömb manipulációs funkciói, például a <xref:microsoft.quantum.arrays.zip>esetében azonban sokkal rövidebb és könnyebben olvasható:</span><span class="sxs-lookup"><span data-stu-id="153f1-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="153f1-109">A szakasz további részében számos példát ismertetünk arra, hogy miként használhatók a Canon által nyújtott különféle flow-vezérlési műveletek és függvények a kvantum-programok tömörítéséhez.</span><span class="sxs-lookup"><span data-stu-id="153f1-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="153f1-110">Műveletek és függvények alkalmazása tömbökön és tartományokon keresztül</span><span class="sxs-lookup"><span data-stu-id="153f1-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="153f1-111">A Canon által biztosított elsődleges absztrakciók egyike az iteráció.</span><span class="sxs-lookup"><span data-stu-id="153f1-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="153f1-112">Vegyünk például egy egységes formát, $U \otimes U \otimes \cdots \otimes U $-t egyetlen qubit egységes $U $-ra.</span><span class="sxs-lookup"><span data-stu-id="153f1-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="153f1-113">A Q #-ban használhatjuk a <xref:microsoft.quantum.arrays.indexrange>t, hogy ezt `for` hurokként adja meg a regiszterben:</span><span class="sxs-lookup"><span data-stu-id="153f1-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

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

<span data-ttu-id="153f1-114">Ezt követően ezt az új műveletet `HAll(register)`ként is használhatja $H \otimes H \otimes \cdots \otimes H $-re való alkalmazásához.</span><span class="sxs-lookup"><span data-stu-id="153f1-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="153f1-115">Ez azonban nehézkes, különösen egy nagyobb algoritmusban.</span><span class="sxs-lookup"><span data-stu-id="153f1-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="153f1-116">Emellett ez a megközelítés arra az adott műveletre specializálódott, amelyet az egyes qubit alkalmazni szeretnénk.</span><span class="sxs-lookup"><span data-stu-id="153f1-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="153f1-117">Azt is felhasználhatjuk, hogy a műveletek első osztályúak legyenek explicit módon kifejezni ezt az algoritmikus koncepciót:</span><span class="sxs-lookup"><span data-stu-id="153f1-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="153f1-118">Itt az utótag `CA` azt jelzi, hogy a `ApplyToEach` meghívása maga is adjointable és ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="153f1-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="153f1-119">Így ha `U` támogatja a `Adjoint` és a `Controlled`, a következő sorok egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="153f1-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="153f1-120">Ez azt jelenti, hogy a `ApplyToEachCA` meghívása olyan műveletekben jelenhet meg, amelyek esetében a adjoint-specializáció automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="153f1-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="153f1-121">Hasonlóképpen, <xref:microsoft.quantum.canon.applytoeachindex> hasznos lehet az űrlap `U(0, targets[0]); U(1, targets[1]); ...`mintázatának ábrázolásához, és a bemenet által támogatott összes-kombinációhoz biztosít verziókat.</span><span class="sxs-lookup"><span data-stu-id="153f1-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="153f1-122">a `ApplyToEach` Type-paraméteres, így olyan műveletekkel használható, amelyek nem `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="153f1-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="153f1-123">Tegyük fel például, hogy `codeBlocks` a <xref:microsoft.quantum.errorcorrection.logicalregister> értékek tömbje, amelyet helyre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="153f1-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="153f1-124">Ezután a `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` a hibajavítási kódot `code` és a helyreállítási függvényt is alkalmazza, `recoveryFn` az egyes blokkokra egymástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="153f1-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="153f1-125">Ez a klasszikus adatbevitelek esetében is megőrzi a következőket: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` a $ \pi/$2-es rotációt alkalmazza a $X $ értékre, amelyet $pi/$3 $Y $ értékkel való elforgatása követ.</span><span class="sxs-lookup"><span data-stu-id="153f1-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="153f1-126">A Q # Canon Emellett támogatja a funkcionális programozáshoz ismert klasszikus enumerálási mintákat is.</span><span class="sxs-lookup"><span data-stu-id="153f1-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="153f1-127">Például a <xref:microsoft.quantum.arrays.fold> implementálja a mintát $f (f (f (s\_{\text{Initial}}, x\_0), x\_1), \dots) $, hogy csökkentse a függvények listáját.</span><span class="sxs-lookup"><span data-stu-id="153f1-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="153f1-128">Ez a minta összegek, termékek, minimumok, Maxima és más hasonló függvények megvalósítására használható:</span><span class="sxs-lookup"><span data-stu-id="153f1-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="153f1-129">Hasonlóképpen, a <xref:microsoft.quantum.arrays.mapped> és <xref:microsoft.quantum.arrays.mappedbyindex> függvények is használhatók a funkcionális programozási fogalmak kifejezésére a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="153f1-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="153f1-130">Műveletek és függvények összeállítása</span><span class="sxs-lookup"><span data-stu-id="153f1-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="153f1-131">A Canon által kínált vezérlési folyamatokat a rendszer bemenetként használja fel, így hasznos lehet több művelet vagy funkció egyetlen hívható számára való összeállítására.</span><span class="sxs-lookup"><span data-stu-id="153f1-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="153f1-132">Például a "^ {\dagger} $ $UVU minta rendkívül gyakori a kvantum-programozásban – úgy, hogy a Canon a műveletet <xref:microsoft.quantum.canon.applywith> a minta absztrakciója adja meg.</span><span class="sxs-lookup"><span data-stu-id="153f1-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="153f1-133">Ez az absztrakció azt is lehetővé teszi, hogy hatékonyabb Compliation legyenek a áramkörök, mivel a sorozatban `U(qubit); V(qubit); Adjoint U(qubit);` nem kell az egyes `U`okra `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="153f1-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="153f1-134">Ha ezt szeretné látni, hagyja, hogy $c (U) $ legyen az egységes képviselő `Controlled U([control], target)`, és hagyja, hogy a $c (V) $ azonos módon legyen definiálva.</span><span class="sxs-lookup"><span data-stu-id="153f1-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="153f1-135">Ezután egy tetszőleges állapothoz $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ ket{1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="153f1-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="153f1-136">a \end{align} a `Controlled`definíciója szerint.</span><span class="sxs-lookup"><span data-stu-id="153f1-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="153f1-137">Másrészről a \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="153f1-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="153f1-138">a \end{align} lineárisan következtetünk arra, hogy az összes bemeneti állapothoz így $U $-t is fel lehet venni.</span><span class="sxs-lookup"><span data-stu-id="153f1-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="153f1-139">Vagyis $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="153f1-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="153f1-140">Mivel a vezérlési műveletek általában költségesek lehetnek, az ellenőrzött változatok (például a `WithC` és a `WithCA`) segítségével csökkentheti az alkalmazandó vezérlő-kezelők számát.</span><span class="sxs-lookup"><span data-stu-id="153f1-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="153f1-141">A $U $ kiszámításának egyik másik következménye, hogy még nem kell tudnia, hogyan kell alkalmazni a `Controlled`-munkafolyamatot `U`re.</span><span class="sxs-lookup"><span data-stu-id="153f1-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="153f1-142">`ApplyWithCA` ezért a vártnál gyengébb aláírással rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="153f1-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="153f1-143">Hasonlóképpen <xref:microsoft.quantum.canon.bind> olyan műveleteket hoz létre, amelyek más műveletek sorozatot alkalmaznak.</span><span class="sxs-lookup"><span data-stu-id="153f1-143">Similarly, <xref:microsoft.quantum.canon.bind> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="153f1-144">Például a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="153f1-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

<span data-ttu-id="153f1-145">Az iterációs minták kombinálásával ez különösen hasznos lehet:</span><span class="sxs-lookup"><span data-stu-id="153f1-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="153f1-146">Idősorba rendezett összeállítás</span><span class="sxs-lookup"><span data-stu-id="153f1-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="153f1-147">Továbbra is folytathatja a flow-szabályozást a részleges alkalmazás-és klasszikus függvények szempontjából, és a klasszikus folyamatok szabályozása szempontjából is elég kifinomult kvantum-fogalmakat modellez.</span><span class="sxs-lookup"><span data-stu-id="153f1-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="153f1-148">Ez az analógia pontosan az a felismerés, hogy az egységes operátorok pontosan megfelelnek a hívási műveletek mellékhatásának, így az egységes operátorok bármely más, az egységes operátorok által meghatározott bontása megfelel egy adott adat létrehozásának. olyan klasszikus alrutinok hívási sorrendje, amelyek az adott egységes operátorként való műveletre vonatkozó utasításokat bocsátanak ki.</span><span class="sxs-lookup"><span data-stu-id="153f1-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="153f1-149">Ebben a nézetben a `Bind` pontosan a mátrix termékének ábrázolását mutatja, mivel a `Bind([A, B])(target)` egyenértékű a `A(target); B(target);`, ami viszont a $BA $ értéknek megfelelő hívási sorrend.</span><span class="sxs-lookup"><span data-stu-id="153f1-149">Under this view, `Bind` is precisely the representation of the matrix product, since `Bind([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="153f1-150">Kifinomultabb példa a [Trotter – Suzuki bővítése](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="153f1-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="153f1-151">Ahogy azt az [adatstruktúrák](xref:microsoft.quantum.libraries.data-structures)dinamikus generátoros ábrázolási szakasza is tárgyalja, a Trotter – Suzuki terjeszkedés különösen hasznos módszert kínál a mátrixok exponenciális kifejezésére.</span><span class="sxs-lookup"><span data-stu-id="153f1-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="153f1-152">Például, ha a legalacsonyabb sorrendben alkalmazza a terjeszkedést, hogy minden operátornál $A $ és $B $, hogy $A = A ^ \dagger $ és $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i A t/n) \exp (i B t/n ) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="153f1-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="153f1-153">\end{align}, ez azt mondja, hogy a $A + B $ alatti állapotot hozzávetőlegesen $A $ és $B $ alatt fejlesztjük.</span><span class="sxs-lookup"><span data-stu-id="153f1-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="153f1-154">Ha a $A $ alatt lévő evolúciót jelöli egy `A : (Double, Qubit[]) => Unit`, amely a következőt alkalmazza: $e ^ {i t A} $, akkor a Trotter – a Suzuki bővítése a hívási folyamatok átrendezése szempontjából egyértelművé válik.</span><span class="sxs-lookup"><span data-stu-id="153f1-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="153f1-155">Konkrétan, egy olyan művelet `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl`, amely `A = U(0, _, _)` és `B = U(1, _, _)`egy olyan új műveletet határozhat meg, amely az űrlap `U` $t</span><span class="sxs-lookup"><span data-stu-id="153f1-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="153f1-156">Ezen a ponton most már a Trotter – Suzuki kiterjesztésre is hivatkozhatunk, *anélkül, hogy a kvantum-mechanikara*lenne szükség.</span><span class="sxs-lookup"><span data-stu-id="153f1-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="153f1-157">A bővítés gyakorlatilag egy nagyon különleges iterációs minta, amelyet a $ \eqref{EQ: Trotter-Suzuki-0} $ alapján motiválnak.</span><span class="sxs-lookup"><span data-stu-id="153f1-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="153f1-158">Ezt az iterációs mintát a <xref:microsoft.quantum.canon.decomposeintotimestepsca>implementálja:</span><span class="sxs-lookup"><span data-stu-id="153f1-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="153f1-159">`DecomposeIntoTimeStepsCA` aláírása a Q #-ban közös mintát követ, ahol a tömbök vagy a menetben lévő elemeket olyan gyűjtemények képviselik, amelyek az első `Int` elemeknek a hosszát jelző rekordok jelölik.</span><span class="sxs-lookup"><span data-stu-id="153f1-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="153f1-160">Összerakva: vezérlési műveletek</span><span class="sxs-lookup"><span data-stu-id="153f1-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="153f1-161">Végül a Canon a `Controlled`-üzemben is felépíthető, ha további lehetőségeket biztosít a kvantum-műveletek feltételéhez.</span><span class="sxs-lookup"><span data-stu-id="153f1-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="153f1-162">Gyakori – különösen a Quantum aritmetika esetében – a \ket{0\cdots 0} $-től eltérő számítási alapon végrehajtott műveletek feltétele.</span><span class="sxs-lookup"><span data-stu-id="153f1-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="153f1-163">A fentiekben bemutatott vezérlési műveletek és függvények használatával egyetlen utasításban több általános kvantum-feltétel is megadható.</span><span class="sxs-lookup"><span data-stu-id="153f1-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="153f1-164">Ugorjunk a <xref:microsoft.quantum.canon.controlledonbitstring> működésének módjára (Sans Type Parameters), majd a darabokat egyenként fogjuk bontani.</span><span class="sxs-lookup"><span data-stu-id="153f1-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="153f1-165">Az első dolog, hogy meg kell határoznia egy olyan műveletet, amely valójában a vezérlő tetszőleges számítási alapon történő megvalósításának jelentős mértékű feloldását végzi.</span><span class="sxs-lookup"><span data-stu-id="153f1-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="153f1-166">Ezt a műveletet nem hívjuk közvetlenül, és így a név elejéhez hozzáadunk `_`, hogy azt jelezze, hogy egy másik szerkezet implementációja máshol.</span><span class="sxs-lookup"><span data-stu-id="153f1-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

<span data-ttu-id="153f1-167">Vegye figyelembe, hogy egy `Bool` tömbként jelölt bitet használunk, amellyel megadhatjuk, hogy milyen feltételt kívánunk alkalmazni az általunk megadott művelet `oracle`.</span><span class="sxs-lookup"><span data-stu-id="153f1-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="153f1-168">Mivel ez a művelet ténylegesen az alkalmazást közvetlenül végzi el, a vezérlő és a cél regisztereket is el kell végezni, mindkettőt `Qubit[]`ként ábrázoljuk.</span><span class="sxs-lookup"><span data-stu-id="153f1-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="153f1-169">Ezt követően vegye figyelembe, hogy a következő számítási állapotot kell megadnia: $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ a $ \vec{s} $ értékre való átalakításával a $ \ket{\vec{s}} $-t $ \ket{0\cdots 0} $ értékre alakíthatja át.</span><span class="sxs-lookup"><span data-stu-id="153f1-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="153f1-170">Különösen a $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="153f1-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="153f1-171">Mivel $X ^ {\dagger} = X $, ez azt jelenti, hogy a $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="153f1-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="153f1-172">Ezért alkalmazhatjuk $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, alkalmazza `Controlled oracle`, és alakítsa vissza a $ \vec{s} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="153f1-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="153f1-173">Ez az építés pontosan `ApplyWith`, ezért az új művelet törzsét ennek megfelelően írjuk:</span><span class="sxs-lookup"><span data-stu-id="153f1-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="153f1-174">Itt a <xref:microsoft.quantum.canon.applypaulifrombitstring> alkalmazta a $P $ használatára, részlegesen alkalmazva a célt a `ApplyWith`használatával való használatra.</span><span class="sxs-lookup"><span data-stu-id="153f1-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="153f1-175">Vegye figyelembe azonban, hogy a *vezérlő* regisztrációját át kell alakítani a kívánt űrlapra, ezért részben alkalmazzuk a *cél*belső műveletét `(Controlled oracle)`.</span><span class="sxs-lookup"><span data-stu-id="153f1-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="153f1-176">Ezzel a `ApplyWith` úgy viselkedik, hogy a vezérlési regisztert $P $, pontosan a kívánt módon regisztrálja.</span><span class="sxs-lookup"><span data-stu-id="153f1-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="153f1-177">Ezen a ponton megtehetjük, de valahogy nem teljesül, hogy az új művelet nem "érzi", mint a `Controlled`-felhasználó alkalmazás alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="153f1-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="153f1-178">Így az új vezérlési folyamat fogalmának meghatározása egy olyan függvény megírásával történik, amely az Oracle felügyeletét végzi, és új műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="153f1-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="153f1-179">Így úgy tűnik, hogy az új függvény nagyon hasonlít a `Controlled`ra, és bemutatjuk, hogy könnyen definiáljuk a Q # és a Canon együttes használatával a hatékony új vezérlési folyamat szerkezetét:</span><span class="sxs-lookup"><span data-stu-id="153f1-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
