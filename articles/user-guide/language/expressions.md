---
title: Kifejezések a Q#
description: Megtudhatja, hogyan adhat meg, hivatkozhat és egyesíthet állandókat, változókat, operátorokat, műveleteket és függvényeket kifejezésként a alkalmazásban Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9bf28e3854eae1892692d7ca840e1860de2e2934
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835842"
---
# <a name="expressions-in-no-locq"></a>Kifejezések a Q#

## <a name="numeric-expressions"></a>Numerikus kifejezések

A numerikus kifejezések a következő típusú kifejezések:, `Int` `BigInt` vagy `Double` .
Vagyis egész vagy lebegőpontos számok.

`Int` a konstansok Q# számjegyek sorozatából vannak írva.
A hexadecimális és a bináris egész számok támogatottak, és a `0x` és `0b` előtaggal vannak írva.

`BigInt` a konstansok Q# záró `l` vagy `L` utótaggal rendelkeznek.
A hexadecimális nagy egész számok támogatottak, és "0x" előtaggal írhatók.
Így az alábbi értékek érvényesek a literálok összes érvényes használatára `BigInt` :

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` a-ben a konstansok Q# számjegyek használatával írt lebegőpontos számok.
Megírhatók decimális ponttal vagy anélkül `.` , illetve az "e" vagy az "e" karakterrel jelzett exponenciális rész (amely után csak egy lehetséges negatív jel és decimális számjegy érvényes).
A következő érvényes `Double` literálok: `0.0` , `1.2e5` , `1e-5` .

Bármilyen típusú tömb kifejezése miatt `Int` a beépített függvény használatával kifejezéseket állíthat be a [`Length`](xref:microsoft.quantum.core.length) tömb kifejezés zárójelek közé.
Ha például `a` egy tömbhöz van kötve, akkor az egy `Length(a)` egész szám kifejezés.
Ha `b` az egész számokból álló tömbök tömbje, akkor a- `Int[][]` ben az `Length(b)` altömbök száma, a `b` `Length(b[1])` pedig a második altömbben lévő egész számok száma `b` .

Az adott típus két numerikus kifejezése, a bináris operátorok, a, `+` `-` és az `*` `/` új numerikus kifejezéseket is felhasználhatja.
Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.

A két egész szám kifejezésnek megfelelően a bináris operátor `^` (Power) használatával új egész kifejezést formálhat.
Ehhez hasonlóan két dupla kifejezés is használható `^` egy új dupla kifejezés létrehozásához.
Végül a `^` bal oldalon egy nagy egész számot és egy egész számot is használhat a jobb oldalon egy új Big Integer típusú kifejezés létrehozásához.
Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, futásidejű hibát jelez.

A megadott két egész vagy nagy egész szám típusú kifejezés egy új egész számot vagy egy Big Integer kifejezést alkot a `%` (modulus), `&&&` (bitenkénti és), `|||` (bitenkénti vagy), vagy `^^^` (bitenkénti XOR) operátorok használatával.

A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) vagy `>>>` (aritmetikai jobbra váltás) operátorok segítségével hozzon létre egy új kifejezést a bal oldali kifejezéssel megegyező típussal.

A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.
A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, futásidejű hibát jelez.
Ha az áthelyezett szám egész szám, akkor a rendszer a eltolási értéket fogja értelmezni, `mod 64` azaz az 1 eltolást és a 65 eltolását.

Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.
A negatív érték balra vagy jobbra való eltolása negatív szám lehet.
Ez azt jelöli, hogy az egyik lépés balra vagy jobbra való eltolása megegyezik a 2. számú szorzással vagy osztással.

Az egész szám és az Integer modulus ugyanazt a viselkedést követi a negatív számok esetében, mint a C#. Vagyis `a % b` mindig ugyanaz a jel, mint a `a` , és `b * (a / b) + a % b` mindig egyenlő `a` . Például:

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| 5 | 2 | 2 | 1 |
| 5 | -2 | -2 | 1 |
| -5 | 2 | -2 | -1 |
| -5 | -2 | 2 | -1 |

A Big Integer osztás és a modulus műveletek ugyanúgy működnek.

A numerikus kifejezéseket megadva egy új kifejezés is létrehozható az `-` unáris operátor használatával.
Az új kifejezés ugyanolyan típusú, mint az összetevő kifejezése.

Egy egész szám vagy egy nagy egész szám kifejezés esetén a `~~~` (bitenkénti komplement) egyoperandusú operátor használatával egy adott típusú új kifejezés is létrehozható.

## <a name="boolean-expressions"></a>Logikai kifejezések

A két `Bool` literális érték a `true` és a `false` .

Az azonos primitív típusú két kifejezés miatt a `==` és a `!=` bináris operátor is használható kifejezés létrehozásához `Bool` .
A kifejezés értéke igaz, ha a két kifejezés egyenlő és hamis, ha nem.

A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani. Például a "kicsomagolás" operátor használatával `!` (részletesen lásd [ Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator):),

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
Például: `49.0 * (1.0/49.0) != 1.0`.

A két numerikus kifejezéstől függően a bináris operátorok, a, `>` `<` `>=` és `<=` felhasználhatók egy olyan új logikai kifejezés létrehozására, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, mint a második kifejezés.

Ha két logikai kifejezés van megadva, a `and` bináris operátor használatával olyan új logikai kifejezést hozhat létre, amely igaz, ha mindkét kifejezés igaz. Hasonlóképpen, az `or` operátor használatával egy olyan kifejezést hoz létre, amely akkor igaz, ha a két kifejezés egyike igaz.

A logikai kifejezéseket megadva az `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.

## <a name="string-expressions"></a>Sztringkifejezések

Q# lehetővé teszi a karakterláncok használatát az `fail` utasításban (a [vezérlési folyamat](xref:microsoft.quantum.guide.controlflow#fail-statement)ismertetése) és a [`Message`](xref:microsoft.quantum.intrinsic.message) standard függvényben. Az utóbbi adott viselkedése a használt szimulátortól függ, de általában egy üzenetet ír a gazdagép-konzolra, amikor egy program során hívja meg Q# .

A karakterláncok Q# literálok vagy interpolált karakterláncok.

A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterlánc-literálokra: a Unicode-karakterek egy sorozata dupla idézőjelek közé `" "` .
Egy karakterláncon belül használja a fordított perjel karaktert `\` egy dupla idézőjeles karakter () elküldéséhez `\"` , vagy egy új vonal ( `\n` ), egy kocsivissza ( `\r` ) vagy egy lap () beszúrásához `\t` .
Például:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Interpolált karakterláncok

A Q# karakterlánc-Interpolációk szintaxisa a C# szintaxis egy részhalmaza. Az alábbiak a legfontosabb pontok, amelyek a következőkre vonatkoznak Q# :

* Ha egy szövegkonstans-karakterláncot interpolált karakterláncként szeretne azonosítani, a szimbólummal megadhatja azt `$` . A és a közötti térköz nem lehet üres `$` `"` karakterláncot indít.

* A következő példa egy olyan alapszintű példát [`Message`](xref:microsoft.quantum.intrinsic.message) mutat be, amely egy mérés eredményét írja a konzolra, más Q# kifejezésekkel együtt.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Bármely érvényes Q# kifejezés interpolált karakterláncban jelenhet meg.

* Az interpolált karakterláncban szereplő kifejezések Q# szintaxisát és nem C# szintaxist követik. A legjelentősebb különbség az, hogy nem Q# támogatja a Verbatim (többsoros) interpolált karakterláncokat.

A C# szintaxissal kapcsolatos további információkért lásd: [*interpolált karakterláncok*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Tartomány kifejezései

A (z `Int` `start` `step` ) és a (z `stop` ) kifejezés `start .. step .. stop` egy olyan tartomány kifejezése, amelynek első eleme a `start` második elem, a `start+step` harmadik elem, `start+step+step` és így tovább, amíg át nem halad `stop` .
A tartomány lehet üres, ha például `step` pozitív és `stop < start` .

A tartomány mindkét végén szerepel. Ez azt eredményezi, hogy ha a és a közötti különbség az `start` `stop` egész szám `step` , a tartomány utolsó eleme lesz `stop` .

`Int` `start` `stop` A kifejezés `start .. stop` egy olyan tartomány kifejezése, amely egyenlő a két kifejezéssel `start .. 1 .. stop` .
Vegye figyelembe, hogy a vélelmezett `step` érték + 1 `stop` , akkor is, ha kevesebb, mint `start` ; ebben az esetben a tartomány üres.

Néhány példa a tartományokra:

- `1..3` az 1., 2. és 3. tartomány.
- `2..2..5` a 2. és 4. tartomány.
- `2..2..6` a 2, 4, 6. tartomány.
- `6..-2..2` a 6, 4, 2 tartomány.
- `2..1` az üres tartomány.
- `2..6..7` a 2. tartomány.
- `2..2..1` az üres tartomány.
- `1..-1..2` az üres tartomány.

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

A rekordos konstans a megfelelő típusú elemek sorozata, vesszővel elválasztva, zárójelek közé zárva.
Például `(1, One)` egy `(Int, Result)` kifejezés.

A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.

## <a name="user-defined-type-expressions"></a>Felhasználó által definiált típusú kifejezések

A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.
Ha például `IntPair` egy felhasználó által definiált típus a (z) alapján `(Int, Int)` , akkor `IntPair(2, 3)` az egy adott típusú érvényes literál.

A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.

## <a name="unwrap-expressions"></a>Kifejezések kicsomagolása

A-ben Q# a kicsomagolási operátor egy záró felkiáltójel `!` .
Ha például `IntPair` egy felhasználó által definiált típus az alapul szolgáló típussal `(Int, Int)` , és `s` egy változó értékkel `IntPair(2, 3)` , akkor `s!` `(2, 3)` a következő:.

Más, felhasználó által definiált típusokban definiált, felhasználó által definiált típusok esetén megismételheti a kicsomagolási operátort. Például `s!!` a kétszeresen kicsomagolt értéket jelöli `s` .
Így ha a `WrappedPair` felhasználó által definiált típus egy alapul szolgáló típusú `IntPair` , és `t` egy változó értékkel `WrappedPair(IntPair(1,2))` , akkor a `t!!` következő: `(1,2)` .

Az `!` operátor magasabb prioritású, mint az összes többi operátor `[]` , mint a tömb indexelése és a szeletelése.
`!` és a `[]` kötés elhelyezése; ez a következő `a[i]![3]` `((a[i])!)[3]` : a (z), a (z), a kicsomagolása `i` , majd a nem `a` burkolt érték harmadik elemének beolvasása (tömbnek kell lennie).

Az operátor elsőbbsége `!` egy olyan hatással van, amely esetleg nem nyilvánvaló.
Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.
Például:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Tömb kifejezései

A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, szögletes zárójelek közé `[]` .
Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.

Ha a két tömb azonos típusú, a bináris `+` operátor használatával olyan új tömböt formálhat, amely a két tömb összefűzése.
Például: `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Tömb létrehozása

Adott típus és `Int` kifejezés `new` alapján a kezelővel lefoglalhatja a megadott méretű új tömböt.
Például `new Int[i + 1]` kioszt egy új `Int` tömböt `i + 1` elemekkel.

Az üres tömb literálok (például `[]` ) nem engedélyezettek.
Ehelyett létrehozhat egy nulla hosszúságú tömböt a használatával `new T[0]` , ahol a a `T` megfelelő típusú helyőrző.

Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.
A legtöbb esetben ez a nulla valamilyen változata.

Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.
Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely nem használható futásidejű hiba nélkül, hasonlóan a nyelvekhez, mint például a C# vagy a Java.
Az qubits vagy callables tartalmazó tömböket nem alapértelmezett értékekkel kell inicializálni az elemek biztonságos használata előtt. A megfelelő inicializálási rutinok: <xref:microsoft.quantum.arrays> .

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
 `Range` | Az üres tartomány, `1..1..0`
 `Callable` | _Érvénytelen hívható_
 `Array['T]` | `'T[0]`

A rekord típusú típusok inicializálása elemről elemre.


### <a name="array-elements"></a>Tömb elemei

Egy tömböt megadó kifejezés és egy `Int` kifejezés, amely egy új kifejezést képez a tömb elem operátor használatával `[]` .
Az új kifejezés ugyanaz, mint a tömb elemének típusa.
Ha például `a` egy típusú tömbhöz van kötve `Double` , akkor `a[4]` egy `Double` kifejezés.

Ha a tömb kifejezése nem egyszerű azonosító, akkor zárójelek közé kell helyeznie egy elem kiválasztásához.
Ha például a `a` és `b` mindkét típusú tömb `Int` , az összefűzésből származó elemek a következőképpen jelennek meg:

```qsharp
(a + b)[13]
```

Az összes tömb Q# nulla-alapú.
Vagyis a tömb első eleme `a` mindig `a[0]` .


### <a name="array-slices"></a>Tömb szeletek

Egy tömb kifejezése és egy `Range` kifejezés alapján egy új kifejezés is létrehozható a tömb szelet operátor használatával `[ ]` .
Az új kifejezés típusa megegyezik a tömb típusával, és tartalmazza a által a által meghatározott sorrendben indexelt elemeket `Range` `Range` .
Ha például `a` egy típusú tömbhöz van kötve `Double` , akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely az első négy elemét tartalmazza, `a` de a fordított sorrendben, ahogy azok megjelennek a ben `a` .

Ha az `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú.

A tömbök viszonyítási elemeihez hasonlóan, ha a tömb kifejezése nem egyszerű azonosító, akkor zárójelek közé kell tenni a szeletet.
Ha például a `a` és `b` mindkét típusú tömb `Int` , az összefűzésből származó szelet a következőként van kifejezve:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Következtetett kezdő/záró értékek

A 0,8-es [verziótól](xref:microsoft.quantum.relnotes)kezdődően a hatókör-szeletelők környezetfüggő kifejezéseket támogatunk. Különösen kihagyhatja a tartomány kezdő és záró értékeit egy tartomány-szeletelő kifejezés kontextusában. Ebben az esetben a fordító a következő szabályok alapján következteti ki a tartományhoz tartozó elhatárolókat:

* Ha a tartomány *indítási* értéke kimarad, akkor a késleltetett indítási érték
  * nulla, ha nincs megadva lépés, vagy a megadott lépés pozitív.  
  * a szeletelt tömb hossza mínusz eggyel, ha a megadott lépés negatív.

* Ha a tartomány *befejezési* értéke kimarad, akkor a következtetett vég értéke
  * a szeletelt tömb hossza mínusz eggyel, ha nincs megadva a lépés, vagy a megadott lépés pozitív.
  * nulla, ha a megadott lépés negatív.

Néhány példa:

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

Mivel Q# az összes típus érték típusú (a qubits valamivel speciális szerepkört vesznek fel), az űrlapos "Copy" (másolás) jön létre, amikor egy érték egy szimbólumhoz van kötve, vagy ha egy szimbólum van kötve. Ez azt jelenti, hogy a viselkedése Q# ugyanaz, mint ha egy példányt egy hozzárendelési operátor használatával hoztak létre. 

Természetesen a gyakorlatban csak az érintett darabok szükségesek újra létrehozva. Ez befolyásolja a tömbök másolásának módját, mert nem lehetséges a tömb elemeinek frissítése. Egy meglévő tömb módosításához a *copy-Update* mechanizmust kell használnia.

Létrehozhat egy új tömböt egy meglévő tömbből *Másolás és frissítés* kifejezések használatával, amelyek a kezelőket és a-t használják `w/` `<-` .
A copy-Update kifejezés az űrlap kifejezése `expression1 w/ expression2 <- expression3` , ahol

* `expression1` valamilyen típusúnak kell lennie `T[]` `T` .
* `expression2` meghatározza, hogy mely indexeket kell megadni a tömbben a `expression1` módosításhoz. `expression2` típusnak `Int` vagy típusnak kell lennie `Range` .
* `expression3` az elemeknek a alkalmazásban való frissítéséhez használt érték (ek) a `expression1` ben megadott indexek alapján `expression2` . Ha `expression2` a típus típusa `Int` , `expression3` típusnak kell lennie `T` . Ha `expression2` a típus típusa `Range` , `expression3` típusnak kell lennie `T[]` .

A copy-and-Update kifejezés például `arr w/ idx <- value` egy új tömböt hoz létre, amely a megfelelő elemeire van beállítva `arr` , kivéve a által megadott elem (ek) et, `idx` amely a (z) értékre van beállítva `value` . 

`arr`A megadott tömb tartalmazza `[0,1,2,3]` , majd 

- `arr w/ 0 <- 10` a tömb `[10,1,2,3]` .
- `arr w/ 2 <- 10` a tömb `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]` a tömb `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Elnevezett elemek másolási és frissítési kifejezései

A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez. 

Vegyük például a következőt: 

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

A callables tömbjét is létrehozhatja.

* Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.
* A tömb elemének típusa az összes elem által [támogatott összes olyan futtatót](xref:microsoft.quantum.guide.operationsfunctions) támogatja.
Például ha a `Op1` , a `Op2` és `Op3` az mind `Qubit[] => Unit` művelet, de támogatja, `Op1` `Adjoint` `Op2` támogatja `Controlled` és `Op3` támogatja mind a következőket:
  * `[Op1, Op2]` a a műveletek tömbje `(Qubit[] => Unit)` .
  * `[Op1, Op3]` a a műveletek tömbje `(Qubit[] => Unit is Adj)` .
  * `[Op2, Op3]` a a műveletek tömbje `(Qubit[] => Unit is Ctl)` .

Azonban bár a műveletek `(Qubit[] => Unit is Adj)` és  `(Qubit[] => Unit is Ctl)` a közös alaptípusa, a `(Qubit[] => Unit)` műveletek *tömbje* nem osztozik közös alaptípuson.

Például `[[Op1], [Op2]]` jelenleg hiba történt, mert megkísérli létrehozni a két nem kompatibilis tömb típusának tömbjét `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .

A callables kapcsolatos további információkért lásd: [hívható kifejezések](#callable-expressions) ezen az oldalon vagy [műveletek és függvények a Q# -ben ](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Feltételes kifejezések

Egy adott típus és egy logikai kifejezés két kifejezése is egy feltételes kifejezést alkot a kérdőjel `?` és a függőleges sáv használatával `|` . A `a==b ? c | d` feltételes kifejezés értéke, `c` Ha `a==b` igaz, és `d` hamis.

### <a name="conditional-expressions-with-callables"></a>Feltételes kifejezések callables

A feltételes kifejezések kiértékelik azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat. Ebben az esetben a feltételes kifejezés típusa egy olyan bemenettel és kimenettel rendelkező művelet, amely támogatja a mindkét kifejezés által támogatott összes feltételt.
Például, ha, `Op1` `Op2` és `Op3` mind a `Qubit[]=>Unit` , de támogatja `Op1` `Adjoint` , `Op2` támogatja `Controlled` és `Op3` támogatja a következőket:

- `flag ? Op1 | Op2` egy `(Qubit[] => Unit)` művelet.
- `flag ? Op1 | Op3` egy `(Qubit[] => Unit is Adj)` művelet.
- `flag ? Op2 | Op3` egy `(Qubit[] => Unit is Ctl)` művelet.

Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor a hívás csak akkor történik meg, ha ez az eredmény a hívás értéke. `a==b ? C(qs) | D(qs)`Ha például `a==b` igaz, akkor a rendszer `C` meghívja a műveletet, és ha az értéke hamis, akkor csak a `D` művelet meghívására kerül sor. Ez a megközelítés hasonló a más nyelveken történő *rövid összekapcsoláshoz* .

## <a name="callable-expressions"></a>Hívható kifejezések

A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve. Például `X` egy olyan műveleti literál, amely a szabványos könyvtári `X` műveletre hivatkozik, és `Message` egy olyan függvény, amely a standard Library `Message` függvényre hivatkozik.

Ha egy művelet támogatja az elválasztó műveletet `Adjoint` , akkor `Adjoint op` egy művelet kifejezése.
Hasonlóképpen, ha a művelet támogatja az elválasztó műveletet `Controlled` , akkor `Controlled op` egy művelet kifejezése.
A kifejezések típusaival kapcsolatos további információkért lásd: a [műveleti specializációk meghívása](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

`Adjoint`A (és `Controlled` ) az összes többi operátorral szorosabban kötődik, kivéve a kicsomagolási operátort és a `!` tömb indexelését `[ ]` .
Így a következők mindegyike érvényes, feltéve, hogy a műveletek támogatják a használt munkafolyamatokat:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Típus – paraméteres hívható kifejezések

Használhat egy meghívásos literálot értékként, például hozzárendelheti egy változóhoz, vagy átadhatja egy másik meghívónak. Ebben az esetben, ha a meghívható [típus paraméterekkel](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)rendelkezik, meg kell adnia a paramétereket a meghívásos érték részeként.

Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel. Ha például az `Fun` egy függvény az aláírással `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Hívható hívási kifejezések

Egy meghívásos kifejezés (művelet vagy függvény) és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos *kifejezéshez* hozzáfűzheti a rekord kifejezését.
A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.

Ha például az `Op` egy művelet az aláírással, a `((Int, Qubit) => Double)` egy `Op(3, qubit1)` típusú kifejezés `Double` .
Hasonlóképpen, ha az `Sin` egy függvény az aláírással `(Double -> Double)` , a egy `Sin(0.1)` típusú kifejezés `Double` .
Végül, ha `Builder` az a függvény az aláírással `(Int -> (Int -> Int))` , akkor a `Builder(3)` függvény a- `Int` ből `Int` .

Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.
Így az előző bekezdésből történő hívás eredményének meghívásához `Builder` a helyes szintaxis a következő:

```qsharp
(Builder(3))(2)
```

A [típus-paraméteres](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) metódus meghívásakor megadható, hogy a tényleges Type paraméterek a `< >` meghívásos kifejezés után a szög zárójelben legyenek.
Ez a művelet általában szükségtelen, mert a Q# fordító vezeti a tényleges típusokat.
Azonban szükség *van* a [részleges alkalmazásra](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , ha egy Type-paraméteres argumentum nincs meghatározva.
Emellett akkor is hasznos, ha a különböző felhasználók által támogatott műveletek továbbítása meghívásos.

Például ha `Func` rendelkezik aláírással, és aláírással rendelkezik, `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` és `Op3` aláírással rendelkezik `(Qubit[] => Unit)` , az `Func` `Op1` első argumentumként, `Op2` a másodikként és `Op3` a harmadikként való meghívásához:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A típus specifikációjának megadása kötelező `Op3` `Op1` , mert különböző típusok vannak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.


## <a name="operator-precedence"></a>Operátori prioritás

* Minden bináris operátor megfelelő társítású, kivéve a következőt: `^` .

* Szögletes zárójelek, `[ ]` a tömb szeletelése és indexelése minden operátor előtt kötést biztosít.

* A kikapcsolók `Adjoint` és a `Controlled` kötés a tömb indexelése után, de az összes többi operátor előtt.

* A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.

Q# az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:

Operátor | Aritása | Description | Operandusok típusai
---------|----------|---------|---------------
 záró `!` | Unáris | Kicsomagolása | Bármely felhasználó által definiált típus
 `-`, `~~~`, `not` | Unáris | Numerikus negatív, bitenkénti komplement, logikai tagadás | `Int`, `BigInt` vagy `Double` esetén `-` a `Int` `BigInt` `~~~` `Bool``not`
 `^` | Bináris | Egész számú Power | `Int` vagy az `BigInt` alaphoz `Int` a kitevő esetében
 `/`, `*`, `%` | Bináris | Osztás, szorzás, egész szám modulusa | `Int`, `BigInt` vagy `Double` `/` `*` `Int` `BigInt``%`
 `+`, `-` | Bináris | Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás | `Int``BigInt`vagy `Double` , vagy `String` bármely tömb típusa a következőhöz:`+`
 `<<<`, `>>>` | Bináris | Bal SHIFT, jobb SHIFT | `Int` vagy `BigInt`
 `<`, `<=`, `>`, `>=` | Bináris | Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás | `Int`, `BigInt` vagy `Double`
 `==`, `!=` | Bináris | egyenlő, nem egyenlő összehasonlítások | bármely primitív típus
 `&&&` | Bináris | Bitenkénti és | `Int` vagy `BigInt`
 `^^^` | Bináris | Bitenkénti XOR | `Int` vagy `BigInt`
 <code>\|\|\|</code> | Bináris | Bitenkénti vagy | `Int` vagy `BigInt`
 `and` | Bináris | Logikai ÉS | `Bool`
 `or` | Bináris | Logikai VAGY | `Bool`
 `..` | Bináris/Ternáris | Tartomány operátora | `Int`
 `?` `|` | Ternáris | Feltételes | `Bool` a bal oldali
`w/` `<-` | Ternáris | Másolás és frissítés | Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)

## <a name="next-steps"></a>Következő lépések

Most, hogy együttműködik a kifejezésekkel a alkalmazásban Q# , lépjen be a [műveletekre Q# és a functions](xref:microsoft.quantum.guide.operationsfunctions) szolgáltatásba, ahol megtudhatja, hogyan határozhat meg és hívhat meg műveleteket és funkciókat.
