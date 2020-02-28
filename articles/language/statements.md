---
title: 'Q # utasítások'
description: 'Ismerje meg az utasítások helyes használatát a Q #-ban, beleértve a függvény-és műveleti deklarációkat, a változó deklarációkat és a hozzárendeléseket, valamint a műveleti hívásokat.'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e801a5fdd24b973f47d23d2aca6f11bbebf333d4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904672"
---
# <a name="statements-and-other-constructs"></a>Utasítások és egyéb szerkezetek

## <a name="comments"></a>Megjegyzések

A megjegyzések két továbbítási perjeltel kezdődnek, `//`, és a sor végéig folytatódnak.
Egy Megjegyzés a Q # forrásfájlban bárhol megjelenhet.

### <a name="documentation-comments"></a>Dokumentációs megjegyzések

A három továbbítási perjelet, `///`t tartalmazó megjegyzéseket a fordító kifejezetten akkor kezeli, ha közvetlenül a névtér, a művelet, a specializáció, a függvény vagy a típus definíciója előtt jelennek meg.
Ebben az esetben a tartalmuk a definiált vagy felhasználó által definiált, a többi .NET-nyelvhez hasonlóan dokumentációként szolgál.

`///` megjegyzésekben az API dokumentációjának részeként megjelenő szöveg [Markdown](https://daringfireball.net/projects/markdown/syntax)van formázva, és a dokumentáció különböző részeit a speciális névvel ellátott fejlécek jelölik.
A Markdown bővítmény a műveletekre, a függvényekre és a felhasználó által definiált típusokra mutató hivatkozásokat tartalmazhatja a Q #-ban a `@"<ref target>"`használatával, ahol a `<ref target>` a hivatkozott kód objektum teljesen minősített nevével helyettesíti.
Szükség esetén a dokumentációs motor további Markdown-bővítményeket is támogat.

Például:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

A rendszer a következő neveket ismeri fel dokumentációs Megjegyzés fejlécként.

- **Összefoglalás**: egy függvény vagy művelet viselkedésének, vagy egy típus céljának rövid összefoglalása. Az összefoglalás első bekezdése a hover-információkhoz használatos. Egyszerű szövegnek kell lennie.
- **Leírás**: függvény vagy művelet viselkedésének vagy egy típusnak a leírása. Az összefoglalás és a Leírás össze van fűzve, hogy a generált dokumentációs fájlt hozza létre a függvényhez, a művelethez vagy a típushoz.
  A Leírás tartalmazhat beágyazott LaTeX-formátumú szimbólumokat és egyenleteket is.
- **Bemenet**: egy művelet vagy függvény bemeneti rekordjának leírása.
  Tartalmazhat további Markdown alszakaszokat is, amelyek a bemeneti rekord egyes elemeit jelzik.
- **Kimenet**: egy művelet vagy függvény által visszaadott rekord leírása.
- **Type Parameters**: üres szakasz, amely minden általános típusparaméter esetében egy további alszakaszt tartalmaz.
- **Példa**: egy rövid példa a művelet, a függvény vagy a típus használatban.
- **Megjegyzések**: a művelet, a függvény vagy a típus néhány aspektusát ismertető egyéb próza.
- **Lásd még**: a kapcsolódó függvényeket, műveleteket vagy felhasználó által meghatározott típusokat jelölő teljes nevek listája.
- **Hivatkozások**: a dokumentált elemre vonatkozó hivatkozások és idézetek listája.

## <a name="namespaces"></a>Névterek

Minden Q # művelet, függvény és felhasználó által definiált típus definiálva van egy névtéren belül.
A Q # ugyanazokat a szabályokat követi, mint az egyéb .NET-nyelvek elnevezése.
A Q # azonban nem támogatja a névterek relatív hivatkozásait.
Ha a névtér `a.b` megnyitása megtörtént, a rendszer nem oldja meg a műveleti nevekre mutató hivatkozást, `c.d` a teljes nevű művelet `a.b.c.d`.

Egy névtér-blokkon belül a `open` direktíva használható a megadott névtérben deklarált összes típus és callables importálására, és azok nem minősített nevük alapján. Ha szükséges, a megnyitott névtérhez tartozó rövid név is meghatározható úgy, hogy az adott névtérből származó összes elemet (és szükség esetén) a megadott rövid névvel kell minősíteni. A `open` direktíva a teljes névtér-blokkra vonatkozik a fájlban.

Egy másik névtérben definiált típust vagy meghívást, amelyet a jelenlegi névtérben nem nyitott meg, a teljes névvel kell hivatkozni.
Ha például egy `Op` nevű műveletet a `X.Y` névtérben kell megadnia, akkor a teljes neve `X.Y.Op`, kivéve, ha az aktuális blokkban korábban megnyitotta a `X.Y` névteret. Ahogy fent említettük, még akkor is, ha a `X` névteret megnyitották, nem lehet a műveletre hivatkozni `Y.Op`ként.
Ha a névtérben és a fájlban a `X.Y` rövid neve `Z` lett definiálva, akkor `Op`nak `Z.Op`néven kell szerepelnie. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Általában jobb, ha a névteret egy `open` direktíva használatával is felveszi.
Teljesen minősített név használata kötelező, ha két névtér definiálja ugyanazt a nevet, és a jelenlegi forrás mindkettőből származó szerkezeteket használ.

## <a name="formatting"></a>Formátum

A legtöbb Q # utasítás és direktíva véget ér a pontosvesszővel, `;`.
Az olyan utasítások és deklarációk, mint például a `for` és `operation`, amelyek egy utasítási blokk végén nem igénylik a megszakítást pontosvesszővel.
Minden utasítás leírása megállapítja, hogy kötelező-e lezáró pontosvessző.

Az utasítások, például a kifejezések, a deklarációk és az irányelvek több sorban is kibonthatók.
Az egyetlen sorban több utasítást kell elkerülni.

## <a name="statement-blocks"></a>Utasítások blokkja

A Q # utasítások utasítás blokkokba vannak csoportosítva.
Egy utasítás-blokk egy nyitó `{` kezdődik, és záró `}`végződik.

Egy másik blokkban található, lexikálisan zárt utasítási blokk a tartalmazó blokk alblokkjának tekintendő; a és az alblokkokat külső és belső blokkoknak is nevezik.

## <a name="symbol-binding-and-assignment"></a>Szimbólum kötése és hozzárendelése

A Q # megkülönbözteti a megváltoztathatatlan és a nem módosítható szimbólumokat.
Általánosságban a nem módosítható szimbólumok használata javasolt, mivel lehetővé teszi, hogy a fordító több optimalizációt végezzen.

A kötés bal oldali lapja egy szimbólumból álló rekordból és egy kifejezés jobb oldaláról áll.

Mivel az összes Q # típus a Value types – a qubits valamivel speciális szerepkört használ – a "Copy" szó akkor jön létre, amikor egy érték egy szimbólumhoz van kötve, vagy ha egy szimbólum van kötve. Ez azt jelenti, hogy a Q # viselkedése megegyezik azzal, mintha egy másolat lett létrehozva a hozzárendelésen. Ez különösen magában foglalja a tömböket is. A gyakorlatban természetesen csak az érintett darabok szükségesek a létrehozásuk során. 

### <a name="tuple-deconstruction"></a>Rekord kiépítése

Ha a kötés jobb oldalán egy rekord található, akkor a rekord a hozzárendelés után kiépíthető.
Ezek a dekonstrukciók beágyazott rekordok tartalmazhatnak, és a teljes vagy részleges kiépítés akkor érvényes, ha a jobb oldalon lévő rekord alakja kompatibilis a szimbólum rekordjának formájával.
A rekord Dekonstrukciója különösen akkor használható, ha a `=` jobb oldalán egy rekord értékű kifejezés szerepel.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Nem változtatható szimbólumok

A megváltoztathatatlan szimbólumok a `let` utasítással köthetők.
Ez nagyjából megegyezik a változó deklarációval és az inicializálással olyan nyelveken C#, mint például a Q # szimbólumok, ha a kötés nem módosítható; `let` kötések nem változtathatók meg.

A nem módosítható kötés a következő kulcsszóból áll: `let`, majd egy szimbólum vagy egy Symbol rekord, egy egyenlőségjel `=`, egy kifejezés, amely a szimbólum (oka) t köti, és leállítja a pontosvesszőt.
A kötött szimbólum (ok) típusa a jobb oldali kifejezésen alapul.

### <a name="mutable-symbols"></a>Változtatható szimbólumok

A megváltoztathatatlan szimbólumok meghatározása és inicializálása a `mutable` utasítás használatával történik.
Előfordulhat, hogy egy `mutable` utasítás részeként deklarált és kötött szimbólumok a kód későbbi részében más értékre lesznek kötve. 

A megváltoztathatatlan kötési utasítás a `mutable`kulcsszót, egy szimbólum vagy egy Symbol rekord, egy egyenlőségjel `=`, egy kifejezés, amely a szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.
A kötött szimbólum (ok) típusa a jobb oldali kifejezésen alapul. Ha egy szimbólum később van kötve a kódban, a típusa nem változik, és a kötött értéknek kompatibilisnek kell lennie az adott típussal.

### <a name="rebinding-of-mutable-symbols"></a>Változtatható szimbólumok újrakötése

Egy változtatható változó lehet egy `set` utasítás használatával.
Az ilyen újrakötések a kulcsszó `set`, majd egy szimbólum vagy egy Symbol rekord, egy egyenlőségjel `=`, egy kifejezés, amely a szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.
Az értéknek kompatibilisnek kell lennie azon szimbólum (ok) típusával, amelyhez hozzá van kötve.

#### <a name="apply-and-reassign-statement"></a>Alkalmazás-és ismételt hozzárendelési utasítás

A set-utasítás egy adott típusra hivatkozik, amely az alkalmazási és az ismételt hozzárendelési utasításra utal, és a jobb oldali összefűzést is lehetővé teszi, ha a jobb oldal egy bináris operátor alkalmazásából áll, és az eredmény a kezelőhöz a bal argumentumhoz lesz kötve. Például:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
a `for` hurok minden egyes iterációjában növeli a számláló `counter` értékét. A fenti kód egyenértékű a következővel 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Hasonló utasítások érhetők el minden olyan bináris operátor esetében, amelyben a bal oldali oldal típusa megegyezik a kifejezés típusával. Ez például az értékek összegyűjtésének kényelmes módja:
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Utasítás frissítése és újbóli társítása

Hasonló Összefűzés található a jobb oldali másolási és frissítési kifejezésekhez. Ennek megfelelően a rendszer a felhasználó által definiált típusokban és a tömbökben lévő megnevezett elemek esetében is tartalmazza a frissítés és az ismételt hozzárendelés utasításait.  

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

Tömbök esetén a szabványos kódtárak tartalmazzák a szükséges eszközöket számos gyakori tömb inicializálási és manipulációs igényéhez, így elkerülhető, hogy az első helyen ne kelljen frissíteni a tömb elemeit. Az Update-and-reassign utasítások szükség esetén alternatív megoldást nyújtanak:

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

> [!TIP]   
> A <xref:microsoft.quantum.arrays>által biztosított eszközök kihasználása révén elkerülhető a frissítési és a hozzárendelési utasítások szükségtelen használata.

A függvény
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
például egyszerűen egyszerűsíthető a `Microsoft.Quantum.Arrays``ConstantArray` függvény, valamint egy másolási és frissítési kifejezés visszaadása:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Kötési hatókörök

Általánosságban elmondható, hogy a szimbólumokra vonatkozó kötések kikerülnek a hatókörből, és a blokk végén nem válnak elérhetővé.
A szabálynak két kivétele van:

- Egy `for` hurok loop változójának kötése a for loop törzséhez tartozik, de a hurok vége után nem.
- A `repeat`/`until` hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.

Mindkét típusú hurok esetében a hurok továbbítása a saját hatókörében történik, így a korábbi pass-kötések nem érhetők el egy későbbi menetben.

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

## <a name="control-flow"></a>Átvitelvezérlés

### <a name="for-loop"></a>Hurok esetén

A `for` utasítás egy egész tartományon vagy egy tömbön keresztül támogatja az ismétlést.
Az utasítás a következő kulcsszóból áll: `for`, egy nyitó zárójel `(`, amelyet egy szimbólum vagy egy szimbólum, a kulcsszó `in`, egy `Range` vagy tömb típusú kifejezés, egy záró zárójel `)`és egy utasítás blokkja.

A rendszer az utasítás blokkját (a hurok törzsét) többször hajtja végre, és a definiált szimbólum (ok) (a hurok változói) a tartomány vagy tömb egyes értékeihez van kötve.
Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem lesz végrehajtva.
A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és a hurok végrehajtása közben nem változik.

A deklarált szimbólum (ok) kötése nem módosítható, és ugyanazokat a szabályokat követi, mint a többi változó kötése. Különösen lehetséges az elpusztulás, például a tömb elemeinek megismétlése egy tömbben a hurok változóhoz való hozzárendelés után.

Például:

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

A hurok változó a hurok törzsének minden bejáratánál, a törzs végén pedig nem köthető.
A Loop változó nem kötődik a for ciklus befejeződése után.

### <a name="repeat-until-success-loop"></a>REPEAT-ig-Success hurok

A `repeat` utasítás az "ismétlés a sikerig" mintát támogatja.
A kulcsszó `repeat`, majd egy utasítási blokk (a _hurok_ törzse), a kulcsszó `until`, a logikai kifejezés, valamint a lezáró pontosvessző vagy a kulcsszó `fixup`, amelyet egy másik utasítás (a _javítás_) követ.
A hurok törzse, állapota és kijavítása egyetlen hatókörnek tekintendő, így a törzsben lévő szimbólumok a feltételben és a javításban is elérhetők.

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

A rendszer végrehajtja a hurok törzsét, majd kiértékeli a feltételt.
Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a rendszer végrehajtja a javítást, és az utasítást a hurok törzsének megfelelően újra végrehajtja.
Vegye figyelembe, hogy a javítás végrehajtásának befejezése befejezi az utasítás hatókörét, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődésekben.

A következő kód például egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt{5}$-T a Hadamard és a T Gates használatával.
A hurok a $ \frac{8}{5}$ ismétlődések átlagában leáll.
A részletekért lásd [ *: egyszeres qubit unitaries*](https://arxiv.org/abs/1311.1074) (Petrovics és Svore, 2014) nem determinisztikus bontása.

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

> [!TIP]   
> Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát. A kapcsolódó funkciókat a függvények hurkoi is biztosítják. 

### <a name="while-loop"></a>Ciklus közben

A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik. Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi összeállítás Q #-ban. Azonban az olyan hurkok, amelyek feltételen alapulnak, és amelynek végrehajtási hosszát a fordítási időn belül ismeretlennek kell lenniük, a kvantum-futtatókörnyezetben különös gondossággal kell kezelni. A függvényeken belüli használatuk azonban nem problémamentes, mivel ezek csak a hagyományos (nem Quantum) hardveren végrehajtandó kódokat tartalmaznak. 

A Q # ezért a csak functions-ben lévő hurkok használatát támogatja. A `while` utasítás a kulcsszó `while`, egy nyitó zárójel `(`, egy feltétel (például egy logikai kifejezés), egy záró zárójel `)`és egy utasítás blokkból áll.
A rendszer az utasítás blokkját (a hurok törzsét) hajtja végre, amíg a feltétel kiértékelése `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Feltételes utasítás

A `if` utasítás támogatja a feltételes végrehajtást.
A kulcsszó `if`, egy nyitó zárójel `(`, egy logikai kifejezésből, egy záró zárójelből `)`ből és egy utasításból álló blokkból áll ( _Ez a blokk_ ).
Ezt követheti tetszőleges számú Else-if záradék, amelyek mindegyike a következő kulcsszóból áll: `elif`, egy nyitó zárójel `(`, egy logikai kifejezés, egy záró zárójel `)`és egy utasítás blokkja (a _másik, ha_ blokk).
Végül az utasítás opcionálisan egy másik záradékkal is kiegészíthető, amely a kulcsszó `else` és egy másik utasítás (az _Else_ blokk) után következik be.
A rendszer kiértékeli a feltételt, és ha az értéke igaz, a rendszer végrehajtja a letiltást.
Ha a feltétel hamis, akkor az első más-if feltétel kiértékelése megtörténik. Ha az értéke igaz, akkor ez a másik a blokkolás végrehajtása.
Ellenkező esetben a második, ha a blokkot teszteli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.
Ha az eredeti if feltétel és az összes más-if záradék hamis értéket ad vissza, akkor a rendszer a másik blokkot hajtja végre, ha meg van határozva.

Vegye figyelembe, hogy a rendszer bármelyik blokkot a saját hatókörében hajtja végre.
Az IF utasítás vége után nem láthatók az olyan kötések, amelyek egy, a "Máskülönben" vagy "else" blokkon belül történnek.

Például:

```qsharp
if (result == One) {
    X(target);
} 
```

vagy

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>Visszatérési

A Return utasítás egy művelet vagy függvény végrehajtását hajtja végre, és egy értéket ad vissza a hívónak.
A kulcsszó `return`, majd a megfelelő típusú kifejezéssel, valamint egy pontosvesszővel végződik.

Egy üres rekordot visszaadó hívható, `()`, nem igényel visszatérési utasítást.
Ha korai kilépés szükséges, `return ()` lehet használni ebben az esetben.
A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.

Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.
A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.

Például:

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

### <a name="fail"></a>Sikertelen

A Fail utasítás befejezi a művelet végrehajtását, és hibaértéket ad vissza a hívónak.
A kulcsszó `fail`, majd egy karakterláncot és egy lezáró pontosvesszőt tartalmaz.
A rendszer a karakterláncot a klasszikus illesztőprogramnak adja vissza hibaüzenetként.

A műveleteken belüli sikertelen utasítások száma nincs korlátozva.
A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.

Például:

```qsharp
fail $"Impossible state reached";
```

vagy

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Qubit-kezelés

Vegye figyelembe, hogy a függvények törzsében egyik utasítás sem engedélyezett.
Csak a műveleteken belül érvényesek.

### <a name="clean-qubits"></a>Qubits tisztítása

A `using` utasítás az új qubits beolvasására szolgál az utasítási blokkokban való használatra.
A qubits a számítási `Zero` állapotba való inicializálása garantált.
A qubits a számlakivonat végén lévő számítási `Zero` állapotban kell lennie; a szimulátorokat javasoljuk, hogy kényszerítse ezt.

Az utasítás a `using`kulcsszóból áll, amelyet egy nyitó zárójel `(`, egy kötés, egy záró zárójel `)`, valamint a qubits elérhetővé tételére szolgáló utasítás blokkja is tartalmaz.
A kötés ugyanazt a mintát követi, mint a `let`i utasítások: vagy egy szimbólumot vagy egy szimbólumot, majd egy egyenlőségjel `=`, és egy vagy több inicializáló egyező rekordot.
Az inicializálók egyetlen qubit érhetők el, amelyek `Qubit()`ként vannak megjelölve, vagy egy `Qubit[`, `Int` kifejezés és `]`által jelzett qubits tömbje.

Például:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Kölcsönzött qubits

A `borrowing` utasítás az ideiglenes használatra szolgáló qubits beszerzésére szolgál. Az utasítás a `borrowing`kulcsszóból áll, amelyet egy nyitó zárójel `(`, egy kötés, egy záró zárójel `)`, valamint a qubits elérhetővé tételére szolgáló utasítás blokkja is tartalmaz.
A kötés ugyanazokat a mintákat és szabályokat követi, mint egy `using` utasításban.

Például:

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

A kölcsönzött qubits ismeretlen állapotban vannak, és az utasítás blokk végén kiléphetnek a hatókörből.
A hitelfelvevő vállalja, hogy a qubits ugyanabban az állapotban hagyja, mint amikor a kölcsönbe kerültek, azaz az utasítás blokkjának elején és végén lévő állapotuknak azonosnak kell lennie.
Ez az állapot különösen nem feltétlenül klasszikus állapotban van, így a legtöbb esetben a hitelfelvételi hatókörök nem tartalmazhatnak mértékeket. 

Tekintse meg a [*Toffoli-alapú Többtényezős 2017 (2n + 2) qubits a*](https://arxiv.org/abs/1611.07995) kölcsönzött Svore-használatra vonatkozó példát.

A qubits hitelfelvételkor a rendszer először megpróbálja betölteni a kérést a használatban lévő qubits, de a `borrowing` utasítás törzsében nem érhetők el.
Ha nincs elég ilyen qubits, akkor a kérés teljesítéséhez új qubits fog kiosztani.

## <a name="conjugations"></a>Conjugations

A klasszikus BITS-vel szemben a kvantum-memória felszabadítása valamivel nagyobb mértékben történik, mivel a qubits vakon alaphelyzetbe állítása nem kívánt hatással lehet a fennmaradó számításra, ha a qubits továbbra is összefonódik. Ezt elkerülheti, ha a memóriát a memória felszabadítása előtt megfelelően elvégezte. A kvantum-számítástechnika általános mintája a következő: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: új: a 0,9-es verziótól kezdődően a fenti átalakítást megvalósító ragozó utasítást támogatunk. Az utasítás használatával a `ApplyWith` művelet a következő módon valósítható meg:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Egy ilyen ragozó utasítás nyilvánvalóan sokkal hasznosabb lehet, ha a külső és belső átalakítás nem érhető el azonnal, hanem több utasításból álló blokk alapján. 

A blokkon belül definiált utasítások inverz átalakítását a fordító automatikusan hozza létre, és az Apply-Block befejeződése után hajtja végre. Mivel a blokk részeként használt változó változók nem használhatók fel az alkalmazás-blokkban, a generált transzformáció garantált, hogy a adjoint a blokkon belül. 

## <a name="expression-evaluation-statements"></a>Kifejezés-értékelési utasítások

A `Unit` típusú hívási kifejezések utasításként is használhatók.
Ez elsősorban akkor használatos, ha a qubits olyan műveleteket hív meg, amelyek `Unit` adnak vissza, mert az utasítás célja az implicit kvantum állapotának módosítása.
A kifejezés-értékelési utasításokhoz pontosvesszőt kell lezárni.

Például:

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
