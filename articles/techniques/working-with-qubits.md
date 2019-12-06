---
title: A qubits használata | Microsoft Docs
description: A qubits használata
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 477b358c3eba58b62926b4e9094770c9741cac92
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864253"
---
# <a name="working-with-qubits"></a><span data-ttu-id="45491-103">A qubits használata</span><span class="sxs-lookup"><span data-stu-id="45491-103">Working with Qubits</span></span> #

<span data-ttu-id="45491-104">A Q # nyelv számos különböző részén láthatjuk, hogy mi is a vastag, és látni fogjuk, hogyan használhatja a qubits magukat.</span><span class="sxs-lookup"><span data-stu-id="45491-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="45491-105">Qubits foglalása</span><span class="sxs-lookup"><span data-stu-id="45491-105">Allocating Qubits</span></span> ##

<span data-ttu-id="45491-106">Először is a Q #-ban használható qubit beszerzéséhez `using` blokkon belül *lefoglaljuk* a qubits:</span><span class="sxs-lookup"><span data-stu-id="45491-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="45491-107">Az ily módon lefoglalt qubits a $ \ket{0}$ állapotban vannak. a fenti példában `register` tehát a $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$ értéket.</span><span class="sxs-lookup"><span data-stu-id="45491-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="45491-108">A `using` blokk végén a blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.</span><span class="sxs-lookup"><span data-stu-id="45491-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="45491-109">A célszámítógépek azt várják, hogy a qubits a $ \ket{0}$ állapotban legyenek közvetlenül a felszabadítás előtt, hogy újra felhasználhatók legyenek, és elérhetők legyenek más `using`-blokkokhoz a kiosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="45491-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="45491-110">Ha lehetséges, az egységes műveletekkel bármely lefoglalt qubits visszatérhet a $ \ket{0}$ értékre.</span><span class="sxs-lookup"><span data-stu-id="45491-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="45491-111">Ha szükséges, a @"microsoft.quantum.intrinsic.reset" művelet használható egy qubit mérésére, és a mérési eredmény használatával biztosíthatja, hogy a mért qubit visszaadja a $ \ket{0}$ értékre.</span><span class="sxs-lookup"><span data-stu-id="45491-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="45491-112">Az ilyen mérések megsemmisítik a felakadás a fennmaradó qubits, és így befolyásolhatják a számítást.</span><span class="sxs-lookup"><span data-stu-id="45491-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span> 

## <a name="intrinsic-operations"></a><span data-ttu-id="45491-113">Belső műveletek</span><span class="sxs-lookup"><span data-stu-id="45491-113">Intrinsic Operations</span></span> ##

<span data-ttu-id="45491-114">A foglalást követően a rendszer egy qubit továbbíthat a functions és a Operations szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="45491-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="45491-115">Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.</span><span class="sxs-lookup"><span data-stu-id="45491-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="45491-116">Ezek a műveletek részletesebben jelennek meg a [belső műveletekben és a funkciókban](xref:microsoft.quantum.libraries.standard.prelude), de egyelőre megemlítünk néhány hasznos műveletet, amelyekkel a qubits lehet használni.</span><span class="sxs-lookup"><span data-stu-id="45491-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="45491-117">Először is az qubit Pauli-operátorok $X $, $Y $ és $Z $ szerepelnek a Q # által a belső műveletek `X`, `Y`és `Z`között, amelyek mindegyike rendelkezik `(Qubit => Unit is Adj + Ctl)`típussal.</span><span class="sxs-lookup"><span data-stu-id="45491-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="45491-118">A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint a $X $, és így `X`, hogy egy kicsit flip művelet vagy nem kapu.</span><span class="sxs-lookup"><span data-stu-id="45491-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="45491-119">Ez lehetővé teszi, hogy előkészítse a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumú állapotokat néhány klasszikus bites sztring $s $ esetén:</span><span class="sxs-lookup"><span data-stu-id="45491-119">This lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> <span data-ttu-id="45491-120">Később további kompakt módokat fogunk látni a művelet megírásához, amelyek nem igénylik a manuális flow-vezérlést.</span><span class="sxs-lookup"><span data-stu-id="45491-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="45491-121">Az olyan állapotokat is elő lehet készíteni, mint például a $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ és a $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ a Hadamard átalakítás $H $, amelyet a belső művelet `H : (Qubit => Unit is Adj + Ctl)`képvisel a Q # által.</span><span class="sxs-lookup"><span data-stu-id="45491-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="45491-122">Mérések</span><span class="sxs-lookup"><span data-stu-id="45491-122">Measurements</span></span> ##

<span data-ttu-id="45491-123">Az olyan `Measure` művelettel, amely egy belső, nem önálló művelettel rendelkezik, a klasszikus adatokat kinyerheti egy `Qubit` típusú objektumból, és olyan eredményként rendelhet hozzá klasszikus értéket, amelynek egy foglalt típusa `Result`, ami azt jelzi, hogy az eredmény már nem kvantum-állapot.</span><span class="sxs-lookup"><span data-stu-id="45491-123">Using the `Measure` operation, which is a built in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span> <span data-ttu-id="45491-124">A `Measure` bemenete egy olyan Pauli-tengely a Bloch szférában, amely egy `Pauli` típusú (azaz például `PauliX`) és egy `Qubit`típusú objektum.</span><span class="sxs-lookup"><span data-stu-id="45491-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by an object of type `Pauli` (i.e., for instance `PauliX`) and an object of type `Qubit`.</span></span> 

<span data-ttu-id="45491-125">Egy egyszerű példa a következő művelet, amely egy qubit hoz létre a $ \ket{0}$ állapotban, majd Hadamard-kaput ``H``, majd a `PauliZ` alapján méri az eredményt.</span><span class="sxs-lookup"><span data-stu-id="45491-125">A simple example is the following operation which creates one qubit in the $\ket{0}$ state, then applies a Hadamard gate ``H`` to it and then measures the result in the `PauliZ` basis.</span></span> 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

<span data-ttu-id="45491-126">A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` ha egy `Qubit[]` típusú regiszterben lévő összes qubits állapota nulla, egy megadott Pauli-alapon mérve és `false` egyéb módon.</span><span class="sxs-lookup"><span data-stu-id="45491-126">A slightly more complicated example is given by the following operation which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero, when measured in a specified Pauli basis and `false` otherwise.</span></span> 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="45491-127">A Q # nyelv lehetővé teszi a klasszikus vezérlési folyamatok függőségeit a qubits mérési eredményein.</span><span class="sxs-lookup"><span data-stu-id="45491-127">The Q# language allows dependencies of classical control flow on measurement results of qubits.</span></span> <span data-ttu-id="45491-128">Ez a funkció lehetővé teszi, hogy hatékony, valószínűséggel rendelkező minialkalmazásokat hozzon létre, amelyek csökkenthetik a számítási költségeket a unitaries megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="45491-128">This in turn enables to implement powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span> <span data-ttu-id="45491-129">Például egyszerűen megvalósítható a Q #-ban az úgynevezett *ismétlés* , amely olyan valószínűségi áramkörök, amelyek a *vártnál* alacsonyabb költségeket mutatnak az elemi kapuk szempontjából, de a valódi költségeket a tényleges futtatástól és a különböző lehetséges ágak tényleges elhagyása függ.</span><span class="sxs-lookup"><span data-stu-id="45491-129">As an example, it is easy to implement so-called *Repeat-Until-Success* in Q# which are probabilistic circuits that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span> 

<span data-ttu-id="45491-130">A REPEAT-ig-Success (RUS) minták megkönnyítése érdekében a Q # támogatja a szerkezetet</span><span class="sxs-lookup"><span data-stu-id="45491-130">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
<span data-ttu-id="45491-131">ahol a `statementBlock1` és az `statementBlock2` nulla vagy több Q # utasítás, és `expression` bármely érvényes kifejezés, amely `Bool`típusú értékre van kiértékelve.</span><span class="sxs-lookup"><span data-stu-id="45491-131">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span> <span data-ttu-id="45491-132">Tipikus használati eset esetén a következő áramkör a (Z) $ (I + 2i Z){5}/\sqrt, a Bloch szférán belül egy irracionális tengely körüli rotációt valósít meg.</span><span class="sxs-lookup"><span data-stu-id="45491-132">In a typical use case, the following circuit implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="45491-133">Ez egy ismert RUS-minta használatával valósítható meg:</span><span class="sxs-lookup"><span data-stu-id="45491-133">This is accomplished by using a known RUS pattern:</span></span> 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="45491-134">Ez a példa egy változtatható változó használatát mutatja be `finished`, amely a teljes REPEAT-ig-javítás ciklus hatókörében van, és amely a hurok előtt inicializálva lesz, és a javítás lépésben frissül.</span><span class="sxs-lookup"><span data-stu-id="45491-134">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="45491-135">Végül egy olyan RUS-mintát mutatunk be, amely a Quantum State $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $-t jeleníti meg, kezdve a $ \ket{+} $ állapottal.</span><span class="sxs-lookup"><span data-stu-id="45491-135">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span> <span data-ttu-id="45491-136">Lásd még: a [standard könyvtárhoz megadott Unit Testing minta](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="45491-136">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span> 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
<span data-ttu-id="45491-137">Az ebben a műveletben bemutatott jelentős programozott funkciók összetettebb `fixup` a hurokhoz, amely magában foglalja a kvantum-műveleteket, valamint a `AssertProb` utasítások használatát annak megállapítására, hogy a program bizonyos meghatározott pontjain a kvantum-állapot mérésének valószínűsége várható-e.</span><span class="sxs-lookup"><span data-stu-id="45491-137">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span> <span data-ttu-id="45491-138">További információ a `Assert` és `AssertProb` utasításokról: [tesztelés és hibakeresés](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="45491-138">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about `Assert` and `AssertProb` statements.</span></span> 
