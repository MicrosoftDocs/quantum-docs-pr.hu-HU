---
title: Folyamat vezérléseQ#
description: Hurkok, feltételesség stb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc619d64bfebfc27d7feac6dafb2dd4cf22825d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867947"
---
# <a name="control-flow-in-no-locq"></a>Folyamat vezérléseQ#

Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan más gyakori klasszikus nyelvekhez.
A vezérlés folyamatát azonban három különböző módon módosíthatja:

* `if`nyilatkozatok
* `for`hurkok
* `repeat-until-success`hurkok

A `if` és a `for` vezérlési folyamat szerkezetét a klasszikus programozási nyelvek többsége ismeri. [`Repeat-until-success`](#repeat-until-success-loop)a hurkokat a cikk későbbi részében tárgyaljuk.

Fontos, hogy `for` a hurkok és `if` utasítások olyan műveletekben használhatók, amelyekben automatikusan létrejönnek a [specializációk](xref:microsoft.quantum.guide.operationsfunctions) . Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.
Ez a művelet a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat. 

## <a name="if-else-if-else"></a>If, máskülönben

Az `if` utasítás támogatja a feltételes végrehajtást.
A kulcsszó `if` , a logikai kifejezés zárójelek között, valamint egy utasítás blokkja (az _akkori_ blokk).
Opcionálisan tetszőleges számú Else-if záradékot követhet, amelyek mindegyike egy kulcsszóból `elif` , egy zárójelben található logikai kifejezésből és egy utasításból álló blokkból áll (a _másik, ha_ blokk).
Végül az utasítás opcionálisan végződhet más záradékkal is, amely a kulcsszót, `else` majd egy másik utasítás blokkját (az _Else_ blokkot) tartalmazza.

A rendszer `if` kiértékeli a feltételt, és ha az *then* értéke *igaz*, a rendszer futtatja a letiltást.
Ha a feltétel *hamis*, akkor az első más-if feltétel kiértékelése megtörténik. Ha ez igaz, akkor az *Else-if* blokk fut.
Ellenkező esetben a második, ha a blokk kiértékeli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.
Ha az eredeti *IF* feltétel és az összes Else-if záradék *Hamis értéket*ad vissza, akkor a *többi* blokk is fut, ha meg van határozva.

Vegye figyelembe, hogy bármelyik blokk fut, a saját hatókörén belül fut.
`if`Az egy, `elif` , vagy blokkon belül végrehajtott kötések `else` nem láthatók a blokk vége után.

Például:

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
vagy
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>Hurok esetén

Az `for` utasítás támogatja az ismétlést egész tartományon vagy tömbön.
Az utasítás a kulcsszót `for` , majd egy szimbólum vagy egy szimbólumot, a kulcsszót `in` és egy Type `Range` vagy Array kifejezést, valamint az összes zárójelet és egy utasítás blokkját tartalmazza.

Az utasítás blokkja (a hurok törzse) ismétlődően fut, és a megadott szimbólummal (a hurok változóval) a tartomány vagy tömb minden értékéhez kötve van.
Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem fut.
A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és a hurok végrehajtása közben nem változik.

A hurok változó a hurok törzsének minden bejáratához van kötve, és a törzs végén van kötve.
A Loop változó nem kötődik a for ciklus befejeződése után.
A hurok változó kötése nem változtatható meg, és ugyanazokat a szabályokat követi, mint a többi változó kötése. 

Ezekben a példákban `qubits` a qubits (pl. típus) regisztrálása `Qubit[]` , 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Vegye figyelembe, hogy a végén a számtani-SHIFT-Left bináris operátort használták `<<<` . További információ: [numerikus kifejezések](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>REPEAT-ig-Success hurok

A Q# nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.
Ez a funkció lehetővé teszi, hogy a hatékony valószínűséggel rendelkező minialkalmazások megvalósításával csökkentse a unitaries megvalósításához szükséges számítási költségeket.
Ilyenek például a *REPEAT-ig-Success* (RUS) minták a alkalmazásban Q# .
Ezek az RUS-minták olyan valószínűségi programok, amelyek az alapvető kapuk szempontjából *várhatóan* alacsony költségeket mutatnak; a felmerülő költségek a tényleges futtatástól és a több lehetséges ág közötti összekapcsolástól függenek.

A sikeres ismétléses (RUS) minták megkönnyítése érdekében Q# támogatja a szerkezeteket

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

ahol a `expression` bármely érvényes kifejezés, amely egy típusú értékre van kiértékelve `Bool` .
A hurok törzse fut, majd kiértékeli a feltételt.
Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a javítás lefut, és az utasítás ismét lefut, a hurok törzsének megfelelően.

Egy RUS-hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve az *egyes ismétlődésekhez*, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.
A javítás végrehajtásának befejezése azonban befejezi a utasítás hatókörét, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődések során.

Az utasítás továbbá `fixup` gyakran hasznos, de nem mindig szükséges.
Abban az esetben, ha nincs rá szükség, a szerkezet

```qsharp
repeat {
    // do stuff
}
until (expression);
```

érvényes RUS-minta is.

További példákért és részletekért tekintse meg a jelen cikk [REPEAT-amíg-sikeres példáit](#repeat-until-success-examples) .

> [!TIP]   
> Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát. Használja *a* hurkokat a függvények megfelelő funkcióinak megadásához. 

## <a name="while-loop"></a>Ciklus közben

A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik. Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi konstrukciója Q# . Azonban az olyan hurkok, amelyek egy adott feltétel alapján törnek át, és amelynek végrehajtási hosszát a fordítási időben nem ismeri, a rendszer a kvantum-futtatókörnyezetben különösen körültekintően kezeli. Azonban a függvényeken belüli használatuk nem problémamentes, mivel ezek a hurkok csak a hagyományos (nem Quantum) hardveren futó kódokat tartalmaznak. 

Q#Ezért a csak a functions-ben lévő hurkok használatát támogatja. Egy `while` utasítás a kulcsszóból `while` , egy logikai kifejezésből áll zárójelben, és egy utasítás blokkot.
Az utasítás blokkja (a hurok törzse) mindaddig fut, amíg a feltétel kiértékelése megtörténik `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a>Visszatérési utasítás

A Return utasítás egy művelet vagy függvény futtatását, és egy értéket ad vissza a hívónak.
Ez a kulcsszóból áll `return` , majd a megfelelő típusú kifejezéssel, valamint egy megszakítási pontosvesszővel.

Például:
```qsharp
return 1;
```
vagy
```qsharp
return (results, qubits);
```

* Egy üres rekordot visszaadó hívható, `()` nem igényel visszatérési utasítást.
* A művelet vagy a függvény korai kilépésének megadásához használja a következőt: `return ();` .
A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.
* Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.
A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.

   
## <a name="fail-statement"></a>Sikertelen utasítás

A Fail utasítás egy művelet futtatásával végződik, és hibaértéket ad vissza a hívónak.
A kulcsszót `fail` , majd egy karakterláncot és egy megszakítást tartalmazó pontosvesszőt tartalmaz.
Az utasítás a klasszikus illesztőprogram sztringjét adja vissza hibaüzenetként.

A műveleteken belüli sikertelen utasítások száma nincs korlátozva.
A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.

Például:

```qsharp
fail $"Impossible state reached";
```
vagy [interpolált karakterláncok](xref:microsoft.quantum.guide.expressions#interpolated-strings)használatával
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Ismételt sikeres példák

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>RUS-minta egyetlen qubit elforgatásához egy irracionális tengelyen 

Tipikus használati eset esetén a következő művelet a Q# (Z) $ (I + 2i Z)/\sqrt $, a Bloch szférán belüli irracionális tengely körüli rotációt valósít {5} meg. A megvalósítás egy ismert RUS mintát használ:

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>RUS-hurok változtatható változóval a hatókörben

Ez a példa egy változtatható változó használatát mutatja be, `finished` amely a teljes REPEAT-ig-javítás hurok hatókörén belül van, és amely a hurok és a javítás lépésének frissítése előtt inicializálva lesz.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>RUS nélkül`fixup`

Ez a példa egy RUS-hurkot mutat be a javítási lépés nélkül. A kód egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ a `H` és a Gates használatával `T` .
A hurok a $ \frac {8} {5} $ Ismétlődések átlagában leáll.
További részletekért lásd: egyszeres qubit unitaries (Petrovics és Svore, 2014) [*nem determinisztikus felbomlása*](https://arxiv.org/abs/1311.1074) .

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>RUS a kvantum-állapot előkészítéséhez

Végezetül Íme egy példa egy olyan RUS-mintázatra, amely a Quantum State $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket \right) $ előkészíti a $ {1} \ket{+} $ állapottól kezdődően.

A műveletben bemutatott jelentős programozott funkciók a következők:

* `fixup`A hurok összetettebb része, amely magában foglalja a kvantum-műveleteket. 
* Az utasítások használata `AssertMeasurementProbability` annak megállapítására, hogy a program bizonyos meghatározott pontjain a kvantum-állapot mérésének valószínűsége várható-e.

További információ a és a [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) műveletekről: [tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

További információkért lásd: [Unit Testing Sample a standard Library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Következő lépések

További információ a [teszteléséről és hibakereséséről](xref:microsoft.quantum.guide.testingdebugging) Q# .
