---
title: Munkavégzés qubitekkel
description: Kitöltés leírása
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885294"
---
# <a name="working-with-qubits"></a>Munkavégzés qubitekkel

A qubits a kvantum-számítástechnika alapvető információi. A qubits általános bemutatása: a kvantum- [számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding), valamint a matematikai ábrázolás mélyebb megismerése [a Qubit](xref:microsoft.quantum.concepts.qubit). 

Ez a cikk bemutatja, hogyan használható a qubits, és hogyan használható a Q # programban. 

> [!IMPORTANT]
>A cikkben tárgyalt utasítások egyike sem érvényes a függvények törzsében. Csak a műveleteken belül érvényesek.

## <a name="allocating-qubits"></a>Qubits foglalása

Mivel a fizikai qubits értékes erőforrások a kvantum-számítógépeken, a fordító feladata, hogy a lehető leghatékonyabban használják őket.
Ezért meg kell adnia a Q #-t, hogy *lefoglalja* a qubits egy adott utasítás blokkon belül.
A qubits kioszthatja egyetlen qubit, vagy qubits tömbként is, amely *regisztrálható*. 

### <a name="clean-qubits"></a>Qubits tisztítása

Az utasítás használatával `using` új qubits foglalhat le az utasításhoz.

Az utasítás a kulcsszót tartalmazza `using` , majd egy kötést zárójelek közé, `( )` valamint azt az utasítást, amelyben a qubits elérhetők.
A kötés ugyanazt a mintát követi, mint az utasítások: egy vagy több szimbólumot `let` vagy egy szimbólumot, majd egy egyenlőségjelet `=` , és egy értéket, vagy az *inicializálók*egyező rekordját.

Az inicializálók a következők lehetnek: egyetlen qubit, `Qubit()` vagy qubits tömbje, `Qubit[n]` ahol `n` a `Int` kifejezés szerepel.
Példa:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Az ily módon lefoglalt qubits a $ \ket $ állapotban kezdődnek {0} . Így az előző példában `auxiliary` egyetlen qubit van a $ \ket {0} $ állapotban, és az `register` öt qubit állapot $ \ket {00000} = \ket \otimes \ket \otimes {0} {0} \cdots \otimes \ket {0} $.
A blokk végén a `using` blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.

> [!WARNING]
> A célszámítógépek felhasználhatják a kiosztott qubits, és a `using` kiosztáshoz más blokkokba is felkínálják azokat. A célszámítógép ezért azt várja, hogy a qubits a {0} felszabadítás előtt azonnal a $ \ket $ állapotban legyenek.
> Ha lehetséges, az egységes műveletek használatával bármilyen lefoglalt qubits visszaadhat $ \ket {0} $-ra.
> Ha szükséges, használhatja a @"microsoft.quantum.intrinsic.reset" műveletet, amely a qubit $ \ket $ értéket adja vissza a {0} méréssel, és az eredmény alapján feltételesen végrehajtja a műveletet. Egy ilyen mérték megsemmisít minden felakadás a fennmaradó qubits, és így hatással lehet a számításra.


### <a name="borrowed-qubits"></a>Kölcsönzött qubits

Használja az `borrowing` utasítást a qubits ideiglenes használatra való lefoglalásához, amely nem feltétlenül adott állapotban van.

Számítás közben a kölcsönzött qubits is felhasználhatja.
Ezek a qubits általában nem tiszta állapotban vannak, azaz nem feltétlenül lettek inicializálva olyan ismert állapotban, mint például a $ \ket {0} $.
Ezeket gyakran "piszkos" qubits nevezik, mert az állapotuk ismeretlen, és a kvantum-számítógép memóriájának más részeivel is összekeverhető.

A kötés ugyanazokat a mintákat és szabályokat követi, mint az `using` utasítás.
Példa:
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
A kölcsönzött qubits ismeretlen állapotban vannak, és az utasítás blokk végén kiléphetnek a hatókörből.
A hitelfelvevő vállalja, hogy a qubits ugyanabban az állapotban hagyja, mint amikor a kölcsönbe vették őket; vagyis az utasítás blokkjának elején és végén lévő állapotuknak azonosnak kell lennie.
Mivel ez az állapot nem feltétlenül klasszikus állapotú, a legtöbb esetben a hitelfelvételi hatókörök nem tartalmazhatnak mértékeket. 

A qubits hitelfelvételkor a rendszer először megpróbálja betölteni a kérést a használatban lévő, de az utasítás törzsében nem elérhető qubits `borrowing` .
Ha nincs elég ilyen qubits, akkor az új qubits foglal le a kérelem teljesítéséhez.

A piszkos qubits ismert használati esetei közül a több vezérelt CNEM-kapuk olyan implementációi, amelyek csak nagyon kevés qubits és a növekményes implementációt igénylik.
Ha példát kíván használni a Q #-ban, tekintse meg a [hitelfelvételi qubits példát](#borrowing-qubits-example) ebben a cikkben, vagy a [*2n + 2 qubits a Toffoli-alapú moduláris szorzást*](https://arxiv.org/abs/1611.07995) (, Roetteler és Svore 2017) használó algoritmust, amely a kölcsönzött qubits használja.

## <a name="intrinsic-operations"></a>Belső műveletek

A foglalást követően átadhat egy qubit a functions és a Operations szolgáltatásnak.
Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.

Ez a cikk néhány hasznos Q # műveletet ismertet, amelyek segítségével használhatja a qubits.
Ezekről és másokról a [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben olvashat részletesebben. 

Először is a qubit Pauli-operátorok $X $, $Y $ és $Z $ a belső műveletek [`X`](xref:microsoft.quantum.intrinsic.x) , a [`Y`](xref:microsoft.quantum.intrinsic.y) és a [`Z`](xref:microsoft.quantum.intrinsic.z) , amelyek mindegyike rendelkezik típussal `(Qubit => Unit is Adj + Ctl)` .

A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint $X $-t és így tovább, `X` mint egy kicsit flip művelet vagy nem kapu.
A `X` művelettel előkészítheti a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumú állapotokat néhány klasszikus bites sztring $s $ esetén:

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
> Később további kompakt módszereket láthat a művelet megírásához, amelyek nem igénylik a kézi vezérlés folyamatát.

Az olyan állapotokat is előkészítheti, mint például a $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ és a $ \ket {-} = \left (\ket {0} -\ket {1} \Right)/\sqrt {2} $ a Hadamard Transform $H $ paranccsal, amely a Q # által a belső műveletben [`H`](xref:microsoft.quantum.intrinsic.h) (Qubit => egység: Adj + CTL)

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

## <a name="measurements"></a>Mérések

Az egyes qubits mérései különböző alapokon végezhetők el, amelyek mindegyike egy Pauli-tengelyen található a [Bloch szférában](xref:microsoft.quantum.glossary#bloch-sphere).
A *számítási alap* a `PauliZ` mértékre hivatkozik, és a mérések leggyakoribb alapja.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Egyetlen qubit mérése az `PauliZ` alapján

A [`M`](xref:microsoft.quantum.intrinsic.m) művelettel, amely egy beépített belső, nem egységes művelet, amely egyetlen qubit mérésére szolgál, `PauliZ` és egy klasszikus értéket rendel hozzá az eredményhez.
`M`egy fenntartott visszatérési típussal rendelkezik, `Result` amely csak értékeket `Zero` vagy `One` a mért állapotoknak felel meg a $ \ket {0} $ vagy $ \ket $ értékkel, ami {1} azt jelzi, hogy az eredmény már nem kvantum-állapot.

Egy egyszerű példa a következő művelet, amely egy qubit foglal le a $ \ket {0} $ állapotban, majd Hadamard műveletet alkalmaz `H` rá, és az eredményt az `PauliZ` alapján méri.

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Egy vagy több qubits mérése adott alapokon

Ha egy vagy több qubits egy tömbjét szeretné mérni adott alapokon, használhatja a [`Measure`](xref:microsoft.quantum.intrinsic.measure) műveletet.

A bemenetek a `Measure` típusok tömbje `Pauli` (például: `[PauliX, PauliZ, PauliZ]` ), valamint a qubits tömbje.

A következő művelet valamivel bonyolultabb példát ad vissza, amely visszaadja a logikai értéket, `true` Ha a qubits lévő összes típus `Qubit[]` állapota nulla, ha a megadott Pauli-alapon van megadva, és az egyéb értéket adja vissza `false` .

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

Vegye figyelembe, hogy ez a példa egyszerre csak `Measure` az egyes qubits hajtja végre, de a művelet több qubits is kiterjeszthető a közös mérésekre.

## <a name="borrowing-qubits-example"></a>Hitelfelvételi qubits – példa

A Canon olyan példákat tartalmaz, amelyek a `borrowing` kulcsszót használják, például a következő függvényt `MultiControlledXBorrow` . Ha azt `controls` jelzi, hogy a vezérlő qubits a `X` művelethez, akkor a megvalósítás által hozzáadott piszkos [ancillas](xref:microsoft.quantum.glossary#ancilla) száma `Length(controls)-2` .

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

Vegye figyelembe, hogy ez a példa a combinator széles körű használatát használta az `With` űrlapján, amely a adjoint támogató műveletekre vonatkozik, például: `WithA` .
Ez jó programozási stílus, mert a vezérlést `With` csak a belső művelethez való hozzáférés-vezérlést érintő struktúrákhoz adja hozzá.
Azt is vegye figyelembe, hogy a `body` műveleten kívül a `controlled` művelet törzsének megvalósítását explicit módon adták meg, nem pedig egy `controlled auto` utasításhoz folyamodnak.
Ennek az az oka, hogy az áramkör szerkezete miatt könnyen hozzáadhat további vezérlőket, amelyek a vezérlésnek a-ben való hozzáadásához képest hasznosak `body` . 

Ez a kód egy másik Canon-függvénnyel hasonlítható össze `MultiControlledXClean` , amely ugyanazt a célt fogja elérni, mint egy szorzásra vezérelt `X` művelet megvalósítását, amely azonban számos tiszta qubits használ a `using` mechanizmus használatával. 

## <a name="next-steps"></a>Következő lépések

Tudnivalók a [vezérlési folyamatról](xref:microsoft.quantum.guide.controlflow) a Q #-ban.