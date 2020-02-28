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
# <a name="working-with-qubits"></a>A qubits használata

A Q # nyelv számos különböző részén láthatjuk, hogy mi is a vastag, és látni fogjuk, hogyan használhatja a qubits magukat.

## <a name="allocating-qubits"></a>Qubits foglalása

Először is a Q #-ban használható qubit beszerzéséhez `using` blokkon belül *lefoglaljuk* a qubits:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Az ily módon lefoglalt qubits a $ \ket{0}$ állapotban vannak. a fenti példában `register` tehát a $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$ értéket.
A `using` blokk végén a blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.

> [!WARNING]
> A célszámítógépek azt várják, hogy a qubits a $ \ket{0}$ állapotban legyenek közvetlenül a felszabadítás előtt, hogy újra felhasználhatók legyenek, és elérhetők legyenek más `using`-blokkokhoz a kiosztáshoz.
> Ha lehetséges, az egységes műveletekkel bármely lefoglalt qubits visszatérhet a $ \ket{0}$ értékre.
> Ha szükséges, a @"microsoft.quantum.intrinsic.reset" művelet használható egy qubit mérésére, és a mérési eredmény használatával biztosíthatja, hogy a mért qubit visszaadja a $ \ket{0}$ értékre. Az ilyen mérések megsemmisítik a felakadás a fennmaradó qubits, és így befolyásolhatják a számítást.

## <a name="intrinsic-operations"></a>Belső műveletek

A foglalást követően a rendszer egy qubit továbbíthat a functions és a Operations szolgáltatásnak.
Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.
Ezek a műveletek részletesebben jelennek meg a [belső műveletekben és a funkciókban](xref:microsoft.quantum.libraries.standard.prelude), de egyelőre megemlítünk néhány hasznos műveletet, amelyekkel a qubits lehet használni.

Először is az qubit Pauli-operátorok $X $, $Y $ és $Z $ szerepelnek a Q # által a belső műveletek `X`, `Y`és `Z`között, amelyek mindegyike rendelkezik `(Qubit => Unit is Adj + Ctl)`típussal.
A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint a $X $, és így `X`, hogy egy kicsit flip művelet vagy nem kapu.
A `X` művelet lehetővé teszi, hogy előkészítse a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumú állapotokat néhány klasszikus bites sztring $s $ esetén:

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
> Később további kompakt módokat fogunk látni a művelet megírásához, amelyek nem igénylik a manuális flow-vezérlést.

Az olyan állapotokat is elő lehet készíteni, mint például a $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ és a $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ a Hadamard átalakítás $H $, amelyet a belső művelet `H : (Qubit => Unit is Adj + Ctl)`képvisel a Q # által.

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

## <a name="measurements"></a>Mérések

A beépített, nem egységes művelettel rendelkező `Measure` művelettel kinyerheti a klasszikus adatokat egy `Qubit` típusú objektumból, és hozzárendelheti a klasszikus értéket az eredményként, amely egy fenntartott típussal rendelkezik `Result`, ami azt jelzi, hogy az eredmény már nem Quantum állapot.
A `Measure` bemenete a Bloch gömb egyik Pauli-tengelye, amelyet `Pauli` (például `PauliX`) típusú érték és `Qubit`típusú érték képvisel.

Egy egyszerű példa a következő művelet, amely egy qubit foglal le a $ \ket{0}$ állapotban, majd egy Hadamard műveletet alkalmaz `H`, és az eredményt `PauliZ` alapján méri.

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

A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` ha a `Qubit[]` típusú regiszterben lévő összes qubits egy megadott Pauli-alapon mérve nulla állapotban van, és amely a `false`t adja vissza.

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

A Q # nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.
Ez a funkció lehetővé teszi a hatékony valószínűségi minialkalmazások megvalósítását, ami csökkentheti a számítási költségeket a unitaries megvalósításához.
A Q #-ban például könnyen megvalósítható az úgynevezett *REPEAT-ig-Success* (RUS) mintázat.
Ezek az RUS-minták olyan valószínűségi programok, amelyek a *vártnál* alacsonyabb költségeket mutatnak az elemi kapuk szempontjából, de a valódi díjak a tényleges futtatástól és a különböző lehetséges elágazások tényleges elhagyása függnek.

A REPEAT-ig-Success (RUS) minták megkönnyítése érdekében a Q # támogatja a szerkezetet

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

ahol a `statementBlock1` és az `statementBlock2` nulla vagy több Q # utasítás, és `expression` bármely érvényes kifejezés, amely `Bool`típusú értékre van kiértékelve.
Tipikus használati eset esetén a következő Q # művelet elforgatást hajt végre a (Z) $ (I + 2i Z){5}/\sqrt, a Bloch szférában. Ez egy ismert RUS-minta használatával valósítható meg:

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

Ez a példa egy változtatható változó használatát mutatja be `finished`, amely a teljes REPEAT-ig-javítás ciklus hatókörében van, és amely a hurok előtt inicializálva lesz, és a javítás lépésben frissül.

Végül egy olyan RUS-mintát mutatunk be, amely a Quantum State $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $-t jeleníti meg, kezdve a $ \ket{+} $ állapottal.
Lásd még: a [standard könyvtárhoz megadott Unit Testing minta](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

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

A műveletben bemutatott jelentős programozott funkciók a hurok összetettebb `fixup` részét képezik, amely magában foglalja a kvantum-műveleteket, valamint a `AssertProb` utasítások használatát annak megállapítására, hogy a program bizonyos megadott pontjain a kvantum-állapot mérésének valószínűsége várható-e.
További információ a [`Assert`](xref:microsoft.quantum.intrinsic.assert) és [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) műveletekről: [tesztelés és hibakeresés](xref:microsoft.quantum.techniques.testing-and-debugging) .
