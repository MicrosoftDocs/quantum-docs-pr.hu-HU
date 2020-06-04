---
title: Munkavégzés qubitekkel
description: Kitöltés leírása
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327543"
---
# <a name="working-with-qubits"></a>Munkavégzés qubitekkel

A Q # nyelv számos különböző részén láthatjuk, hogy mi is a vastag, és látni fogjuk, hogyan használhatja a qubits magukat.

Vegye figyelembe, hogy a függvények törzsében egyik utasítás sem engedélyezett.
Csak a műveleteken belül érvényesek.

## <a name="allocating-qubits"></a>Qubits foglalása

### <a name="clean-qubits"></a>Qubits tisztítása

Az `using` utasítás az új qubits *lefoglalására* szolgál az utasítási blokkokban való használatra.

Az utasítás a kulcsszót tartalmazza `using` , majd egy nyitó zárójelet `(` , egy kötést, egy záró zárójelet `)` , valamint azt az utasítás-blokkot, amelyen belül a qubits elérhető lesz.
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

Az ily módon lefoglalt qubits a $ \ket {0} $ állapotban vannak, a fenti példában `register` tehát a $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $ állapotú állapotban van.
A blokk végén a `using` blokk által lefoglalt összes qubits azonnal felszabadítva lesz, és nem használható tovább.

> [!WARNING]
> A célszámítógépek azt várják, hogy a qubits a {0} deallokáció előtt azonnal a $ \ket $ állapotban legyenek, hogy újra felhasználhatók legyenek, és más blokkok számára is elérhetők legyenek a `using` kiosztáshoz.
> Ha lehetséges, az egységes műveletek használatával bármilyen lefoglalt qubits visszaadhat $ \ket {0} $-ra.
> Ha szükséges, a @"microsoft.quantum.intrinsic.reset" művelet használható egy qubit mérésére, és a mérési eredmény használatával biztosíthatja, hogy a mért qubit visszaadja a $ \ket $ értékre {0} . Az ilyen mérések megsemmisítik a felakadás a fennmaradó qubits, és így befolyásolhatják a számítást.


### <a name="borrowed-qubits"></a>Kölcsönzött qubits

Az `borrowing` utasítás a qubits ideiglenes használatra való elérhetővé tételére szolgál, amelyek nem igényelnek konkrét állapotot.

A hitelfelvételi mechanizmus lehetővé teszi az olyan qubits kiosztását, amelyek felhasználhatók a kiszámítások során felmerülő területként.
Ezek a qubits általában nem tiszta állapotban vannak, azaz nem feltétlenül inicializálva vannak olyan ismert állapotban, mint például a $ \ket {0} $.
Ezeket gyakran "piszkos" qubits nevezik, mert az állapotuk ismeretlen, és a kvantum-számítógép memóriájának más részeivel is összekeverhető.

A kötés ugyanazokat a mintákat és szabályokat követi, mint egy `using` utasításban.
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
A hitelfelvevő vállalja, hogy a qubits ugyanabban az állapotban hagyja, mint amikor a kölcsönbe kerültek, azaz az utasítás blokkjának elején és végén lévő állapotuknak azonosnak kell lennie.
Ez az állapot különösen nem feltétlenül klasszikus állapotban van, így a legtöbb esetben a hitelfelvételi hatókörök nem tartalmazhatnak mértékeket. 

A qubits hitelfelvételkor a rendszer először megpróbálja betölteni a kérést a használatban lévő qubits, de az utasítás törzse nem fér hozzá `borrowing` .
Ha nincs elég ilyen qubits, akkor a kérés teljesítéséhez új qubits fog kiosztani.


A piszkos qubits ismert használati esetei közül a több vezérelt CNEM-kapuk olyan implementációi, amelyek csak nagyon kevés qubits és a növekményes implementációt igénylik.
Tekintse meg az alábbi [hitelfelvételi qubits példát](#borrowing-qubits-example) a Q #-ban való használatra, illetve a [*2n + 2 qubits a Toffoli-alapú moduláris szorzással*](https://arxiv.org/abs/1611.07995) (a, a Roetteler és a Svore 2017) való használatára egy olyan algoritmus esetében, amely a kölcsönzött qubits használja.


## <a name="intrinsic-operations"></a>Belső műveletek

A foglalást követően a rendszer egy qubit továbbíthat a functions és a Operations szolgáltatásnak.
Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud csinálni, mivel a végrehajtandó műveletek mindegyike műveletként van definiálva.
Ezek a műveletek részletesebben jelennek meg a [belső műveletekben és a funkciókban](xref:microsoft.quantum.libraries.standard.prelude), de egyelőre megemlítünk néhány hasznos műveletet, amelyekkel a qubits lehet használni.

Először is a qubit Pauli-operátorok $X $, $Y $ és $Z $ a belső műveletek `X` , a `Y` és a `Z` , amelyek mindegyike rendelkezik típussal `(Qubit => Unit is Adj + Ctl)` .
A [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude)című témakörben leírtak szerint $X $-t és így továbbra is áttekinthető `X` műveletnek számítunk, és nem kapunk.
A `X` művelet lehetővé teszi, hogy a (z) $ \ket{s_0 s_1 \dots s_n} $ formátumban készítse elő az egyes klasszikus bites karakterláncok $s $:

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

Az olyan állapotokat is elő lehet készíteni, mint például a $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ és a $ \ket {-} = \left (\ket {0} -\ket {1} \Right)/\sqrt {2} $ a Hadamard Transform $H $ paranccsal, amelyet a belső művelet a Q # képvisel `H : (Qubit => Unit is Adj + Ctl)` .

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

A `Measure` beépített belső, nem önálló művelettel rendelkező művelettel kinyerheti a klasszikus adatokat egy típusú objektumból, `Qubit` és hozzárendelheti a klasszikus értéket, amely egy fenntartott típussal rendelkezik, ami azt `Result` jelzi, hogy az eredmény már nem kvantum-állapot.
A bemenet a `Measure` Bloch gömb egyik Pauli-tengelye, amelynek típusa `Pauli` (például `PauliX` ) és egy típusú érték `Qubit` .

Egy egyszerű példa a következő művelet, amely egy qubit foglal le a $ \ket {0} $ állapotban, majd Hadamard műveletet alkalmaz `H` rá, és az eredményt az `PauliZ` alapján méri.

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

## <a name="borrowing-qubits-example"></a>Hitelfelvételi qubits – példa

A Canonban vannak olyan példák, amelyek a `borrowing` kulcsszót használják, például az `MultiControlledXBorrow` alább definiált függvényt.
Ha azt `controls` a vezérlő qubits jelöli, amelyet hozzá szeretne adni egy `X` művelethez, akkor ez a `Length(controls)-2` megvalósítás számos inkonzisztens ancillas ad hozzá.

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

Vegye figyelembe, hogy a `With` ---combinator a adjoint-t támogató műveletekre alkalmazható, például `WithA` ---a jelen példában.
Ez jó programozási stílus, mert a vezérlést `With` csak a belső művelethez való hozzáférés-vezérlést érintő struktúrákhoz adja hozzá.
Továbbá vegye figyelembe, hogy a `body` műveleten kívül a `controlled` művelet törzsének megvalósítását explicit módon adták meg, nem pedig egy `controlled auto` utasításhoz.
Ennek az az oka, hogy tisztában vagyunk az áramkör struktúrájával, így könnyen hozzáadhat további vezérlőket, amelyek hasznosak a vezérlés hozzáadásához az egyes és minden egyes kapuhoz képest `body` . 

Ez a kód egy másik Canon-függvénnyel hasonlítható össze `MultiControlledXClean` , amely ugyanazt a célt fogja elérni, mint egy szorzásra vezérelt `X` művelet megvalósítását, amely azonban számos tiszta qubits használ a `using` mechanizmus használatával. 

## <a name="next-steps"></a>Következő lépések

Tudnivalók a [vezérlési folyamatról](xref:microsoft.quantum.guide.controlflow) a Q #-ban.