---
title: 'A Q # standard libararies lévő flow-vezérlők'
description: 'Ismerkedjen meg a Microsoft Q # standard Library folyamat-vezérlési műveleteivel és funkcióival.'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275017"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="59c30-103">Magasabb rendű vezérlési folyamat</span><span class="sxs-lookup"><span data-stu-id="59c30-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="59c30-104">A standard szintű kódtár egyik elsődleges szerepköre, hogy könnyebb legyen a [kvantum-programok](https://en.wikipedia.org/wiki/Quantum_programming)segítségével kifejezni a magas szintű algoritmusos ötleteket.</span><span class="sxs-lookup"><span data-stu-id="59c30-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="59c30-105">Így a Q # Canon számos különböző Flow Control-szerkezetet biztosít, amelyek mindegyike a függvények és műveletek részleges alkalmazásával valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="59c30-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="59c30-106">Tekintse át azonnal a példát, és vegye figyelembe, hogy az egyik "CNEM-létrát" szeretné létrehozni egy regiszteren:</span><span class="sxs-lookup"><span data-stu-id="59c30-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="59c30-107">Ezt a mintát iteráció és hurkok használatával lehet kifejezni `for` :</span><span class="sxs-lookup"><span data-stu-id="59c30-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="59c30-108">A <xref:microsoft.quantum.canon.applytoeachca> és a tömbben kifejezett manipulációs függvények, például a <xref:microsoft.quantum.arrays.zip> , ez sokkal rövidebb és könnyebben olvasható:</span><span class="sxs-lookup"><span data-stu-id="59c30-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="59c30-109">A szakasz további részében számos példát ismertetünk arra, hogy miként használhatók a Canon által nyújtott különféle flow-vezérlési műveletek és függvények a kvantum-programok tömörítéséhez.</span><span class="sxs-lookup"><span data-stu-id="59c30-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="59c30-110">Műveletek és függvények alkalmazása tömbökön és tartományokon keresztül</span><span class="sxs-lookup"><span data-stu-id="59c30-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="59c30-111">A Canon által biztosított elsődleges absztrakciók egyike az iteráció.</span><span class="sxs-lookup"><span data-stu-id="59c30-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="59c30-112">Vegyünk például egy egységes formát, $U \otimes U \otimes \cdots \otimes U $-t egyetlen qubit egységes $U $-ra.</span><span class="sxs-lookup"><span data-stu-id="59c30-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="59c30-113">A Q #-ban felhasználhatjuk, <xref:microsoft.quantum.arrays.indexrange> hogy ezt a következő módon használjuk `for` hurokként egy regiszterben:</span><span class="sxs-lookup"><span data-stu-id="59c30-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="59c30-114">Ezt követően ezt az új műveletet úgy használhatja, `HAll(register)` hogy alkalmazza $H \Otimes h \otimes \cdots \Otimes h $-t.</span><span class="sxs-lookup"><span data-stu-id="59c30-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="59c30-115">Ez azonban nehézkes, különösen egy nagyobb algoritmusban.</span><span class="sxs-lookup"><span data-stu-id="59c30-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="59c30-116">Emellett ez a megközelítés arra az adott műveletre specializálódott, amelyet az egyes qubit alkalmazni szeretnénk.</span><span class="sxs-lookup"><span data-stu-id="59c30-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="59c30-117">Azt is felhasználhatjuk, hogy a műveletek első osztályúak legyenek explicit módon kifejezni ezt az algoritmikus koncepciót:</span><span class="sxs-lookup"><span data-stu-id="59c30-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="59c30-118">Itt az utótag `CA` azt jelzi, hogy a hívása `ApplyToEach` maga is adjointable és ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="59c30-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="59c30-119">Így ha `U` a támogatja `Adjoint` és `Controlled` a-t, a következő sorok egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="59c30-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="59c30-120">Ez azt jelenti, hogy a `ApplyToEachCA` megjelenő hívások olyan műveletekben jelenhetnek meg, amelyeknél a adjoint-specializáció automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="59c30-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="59c30-121">Hasonlóképpen, az <xref:microsoft.quantum.canon.applytoeachindex> űrlap mintázatának ábrázolására is hasznos, `U(0, targets[0]); U(1, targets[1]); ...` és a bemenetek által támogatott összes-kombinációhoz biztosít verziókat.</span><span class="sxs-lookup"><span data-stu-id="59c30-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="59c30-122">`ApplyToEach`a Type-paraméter úgy van megadva, hogy olyan műveletekkel is használható legyen, amelyek nem a (z) értéket használják `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="59c30-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="59c30-123">Tegyük fel például, hogy a `codeBlocks` <xref:microsoft.quantum.errorcorrection.logicalregister> helyreállításhoz szükséges értékek tömbje.</span><span class="sxs-lookup"><span data-stu-id="59c30-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="59c30-124">Ezután `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` alkalmazza a hiba – a kód és a `code` helyreállítási függvényt az `recoveryFn` egyes blokkokra egymástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="59c30-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="59c30-125">Ez a klasszikus bemenetek esetében is `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` érvényes: a $ \pi/$2 rotációját alkalmazza a $X $ értékre, amelyet a $PI/$3 $Y $ értékkel való elforgatása követ.</span><span class="sxs-lookup"><span data-stu-id="59c30-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="59c30-126">A Q # Canon Emellett támogatja a funkcionális programozáshoz ismert klasszikus enumerálási mintákat is.</span><span class="sxs-lookup"><span data-stu-id="59c30-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="59c30-127">Például <xref:microsoft.quantum.arrays.fold> implementálja a mintát $f (f (f (s \_ {\text{Initial}}, x \_ 0), x \_ 1), \dots) $, hogy csökkentse a függvények listáját.</span><span class="sxs-lookup"><span data-stu-id="59c30-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="59c30-128">Ez a minta összegek, termékek, minimumok, Maxima és más hasonló függvények megvalósítására használható:</span><span class="sxs-lookup"><span data-stu-id="59c30-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="59c30-129">Hasonlóképpen, a (z <xref:microsoft.quantum.arrays.mapped> ) és a függvények <xref:microsoft.quantum.arrays.mappedbyindex> a funkcionális programozási fogalmakat is kihasználhatják a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="59c30-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="59c30-130">Műveletek és függvények összeállítása</span><span class="sxs-lookup"><span data-stu-id="59c30-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="59c30-131">A Canon által kínált vezérlési folyamatokat a rendszer bemenetként használja fel, így hasznos lehet több művelet vagy funkció egyetlen hívható számára való összeállítására.</span><span class="sxs-lookup"><span data-stu-id="59c30-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="59c30-132">Például a "^ {\dagger} $ $UVU minta rendkívül gyakori a kvantum-programozásban – úgy, hogy a Canon a műveletet <xref:microsoft.quantum.canon.applywith> absztraktként adja meg ehhez a mintához.</span><span class="sxs-lookup"><span data-stu-id="59c30-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="59c30-133">Ez az absztrakció azt is lehetővé teszi, hogy a folyamatok hatékonyabb Compliation legyenek, ahogy `Controlled` a sorozatot illetően `U(qubit); V(qubit); Adjoint U(qubit);` nem kell mindegyikre hatnia `U` .</span><span class="sxs-lookup"><span data-stu-id="59c30-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="59c30-134">Ha ezt szeretné látni, hagyja, hogy $c (U) $ legyen az egységes képviselő, `Controlled U([control], target)` és hagyja, hogy a $c (V) $ azonos módon legyen definiálva.</span><span class="sxs-lookup"><span data-stu-id="59c30-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="59c30-135">Ezután egy tetszőleges állapothoz $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (UVU ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="59c30-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="59c30-136">a \end{align} a definíciója szerint `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="59c30-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="59c30-137">Másrészről a \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes u) (c (v)) (\boldone \otimes u ^ \dagger) \ket {0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="59c30-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="59c30-138">a \end{align} lineárisan következtetünk arra, hogy az összes bemeneti állapothoz így $U $-t is fel lehet venni.</span><span class="sxs-lookup"><span data-stu-id="59c30-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="59c30-139">Vagyis $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="59c30-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="59c30-140">Mivel a vezérlési műveletek általában költségesek lehetnek, az ellenőrzött változatok, például a `WithC` és `WithCA` a segítségével csökkentheti az alkalmazandó vezérlő-kezelők számát.</span><span class="sxs-lookup"><span data-stu-id="59c30-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="59c30-141">A $U $ kiszámításának egyik másik következménye, hogy nem kell még azt is tudnia, hogy hogyan kell alkalmazni az üzemben lévőket `Controlled` `U` .</span><span class="sxs-lookup"><span data-stu-id="59c30-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="59c30-142">`ApplyWithCA`Ezért a vártnál gyengébb aláírással rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="59c30-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="59c30-143">Hasonlóképpen <xref:microsoft.quantum.canon.bound> olyan műveleteket állít elő, amelyek más műveletek sorozatot alkalmaznak.</span><span class="sxs-lookup"><span data-stu-id="59c30-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="59c30-144">Például a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="59c30-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="59c30-145">Az iterációs minták kombinálásával ez különösen hasznos lehet:</span><span class="sxs-lookup"><span data-stu-id="59c30-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="59c30-146">Idősorba rendezett összeállítás</span><span class="sxs-lookup"><span data-stu-id="59c30-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="59c30-147">Továbbra is folytathatja a flow-szabályozást a részleges alkalmazás-és klasszikus függvények szempontjából, és a klasszikus folyamatok szabályozása szempontjából is elég kifinomult kvantum-fogalmakat modellez.</span><span class="sxs-lookup"><span data-stu-id="59c30-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="59c30-148">Ez az analógia pontosan az a felismerés, hogy az egységes operátorok pontosan megegyeznek a hívási műveletek mellékhatásával, így az egységes operátorok más, az egységes operátorok általi lebomlása megfelel egy adott hívási sorrend létrehozásához a klasszikus alrutinok számára, amelyek olyan utasításokat bocsátanak ki, amelyek adott egységes operátorként működnek.</span><span class="sxs-lookup"><span data-stu-id="59c30-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="59c30-149">Ebben a nézetben `Bound` pontosan a mátrix termék ábrázolása, mivel az `Bound([A, B])(target)` egyenértékű a következővel, `A(target); B(target);` amely viszont a $ba $ értéknek megfelelő hívási sorrend.</span><span class="sxs-lookup"><span data-stu-id="59c30-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="59c30-150">Kifinomultabb példa a [Trotter – Suzuki bővítése](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="59c30-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="59c30-151">Ahogy azt az [adatstruktúrák](xref:microsoft.quantum.libraries.data-structures)dinamikus generátoros ábrázolási szakasza is tárgyalja, a Trotter – Suzuki terjeszkedés különösen hasznos módszert kínál a mátrixok exponenciális kifejezésére.</span><span class="sxs-lookup"><span data-stu-id="59c30-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="59c30-152">Például, ha a legalacsonyabb sorrendben alkalmazza a terjeszkedést, az olyan operátorok esetében, $A $ és $B $, hogy $A = A ^ \dagger $ és $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i A t/n) \exp (i B t/n) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="59c30-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="59c30-153">\end{align}, ez azt mondja, hogy a $A + B $ alatti állapotot hozzávetőlegesen $A $ és $B $ alatt fejlesztjük.</span><span class="sxs-lookup"><span data-stu-id="59c30-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="59c30-154">Ha a $A $ alatti evolúciót jelöli egy olyan művelettel, amely a következőt `A : (Double, Qubit[]) => Unit` alkalmazza: $e ^ {i t A} $, akkor a Trotter – Suzuki terjeszkedés a hívási folyamatok átrendezése szempontjából egyértelművé válik.</span><span class="sxs-lookup"><span data-stu-id="59c30-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="59c30-155">Konkrétan egy művelet, `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` amely egy olyan műveletet `A = U(0, _, _)` `B = U(1, _, _)` határoz meg, amely a `U` (z) $t $ időpontban való integrálása melletti új műveletet is definiálhat az űrlap létrehozásával</span><span class="sxs-lookup"><span data-stu-id="59c30-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="59c30-156">Ezen a ponton most már a Trotter – Suzuki kiterjesztésre is hivatkozhatunk, *anélkül, hogy a kvantum-mechanikara*lenne szükség.</span><span class="sxs-lookup"><span data-stu-id="59c30-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="59c30-157">A bővítés gyakorlatilag egy nagyon különleges iterációs minta, amelyet a $ \eqref{EQ: Trotter-Suzuki-0} $ alapján motiválnak.</span><span class="sxs-lookup"><span data-stu-id="59c30-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="59c30-158">Ezt az iterációs mintát a következő implementálja <xref:microsoft.quantum.canon.decomposeintotimestepsca> :</span><span class="sxs-lookup"><span data-stu-id="59c30-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="59c30-159">Az aláírás a `DecomposeIntoTimeStepsCA` következő általános mintát követi a Q #-ban, ahol olyan gyűjtemények jelenhetnek meg, amelyek a tömbökben vagy a menet közbeni elemek kiszámításához használhatók, és amelyek az első elemek rekordok jelölik `Int`</span><span class="sxs-lookup"><span data-stu-id="59c30-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="59c30-160">Összerakva: vezérlési műveletek</span><span class="sxs-lookup"><span data-stu-id="59c30-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="59c30-161">Végül a Canon a `Controlled` feltételhez további lehetőségeket biztosít a kvantum-műveletek megkötésére.</span><span class="sxs-lookup"><span data-stu-id="59c30-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="59c30-162">Gyakori – különösen a Quantum aritmetika esetében – a \ket{0\cdots 0} $-től eltérő számítási alapon végrehajtott műveletek feltétele.</span><span class="sxs-lookup"><span data-stu-id="59c30-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="59c30-163">A fentiekben bemutatott vezérlési műveletek és függvények használatával egyetlen utasításban több általános kvantum-feltétel is megadható.</span><span class="sxs-lookup"><span data-stu-id="59c30-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="59c30-164">Ismerkedjen meg a <xref:microsoft.quantum.canon.controlledonbitstring> következővel: Hogyan (Sans Type Parameters), majd a darabokat eggyel bontják le.</span><span class="sxs-lookup"><span data-stu-id="59c30-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="59c30-165">Az első dolog, hogy meg kell határoznia egy olyan műveletet, amely valójában a vezérlő tetszőleges számítási alapon történő megvalósításának jelentős mértékű feloldását végzi.</span><span class="sxs-lookup"><span data-stu-id="59c30-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="59c30-166">Ezt a műveletet nem hívjuk közvetlenül, és így a név elejéhez hozzáadjuk azt, `_` hogy jelezze, hogy egy másik szerkezet implementációja máshol.</span><span class="sxs-lookup"><span data-stu-id="59c30-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="59c30-167">Vegye figyelembe, hogy egy tömbként jelölt BITS-karakterláncot `Bool` használunk, amellyel megadhatjuk, hogy milyen feltételt szeretnénk alkalmazni a megadott művelethez `oracle` .</span><span class="sxs-lookup"><span data-stu-id="59c30-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="59c30-168">Mivel ez a művelet ténylegesen az alkalmazást közvetlenül végzi el, a vezérlő és a cél regisztereket is el kell végeznie, mindkettőt pedig a következőként ábrázoljuk `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="59c30-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="59c30-169">Ezt követően vegye figyelembe, hogy a $ \ket{\vec{s}} $ értéknek a $ \ket{0\cdots $ értékre való átalakításával a $ \ket{\vec{s}} = \ket{s \_ 0 s 1 \dots s {n-1}} $ kiszámítási állapotának vezérlését a $ \_ \_ \vec{s} $ értékre konvertálva lehet megvalósítani.</span><span class="sxs-lookup"><span data-stu-id="59c30-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="59c30-170">Különösen a $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="59c30-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="59c30-171">Mivel $X ^ {\dagger} = X $, ez azt jelenti, hogy a $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="59c30-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="59c30-172">Ezért alkalmazhatjuk $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $, Apply `Controlled oracle` , és retransform to $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="59c30-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="59c30-173">Ez az építés pontosan működik `ApplyWith` , ezért az új művelet törzsét ennek megfelelően írjuk:</span><span class="sxs-lookup"><span data-stu-id="59c30-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="59c30-174">Itt <xref:microsoft.quantum.canon.applypaulifrombitstring> alkalmazta a $P $-t, részben alkalmazva azt a cél használatára a szolgáltatással való használatra `ApplyWith` .</span><span class="sxs-lookup"><span data-stu-id="59c30-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="59c30-175">Vegye figyelembe azonban, hogy a *vezérlő* regisztrációját át kell alakítani a kívánt űrlapra, ezért részben alkalmazzuk a belső műveletet a `(Controlled oracle)` *célhelyen*.</span><span class="sxs-lookup"><span data-stu-id="59c30-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="59c30-176">Így `ApplyWith` a vezérlő regisztrálása a $P $ értékkel pontosan úgy működik, ahogy a kívánt módon.</span><span class="sxs-lookup"><span data-stu-id="59c30-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="59c30-177">Ezen a ponton megtehetjük, de valahogy nem teljesül, hogy az új műveletünk nem "érzi", mint az elmaradó alkalmazása `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="59c30-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="59c30-178">Így az új vezérlési folyamat fogalmának meghatározása egy olyan függvény megírásával történik, amely az Oracle felügyeletét végzi, és új műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="59c30-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="59c30-179">Így úgy tűnik, hogy az új függvény nagyon hasonlít `Controlled` , és bemutatjuk, hogy könnyen definiáljuk a Q # és a Canon együttes használatával a hatékony új vezérlési folyamatokat:</span><span class="sxs-lookup"><span data-stu-id="59c30-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
