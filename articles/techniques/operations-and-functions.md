---
title: 'Q # technikák – műveletek és függvények | Microsoft Docs'
description: 'Q # technikák – műveletek és függvények'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 06da09dc9c6e0ba0331db6bc0cd3d2ddeb287113
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183454"
---
# <a name="q-operations-and-functions"></a>Q # műveletek és függvények

A Q # programok egy vagy több olyan *műveletből* állnak, amelyek leírják a kvantum-műveleteket a Quantum-adatokon, és egy vagy több olyan *függvényt* , amely engedélyezi a klasszikus adatok módosítását. A műveletekkel szemben a függvények a tisztán klasszikus viselkedés leírására szolgálnak, és nem gyakorolnak semmilyen hatást a klasszikus számítástechnikai értékek mellett.

A Q # által meghatározott minden művelet hívhat meg tetszőleges számú egyéb műveletet, beleértve a nyelv által meghatározott beépített belső műveleteket is. A belső műveletek meghatározásának konkrét módja a célszámítógéptől függ. A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.

## <a name="defining-new-operations"></a>Új műveletek definiálása

A fentiekben leírtak szerint egy, a Q #-ban írt kvantum-program legalapvetőbb építőeleme egy *művelet*, amely hívható a klasszikus .NET-alkalmazásokból, például szimulátor használatával vagy más, a q #-on belüli műveletekkel.
Mindegyik művelet egy bemenetet hoz létre, kimenetet állít elő, és meghatározza egy vagy több műveleti specializáció megvalósítását.
A következő művelet például csak az alapértelmezett szövegtörzset definiálja, és egyetlen qubit fogad hozzá bemenetként, majd meghívja a beépített `X` műveletet az adott bemeneten:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A kulcsszó `operation` megkezdi a művelet definícióját, és ezt a nevet követi; Itt `BitFlip`.
Ezután a bemenet típusa `Qubit`ként van definiálva, valamint egy név `target`, amely az új műveletben lévő bemenetre hivatkozik.
Hasonlóképpen, a `Unit` azt is meghatározza, hogy a művelet kimenete üres.
Ezt ugyanúgy használják, mint a C# és más, a `void` és más hasznos nyelveken, valamint F# a `unit` és más funkcionális nyelvek esetében.

> [!NOTE]
> Ezt részletesebben is megvizsgáljuk, de a Q # minden művelete pontosan egy bemenetet vesz fel, és pontosan egy kimenetet ad vissza.
> Ezután több bemenet és kimenet is képviselteti magát a *rekordok*használatával, amely egyszerre több értéket gyűjt össze egyetlen értékkel.
> Informálisan azt mondjuk, hogy a Q # egy "rekordos kijelentkezés" nyelv.
> Ezt a fogalmat követve a `()` az "üres" rekordként kell olvasni, amelynek típusa `Unit`.

Az új műveleten belül a megvalósítás közvetlenül a deklarációban adható meg, ha csak az alapértelmezett szövegtörzs-specializáció megvalósítását explicit módon kell megadni. Emellett lehetséges a megvalósítások definiálása, például egy vagy több `functor` művelet, az alábbi módon: A fenti példában az egyetlen utasítás a beépített Q # művelet <xref:microsoft.quantum.intrinsic.x>meghívása.

A műveletek több érdekes típust is visszaadhatnak, mint a `Unit`.
A <xref:microsoft.quantum.intrinsic.m> művelet például `Result`típusú kimenetet ad vissza, amely a mérés végrehajtásával jár. Egy művelet kimenetét átadhatja egy másik műveletnek, vagy használhatja a `let` kulcsszóval egy új változó definiálásához.
<!-- Link to UID for superdense conceptual and example documentation. -->
Ez lehetővé teszi a klasszikus számításokat, amelyek alacsony szinten működnek a kvantum-műveletekkel, például a sűrűbb kódolásban:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Adjoint és vezérelt
Ha egy művelet egy egységes átalakítást valósít meg, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen. Egy művelet adjoint megadásával megadható, hogy a hogyan működik, amikor fordított állapotban van, míg a szabályozott specializáció meghatározza, hogy a művelet hogyan viselkedik, ha a rendszer a kvantum-regiszter állapotára alkalmazza a műveletet.
Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható: `is Adj + Ctl` a következő példában. Ezután a fordító létrehozza a megfelelő implementációt minden ilyen implicit módon deklarált specializációhoz. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> A Q # számos művelete egységes kapukat képvisel.
> Ha $U $ a művelet `U`által reprezentált egységes kapu, akkor `Adjoint U` az egységes kaput jelöli $U ^ \dagger $.

Abban az esetben, ha a fordító nem tudja létrehozni a megvalósítást, explicit módon megadható. Az ilyen explicit specializációs nyilatkozatok megfelelő generációs irányelvből vagy felhasználó által definiált implementációból állhatnak. A fenti `PrepareEntangledPair` található kód például az alábbi kóddal egyenértékű, explicit specializációs deklarációkat tartalmaz: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan hozhatja ki a specializáció megvalósítását.
Ha a fordító nem tud automatikusan előállítani egy bizonyos specializáció megvalósítását, vagy ha hatékonyabb megvalósításra van lehetőség, akkor a megvalósítás manuálisan is megadható.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
A fenti példában a `adjoint invert;` azt jelzi, hogy a adjoint specializációt a törzs megvalósításának visszafordításával kell létrehozni, és `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint-specializációt úgy kell létrehozni, hogy a megadott implementációját visszaállítja a irányított specializáció.

Ennek további példáit láthatjuk a [magasabb rendű vezérlési folyamatokban](xref:microsoft.quantum.concepts.control-flow).

Egy művelet specializációjának meghívásához használja a `Adjoint` vagy `Controlled` kulcsszavakat.
Például a fenti kondenzátor-kódolási példa az `PrepareEntangledPair` adjoint használatával tömören írható, hogy a kusza állapotot visszaalakítsa egy nem összeillesztett qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Számos fontos korlátozást kell figyelembe venni, amikor a rendszer megtervezi, hogy milyen műveleteket végeznek az üzemben.
A legtöbb kritikus jelentőséggel bír, ha egy olyan műveletre specializálódott, amely bármely más művelet kimeneti értékét használja, nem lehet automatikusan generálni a fordítótól, mert nem egyértelmű, hogy az ilyen műveletekben szereplő utasítások hogyan rendezhetők át ugyanezen hatás megszerzése érdekében.


## <a name="defining-new-functions"></a>Új függvények definiálása

A Q # Emellett lehetővé teszi a *függvények*definiálását is, amelyek nem azonosak a kimeneti érték kiszámításának következményeivel.
A függvények nem hívhatják meg a műveleteket, a qubits, a véletlenszerű számú mintákat, vagy más módon a bemeneti értéken kívüli állapottól függenek.
Ennek következményeként a Q # függvények *tisztán*vannak rendelve, hogy mindig ugyanazokat a bemeneti értékeket rendelik ugyanahhoz a kimeneti értékekhez.
Így a Q # fordító biztonságosan átrendezheti, hogyan és mikor hívja meg a függvényeket a műveleti specializációk létrehozásakor.

A függvények definiálása hasonlóan működik a művelet definiálásához, azzal a kivétellel, hogy egy függvényhez nem lehet adjoint vagy vezérelt specializációt meghatározni.
Például:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Ha ezt megteheti, hasznos lehet a klasszikus logikát kiírni a függvények helyett, hogy azok a műveletek során könnyebben használhatók legyenek.
Ha például egy műveletként írt `Square`, akkor a fordító nem tudta volna garantálni, hogy ugyanazt a bemenetet ugyanazzal a kimenettel fogja megszólítani.

A függvények és a műveletek közötti különbség kihangsúlyozása érdekében vegye figyelembe, hogy egy véletlenszerűen kiválasztott számnak a Q #-műveletből való klasszikus mintavételezési problémája:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Minden alkalommal, amikor a `U` meghívása megtörtént, a `target`egy másik művelettel fog rendelkezni.
A fordító nem tudja garantálni, hogy ha `adjoint auto` specializációs nyilatkozatot adott hozzá `U`hoz, akkor `U(target); Adjoint U(target);` identitásként viselkedik (azaz nem op).
Ez sérti a [vektorokban és mátrixokban](xref:microsoft.quantum.concepts.vectors)megjelenő adjoint definícióját, amely lehetővé teszi, hogy egy adjoint-specializációt egy olyan műveletben engedélyezzen, amelybe a művelet <xref:microsoft.quantum.math.randomreal>, hogy megszegi a fordító által biztosított garanciákat ; <xref:microsoft.quantum.math.randomreal> olyan művelet, amelynek nem létezik adjoint vagy vezérelt verziója.

Másfelől lehetővé teszi, hogy a függvényhívás, például a `Square` biztonságos legyen, abban az esetben, ha a fordító biztos lehet abban, hogy csak a bemenetet kell megőriznie `Square` a kimenet stabilitásának megőrzése érdekében.
Így a lehető legtöbb klasszikus logikát elkülönítheti a functions szolgáltatásban, így a logika más funkciókban és műveletekben is felhasználható.

## <a name="control-flow"></a>Átvitelvezérlés

Egy műveleten vagy függvényen belül minden utasítás sorrendben fut, hasonlóan a leggyakoribb klasszikus nyelvekhez.
Ez a vezérlési folyamat azonban három különböző módon módosítható:

- `if` utasítások
- `for` hurkok
- `repeat`-`until` hurkok

Addig elhalasztjuk a vitát, amíg meg nem vitatjuk a [sikeres (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) áramköröket.
A `if` és `for` Control flow szerkezetek azonban a klasszikus programozási nyelvek többségében jól ismertek.
Egy `if` utasítás egy feltételt is igénybe vehet, amelyet egy vagy több `elif` utasítás követ, és a `else`is végződhet:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

Hasonlóképpen, `for` hurkok több egész szám vagy egy tömb elemeinek megismétlését jelölik:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Fontos, hogy `for` hurkokat és `if` utasításokat olyan műveletekben is felhasználhatjuk, amelyekben automatikusan létrejönnek a specializációk. Ebben az esetben a `for` hurok adjoint megfordítja az irányt, és az egyes iterációk adjoint veszi át.
Ez a "cipők és zoknik" elvét követi: Ha vissza kívánja vonni a SOCKs-t, majd a cipőket, vissza kell vonnia a cipőket, majd vissza kell vonnia a zoknikat.
Határozottan kevésbé jól működik, ha a cipőjét továbbra is ki szeretné próbálni.

## <a name="operations-and-functions-as-first-class-values"></a>Műveletek és függvények első osztályú értékként

Az egyik kritikus módszer, amellyel a vezérlési folyamat és a klasszikus logika a függvények helyett functions használatával történik, hogy a Q # *első osztályú*műveleteit és funkcióit használják.
Ez azt eredményezi, hogy a nyelv minden értéke a saját jobb oldalán van.
Például a következőkben teljesen érvényes Q # kód van, ha egy kicsit indirekt:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

A fenti kódrészletben `ourH` változó értéke a művelet <xref:microsoft.quantum.intrinsic.h>, így például bármely más művelethez hasonlóan hívhatjuk ezt az értéket.
Ez lehetővé teszi olyan műveletek írását, amelyek a bemenetük részeként végzik a műveleteket, és a magasabb rendű vezérlési folyamatokra vonatkozó fogalmakat képeznek.
Tegyük fel például, hogy a "Square" műveletet úgy képzeli el, hogy kétszer ugyanazt a cél qubit alkalmazza.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

Ebben a példában a `(Qubit => Unit)` típusban megjelenő `=>` nyíl azt jelzi, hogy a beviteli mező `op` egy olyan művelet, amely a `Qubit` típusként adja meg a bemenetet, és a kimenetként üres rekordot hoz létre.
Ezen túlmenően a művelet típusának jellemzőit is megadjuk, amely tartalmazza azokat az információkat, amelyek támogatottak.
Egy `(Qubit => Unit)` típusú művelet sem a `Adjoint`, sem a `Controlled`-kezelőt is támogatja. Ha azt szeretnénk jelezni, hogy az adott típusú műveletnek támogatnia kell például az `Adjoint`-t, akkor azt adjointable kell bejelenteni. Ez a típushoz tartozó jegyzet `is Adj` használatával végezhető el. Hasonlóképpen `(Qubit => Unit is Ctl)` azt is jelzi, hogy az adott típusú művelet támogatja a `Controlled`-munkafolyamatot. Ezt részletesebben is megvizsgáljuk, amikor a [types in Q #] (xref: Microsoft. Quantum. Language. Type-Model) általánosságban tárgyaljuk.

Most Kiemeljük, hogy a kimenetek részeként is visszaadhatjuk a műveleteket, így a klasszikus feltételes logika valamilyen módon elkülöníthető klasszikus függvényként, amely egy művelet formájában egy kvantum-program leírását adja vissza.
Egyszerű példaként tekintse meg a teleportálás példáját, amelyben a kétbites klasszikus üzenetet fogadó fél az üzenetet arra használja, hogy dekódolja a qubit a megfelelő teleportált állapotba.
Ezt egy olyan függvényben írhatjuk, amely a két klasszikus bitet veszi át, és visszaadja a megfelelő dekódolási műveletet.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Ez az új függvény valóban egy függvény, abban az esetben, ha a `hereBit` és `thereBit`megegyező értékekkel hívjuk, mindig ugyanezt a műveletet fogjuk visszakapni.
Így a dekóder biztonságosan futtatható a műveletekben anélkül, hogy meg kellene indokolnia, hogy a dekódolási logika hogyan működjön együtt a különböző műveleti szakosodások definícióinak használatával.
Ez azt is megteheti, hogy elszigetelte a klasszikus logikát egy függvényen belül, garantálva azt a fordítót, hogy a függvény hívása büntetlenül rendezhető, feltéve, hogy a bevitel megmarad.

A függvényeket az első osztályú értékekként is kezelhetjük, mivel a [műveletekről és a függvények típusairól](#operations-and-functions-as-first-class-values)részletesebben is tájékozódhat.

## <a name="partially-applying-operations-and-functions"></a>A műveletek és függvények részleges alkalmazása

A műveleteknek a *részleges alkalmazás*használatával történő visszaadását lehetővé tehetjük, amelyekben a bemenet egy vagy több részének megadásával egy függvénynek vagy műveletnek a tényleges hívása nélkül is megadható. Ha például visszahívja a fenti `ApplyTwice` példát, jelezheti, hogy nem szeretnénk megadni, azonnal, hogy a bemeneti művelet melyik qubit vonatkozzon:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Ebben az esetben a helyi változó `twiceOp` a részlegesen alkalmazott művelet `ApplyTwice(op, _)`, ahol a bemenetben még nem megadott részek szerepelnek `_`.
Ha a következő sorban ténylegesen meghívja a `twiceOp`t, akkor a bemenetnek a részlegesen alkalmazott művelethez adja át az eredeti művelet összes fennmaradó részét.
Így a fenti kódrészlet gyakorlatilag azonos ahhoz, hogy `ApplyTwice(op, target)` közvetlenül meghívja őket, mentse, hogy egy új helyi változót vezettünk be, amely lehetővé teszi számunkra, hogy késleltetjük a hívást, miközben a bemenet egyes részeit biztosítjuk.

Mivel egy részlegesen alkalmazott művelet valójában nem lett meghívva, amíg a teljes adatbevitel meg nem történt, akkor a függvényekből is biztonságosan részben alkalmazhatjuk a műveleteket.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Elvileg a `SquareOperation`on belüli klasszikus logika sokkal több résztvevő lehet, de továbbra is el van különítve a többi művelettől, mert az garantálja, hogy a fordító a functions szolgáltatással kapcsolatban tud nyújtani.
Ezt a megközelítést fogja használni a Q # standard könyvtárban a klasszikus vezérlési folyamat kifejezésére, amely a kvantum-programokban könnyen használható.
