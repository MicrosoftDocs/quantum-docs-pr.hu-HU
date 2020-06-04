---
title: 'Vezérlési folyamat a Q-ban #'
description: Hurkok, feltételesség stb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326540"
---
# <a name="control-flow-in-q"></a>Vezérlési folyamat a Q-ban #

Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan a leggyakoribb klasszikus nyelvekhez.
Ez a vezérlési folyamat azonban három különböző módon módosítható:

- `if`nyilatkozatok
- `for`hurkok
- `repeat`-`until`hurkok

Az utóbbival kapcsolatos vitát elhalasztjuk [alább](#repeat-until-success-loop).
A `if` és a `for` vezérlés folyamata azonban a klasszikus programozási nyelvek többsége számára jól ismert.

Fontos, hogy `for` a hurkok és `if` utasítások olyan műveletekben is használhatók, amelyekhez a rendszer automatikusan létrehozza a specializációkat. Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.
Ez a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat.
Határozottan kevésbé jól működik, ha a cipőjét továbbra is ki szeretné próbálni.

## <a name="if-else-if-else"></a>If, máskülönben

Az `if` utasítás támogatja a feltételes végrehajtást.
A kulcsszóból `if` , egy nyitó zárójelből `(` , egy logikai kifejezésből, egy záró zárójelből `)` és egy utasításból álló blokkból áll (ez a blokk). _then_
Ezt követheti tetszőleges számú Else-if záradék, amelyek mindegyike egy kulcsszóból `elif` , egy nyitó zárójelből `(` , egy logikai kifejezésből, egy záró zárójelből `)` és egy utasításból álló blokkból áll (ez a _másik_ blokk).
Végül az utasítás opcionálisan végződhet más záradékkal is, amely a kulcsszót, `else` majd egy másik utasítás blokkját (az _Else_ blokkot) tartalmazza.

A rendszer `if` kiértékeli a feltételt, és ha az értéke igaz, a rendszer végrehajtja a letiltást.
Ha a feltétel hamis, akkor az első más-if feltétel kiértékelése megtörténik. Ha az értéke igaz, akkor ez a másik a blokkolás végrehajtása.
Ellenkező esetben a második, ha a blokkot teszteli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.
Ha az eredeti if feltétel és az összes más-if záradék hamis értéket ad vissza, akkor a rendszer a másik blokkot hajtja végre, ha meg van határozva.

Vegye figyelembe, hogy a rendszer bármelyik blokkot a saját hatókörében hajtja végre.
Az egy `if` , `elif` , vagy blokkon belül végrehajtott kötések `else` nem láthatók a vége után.

Példa:

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

Az `for` utasítás egy egész tartományon vagy egy tömbön keresztül támogatja az ismétlést.
Az utasítás a kulcsszóból `for` , egy nyitott zárójelből `(` , egy szimbólum vagy egy szimbólum, egy `in` tömbből, egy típusú vagy egy tömbből álló kifejezésből, `Range` egy záró zárójelből `)` és egy utasításból áll.

A rendszer az utasítás blokkját (a hurok törzsét) többször hajtja végre, és a definiált szimbólum (ok) (a hurok változói) a tartomány vagy tömb egyes értékeihez van kötve.
Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem lesz végrehajtva.
A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és a hurok végrehajtása közben nem változik.

A hurok változó a hurok törzsének minden bejáratánál, a törzs végén pedig nem köthető.
A Loop változó nem kötődik a for ciklus befejeződése után.
A deklarált szimbólum (ok) kötése nem módosítható, és ugyanazokat a szabályokat követi, mint a többi változó kötése. 

Néhány példa arra, hogy `qubits` a qubits (azaz típus) regisztrálása a következő: `Qubit[]` 

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
Vegye figyelembe, hogy a végén a számtani-SHIFT-Left bináris operátort használták, `<<<` amely részletesen megtalálhatja a [numerikus kifejezéseket](xref:microsoft.quantum.guide.expressions#numeric-expressions) .


## <a name="repeat-until-success-loop"></a>REPEAT-ig-Success hurok

A Q # nyelv lehetővé teszi, hogy a klasszikus vezérlési folyamat a qubits mérési eredményeitől függ.
Ez a funkció lehetővé teszi a hatékony valószínűségi minialkalmazások megvalósítását, ami csökkentheti a számítási költségeket a unitaries megvalósításához.
A Q #-ban például könnyen megvalósítható az úgynevezett *REPEAT-ig-Success* (RUS) mintázat.
Ezek az RUS-minták olyan valószínűségi programok, amelyek a *vártnál* alacsonyabb költségeket mutatnak az elemi kapuk szempontjából, de a valódi díjak a tényleges futtatástól és a különböző lehetséges elágazások tényleges elhagyása függnek.

A REPEAT-ig-Success (RUS) minták megkönnyítése érdekében a Q # támogatja a szerkezeteket

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
A rendszer végrehajtja a hurok törzsét, majd kiértékeli a feltételt.
Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a rendszer végrehajtja a javítást, és az utasítást a hurok törzsének megfelelően újra végrehajtja.

Az Ismétlési/a hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve az *egyes ismétlődésekhez*, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.
A javítás végrehajtásának befejezése azonban befejezi az utasítás hatókörét, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődések során.

Az utasítás továbbá `fixup` gyakran hasznos, de nem mindig szükséges.
Abban az esetben, ha nincs rá szükség, a szerkezet
```qsharp
repeat {
    // do stuff
}
until (expression);
```
érvényes RUS-minta is.

A lap alján az [RUS-hurkok néhány példáját](#repeat-until-success-examples)mutatjuk be.

> [!TIP]   
> Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát. A kapcsolódó funkciókat a függvények hurkoi is biztosítják. 

## <a name="while-loop"></a>Ciklus közben

A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik. Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi összeállítás Q #-ban. Azonban az olyan hurkok, amelyek feltételen alapulnak, és amelynek végrehajtási hosszát a fordítási időn belül ismeretlennek kell lenniük, a kvantum-futtatókörnyezetben különös gondossággal kell kezelni. A függvényeken belüli használatuk azonban nem problémamentes, mivel ezek csak a hagyományos (nem Quantum) hardveren végrehajtandó kódokat tartalmaznak. 

A Q # ezért a csak functions-ben lévő hurkok használatát támogatja. Egy `while` utasítás a kulcsszóból `while` , egy nyitó zárójelből `(` , egy feltétellel (például logikai kifejezésből), egy záró zárójelből `)` és egy utasításból áll.
A rendszer az utasítás blokkját (a hurok törzsét) hajtja végre, amíg a feltétel kiértékelése megtörténik `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Visszatérési utasítás

A Return utasítás egy művelet vagy függvény végrehajtását hajtja végre, és egy értéket ad vissza a hívónak.
Ez a kulcsszóból áll `return` , majd a megfelelő típusú kifejezéssel, valamint egy megszakítási pontosvesszővel.

Egy üres rekordot visszaadó hívható, `()` nem igényel visszatérési utasítást.
Ha korai kilépés szükséges, `return ()` akkor ebben az esetben is használható.
A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.

Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.
A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.

Példa:
```qsharp
return 1;
```
vagy
```qsharp
return ();
```
vagy
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Sikertelen utasítás

A Fail utasítás befejezi a művelet végrehajtását, és hibaértéket ad vissza a hívónak.
A kulcsszót `fail` , majd egy karakterláncot és egy megszakítást tartalmazó pontosvesszőt tartalmaz.
A rendszer a karakterláncot a klasszikus illesztőprogramnak adja vissza hibaüzenetként.

A műveleteken belüli sikertelen utasítások száma nincs korlátozva.
A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.

Példa:
```qsharp
fail $"Impossible state reached";
```
vagy [interpolált karakterláncok](xref:microsoft.quantum.guide.expressions#interpolated-strings)használatával
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Ismételt sikeres példák

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>RUS-minta egyetlen qubit elforgatásához egy irracionális tengelyen 

Egy tipikus használati eset esetében a következő Q # művelet végrehajt egy, az/\sqrt $ (I + 2i Z) és a Bloch gömb közötti irracionális tengely körüli rotációt {5} . Ez egy ismert RUS-minta használatával valósítható meg:

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>RUS-hurok változtatható változóval a hatókörben

Ez a példa egy változtatható változó használatát mutatja be, `finished` amely a teljes REPEAT-ig-javítás hurok hatókörében van, és amely a hurok és a javítás lépésének frissítése előtt inicializálva lesz.

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

A következő kód például egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ a `H` és a Gates használatával `T` .
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

Végül egy olyan RUS-mintát mutatunk be, amely az $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $ értéket, a $ \ket{+} $ állapottól kezdődően előkészíti a kvantum-állapotot.
Lásd még: a [standard könyvtárhoz megadott Unit Testing minta](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

Az ebben a műveletben bemutatott jelentős programozott funkciók a hurok összetettebb `fixup` részét képezik, amely magában foglalja a kvantum-műveleteket, valamint az `AssertProb` utasítások használatát annak megállapítására, hogy a program bizonyos meghatározott pontjain a kvantum-állapot mérésének valószínűsége várható-e.
Lásd még: [tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging) , további információ a [`Assert`](xref:microsoft.quantum.intrinsic.assert) és a [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) műveletekről.


## <a name="next-steps"></a>Következő lépések

A [tesztelés és a hibakeresés](xref:microsoft.quantum.guide.testingdebugging) megismertetése a Q #-ban.