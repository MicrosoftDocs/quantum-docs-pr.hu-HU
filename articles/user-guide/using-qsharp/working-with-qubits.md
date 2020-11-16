---
title: Munkavégzés qubitekkel
description: 'A qubits használatának megismerése Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 9a3d7e03016332a04ac9d1610428b6fcd546d1f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691576"
---
# <a name="working-with-qubits"></a><span data-ttu-id="4a9d6-103">Munkavégzés qubitekkel</span><span class="sxs-lookup"><span data-stu-id="4a9d6-103">Working with qubits</span></span>

<span data-ttu-id="4a9d6-104">A qubits a kvantum-számítástechnika alapvető információi.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="4a9d6-105">A qubits általános bemutatása: a kvantum- [számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding), valamint a matematikai ábrázolás mélyebb megismerése [a Qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="4a9d6-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="4a9d6-106">Ez a cikk azt ismerteti, hogyan használható a qubits egy Q# programban.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="4a9d6-107">A cikkben tárgyalt utasítások egyike sem érvényes a függvények törzsében.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="4a9d6-108">Csak a műveleteken belül érvényesek.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="4a9d6-109">Qubits foglalása</span><span class="sxs-lookup"><span data-stu-id="4a9d6-109">Allocating Qubits</span></span>

<span data-ttu-id="4a9d6-110">Mivel a fizikai qubits értékes erőforrások a kvantum-számítógépeken, a fordító feladata, hogy a lehető leghatékonyabban használják őket.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="4a9d6-111">Ezért meg kell adnia, hogy a Q# qubits egy adott utasítás blokkon belül kell-e *lefoglalni* .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="4a9d6-112">A qubits kioszthatja egyetlen qubit, vagy qubits tömbként is, amely *regisztrálható* .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register* .</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="4a9d6-113">Qubits tisztítása</span><span class="sxs-lookup"><span data-stu-id="4a9d6-113">Clean qubits</span></span>

<span data-ttu-id="4a9d6-114">Az utasítás használatával `using` új qubits foglalhat le az utasításhoz.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="4a9d6-115">Az utasítás a kulcsszót tartalmazza `using` , majd egy kötést zárójelek közé, `( )` valamint azt az utasítást, amelyben a qubits elérhetők.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="4a9d6-116">A kötés ugyanazt a mintát követi, mint az utasítások: egy vagy több szimbólumot `let` vagy egy szimbólumot, majd egy egyenlőségjelet `=` , és egy értéket, vagy az *inicializálók* egyező rekordját.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers* .</span></span>

<span data-ttu-id="4a9d6-117">Az inicializálók a következők lehetnek: egyetlen qubit, `Qubit()` vagy qubits tömbje, `Qubit[n]` ahol `n` a `Int` kifejezés szerepel.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="4a9d6-118">Például:</span><span class="sxs-lookup"><span data-stu-id="4a9d6-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="4a9d6-119">Az ily módon lefoglalt qubits a $ \ket $ állapotban kezdődnek {0} .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="4a9d6-120">Így az előző példában `auxiliary` egyetlen qubit van a $ \ket {0} $ állapotban, és az `register` öt qubit állapot $ \ket {00000} = \ket \otimes \ket \otimes {0} {0} \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="4a9d6-121">A blokk végén a `using` blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="4a9d6-122">A célszámítógépek felhasználhatják a kiosztott qubits, és a `using` kiosztáshoz más blokkokba is felkínálják azokat.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="4a9d6-123">A célszámítógép ezért azt várja, hogy a qubits a {0} felszabadítás előtt azonnal a $ \ket $ állapotban legyenek.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="4a9d6-124">Ha lehetséges, az egységes műveletek használatával bármilyen lefoglalt qubits visszaadhat $ \ket {0} $-ra.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="4a9d6-125">Ha szükséges, használhatja a @"microsoft.quantum.intrinsic.reset" műveletet, amely a qubit $ \ket $ értéket adja vissza a {0} méréssel, és az eredmény alapján feltételesen végrehajtja a műveletet.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="4a9d6-126">Egy ilyen mérték megsemmisít minden felakadás a fennmaradó qubits, és így hatással lehet a számításra.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="4a9d6-127">Kölcsönzött qubits</span><span class="sxs-lookup"><span data-stu-id="4a9d6-127">Borrowed Qubits</span></span>

<span data-ttu-id="4a9d6-128">Használja az `borrowing` utasítást a qubits ideiglenes használatra való lefoglalásához, amely nem feltétlenül adott állapotban van.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="4a9d6-129">Számítás közben a kölcsönzött qubits is felhasználhatja.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="4a9d6-130">Ezek a qubits általában nem tiszta állapotban vannak, azaz nem feltétlenül lettek inicializálva olyan ismert állapotban, mint például a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="4a9d6-131">Ezeket gyakran "piszkos" qubits nevezik, mert az állapotuk ismeretlen, és a kvantum-számítógép memóriájának más részeivel is összekeverhető.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="4a9d6-132">A kötés ugyanazokat a mintákat és szabályokat követi, mint az `using` utasítás.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="4a9d6-133">Például:</span><span class="sxs-lookup"><span data-stu-id="4a9d6-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="4a9d6-134">A kölcsönzött qubits ismeretlen állapotban vannak, és az utasítás blokk végén kiléphetnek a hatókörből.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="4a9d6-135">A hitelfelvevő vállalja, hogy a qubits ugyanabban az állapotban hagyja, mint amikor a kölcsönbe vették őket; vagyis az utasítás blokkjának elején és végén lévő állapotuknak azonosnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="4a9d6-136">Mivel ez az állapot nem feltétlenül klasszikus állapotú, a legtöbb esetben a hitelfelvételi hatókörök nem tartalmazhatnak mértékeket.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="4a9d6-137">A qubits hitelfelvételkor a rendszer először megpróbálja betölteni a kérést a használatban lévő, de az utasítás törzsében nem elérhető qubits `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="4a9d6-138">Ha nincs elég ilyen qubits, akkor az új qubits foglal le a kérelem teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="4a9d6-139">A piszkos qubits ismert használati esetei közül a több vezérelt CNEM-kapuk olyan implementációi, amelyek csak nagyon kevés qubits és a növekményes implementációt igénylik.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="4a9d6-140">A alkalmazásban való használatáról például a Q# cikk a [qubits](#borrowing-qubits-example) című cikkben, a [*2n + 2 qubits pedig a Toffoli-alapú moduláris szorzás*](https://arxiv.org/abs/1611.07995) (a Roetteler és a Svore 2017) használatával című témakörben találhat példát a kölcsönzött qubits használó algoritmusra.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="4a9d6-141">Belső műveletek</span><span class="sxs-lookup"><span data-stu-id="4a9d6-141">Intrinsic Operations</span></span>

<span data-ttu-id="4a9d6-142">A foglalást követően átadhat egy qubit a functions és a Operations szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="4a9d6-143">Bizonyos értelemben ez azt eredményezi, hogy egy Q# program qubit végezhető el, mivel az elvégezhető műveletek mindegyike műveletként van definiálva.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="4a9d6-144">Ez a cikk néhány hasznos műveletet mutat be, amelyek segítségével használhatja a Q# qubits.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="4a9d6-145">Ezekről és másokról a [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben olvashat részletesebben.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="4a9d6-146">Első lépésként a qubit Pauli-operátorok $X $, $Y $ és $Z $ a Q# belső műveletek, a és a [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`Y`](xref:Microsoft.Quantum.Intrinsic.Y) [`Z`](xref:Microsoft.Quantum.Intrinsic.Z) , amelyek mindegyike rendelkezik típussal `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:Microsoft.Quantum.Intrinsic.X), [`Y`](xref:Microsoft.Quantum.Intrinsic.Y), and [`Z`](xref:Microsoft.Quantum.Intrinsic.Z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="4a9d6-147">A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint $X $-t és így tovább, `X` mint egy kicsit flip művelet vagy nem kapu.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="4a9d6-148">A `X` művelettel előkészítheti a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumú állapotokat néhány klasszikus bites sztring $s $ esetén:</span><span class="sxs-lookup"><span data-stu-id="4a9d6-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="4a9d6-149">Később további kompakt módszereket láthat a művelet megírásához, amelyek nem igénylik a kézi vezérlés folyamatát.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="4a9d6-150">Az olyan állapotokat is előkészítheti, mint például a $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ és a $ \ket {-} = \left (\ket {0} -\ket {1} \Right)/\sqrt {2} $ a Hadamard Transform $H $ paranccsal, amelyet Q# a belső művelet [`H`](xref:Microsoft.Quantum.Intrinsic.H) (Qubit => egység: Adj + CTL) ") használ:</span><span class="sxs-lookup"><span data-stu-id="4a9d6-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:Microsoft.Quantum.Intrinsic.H) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="4a9d6-151">Mérések</span><span class="sxs-lookup"><span data-stu-id="4a9d6-151">Measurements</span></span>

<span data-ttu-id="4a9d6-152">Az egyes qubits mérései különböző alapokon végezhetők el, amelyek mindegyike egy Pauli-tengelyen található a [Bloch szférában](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="4a9d6-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="4a9d6-153">A *számítási alap* a `PauliZ` mértékre hivatkozik, és a mérések leggyakoribb alapja.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="4a9d6-154">Egyetlen qubit mérése az `PauliZ` alapján</span><span class="sxs-lookup"><span data-stu-id="4a9d6-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="4a9d6-155">A [`M`](xref:Microsoft.Quantum.Intrinsic.M) művelettel, amely egy beépített belső, nem egységes művelet, amely egyetlen qubit mérésére szolgál, `PauliZ` és egy klasszikus értéket rendel hozzá az eredményhez.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-155">Use the [`M`](xref:Microsoft.Quantum.Intrinsic.M) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="4a9d6-156">`M` egy fenntartott visszatérési típussal rendelkezik, `Result` amely csak értékeket `Zero` vagy `One` a mért állapotoknak felel meg a $ \ket {0} $ vagy $ \ket $ értékkel, ami {1} azt jelzi, hogy az eredmény már nem kvantum-állapot.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="4a9d6-157">Egy egyszerű példa a következő művelet, amely egy qubit foglal le a $ \ket {0} $ állapotban, majd Hadamard műveletet alkalmaz `H` rá, és az eredményt az `PauliZ` alapján méri.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="4a9d6-158">Egy vagy több qubits mérése adott alapokon</span><span class="sxs-lookup"><span data-stu-id="4a9d6-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="4a9d6-159">Ha egy vagy több qubits egy tömbjét szeretné mérni adott alapokon, használhatja a [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) műveletet.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) operation.</span></span>

<span data-ttu-id="4a9d6-160">A bemenetek a `Measure` típusok tömbje `Pauli` (például: `[PauliX, PauliZ, PauliZ]` ), valamint a qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="4a9d6-161">A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` Ha a qubits lévő összes típus `Qubit[]` állapota nulla, ha a megadott Pauli-alapon van megadva, és az egyéb értéket adja vissza `false` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="4a9d6-162">Vegye figyelembe, hogy ez a példa egyszerre csak `Measure` az egyes qubits hajtja végre, de a művelet több qubits is kiterjeszthető a közös mérésekre.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="4a9d6-163">Hitelfelvételi qubits – példa</span><span class="sxs-lookup"><span data-stu-id="4a9d6-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="4a9d6-164">A Canon olyan példákat tartalmaz, amelyek a `borrowing` kulcsszót használják, például a következő függvényt `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="4a9d6-165">Ha azt `controls` jelzi, hogy a vezérlő qubits a `X` művelethez, akkor a megvalósítás által hozzáadott piszkos [ancillas](xref:microsoft.quantum.glossary#ancilla) száma `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="4a9d6-166">Vegye figyelembe, hogy ez a példa a combinator széles körű használatát használta az `With` űrlapján, amely a adjoint támogató műveletekre vonatkozik, például: `WithA` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="4a9d6-167">Ez jó programozási stílus, mert a vezérlést `With` csak a belső művelethez való hozzáférés-vezérlést érintő struktúrákhoz adja hozzá.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="4a9d6-168">Azt is vegye figyelembe, hogy a `body` műveleten kívül a `controlled` művelet törzsének megvalósítását explicit módon adták meg, nem pedig egy `controlled auto` utasításhoz folyamodnak.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="4a9d6-169">Ennek az az oka, hogy az áramkör szerkezete miatt könnyen hozzáadhat további vezérlőket, amelyek a vezérlésnek a-ben való hozzáadásához képest hasznosak `body` .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="4a9d6-170">Ez a kód egy másik Canon-függvénnyel hasonlítható össze `MultiControlledXClean` , amely ugyanazt a célt fogja elérni, mint egy szorzásra vezérelt `X` művelet megvalósítását, amely azonban számos tiszta qubits használ a `using` mechanizmus használatával.</span><span class="sxs-lookup"><span data-stu-id="4a9d6-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="4a9d6-171">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="4a9d6-171">Next steps</span></span>

<span data-ttu-id="4a9d6-172">Ismerje meg a [vezérlés folyamatát](xref:microsoft.quantum.guide.controlflow) a alkalmazásban Q# .</span><span class="sxs-lookup"><span data-stu-id="4a9d6-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>