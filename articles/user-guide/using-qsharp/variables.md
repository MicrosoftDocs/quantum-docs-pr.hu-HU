---
title: 'Változók a Q-ban #'
description: Kitöltés leírása
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430900"
---
# <a name="variables-in-q"></a>Változók a Q-ban #

A Q # különbséget tesz a változó és a nem módosítható szimbólumok, vagy a "változók" között, amelyek a kifejezésekhez vannak kötve/társítva.
Általánosságban a nem módosítható szimbólumok használata javasolt, mivel lehetővé teszi, hogy a fordító több optimalizációt végezzen.

A kötés bal oldali lapja egy szimbólumból álló rekordból és egy kifejezés jobb oldaláról áll.

## <a name="immutable-variables"></a>Megváltoztathatatlan változók

A Q # bármelyik típusának értéke hozzárendelhető egy változóhoz egy műveleten vagy függvényen belül a `let` kulcsszó használatával.

Egy nem módosítható kötés a kulcsszóból `let` , majd egy szimbólum vagy egy szimbólum, egy egyenlőségjel, egy egyenlőségjelet, egy kifejezés, amely `=` a szimbólum (oka) t és egy lezáró pontosvesszőt tartalmaz.

Ilyenek például a következők:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Ez a Pauli-operátorok egy adott tömbjét rendeli hozzá a változó nevéhez (vagy "szimbólum") `measurementOperator` .

> [!NOTE]
> Nem kell explicit módon megadnia az új változó típusát, mert az utasítás jobb oldalán lévő kifejezés nem `let` egyértelmű, és a típust a fordító következteti ki. 

A használatával definiált változók nem `let` *változtathatók*meg, ami azt jelenti, hogy ha már definiálva van, akkor az már nem módosítható semmilyen módon.
Ez számos hasznos optimalizálást tesz lehetővé, beleértve a változókra alkalmazott klasszikus logika optimalizálását a `Adjoint` művelet változatának átrendezéséhez.

## <a name="mutable-variables"></a>Változtatható változók

Egy változónak a használatával való létrehozásának alternatívájaként `let` a `mutable` kulcsszó egy változtatható változót hoz létre, *can* amely újra köthető, miután a kulcsszóval létrehozta azt `set` .

A deklarált és az utasítás részeként kötött szimbólumok `mutable` a kód későbbi részében más értékre is visszaköthetők. Ha a kódban később egy szimbólum van kötve, a típusa nem változik, és az újonnan kötött értéknek kompatibilisnek kell lennie az adott típussal.

### <a name="rebinding-of-mutable-symbols"></a>Változtatható szimbólumok újrakötése

Egy változtatható változót egy utasítás használatával lehet visszakötni `set` .
Egy ilyen újrakötés a kulcsszóból, egy szimbólum vagy egy szimbólum, egy egyenlőségjelet, egy `set` egyenlőségjel, egy kifejezés, amely a `=` szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.

Íme néhány lehetséges példa az újrakötési utasítási technikákra

### <a name="apply-and-reassign-statements"></a>Utasítások alkalmazása és újbóli társítása

Egy adott típusú `set` -utasításra hivatkozunk, mint az *alkalmazásra és az ismételt hozzárendelésre* vonatkozó utasítás, amely kényelmes megoldást kínál az Összefűzésre, ha a jobb oldalon egy bináris operátor alkalmazásából áll, és az eredmény a kezelőhöz a bal argumentumhoz lesz kötve. Példa:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
növeli a számláló értékét a `counter` hurok minden egyes iterációjában `for` . A fenti kód egyenértékű a következővel 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Hasonló utasítások érhetők el minden olyan bináris operátor esetében, amelyben a bal oldali oldal típusa megegyezik a kifejezés típusával. Ez például egy kényelmes módszer az értékek összegyűjtéséhez.

Tegyük fel például, hogy `qubits` a qubits egy regsiter:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Utasítások frissítése és újbóli társítása

Hasonló Összefűzés található a jobb oldali [másolási és frissítési kifejezésekhez](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .
Ennek megfelelően a rendszer a felhasználó által definiált típusokban és a *tömbökben*lévő *megnevezett elemek* esetében is tartalmazza a *frissítés és az ismételt hozzárendelés* utasításait.  

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

Tömbök esetén a [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) standard könyvtárakban számos gyakori tömb-inicializálási és-manipulációs igényt biztosítunk, így elkerülhető, hogy a tömb elemeit az első helyen frissítse. 

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

A-ben megadott tár-eszközök használatával [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) például egyszerűen meghatározhat egy olyan függvényt, amely Paulis tömböt ad vissza, ahol a Pauli at indexben a `i` megadott érték és az összes többi bejegyzés az identitás.

Íme egy ilyen függvény két definíciója, a második pedig kihasználja a rendelkezésére álló eszközöket.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

Ahelyett, hogy megismétli a tömbben lévő egyes indexeket, és feltételesen beállítja a `PauliI` vagy a `Pauli` rendszerre, ehelyett a `ConstantArray` következővel lehet [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) létrehozni egy tömböt `PauliI` :, majd egyszerűen egy másolási és frissítési kifejezést ad vissza, amelyben módosítottuk a különös értéket az indexnél `location`

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Rekord kiépítése

Egyetlen változó kiosztása mellett a `let` és a `mutable` kulcsszavak---vagy valójában bármilyen más kötési szerkezet, például `set` (lásd alább)---is lehetővé teszi, hogy kicsomagolja a [rekord típusú](xref:microsoft.quantum.guide.types#tuple-types)tartalmat.
Az űrlap kiosztása a rekord elemeinek *kiépítése* .

Ha a kötés jobb oldalán egy rekord található, akkor a rekord a hozzárendelés után kiépíthető.
Ezek a dekonstrukciók beágyazott rekordok tartalmazhatnak, és a teljes vagy részleges kiépítés akkor érvényes, ha a jobb oldalon lévő rekord alakja kompatibilis a szimbólum rekordjának formájával.

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
- A `repeat` / `until` hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.

Mindkét típusú hurok esetében a hurok továbbítása a saját hatókörében történik, így a korábbi pass-kötések nem érhetők el egy későbbi menetben.
Ezekről a hurkok részletei a [vezérlés folyamatában](xref:microsoft.quantum.guide.controlflow)találhatók.

A külső blokkokból származó szimbólum-kötéseket belső blokkok öröklik.
Egy szimbólum csak egyszer köthető egy blokkban; nem engedélyezett olyan szimbólumot definiálni, amelynek a neve megegyezik a hatókörön belüli másik szimbólummal (nincs "árnyék").
A következő szakaszokban lenne jogi:

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

## <a name="whats-next"></a>Vajon mi a következő lépés?
További információ a [qubits](xref:microsoft.quantum.guide.qubits) használatáról a Q #-ban.