---
title: A qubits használata | Microsoft Docs
description: A qubits használata
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183471"
---
# <a name="working-with-qubits"></a>A qubits használata #

A Q # nyelv számos különböző részén láthatjuk, hogy mi is a vastag, és látni fogjuk, hogyan használhatja a qubits magukat.

## <a name="allocating-qubits"></a>Qubits foglalása ##

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

## <a name="intrinsic-operations"></a>Belső műveletek ##

A foglalást követően a rendszer egy qubit továbbíthat a functions és a Operations szolgáltatásnak.
Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.
Ezek a műveletek részletesebben jelennek meg a [belső műveletekben és a funkciókban](xref:microsoft.quantum.libraries.standard.prelude), de egyelőre megemlítünk néhány hasznos műveletet, amelyekkel a qubits lehet használni.

Először is az qubit Pauli-operátorok $X $, $Y $ és $Z $ szerepelnek a Q # által a belső műveletek `X`, `Y`és `Z`között, amelyek mindegyike rendelkezik `(Qubit => Unit is Adj + Ctl)`típussal.
A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint a $X $, és így `X`, hogy egy kicsit flip művelet vagy nem kapu.
Ez lehetővé teszi, hogy előkészítse a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumú állapotokat néhány klasszikus bites sztring $s $ esetén:

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
> Később további kompakt módokat fogunk látni a művelet megírásához, amelyek nem igénylik a manuális flow-vezérlést.

Olyan állapotokat is elő tudunk készíteni, mint a $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ és $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ a Hadamard átalakítás $H $ használatával , amelyet a belső művelet `H : (Qubit => Unit is Adj + Ctl)`a Q # képvisel:

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

## <a name="measurements"></a>Mérések ##

Az olyan `Measure` művelettel, amely egy belső, nem önálló művelettel rendelkezik, kinyerheti a klasszikus adatokat egy `Qubit` típusú objektumból, és hozzárendelheti a klasszikus értéket, amelynek eredményeként a lefoglalt típus `Result`, ami azt jelzi, hogy az eredmény nem már a kvantum állapota. A `Measure` bemenete egy olyan Pauli-tengely a Bloch szférában, amely egy `Pauli` típusú (azaz például `PauliX`) és egy `Qubit`típusú objektum. 

Egy egyszerű példa a következő művelet, amely egy qubit hoz létre a $ \ket{0}$ állapotban, majd Hadamard-kaput ``H``, majd a `PauliZ` alapján méri az eredményt. 

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

A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` ha egy `Qubit[]` típusú regiszterben lévő összes qubits állapota nulla, egy megadott Pauli-alapon mérve és `false` egyéb módon. 

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

A Q # nyelv lehetővé teszi a klasszikus vezérlési folyamatok függőségeit a qubits mérési eredményein. Ez a funkció lehetővé teszi, hogy hatékony, valószínűséggel rendelkező minialkalmazásokat hozzon létre, amelyek csökkenthetik a számítási költségeket a unitaries megvalósításához. Így például könnyen megvalósítható a Q #-ban az úgynevezett *ismétlés* , amely olyan valószínűségi áramkörök, amelyek a *vártnál* alacsonyabb költségeket mutatnak az elemi kapuk szempontjából, de a valódi ár a tényleges futtatástól és a ténylegestől függ. különböző lehetséges ágak összehagyása. 

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
ahol a `statementBlock1` és az `statementBlock2` nulla vagy több Q # utasítás, és `expression` bármely érvényes kifejezés, amely `Bool`típusú értékre van kiértékelve. Tipikus használati eset esetén a következő áramkör a (Z) $ (I + 2i Z){5}/\sqrt, a Bloch szférán belül egy irracionális tengely körüli rotációt valósít meg. Ez egy ismert RUS-minta használatával valósítható meg: 

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

Ez a példa egy változtatható változó használatát mutatja be `finished`, amely a teljes REPEAT-ig-javítás ciklus hatókörében van, és amely a hurok előtt inicializálva lesz, és a javítás lépésben frissül.

Végül egy olyan RUS-mintát mutatunk be, amely a Quantum State $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $-t jeleníti meg, kezdve a $ \ket{+} $ állapottal. Lásd még: a [standard könyvtárhoz megadott Unit Testing minta](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

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
 
Az ebben a műveletben bemutatott jelentős programozott funkciók összetettebb `fixup` a hurokhoz, amely magában foglalja a kvantum-műveleteket, valamint a `AssertProb` utasítások használatát annak megállapítására, hogy a kvantum-állapot mérése milyen valószínűséggel történik a program. További információ a `Assert` és `AssertProb` utasításokról: [tesztelés és hibakeresés](xref:microsoft.quantum.techniques.testing-and-debugging) . 
