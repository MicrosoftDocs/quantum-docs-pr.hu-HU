---
title: Munkavégzés qubitekkel
description: Kitöltés leírása
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430934"
---
# <a name="working-with-qubits"></a><span data-ttu-id="9e39f-103">Munkavégzés qubitekkel</span><span class="sxs-lookup"><span data-stu-id="9e39f-103">Working with qubits</span></span>

<span data-ttu-id="9e39f-104">A Q # nyelv számos különböző részén láthatjuk, hogy mi is a vastag, és látni fogjuk, hogyan használhatja a qubits magukat.</span><span class="sxs-lookup"><span data-stu-id="9e39f-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="9e39f-105">Vegye figyelembe, hogy a függvények törzsében egyik utasítás sem engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="9e39f-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="9e39f-106">Csak a műveleteken belül érvényesek.</span><span class="sxs-lookup"><span data-stu-id="9e39f-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="9e39f-107">Qubits foglalása</span><span class="sxs-lookup"><span data-stu-id="9e39f-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="9e39f-108">Qubits tisztítása</span><span class="sxs-lookup"><span data-stu-id="9e39f-108">Clean qubits</span></span>

<span data-ttu-id="9e39f-109">Az `using` utasítás az új qubits *lefoglalására* szolgál az utasítási blokkokban való használatra.</span><span class="sxs-lookup"><span data-stu-id="9e39f-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="9e39f-110">Az utasítás a kulcsszót tartalmazza `using` , majd egy nyitó zárójelet `(` , egy kötést, egy záró zárójelet `)` , valamint azt az utasítás-blokkot, amelyen belül a qubits elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="9e39f-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="9e39f-111">A kötés ugyanazt a mintát követi, mint az utasítások: egy vagy több szimbólumot `let` vagy egy szimbólumot, majd egy egyenlőségjelet `=` , és egy értéket, vagy az *inicializálók*egyező rekordját.</span><span class="sxs-lookup"><span data-stu-id="9e39f-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="9e39f-112">Az inicializálók a következők lehetnek: egyetlen qubit, `Qubit()` vagy qubits tömbje, `Qubit[n]` ahol `n` a `Int` kifejezés szerepel.</span><span class="sxs-lookup"><span data-stu-id="9e39f-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="9e39f-113">Például:</span><span class="sxs-lookup"><span data-stu-id="9e39f-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="9e39f-114">Az ily módon lefoglalt qubits a $ \ket {0} $ állapotban vannak, a fenti példában `register` tehát a $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $ állapotú állapotban van.</span><span class="sxs-lookup"><span data-stu-id="9e39f-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="9e39f-115">A blokk végén a `using` blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.</span><span class="sxs-lookup"><span data-stu-id="9e39f-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="9e39f-116">A célszámítógépek azt várják, hogy a qubits a {0} deallokáció előtt azonnal a $ \ket $ állapotban legyenek, hogy újra felhasználhatók legyenek, és más blokkok számára is elérhetők legyenek a `using` kiosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="9e39f-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="9e39f-117">Ha lehetséges, az egységes műveletek használatával bármilyen lefoglalt qubits visszaadhat $ \ket {0} $-ra.</span><span class="sxs-lookup"><span data-stu-id="9e39f-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="9e39f-118">Ha szükséges, a @"microsoft.quantum.intrinsic.reset" művelet használható egy qubit mérésére, és a mérési eredmény használatával biztosíthatja, hogy a mért qubit visszaadja a $ \ket $ értékre {0} .</span><span class="sxs-lookup"><span data-stu-id="9e39f-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="9e39f-119">Az ilyen mérések megsemmisítik a felakadás a fennmaradó qubits, és így befolyásolhatják a számítást.</span><span class="sxs-lookup"><span data-stu-id="9e39f-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="9e39f-120">Kölcsönzött qubits</span><span class="sxs-lookup"><span data-stu-id="9e39f-120">Borrowed Qubits</span></span>

<span data-ttu-id="9e39f-121">Az `borrowing` utasítás a qubits ideiglenes használatra való elérhetővé tételére szolgál, amelyek nem igényelnek konkrét állapotot.</span><span class="sxs-lookup"><span data-stu-id="9e39f-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="9e39f-122">A hitelfelvételi mechanizmus lehetővé teszi az olyan qubits kiosztását, amelyek felhasználhatók a kiszámítások során felmerülő területként.</span><span class="sxs-lookup"><span data-stu-id="9e39f-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="9e39f-123">Ezek a qubits általában nem tiszta állapotban vannak, azaz nem feltétlenül inicializálva vannak olyan ismert állapotban, mint például a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9e39f-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="9e39f-124">Ezeket gyakran "piszkos" qubits nevezik, mert az állapotuk ismeretlen, és a kvantum-számítógép memóriájának más részeivel is összekeverhető.</span><span class="sxs-lookup"><span data-stu-id="9e39f-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="9e39f-125">A kötés ugyanazokat a mintákat és szabályokat követi, mint egy `using` utasításban.</span><span class="sxs-lookup"><span data-stu-id="9e39f-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="9e39f-126">Például:</span><span class="sxs-lookup"><span data-stu-id="9e39f-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="9e39f-127">A kölcsönzött qubits ismeretlen állapotban vannak, és az utasítás blokk végén kiléphetnek a hatókörből.</span><span class="sxs-lookup"><span data-stu-id="9e39f-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="9e39f-128">A hitelfelvevő vállalja, hogy a qubits ugyanabban az állapotban hagyja, mint amikor a kölcsönbe kerültek, azaz az utasítás blokkjának elején és végén lévő állapotuknak azonosnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9e39f-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="9e39f-129">Ez az állapot különösen nem feltétlenül klasszikus állapotban van, így a legtöbb esetben a hitelfelvételi hatókörök nem tartalmazhatnak mértékeket.</span><span class="sxs-lookup"><span data-stu-id="9e39f-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="9e39f-130">A qubits hitelfelvételkor a rendszer először megpróbálja betölteni a kérést a használatban lévő qubits, de az utasítás törzse nem fér hozzá `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="9e39f-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="9e39f-131">Ha nincs elég ilyen qubits, akkor a kérés teljesítéséhez új qubits fog kiosztani.</span><span class="sxs-lookup"><span data-stu-id="9e39f-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="9e39f-132">A piszkos qubits ismert használati esetei közül a több vezérelt CNEM-kapuk olyan implementációi, amelyek csak nagyon kevés qubits és a növekményes implementációt igénylik.</span><span class="sxs-lookup"><span data-stu-id="9e39f-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="9e39f-133">Tekintse meg az alábbi [hitelfelvételi qubits példát](#borrowing-qubits-example) a Q #-ban való használatra, illetve a [*2n + 2 qubits a Toffoli-alapú moduláris szorzással*](https://arxiv.org/abs/1611.07995) (a, a Roetteler és a Svore 2017) való használatára egy olyan algoritmus esetében, amely a kölcsönzött qubits használja.</span><span class="sxs-lookup"><span data-stu-id="9e39f-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="9e39f-134">Belső műveletek</span><span class="sxs-lookup"><span data-stu-id="9e39f-134">Intrinsic Operations</span></span>

<span data-ttu-id="9e39f-135">A foglalást követően a rendszer egy qubit továbbíthat a functions és a Operations szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="9e39f-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="9e39f-136">Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.</span><span class="sxs-lookup"><span data-stu-id="9e39f-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="9e39f-137">Ezek a műveletek részletesebben jelennek meg a [belső műveletekben és a funkciókban](xref:microsoft.quantum.libraries.standard.prelude), de egyelőre megemlítünk néhány hasznos műveletet, amelyekkel a qubits lehet használni.</span><span class="sxs-lookup"><span data-stu-id="9e39f-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="9e39f-138">Először is a qubit Pauli-operátorok $X $, $Y $ és $Z $ a belső műveletek `X` , a `Y` és a `Z` , amelyek mindegyike rendelkezik típussal `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="9e39f-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="9e39f-139">A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint $X $-t és így továbbra is áttekinthető `X` műveletnek számítunk, és nem kapunk.</span><span class="sxs-lookup"><span data-stu-id="9e39f-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="9e39f-140">A `X` művelet lehetővé teszi, hogy a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumban készítse elő az egyes klasszikus bites karakterláncok $s $:</span><span class="sxs-lookup"><span data-stu-id="9e39f-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="9e39f-141">Később további kompakt módokat fogunk látni a művelet megírásához, amelyek nem igénylik a manuális flow-vezérlést.</span><span class="sxs-lookup"><span data-stu-id="9e39f-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="9e39f-142">Az olyan állapotokat is elő lehet készíteni, mint például a $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ és a $ \ket {-} = \left (\ket {0} -\ket {1} \Right)/\sqrt {2} $ a Hadamard Transform $H $ paranccsal, amelyet a belső művelet a Q # képvisel `H : (Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="9e39f-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="9e39f-143">Mérések</span><span class="sxs-lookup"><span data-stu-id="9e39f-143">Measurements</span></span>

<span data-ttu-id="9e39f-144">A `Measure` beépített belső, nem önálló művelettel rendelkező művelettel kinyerheti a klasszikus adatokat egy típusú objektumból, `Qubit` és hozzárendelheti a klasszikus értéket, amely egy fenntartott típussal rendelkezik, ami azt `Result` jelzi, hogy az eredmény már nem kvantum-állapot.</span><span class="sxs-lookup"><span data-stu-id="9e39f-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="9e39f-145">A bemenet a `Measure` Bloch gömb egyik Pauli-tengelye, amelynek típusa `Pauli` (például `PauliX` ) és egy típusú érték `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="9e39f-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="9e39f-146">Egy egyszerű példa a következő művelet, amely egy qubit foglal le a $ \ket {0} $ állapotban, majd Hadamard műveletet alkalmaz `H` rá, és az eredményt az `PauliZ` alapján méri.</span><span class="sxs-lookup"><span data-stu-id="9e39f-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="9e39f-147">A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` Ha a qubits lévő összes típus `Qubit[]` állapota nulla, ha a megadott Pauli-alapon van megadva, és az egyéb értéket adja vissza `false` .</span><span class="sxs-lookup"><span data-stu-id="9e39f-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

## <a name="borrowing-qubits-example"></a><span data-ttu-id="9e39f-148">Hitelfelvételi qubits – példa</span><span class="sxs-lookup"><span data-stu-id="9e39f-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="9e39f-149">A Canonban vannak olyan példák, amelyek a `borrowing` kulcsszót használják, például az `MultiControlledXBorrow` alább definiált függvényt.</span><span class="sxs-lookup"><span data-stu-id="9e39f-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="9e39f-150">Ha azt `controls` a vezérlő qubits jelöli, amelyet hozzá szeretne adni egy `X` művelethez, akkor ez a `Length(controls)-2` megvalósítás számos inkonzisztens ancillas ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="9e39f-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="9e39f-151">Vegye figyelembe, hogy a `With` ---combinator a adjoint-t támogató műveletekre alkalmazható, például `WithA` ---a jelen példában.</span><span class="sxs-lookup"><span data-stu-id="9e39f-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="9e39f-152">Ez jó programozási stílus, mert a vezérlést `With` csak a belső művelethez való hozzáférés-vezérlést érintő struktúrákhoz adja hozzá.</span><span class="sxs-lookup"><span data-stu-id="9e39f-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="9e39f-153">Továbbá vegye figyelembe, hogy a `body` műveleten kívül a `controlled` művelet törzsének megvalósítását explicit módon adták meg, nem pedig egy `controlled auto` utasításhoz.</span><span class="sxs-lookup"><span data-stu-id="9e39f-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="9e39f-154">Ennek az az oka, hogy tisztában vagyunk az áramkör struktúrájával, így könnyen hozzáadhat további vezérlőket, amelyek hasznosak a vezérlés hozzáadásához az egyes és minden egyes kapuhoz képest `body` .</span><span class="sxs-lookup"><span data-stu-id="9e39f-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="9e39f-155">Ez a kód egy másik Canon-függvénnyel hasonlítható össze `MultiControlledXClean` , amely ugyanazt a célt fogja elérni, mint egy szorzásra vezérelt `X` művelet megvalósítását, amely azonban számos tiszta qubits használ a `using` mechanizmus használatával.</span><span class="sxs-lookup"><span data-stu-id="9e39f-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="9e39f-156">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="9e39f-156">What's Next?</span></span>
<span data-ttu-id="9e39f-157">Tudnivalók a [vezérlési folyamatról](xref:microsoft.quantum.guide.controlflow) a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="9e39f-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>