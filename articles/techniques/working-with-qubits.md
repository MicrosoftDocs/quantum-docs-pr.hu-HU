---
title: A qubits használata
description: Megtudhatja, hogyan foglalhat le qubits, hogyan használhatja őket a műveletekben és a függvényekben, és mérje fel az eredményeket.
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907647"
---
# <a name="working-with-qubits"></a><span data-ttu-id="03e8a-103">A qubits használata</span><span class="sxs-lookup"><span data-stu-id="03e8a-103">Working with Qubits</span></span>

<span data-ttu-id="03e8a-104">A Q # nyelv számos különböző részén láthatjuk, hogy mi is a vastag, és látni fogjuk, hogyan használhatja a qubits magukat.</span><span class="sxs-lookup"><span data-stu-id="03e8a-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="03e8a-105">Qubits foglalása</span><span class="sxs-lookup"><span data-stu-id="03e8a-105">Allocating Qubits</span></span>

<span data-ttu-id="03e8a-106">Először is a Q #-ban használható qubit beszerzéséhez `using` blokkon belül *lefoglaljuk* a qubits:</span><span class="sxs-lookup"><span data-stu-id="03e8a-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="03e8a-107">Az ily módon lefoglalt qubits a $ \ket{0}$ állapotban vannak. a fenti példában `register` tehát a $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$ értéket.</span><span class="sxs-lookup"><span data-stu-id="03e8a-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="03e8a-108">A `using` blokk végén a blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.</span><span class="sxs-lookup"><span data-stu-id="03e8a-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="03e8a-109">A célszámítógépek azt várják, hogy a qubits a $ \ket{0}$ állapotban legyenek közvetlenül a felszabadítás előtt, hogy újra felhasználhatók legyenek, és elérhetők legyenek más `using`-blokkokhoz a kiosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="03e8a-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="03e8a-110">Ha lehetséges, az egységes műveletekkel bármely lefoglalt qubits visszatérhet a $ \ket{0}$ értékre.</span><span class="sxs-lookup"><span data-stu-id="03e8a-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="03e8a-111">Ha szükséges, a @"microsoft.quantum.intrinsic.reset" művelet használható egy qubit mérésére, és a mérési eredmény használatával biztosíthatja, hogy a mért qubit visszaadja a $ \ket{0}$ értékre.</span><span class="sxs-lookup"><span data-stu-id="03e8a-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="03e8a-112">Az ilyen mérések megsemmisítik a felakadás a fennmaradó qubits, és így befolyásolhatják a számítást.</span><span class="sxs-lookup"><span data-stu-id="03e8a-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="03e8a-113">Belső műveletek</span><span class="sxs-lookup"><span data-stu-id="03e8a-113">Intrinsic Operations</span></span>

<span data-ttu-id="03e8a-114">A foglalást követően a rendszer egy qubit továbbíthat a functions és a Operations szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="03e8a-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="03e8a-115">Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.</span><span class="sxs-lookup"><span data-stu-id="03e8a-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="03e8a-116">Ezek a műveletek részletesebben jelennek meg a [belső műveletekben és a funkciókban](xref:microsoft.quantum.libraries.standard.prelude), de egyelőre megemlítünk néhány hasznos műveletet, amelyekkel a qubits lehet használni.</span><span class="sxs-lookup"><span data-stu-id="03e8a-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="03e8a-117">Először is az qubit Pauli-operátorok $X $, $Y $ és $Z $ szerepelnek a Q # által a belső műveletek `X`, `Y`és `Z`között, amelyek mindegyike rendelkezik `(Qubit => Unit is Adj + Ctl)`típussal.</span><span class="sxs-lookup"><span data-stu-id="03e8a-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="03e8a-118">A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint a $X $, és így `X`, hogy egy kicsit flip művelet vagy nem kapu.</span><span class="sxs-lookup"><span data-stu-id="03e8a-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="03e8a-119">A `X` művelet lehetővé teszi, hogy előkészítse a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumú állapotokat néhány klasszikus bites sztring $s $ esetén:</span><span class="sxs-lookup"><span data-stu-id="03e8a-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="03e8a-120">Később további kompakt módokat fogunk látni a művelet megírásához, amelyek nem igénylik a manuális flow-vezérlést.</span><span class="sxs-lookup"><span data-stu-id="03e8a-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="03e8a-121">Az olyan állapotokat is elő lehet készíteni, mint például a $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ és a $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ a Hadamard átalakítás $H $, amelyet a belső művelet `H : (Qubit => Unit is Adj + Ctl)`képvisel a Q # által.</span><span class="sxs-lookup"><span data-stu-id="03e8a-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="03e8a-122">Mérések</span><span class="sxs-lookup"><span data-stu-id="03e8a-122">Measurements</span></span>

<span data-ttu-id="03e8a-123">A beépített, nem egységes művelettel rendelkező `Measure` művelettel kinyerheti a klasszikus adatokat egy `Qubit` típusú objektumból, és hozzárendelheti a klasszikus értéket az eredményként, amely egy fenntartott típussal rendelkezik `Result`, ami azt jelzi, hogy az eredmény már nem Quantum állapot.</span><span class="sxs-lookup"><span data-stu-id="03e8a-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="03e8a-124">A `Measure` bemenete a Bloch gömb egyik Pauli-tengelye, amelyet `Pauli` (például `PauliX`) típusú érték és `Qubit`típusú érték képvisel.</span><span class="sxs-lookup"><span data-stu-id="03e8a-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="03e8a-125">Egy egyszerű példa a következő művelet, amely egy qubit foglal le a $ \ket{0}$ állapotban, majd egy Hadamard műveletet alkalmaz `H`, és az eredményt `PauliZ` alapján méri.</span><span class="sxs-lookup"><span data-stu-id="03e8a-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="03e8a-126">A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` ha a `Qubit[]` típusú regiszterben lévő összes qubits egy megadott Pauli-alapon mérve nulla állapotban van, és amely a `false`t adja vissza.</span><span class="sxs-lookup"><span data-stu-id="03e8a-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="03e8a-127">A Q # nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.</span><span class="sxs-lookup"><span data-stu-id="03e8a-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="03e8a-128">Ez a funkció lehetővé teszi a hatékony valószínűségi minialkalmazások megvalósítását, ami csökkentheti a számítási költségeket a unitaries megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="03e8a-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="03e8a-129">A Q #-ban például könnyen megvalósítható az úgynevezett *REPEAT-ig-Success* (RUS) mintázat.</span><span class="sxs-lookup"><span data-stu-id="03e8a-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="03e8a-130">Ezek az RUS-minták olyan valószínűségi programok, amelyek a *vártnál* alacsonyabb költségeket mutatnak az elemi kapuk szempontjából, de a valódi díjak a tényleges futtatástól és a különböző lehetséges elágazások tényleges elhagyása függnek.</span><span class="sxs-lookup"><span data-stu-id="03e8a-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="03e8a-131">A REPEAT-ig-Success (RUS) minták megkönnyítése érdekében a Q # támogatja a szerkezetet</span><span class="sxs-lookup"><span data-stu-id="03e8a-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="03e8a-132">ahol a `statementBlock1` és az `statementBlock2` nulla vagy több Q # utasítás, és `expression` bármely érvényes kifejezés, amely `Bool`típusú értékre van kiértékelve.</span><span class="sxs-lookup"><span data-stu-id="03e8a-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="03e8a-133">Tipikus használati eset esetén a következő Q # művelet elforgatást hajt végre a (Z) $ (I + 2i Z){5}/\sqrt, a Bloch szférában.</span><span class="sxs-lookup"><span data-stu-id="03e8a-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="03e8a-134">Ez egy ismert RUS-minta használatával valósítható meg:</span><span class="sxs-lookup"><span data-stu-id="03e8a-134">This is accomplished by using a known RUS pattern:</span></span>

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

<span data-ttu-id="03e8a-135">Ez a példa egy változtatható változó használatát mutatja be `finished`, amely a teljes REPEAT-ig-javítás ciklus hatókörében van, és amely a hurok előtt inicializálva lesz, és a javítás lépésben frissül.</span><span class="sxs-lookup"><span data-stu-id="03e8a-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="03e8a-136">Végül egy olyan RUS-mintát mutatunk be, amely a Quantum State $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $-t jeleníti meg, kezdve a $ \ket{+} $ állapottal.</span><span class="sxs-lookup"><span data-stu-id="03e8a-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="03e8a-137">Lásd még: a [standard könyvtárhoz megadott Unit Testing minta](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="03e8a-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
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

<span data-ttu-id="03e8a-138">A műveletben bemutatott jelentős programozott funkciók a hurok összetettebb `fixup` részét képezik, amely magában foglalja a kvantum-műveleteket, valamint a `AssertProb` utasítások használatát annak megállapítására, hogy a program bizonyos megadott pontjain a kvantum-állapot mérésének valószínűsége várható-e.</span><span class="sxs-lookup"><span data-stu-id="03e8a-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="03e8a-139">További információ a [`Assert`](xref:microsoft.quantum.intrinsic.assert) és [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) műveletekről: [tesztelés és hibakeresés](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="03e8a-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
