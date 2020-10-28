---
title: Változók a-ben Q#
description: 'Megtudhatja, hogyan dolgozhat különböző változókkal a következőben: Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67c71c09e004d77360902360fefc7a7752e4a829
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690931"
---
# <a name="variables-in-no-locq"></a>Változók a-ben Q#

Q# megkülönbözteti a változókat és a nem módosítható szimbólumokat, illetve a kifejezésekhez hozzárendelt vagy hozzájuk rendelt *változókat* .
Általánosságban a nem módosítható szimbólumok használata javasolt, mivel lehetővé teszi, hogy a fordító több optimalizációt végezzen.

A kötés bal oldali oldala egy szimbólum és egy kifejezés jobb oldalán áll.

## <a name="immutable-variables"></a>Megváltoztathatatlan változók

A kulcsszó használatával bármilyen típusú értéket hozzárendelhet Q# egy változóhoz egy műveleten vagy függvényen belüli újrafelhasználáshoz `let` . 

Egy nem módosítható kötés a kulcsszóból `let` , majd egy szimbólum vagy egy szimbólum, egy egyenlőségjel, egy egyenlőségjelet, egy kifejezés, amely `=` a szimbólum (oka) t és egy lezáró pontosvesszőt tartalmaz.

Ilyenek például a következők:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Ez a Pauli-operátorok egy adott tömbjét rendeli hozzá a változó nevéhez (vagy "szimbólum") `measurementOperator` .

> [!NOTE]
> Az előző példában nem kell explicit módon megadnia az új változó típusát, mivel az utasítás jobb oldalán lévő kifejezés nem `let` egyértelmű, és a fordító kikövetkezteti a megfelelő típust. 

A használatával definiált változók `let` nem *változtathatók* meg, ami azt jelenti, hogy a meghatározása után a továbbiakban nem módosítható.
Ez számos hasznos optimalizálást tesz lehetővé, többek között a klasszikus logika optimalizálását, amely a változókat a művelet változatának átrendezésére fogja alkalmazni `Adjoint` .

## <a name="mutable-variables"></a>Változtatható változók

Egy változónak a használatával való létrehozásának alternatívájaként `let` a `mutable` kulcsszó egy változtatható változót hoz létre, amely a kulcsszóval való első létrehozás után újrakötésre *képes* `set` .

Egy utasítás részeként deklarált és kötött szimbólumokat a `mutable` kód későbbi részében egy másik értékre lehet visszakötni. Ha egy szimbólum később van kötve a kódban, a típusa nem változik, és az újonnan kötött értéknek kompatibilisnek kell lennie az adott típussal.

### <a name="rebinding-of-mutable-symbols"></a>Változtatható szimbólumok újrakötése

Egy megváltoztathatatlan változót egy utasítás használatával lehet újra kötni `set` .
Egy ilyen újrakötés a kulcsszóból, egy szimbólum vagy egy szimbólum, egy egyenlőségjelet, egy `set` egyenlőségjel, egy kifejezés, amely a `=` szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.

Az alábbiakban néhány példát talál az újrakötési utasításokra vonatkozó eljárásokra.

#### <a name="apply-and-reassign-statements"></a>Utasítások alkalmazása és újbóli társítása

Egy adott típusú `set` utasítás, az *Apply-and-reassign* utasítás kényelmes módot biztosít az Összefűzésre, ha a jobb oldal egy bináris operátor alkalmazásából áll, és az eredmény az operátorhoz a bal argumentumhoz lesz kötve. Például:

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
növeli a számláló értékét a `counter` hurok minden egyes iterációjában `for` . Az előző kód egyenértékű a következővel 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Hasonló utasítások érhetők el minden olyan bináris operátor esetében, amelyben a bal oldali oldal típusa megegyezik a kifejezés típusával. Ezek az utasítások az értékek összegyűjtésének kényelmes módját biztosítják.

Tegyük fel például, hogy `qubits` a qubits egy regisztrálása:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Utasítások frissítése és újbóli társítása

Hasonló Összefűzés található a jobb oldali [másolási és frissítési kifejezésekhez](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .
Ennek megfelelően a rendszer a felhasználó által definiált típusokban és a *tömbökben* lévő *megnevezett elemek* esetében is tartalmazza a *frissítés és az ismételt hozzárendelés* utasításait.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

Tömbök esetén a [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) Q# standard szintű függvénytárban a szükséges eszközök számos gyakran használt tömb inicializálási és manipulációs igényeihez szükségesek, így elkerülhető, hogy a tömb elemeit az első helyen frissítse. 

Az Update-and-reassign utasítások szükség esetén alternatív megoldást nyújtanak:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

A-ben megadott tár-eszközök használatával [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) például egyszerűen meghatározhat egy olyan függvényt, amely egy olyan típusú tömböt ad vissza, `Pauli` amelyben az indexben található elem `i` egy adott értéket vesz igénybe `Pauli` , és az összes többi bejegyzés az Identity ( `PauliI` ).

Íme egy ilyen függvény két definíciója, a második pedig kihasználja a rendelkezésére álló eszközöket.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Ahelyett, hogy megismétli a tömbben lévő egyes indexeket, és feltételesen Beállítja azt a `PauliI` vagy a megadott `pauli` `ConstantArray` értékre, a from paranccsal [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) létrehozhat egy tömb típusú tömböt `PauliI` , majd egyszerűen visszaállíthat egy olyan másolási és frissítési kifejezést, amelyben módosította az adott értéket az indexnél `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Rekord kiépítése

Egyetlen változó hozzárendelésén kívül használhatja a `let` és a `mutable` kulcsszavakat is, vagy bármely más kötési összeállítást, például a `set` -t egy [rekord típusú](xref:microsoft.quantum.guide.types#tuple-types)tartalom kicsomagolásához.
Az űrlap kiosztása a rekord elemeinek *kiépítése* .

Ha a kötés jobb oldalán egy rekord található, akkor a hozzárendelés után visszaállíthatja ezt a rekordot.
Ezek a dekonstrukciók beágyazott rekordok is tartalmazhatnak, és a teljes vagy részleges kiépítés akkor érvényes, ha a jobb oldalon lévő rekord alakja kompatibilis a Symbol rekord alakzatával.

Például:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Kötési hatókörök

Általánosságban elmondható, hogy a szimbólumokra vonatkozó kötések kikerülnek a hatókörből, és a blokk végén nem válnak elérhetővé.
A szabálynak két kivétele van:

- Egy hurok hurok-változójának kötése `for` hatókörben van a for ciklus törzséhez, de a hurok vége után nem.
- A ciklus mindhárom része `repeat` / `until` (a törzs, a teszt és a javítás) egyetlen hatókörként működik, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.

Mindkét típusú hurok esetében a hurok továbbítása a saját hatókörében történik, így a korábbi pass-kötések nem érhetők el egy későbbi menetben.
További információ ezekről a hurkokkal kapcsolatban: [vezérlési folyamat](xref:microsoft.quantum.guide.controlflow).

A belső blokkok öröklik a szimbólum-kötéseket a külső blokkokból.
Blokkon keresztül csak egyszer köthető szimbólum. nem engedélyezett olyan szimbólumot definiálni, amelynek a neve megegyezik a hatókörön belüli másik szimbólummal (nincs "árnyék").
A következő szakaszokban jogi információk szerepelnek:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

és

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Ez azonban nem engedélyezett:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

például:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a>Következő lépések

Ismerje meg, hogyan [dolgozhat a qubits](xref:microsoft.quantum.guide.qubits) a alkalmazásban Q# .