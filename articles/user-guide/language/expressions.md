---
title: 'Kifejezések megadása a Q-ban #'
description: 'Megtudhatja, hogyan adhat meg, hivatkozhat és egyesíthet állandókat, változókat, operátorokat, műveleteket és függvényeket kifejezésként a Q #-ban.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431206"
---
# <a name="type-expressions-in-q"></a>Kifejezések megadása a Q-ban #

## <a name="numeric-expressions"></a>Numerikus kifejezések

A numerikus kifejezések a következő típusú kifejezések:, `Int` `BigInt` vagy `Double` .
Vagyis egész vagy lebegőpontos számok.

`Int`a Q # literálok csak számjegyek sorozatából írhatók.
A hexadecimális és a bináris egész számok a `0x` és a `0b` előtaggal támogatottak.

`BigInt`a Q # karakteres literálok egy záró `l` vagy `L` utótaggal íródnak.
A hexadecimális nagy egész számok "0x" előtaggal támogatottak.
Így az alábbi értékek érvényesek a literálok összes érvényes használatára `BigInt` :

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`a Q # literális lebegőpontos számok, amelyek decimális számjegyek használatával íródnak.
Ezek írhatók decimális ponttal, `.` és/vagy az "e" vagy "e" karakterrel jelzett exponenciális rész (amely után csak egy lehetséges negatív jel és decimális számjegy érvényes).
A következő érvényes `Double` literálok: `0.0` , `1.2e5` , `1e-5` .

Egy adott elemtípus tömb kifejezése miatt a beépített függvénnyel létrehozható egy `Int` kifejezés, [`Length`](xref:microsoft.quantum.core.length) amely zárójelek közé foglalt tömb kifejezéssel `(` és `)` .
Ha például `a` egy tömbhöz van kötve, akkor az egy `Length(a)` egész szám kifejezés.
Ha `b` az egész számokból álló tömbök tömbje, akkor a- `Int[][]` ben az `Length(b)` altömbök száma, a `b` `Length(b[1])` pedig a második altömbben lévő egész számok száma `b` .

Az adott típus két numerikus kifejezése, a bináris operátorok, a, `+` `-` és az `*` `/` új numerikus kifejezéseket is felhasználhatja.
Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.

A két egész szám kifejezés miatt a bináris operátor `^` (Power) egy új egész kifejezés létrehozásához használható.
Hasonlóképpen, két kettős kifejezéssel is használható, amelyek `^` új dupla kifejezést alkotnak.
Végül a `^` bal oldalon egy nagy egész számmal, a jobb oldalon pedig egy egész számmal, egy új Big Integer típusú kifejezés létrehozásához is használható.
Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, a rendszer futásidejű hibát jelez.

A két egész vagy nagy egész szám típusú kifejezés esetében egy új egész vagy Big Integer kifejezés is létrehozható a `%` (modulus), `&&&` (bitenkénti és), `|||` (bitenkénti vagy), vagy `^^^` (bitenkénti XOR) operátorok használatával.

A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) vagy `>>>` (aritmetikai jobbra váltás) operátorok használhatók a bal oldali kifejezéssel megegyező típusú új kifejezés létrehozására.

A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.
A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, a rendszer futásidejű hibát jelez.
Ha az áthelyezhető szám egész szám, akkor a rendszer a eltolási értéket fogja értelmezni, `mod 64` azaz az 1. és a 65-es váltás hatása megegyezik.

Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.
A negatív érték eltolása balra vagy jobbra is negatív számot eredményez.
Ez azt okozhatja, hogy az egyik lépés balra vagy jobbra való eltolása pontosan ugyanaz, mint a 2. számú szorzás vagy osztás.

Az egész szám és az Integer modulus ugyanazt a viselkedést követi a negatív számok esetében, mint a C#.
Ez azt `a % b` eredményezi, hogy mindig ugyanazzal a jellel fog rendelkezni `a` , és `b * (a / b) + a % b` mindig egyenlő lesz `a` .
Például:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

A Big Integer osztás és a modulus hasonló módon működik.

A numerikus kifejezéseket megadva egy új kifejezés hozható létre az `-` unáris operátor használatával.
Az új kifejezés ugyanolyan típusú lesz, mint az összetevő kifejezése.

Adott egész szám vagy nagy egész szám kifejezés esetén az azonos típusú új kifejezés az `~~~` (bitenkénti komplement) unáris operátor használatával hozható létre.

## <a name="boolean-expressions"></a>Logikai kifejezések

A két `Bool` literális érték a `true` és a `false` .

Az azonos primitív típusú két kifejezés miatt a `==` és a `!=` bináris operátor is használható kifejezés létrehozásához `Bool` .
A kifejezés akkor igaz, ha a két kifejezés egyenlő, és hamis, ha nem.

A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani. Például a "kicsomagolás" operátor használatával `!` (részletes magyarázat a [Q # típusokban](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator))

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Az értékek egyenlőségének összehasonlítása az `Qubit` identitással egyenlő, azaz azt, hogy a két kifejezés ugyanazt a qubit azonosítja-e.
A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.

Az értékek egyenlőségének összehasonlítása a `Double` kerekítési hatások miatt félrevezető lehet.
Például: `49.0 * (1.0/49.0) != 1.0` .

A két numerikus kifejezéstől függően a bináris operátorok, a, `>` `<` `>=` és `<=` felhasználhatók egy olyan új logikai kifejezés létrehozására, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, mint a második kifejezés.

A két logikai kifejezés miatt a `and` és a `or` bináris operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha a két kifejezés mindkét (vagy mindkét) értéke igaz.

A logikai kifejezéseket megadva az `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.

## <a name="string-expressions"></a>Karakterlánc-kifejezések

A Q # lehetővé teszi a karakterláncok használatát az `fail` utasításban (a [vezérlési folyamat](xref:microsoft.quantum.guide.controlflow#fail-statement)ismertetése) és a [`Message`](xref:microsoft.quantum.intrinsic.message) standard függvényben.
Az utóbbi adott viselkedése a használt szimulátortól függ, de általában egy üzenetet ír a gazdagép-konzolra, amikor a rendszer egy Q # programban hívja meg.

A Q # sztringek literálok vagy interpolált karakterláncok.

A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterlánc-literálokra: az Unicode-karakterek egy számsorozata idézőjelek közé `"` .
Egy karakterláncon belül a háttér-perjel karakter `\` felhasználható dupla idézőjelek kiírására, valamint egy új vonal beszúrására, `\n` a kocsivissza karaktert `\r` és a lapot `\t` .
Ilyenek például a következők:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Interpolált karakterláncok

A Q # szintaxis a karakterlánc-Interpolációk esetében a C# szintaxis egy részhalmaza, de itt összefoglaljuk azokat a kulcsfontosságú pontokat, amelyek a Q #-ra vonatkoznak.
A legfontosabb különbségeket az alábbiakban tárgyaljuk.

Ha egy szövegkonstans-karakterláncot interpolált karakterláncként szeretne azonosítani, a szimbólummal megadhatja azt `$` .
A és a között nem lehet szóköz, `$` `"` amely egy szövegkonstans-karakterláncot indít el.

A következő példa egy olyan alapszintű példát mutat be, amely a [`Message`](xref:microsoft.quantum.intrinsic.message) mérés eredményét a konzolra írja, más Q # kifejezésekkel együtt.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Bármely érvényes Q # kifejezés egy interpolált karakterláncban jelenhet meg.

A C# szintaxissal kapcsolatos további részletek az [*interpolált karakterláncokban*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)találhatók.
A legfontosabb különbség az, hogy a Q # nem támogatja a Verbatim (többsoros) interpolált karakterláncokat.
Az interpolált karakterláncban szereplő kifejezések a Q # szintaxist követik, nem a C# szintaxist.

## <a name="range-expressions"></a>Tartomány kifejezései

`Int`Egy három kifejezés `start` , a `step` és a `stop` `start .. step .. stop` egy olyan tartomány kifejezése, amelynek első eleme a, a `start` második elem `start+step` , a harmadik elem, `start+step+step` stb., amíg `stop` a rendszer át nem adja.
A tartomány lehet üres, ha például a `step` pozitív és a `stop < start` .
A tartomány utolsó eleme abban az esetben lesz `stop` , ha a és a közötti különbség a `start` `stop` többszöröse `step` ; vagyis a tartomány mindkét végén szerepel.

`Int`A két kifejezésnek `start` `stop` megfelelő, és `start .. stop` egy tartománybeli kifejezés, amely egyenlő `start .. 1 .. stop` .
Vegye figyelembe, hogy a vélelmezett `step` érték + 1 `stop` , akkor is, ha kevesebb, mint `start` ; ebben az esetben a tartomány üres.

Néhány példa a tartományokra:

- `1..3`az 1., 2. és 3. tartomány.
- `2..2..5`a 2. és 4. tartomány.
- `2..2..6`a 2, 4, 6. tartomány.
- `6..-2..2`a 6, 4, 2 tartomány.
- `2..1`az üres tartomány.
- `2..6..7`a 2. tartomány.
- `2..2..1`az üres tartomány.
- `1..-1..2`az üres tartomány.

## <a name="qubit-expressions"></a>Qubit kifejezések

Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékek vagy tömb elemeihez van kötve `Qubit` .
Nincsenek `Qubit` literálok.

## <a name="pauli-expressions"></a>Pauli-kifejezések

A négy érték:,,, `Pauli` `PauliI` `PauliX` `PauliY` és `PauliZ` , minden érvényes `Pauli` kifejezés.

Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékek vagy tömb elemeihez van kötve `Pauli` .

## <a name="result-expressions"></a>Eredmény kifejezései

A két `Result` érték ( `One` és `Zero` `Result` ) érvényes kifejezés.

Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékek vagy tömb elemeihez van kötve `Result` .
Különösen fontos megjegyezni, hogy `One` nem ugyanaz, mint az egész szám `1` , és nincs közvetlen konverzió a közöttük.
Ugyanez érvényes a és a esetében is `Zero` `0` .

## <a name="tuple-expressions"></a>Rekordos kifejezések

A rekordos literál a megfelelő típusú elemek sorozata, vesszővel elválasztva, a és a közé foglalt módon `(` `)` .
Például `(1, One)` egy `(Int, Result)` kifejezés.

A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.

## <a name="user-defined-type-expressions"></a>Felhasználó által definiált típusú kifejezések

A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.
Ha például a `IntPair` felhasználó által definiált típus a (z) alapján `(Int, Int)` , akkor az `IntPair(2, 3)` adott típusú érvényes literál lenne.

A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.

## <a name="unwrap-expressions"></a>Kifejezések kicsomagolása

A Q # értéknél a kicsomagolás operátor egy záró felkiáltójel `!` .
Például, ha `IntPair` egy felhasználó által definiált típus, amely egy alapul szolgáló típussal rendelkezik `(Int, Int)` , és `s` egy változó értékkel rendelkezik `IntPair(2, 3)` , akkor a következő `s!` lesz: `(2, 3)` .

A felhasználó által definiált típusok esetében definiált más felhasználók által definiált típusok esetében. lehet, hogy a kicsomagolási operátor megismétlődik; például `s!!` a kétszeresen kicsomagolt értéket jelöli `s` .
Így ha a `WrappedPair` felhasználó által definiált típus egy alapul szolgáló típusú `IntPair` , és `t` egy változó értékkel `WrappedPair(IntPair(1,2))` , akkor a következő `t!!` lesz: `(1,2)` .

Az `!` operátor magasabb prioritású, mint az összes többi operátor `[]` , mint a tömb indexelése és a szeletelése.
`!`és a `[]` kötés elhelyezése, azaz a `a[i]![3]` következőképpen kell elolvasni `((a[i])!)[3]` : a `i` "th elemének `a` kicsomagolása, a kicsomagolása, majd a nem burkolt érték harmadik elemének beolvasása (tömbnek kell lennie).

Az operátor elsőbbsége `!` egy olyan hatással van, amely esetleg nem nyilvánvaló.
Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.
Például:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Tömb kifejezései

A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, a és a `[` közé `]` .
Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.


Mivel a két tömb azonos típusú, a bináris `+` operátor egy olyan új tömb létrehozásához használható, amely a két tömb összefűzése.
Például: `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Tömb létrehozása

Adott típus és kifejezés alapján `Int` az `new` operátor felhasználható a megadott méretű új tömb kiosztására.
Például `new Int[i + 1]` lefoglalhat egy új `Int` tömböt `i + 1` elemekkel.

Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.
A legtöbb esetben ez a nulla valamilyen változata.

Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.
Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely futásidejű hiba nélkül nem használható.
Ez hasonló a más nyelveken (például C# vagy Java) található null hivatkozáshoz.
A qubits vagy callables tartalmazó tömböket megfelelően kell inicializálni a nem alapértelmezett értékekkel, mielőtt az elemek biztonságosan használhatók legyenek. A megfelelő inicializálási rutinok a következő címen találhatók: <xref:microsoft.quantum.arrays> .

Az egyes típusok alapértelmezett értékei a következők:

Típus | Alapértelmezett
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Érvénytelen qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Az üres tartomány,`1..1..0`
 `Callable` | _Érvénytelen hívható_
 `Array['T]` | `'T[0]`

A rekord típusú típusok inicializálása elem-by-Element.


### <a name="array-elements"></a>Tömb elemei

Egy tömb kifejezése és egy `Int` kifejezés alapján egy új kifejezés is létrehozható a `[` és a `]` tömb elem operátor használatával.
Az új kifejezés ugyanolyan típusú lesz, mint a tömb elemének típusa.
Ha például `a` egy tömbhöz van kötve `Double` , akkor `a[4]` egy `Double` kifejezés.

Ha a tömb kifejezése nem egyszerű azonosító, zárójelek közé kell tenni, hogy ki lehessen választani egy elemet.
Ha például a `a` és `b` mindkét tömbje `Int` , az összefűzésből származó elem a következőként lesz kifejezve:

```qsharp
(a + b)[13]
```

A Q # összes tömbje nulla-alapú.
Vagyis a tömb első eleme `a` mindig `a[0]` .


### <a name="array-slices"></a>Tömb szeletek

Egy tömböt megadó kifejezés és egy `Range` kifejezés alapján egy új kifejezés is létrehozható a `[` és a `]` tömb szelet operátor használatával.
Az új kifejezés ugyanolyan típusú, mint a tömb, és a () elemei által indexelt tömb elemeket fogja tartalmazni `Range` a által definiált sorrendben `Range` .
Ha például egy `a` tömbhöz van kötve `Double` , akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely az első négy elemét tartalmazza, `a` de a fordított sorrendben, ahogy azok megjelennek a következőben: `a` .

Ha az `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú lesz.

A tömb elemeihez hasonlóan, ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell tenni a szelethez.
Ha `a` és `b` mindkét tömbje `Int` , az összefűzésből származó szeletek a következőképpen lesznek kifejezve:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Következtetett kezdő/záró értékek

A 0,8-es verziótól kezdődően a hatókör-szeletelők környezetfüggő kifejezéseket támogatunk. A tartomány indítási és befejezési értékei a tartomány-szeletelő kifejezés kontextusában is kihagyhatók. Ebben az esetben a fordító a következő szabályok alkalmazásával következteti ki a tartományhoz tartozó elhatárolókat. 

Ha például a tartomány indítási értéke kimarad, akkor a késleltetett indítási érték 
- nulla, ha nincs megadva lépés, vagy a megadott lépés pozitív, és 
- a szeletelt tömb hossza mínusz eggyel, ha a megadott lépés negatív. 

Ha a tartomány befejezési értéke kimarad, akkor a következtetett vég értéke 
- a szeletelt tömb hossza mínusz eggyel, ha nincs megadva lépés, vagy a megadott lépés pozitív, és 
- nulla, ha a megadott lépés negatív. 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Másolás és frissítés kifejezések

Mivel az összes Q # típus érték típusú, és a qubits némileg speciális szerepkört vesznek fel – a "Copy" szó akkor jön létre, amikor egy érték egy szimbólumhoz van kötve, vagy ha egy szimbólum újra van kötve. Ez azt jelenti, hogy a Q # viselkedése megegyezik azzal, mintha egy másolat lett létrehozva a hozzárendelésen.
A gyakorlatban természetesen csak az érintett darabok szükségesek a létrehozásuk során. 

Ez különösen magában foglalja a tömböket is.
Különösen nem lehetséges a tömb elemeinek frissítése. Egy meglévő tömb módosításához a *copy-Update* mechanizmust kell használnia.

Új tömbök hozhatók létre a meglévő *példányokból másolás és frissítés* kifejezések használatával.
A copy-Update kifejezés az űrlap kifejezése `expression1 w/ expression2 <- expression3` , amelyben valamilyen típusú típusnak `expression1` kell lennie `T[]` `T` .
A második `expression2` meghatározza, hogy az elem (ek) milyen indexeket módosítson a tömbhöz képest, `expression1` és a típusnak vagy típusúnak kell lennie `Int` `Range` .
Ha a `expression2` típusa típusú `Int` , a `expression3` típusnak kell lennie `T` . Ha a `expression2` típusa típusú `Range` , a `expression3` típusnak kell lennie `T[]` .

A másolási és frissítési kifejezés `arr w/ idx <- value` egy új tömböt hoz létre, amely a megfelelő elemre van állítva `arr` , kivéve a (z) elem (ek) et, amely a (z) értékre `idx` van beállítva `value` . Ha például `arr` egy tömböt tartalmaz `[0,1,2,3]` , akkor 
- `arr w/ 0 <- 10`a tömb `[10,1,2,3]` .
- `arr w/ 2 <- 10`a tömb `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`a tömb `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Elnevezett elemek másolási és frissítési kifejezései

A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez. 

Vegyük például a típust 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Ha `c` a érték tartalmazza a Type értéket `Complex(1., -1.)` , akkor a a `c w/ Re <- 0.` következő típusú kifejezést adja `Complex` vissza: `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Szaggatott tömbök

Egy szaggatott tömb, más néven "tömbök tömbje", egy tömb, amelynek elemei tömbök.
A szaggatott tömb elemei eltérő méretűek lehetnek.
Az alábbi példa azt szemlélteti, hogyan deklarálható és inicializálható egy többrészes táblát jelképező szaggatott tömb.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Callables tömbök 

Vegye figyelembe, hogy a hívható típusokkal kapcsolatos további részletek az alábbiakban láthatók, valamint a következő oldalon a [Q #-ban található műveletek és függvények](xref:microsoft.quantum.guide.operationsfunctions).

Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.
A tömb elemének típusa az összes elem által támogatott összes olyan futtatót támogatni fogja.
Például, ha, `Op1` `Op2` és `Op3` mind a `Qubit[] => Unit` , de támogatja `Op1` `Adjoint` , `Op2` támogatja `Controlled` és `Op3` támogatja a következőket:

- `[Op1, Op2]`a a műveletek tömbje `(Qubit[] => Unit)` .
- `[Op1, Op3]`a a műveletek tömbje `(Qubit[] => Unit is Adj)` .
- `[Op2, Op3]`a a műveletek tömbje `(Qubit[] => Unit is Ctl)` .

Az üres tömb literálok `[]` nem engedélyezettek.
A használata helyett, `new ★[0]` ahol a `★` egy megfelelő típusú helyőrző, lehetővé teszi a nulla hosszúságú kívánt tömb létrehozását.


## <a name="conditional-expressions"></a>Feltételes kifejezések

Egy adott típus és egy logikai kifejezés két másik kifejezése alapján a feltételes kifejezés a kérdőjel `?` és a függőleges sáv használatával hozható létre `|` .
Például: `a==b ? c | d` .
Ebben a példában a feltételes kifejezés értéke `c` `a==b` true (igaz `d` ) és false (hamis) lesz.

### <a name="conditional-expressions-with-callables"></a>Feltételes kifejezések callables

A két kifejezés kiértékelheti azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.
Ebben az esetben a feltételes kifejezés típusa olyan művelet, amely azokat a bemeneteket és kimeneteket támogatja, amelyek a mindkét kifejezés által támogatott összes feltételt támogatják.
Például, ha, `Op1` `Op2` és `Op3` mind a `Qubit[]=>Unit` , de támogatja `Op1` `Adjoint` , `Op2` támogatja `Controlled` és `Op3` támogatja a következőket:

- `flag ? Op1 | Op2`egy `(Qubit[] => Unit)` művelet.
- `flag ? Op1 | Op3`egy `(Qubit[] => Unit is Adj)` művelet.
- `flag ? Op2 | Op3`egy `(Qubit[] => Unit is Ctl)` művelet.

Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor ez a hívás csak akkor kerül sor, ha az eredmény a hívás értéke lesz.
`a==b ? C(qs) | D(qs)`Ha például `a==b` igaz, akkor a rendszer `C` meghívja a műveletet, és ha hamis, akkor csak a rendszer `D` hívja meg.
Ez hasonló a más nyelvek rövid összekapcsolásához.

## <a name="callable-expressions"></a>Hívható kifejezések

A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.
Például egy olyan `X` műveleti literál, amely a szabványos könyvtári `X` műveletre hivatkozik, és `Message` egy függvény literál, amely a standard Library `Message` függvényre hivatkozik.

Ha egy művelet támogatja az elválasztó műveletet `Adjoint` , akkor `Adjoint op` egy művelet kifejezése.
Hasonlóképpen, ha a művelet támogatja az elválasztó műveletet `Controlled` , akkor `Controlled op` egy művelet kifejezése.
Ezeknek a kifejezéseknek a típusa a [Hívási művelet specializációjában](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)van megadva.

A (z `Adjoint` ) és a (z) (és `Controlled` ) az összes többi operátornál jobban kötődik, kivéve a kicsomagolási operátort és a tömb indexelését a következővel: `!` [].
Így a következők mindegyike jogi, feltételezve, hogy a műveletek támogatják a használt munkafolyamatokat:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Típus – paraméteres hívható kifejezések

Egy meghívásos literál is használható értékként, azaz egy változóhoz való hozzárendeléshez, vagy egy másik meghíváshoz való továbbításhoz.
Ebben az esetben, ha a meghívható [paraméterekkel](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)rendelkezik, azokat a meghívásos érték részeként kell megadni.
Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel.

Ha például a `Fun` függvény aláírása `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Hívható hívási kifejezések

Egy meghívásos (művelet vagy függvény) kifejezés és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos kifejezés úgy hozható létre, hogy hozzáfűzi a rekord kifejezését a meghívható kifejezéshez.
A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.

Ha például `Op` az egy aláírással rendelkező művelet, a egy `((Int, Qubit) => Double)` `Op(3, qubit1)` típusú kifejezés `Double` .
Hasonlóképpen, ha `Sin` az egy függvény az aláírással `(Double -> Double)` , `Sin(0.1)` egy típusú kifejezés `Double` .
Végül, ha `Builder` az a függvény az aláírással `(Int -> (Int -> Int))` , akkor `Builder(3)` a függvény a from int értékre.

Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.
Így az előző bekezdésből történő hívás eredményének meghívásához `Builder` a helyes szintaxis a következő:

```qsharp
(Builder(3))(2)
```

A [típus-paraméteres](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) metódus meghívásakor a tényleges Type paraméterek a szögletes zárójelben `<` és `>` a meghívásos kifejezés után is megadhatók.
Ez általában szükségtelen, mivel a Q # fordítóprogram a tényleges típusokat fogja kikövetkeztetni.
Azonban szükség *van* a [részleges alkalmazásra](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , ha egy Type-paraméteres argumentum nincs meghatározva.
Időnként hasznos lehet, ha a különböző felállókkal rendelkező műveletek átadása meghívásos támogatással történik.

Ha például `Func` rendelkezik aláírással, és aláírással rendelkezik, `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` és `Op3` aláírással rendelkezik `(Qubit[] => Unit)` , az `Func` `Op1` első argumentumként, `Op2` a másodikként és `Op3` a harmadikként való meghívásához:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A típus specifikációjának megadása kötelező `Op3` `Op1` , mert különböző típusok vannak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.


## <a name="operator-precedence"></a>Operátori prioritás

Minden bináris operátor megfelelő társítású, kivéve a következőt: `^` .

Szögletes zárójelek, `[` valamint `]` a tömb szeleteléséhez és indexeléséhez minden operátor előtt kötést kell kötni.

A kikapcsolók `Adjoint` és a `Controlled` kötés a tömb indexelése után, de az összes többi operátor előtt.

A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.

Az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:

Operátor | Aritása | Leírás | Operandusok típusai
---------|----------|---------|---------------
 záró`!` | Unáris | Kicsomagolása | Bármely felhasználó által definiált típus
 `-`, `~~~`, `not` | Unáris | Numerikus negatív, bitenkénti komplement, logikai tagadás | `Int`, `BigInt` vagy `Double` esetén `-` a `Int` `BigInt` `~~~` `Bool``not`
 `^` | Bináris | Egész számú Power | `Int`vagy az `BigInt` alaphoz `Int` a kitevő esetében
 `/`, `*`, `%` | Bináris | Osztás, szorzás, egész szám modulusa | `Int`, `BigInt` vagy `Double` `/` `*` `Int` `BigInt``%`
 `+`, `-` | Bináris | Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás | `Int``BigInt`vagy `Double` , vagy `String` bármely tömb típusa a következőhöz:`+`
 `<<<`, `>>>` | Bináris | Bal SHIFT, jobb SHIFT | `Int` vagy `BigInt`
 `<`, `<=`, `>`, `>=` | Bináris | Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás | `Int`, `BigInt` vagy`Double`
 `==`, `!=` | Bináris | egyenlő, nem egyenlő összehasonlítások | bármely primitív típus
 `&&&` | Bináris | Bitenkénti és | `Int` vagy `BigInt`
 `^^^` | Bináris | Bitenkénti XOR | `Int` vagy `BigInt`
 <code>\|\|\|</code> | Bináris | Bitenkénti vagy | `Int` vagy `BigInt`
 `and` | Bináris | Logikai és | `Bool`
 `or` | Bináris | Logikai vagy | `Bool`
 `..` | Bináris/Ternáris | Tartomány operátora | `Int`
 `?` `|` | Ternáris | Feltételes | `Bool`a bal oldali
`w/` `<-` | Ternáris | Másolás és frissítés | Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)

## <a name="whats-next"></a>Vajon mi a következő lépés?
Most, hogy a Q #-ban kifejezésekkel dolgozhat, a [q # műveletekhez és függvényekhez](xref:microsoft.quantum.guide.operationsfunctions) is megtudhatja, hogyan határozhatja meg és hívhatja meg a műveleteket és a függvényeket.
