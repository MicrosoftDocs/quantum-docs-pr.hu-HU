---
title: Kifejezések | Microsoft Docs
description: Kifejezések
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185205"
---
# <a name="expressions"></a>Kifejezések

## <a name="grouping"></a>Csoportosítás

Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.
Például a `(7)` egy `Int` kifejezés, `([1,2,3])` `Int`s tömb típusú kifejezés, a `((1,2))` pedig `(Int, Int)`típusú kifejezés.

A [modellben](xref:microsoft.quantum.language.type-model#tuple-types) leírt egyszerű értékek és egyelemes rekordok közötti egyenértékűség eltávolítja a `(6)` csoportként való kétértelműség és a `(6)` egyelemű rekord között.

## <a name="symbols"></a>Szimbólumok

Egy `'T` típusú értékhez kötött vagy hozzárendelt szimbólum neve `'T`típusú kifejezés.
Ha például a szimbólum `count` az egész értékhez van kötve `5`, akkor `count` egy egész szám kifejezés.

## <a name="numeric-expressions"></a>Numerikus kifejezések

A numerikus kifejezések `Int`, `BigInt`vagy `Double`típusú kifejezések.
Vagyis egész vagy lebegőpontos számok.

a Q # `Int` literálok a (z) értékekben egyeznek C#meg, azzal a különbséggel, hogy nincs szükség "l" vagy "l" kifejezésre (vagy engedélyezett).
A hexadecimális és a bináris egész számok "0x" és "0b" előtaggal támogatottak.

a Q # `BigInt` literálok megegyeznek a .NET-ben található Big Integer karakterláncokkal, amelyek "l" vagy "L" karakterrel rendelkeznek.
A hexadecimális nagy egész számok "0x" előtaggal támogatottak.
Így az alábbi `BigInt` literálok összes érvényes használata:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

a Q # `Double` literálok megegyeznek a kettős literálokkal, C#azzal a különbséggel, hogy a "d" vagy a "d" kifejezés nem kötelező (vagy engedélyezett).

Bármely elemtípus tömb kifejezése miatt a `Int` kifejezés a `Length` beépített függvény használatával hozható létre, a tömb kifejezés zárójelek közé, `(` és `)`.
Ha például `a` egy tömbhöz van kötve, akkor `Length(a)` egy egész szám kifejezés.
Ha `b` az egész számokból álló tömbök tömbje, `Int[][]`, `Length(b)` a `b`ban található altömbök száma, és a `Length(b[1])` a második altömbben lévő egész számok száma `b`.

Adott típusú két numerikus kifejezés, a bináris operátorok `+`, `-`, `*`és `/` használhatók új numerikus kifejezés megírásához.
Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.

A két egész szám kifejezés miatt a bináris operátor `^` (Power) egy új egész kifejezés kiírására használható.
Hasonlóképpen, `^` két kettős kifejezéssel is használható, amelyek új dupla kifejezést alkotnak.
Végezetül `^` a bal oldalon egy nagy egész számmal, a jobb oldalon pedig egy egész számmal, egy új Big Integer típusú kifejezés létrehozásához.
Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, a rendszer futásidejű hibát jelez.

A két egész vagy nagy egész szám típusú kifejezés esetében egy új egész vagy Big Integer kifejezés is létrehozható a `%` (modulus), a `&&&` (bitenkénti és), a `|||` (bitenkénti vagy), vagy a `^^^` (bitenkénti XOR) operátorok használatával.

A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) vagy `>>>` (aritmetikai jobbra váltás) operátorok használhatók egy új kifejezés létrehozásához, amely ugyanolyan típusú, mint a bal oldali kifejezés.

A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.
A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, a rendszer futásidejű hibát jelez.
Ha az elmozdulni kívánt szám egész szám, akkor a rendszer a váltási összeget `mod 64`értelmezi. Ez azt eredményezi, hogy az 1. és a 65 eltolása ugyanaz a hatása.

Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.
A negatív érték eltolása balra vagy jobbra is negatív számot eredményez.
Ez azt okozhatja, hogy az egyik lépés balra vagy jobbra való eltolása pontosan ugyanaz, mint a 2. számú szorzás vagy osztás.

Az egész szám és az egész számú modulus ugyanazt a viselkedést C#követi, mint a negatív számok.
Ez azt eredményezi, hogy a `a % b` mindig ugyanazzal a jellel fog rendelkezni, mint `a`, és a `b * (a / b) + a % b` mindig egyenlő lesz `a`.
Példa:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 – 5 | 2 | -2 | -1
 – 5 | -2 | 2 | -1

A Big Integer osztás és a modulus hasonló módon működik.

A numerikus kifejezéseket megadva egy új kifejezés hozható létre a `-` egyoperandusú operátor használatával.
Az új kifejezés ugyanolyan típusú lesz, mint az összetevő kifejezése.

Adott egész szám vagy nagy egész szám kifejezés esetén az azonos típusú új kifejezés az `~~~` (bitenkénti komplement) egyoperandusú operátor használatával hozható létre.

## <a name="boolean-expressions"></a>Logikai kifejezések

A két `Bool` literális érték `true` és `false`.

Az azonos primitív típus két kifejezése miatt a `==` és a `!=` bináris operátorok is használhatók `Bool` kifejezés létrehozásához.
A kifejezés akkor igaz, ha a két kifejezés (ill. nem) egyenlő.

A felhasználó által definiált típusok értéke nem hasonlítható össze, csak az értékeiket lehet összehasonlítani. Például:

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

`Qubit` értékek egyenlőségének összehasonlítása az identitások egyenlősége; Ez azt jelzi, hogy a két kifejezés ugyanazt a qubit azonosítja-e.
A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.

A `Double` értékek egyenlőségének összehasonlítása a kerekítési hatások miatt félrevezető lehet.
Például `49.0 * (1.0/49.0) != 1.0`.

A két numerikus kifejezés miatt a bináris operátorok `>`, `<`, `>=`és `<=` használhatók olyan új logikai kifejezés létrehozásához, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő , vagy kisebb vagy egyenlő, mint a második kifejezés.

A két logikai kifejezés miatt a `and` és `or` bináris operátorok egy olyan új logikai kifejezés létrehozásához használhatók, amely igaz, ha a két kifejezés mindkét (ill. vagy mindkettő) értéke igaz.

A logikai kifejezéseket megadva a `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.

## <a name="string-expressions"></a>Karakterlánc-kifejezések

A Q # lehetővé teszi a karakterláncok használatát a `fail` utasításban és a `Log` standard függvényben.

A Q # sztringek literálok vagy interpolált karakterláncok.
A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterláncokhoz: az Unicode-karakterek egy számsorozata idézőjelek között, `"`.
Egy karakterláncon belül a háttér-perjel karakter `\` a kettős idézőjelek karakterének kiírására, valamint egy új vonal `\n`ba való beszúrására, egy kocsivissza karaktert `\r`ként, és egy tabulátort `\t`.
Például:

```qsharp
"\"Hello world!\", she said.\n"
```

A Q # szintaxis a karakterlánc-interpolációhoz az C# 7,0 szintaxis részhalmaza. A Q # nem támogatja a Verbatim (többsoros) interpolált karakterláncokat.
Lásd: [*interpolált karakterláncok*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) a C# szintaxishoz.

Az interpolált karakterláncban szereplő kifejezések a Q # szintaxist követik C# , nem pedig a szintaxist.
Bármely érvényes Q # kifejezés egy interpolált karakterláncban jelenhet meg.

## <a name="qubit-expressions"></a>Qubit kifejezések

Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékekhez vagy `Qubit` tömbök tömb elemeihez van kötve.
Nincsenek `Qubit` literálok.

## <a name="pauli-expressions"></a>Pauli-kifejezések

A négy `Pauli` érték, `PauliI`, `PauliX`, `PauliY`és `PauliZ`egyaránt érvényes `Pauli` kifejezés.

Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékekhez vagy `Pauli` tömbök tömb elemeihez van kötve.

## <a name="result-expressions"></a>Eredmény kifejezései

A két `Result` érték, `One` és `Zero`érvényes `Result` kifejezés.

Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékekhez vagy `Result` tömbök tömb elemeihez van kötve.
Fontos megjegyezni, hogy `One` nem egyezik meg a `1`egész számmal, és a között nincs közvetlen konverzió.
Ugyanez érvényes a `Zero` és a `0`.

## <a name="range-expressions"></a>Tartomány kifejezései

A három `Int` kifejezés `start`, `step`és `stop`esetén a `start .. step .. stop` egy olyan tartomány kifejezés, amelynek első eleme `start`, a második elem `start+step`, a harmadik elem `start+step+step`, stb., amíg `stop` át nem adja.
A tartomány lehet üres, ha például `step` pozitív és `stop < start`.
A tartomány utolsó eleme akkor `stop`, ha a `start` és a `stop` közötti különbség a `step`elválaszthatatlan többszöröse. vagyis a tartomány mindkét végén szerepel.

`start` és `stop`két `Int` kifejezést adott meg, `start .. stop` egy tartománybeli kifejezés, amely `start .. 1 .. stop`egyenlő.
Vegye figyelembe, hogy a hallgatólagos `step` akkor is + 1, ha a `stop` kisebb, mint `start`; ilyen esetben a tartomány üres.

Néhány példa a tartományokra:

- `1..3` az 1., 2. és 3. tartomány.
- `2..2..5` a 2, 4 tartomány.
- `2..2..6` a 2, 4, 6 tartomány.
- `6..-2..2` a 6, 4, 2 tartomány.
- `2..1` az üres tartomány.
- `2..6..7` a 2. tartomány.
- `2..2..1` az üres tartomány.
- `1..-1..2` az üres tartomány.

## <a name="callable-expressions"></a>Hívható kifejezések

A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.
Például a `X` egy olyan műveleti literál, amely a szabványos függvénytár `X` műveletre hivatkozik, és a `Message` egy függvény literál, amely a szabványos függvénytár `Message` függvényre hivatkozik.

Ha egy művelet támogatja a `Adjoint`-kezelőt, akkor `Adjoint op` egy műveleti kifejezés.
Hasonlóképpen, ha a művelet támogatja a `Controlled`t, akkor `Controlled op` egy műveleti kifejezés.
Ezeknek a kifejezéseknek a típusai a következőben vannak [megadva.](xref:microsoft.quantum.language.type-model#functors)

A következő operátorok (`Adjoint` és `Controlled`) jobban kötődik az összes többi kezelőhöz, kivéve a kicsomagolási operátort, `!` és a tömb indexelését `[]`.
Így a következők mindegyike jogi, feltételezve, hogy a műveletek támogatják a használt munkafolyamatokat:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Egy meghívásos literál is használható értékként, azaz egy változóhoz való hozzárendeléshez, vagy egy másik meghíváshoz való továbbításhoz.
Ebben az esetben, ha a meghívható paraméterekkel rendelkezik, azokat a meghívásos érték részeként kell megadni.
Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel.

Ha például az `Fun` egy aláírással `'T1->Unit`függvény:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Hívható hívási kifejezések

Egy meghívásos (művelet vagy függvény) kifejezés és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos kifejezés úgy hozható létre, hogy hozzáfűzi a rekord kifejezését a meghívható kifejezéshez.
A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.

Ha például az `Op` egy `((Int, Qubit) => Double)`aláírással rendelkező művelet, `Op(3, qubit1)` `Double`típusú kifejezés.
Hasonlóképpen, ha a `Sin` az aláírás `(Double -> Double)`függvény, `Sin(0.1)` `Double`típusú kifejezés.
Végül, ha a `Builder` egy aláírási `(Int -> (Int -> Int))`függvény, akkor a `Builder(3)` függvény a-tól az int-ig.

Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.
Így a `Builder` az előző bekezdésből való meghívása eredményének meghívásához a helyes szintaxis a következő:

```qsharp
(Builder(3))(2)
```

A típus-paraméteres metódus meghívásakor a tényleges Type paraméterek megadhatók a szögletes zárójelek között `<` és `>` a meghívásos kifejezés után.
Ez általában szükségtelen, mivel a Q # fordítóprogram a tényleges típusokat fogja kikövetkeztetni.
A részleges alkalmazáshoz szükséges (lásd alább), ha egy Type-paraméteres argumentum nincs megadva.
Időnként hasznos lehet, ha a különböző felállókkal rendelkező műveletek átadása meghívásos támogatással történik.

Ha például `Func` rendelkezik aláírással `('T1, 'T2, 'T1) -> 'T2`, `Op1` és `Op2` rendelkezik aláírási `(Qubit[] => Unit is Adj)`, és `Op3` aláírása `(Qubit[] => Unit)`, hogy meghívja `Func` az első argumentumként, `Op1` a második és `Op3` a harmadikként:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A típus specifikációjának megadása kötelező, mert `Op3` és `Op1` különböző típusúak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.

### <a name="partial-application"></a>Részleges alkalmazás

Egy meghívásos kifejezés miatt egy új hívható is létrehozható az argumentumok egy részhalmazának megadásával a meghívónak.
Ezt nevezzük _részleges alkalmazásnak_.

A Q #-ban a részlegesen alkalmazott meghívót normál meghívásos kifejezés megírásával fejezzük ki, de a meghatározatlan argumentumok esetében aláhúzást `_`használ.
Az eredményül kapott meghívó ugyanazzal az eredménnyel rendelkezik, mint az alapszintű hívható, és ugyanazokat a specializációkat kell megadnia a műveletekhez.
A részleges alkalmazás bemeneti típusa egyszerűen az eredeti típus, ahol a megadott argumentumok el lettek távolítva.

Ha egy megváltoztathatatlan változót egy részleges alkalmazás létrehozásakor megadott argumentumként ad át, a rendszer a változó aktuális értékét használja.
A változó értékének módosítása később nem befolyásolja a részleges alkalmazást.

Ha például `Op` típusa `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` típusa `(((Qubit,Qubit), Double) => Unit is Adj)`, ezért `Op(5,_)`.
- a `Op(_,(_,1.0))` típusa `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- a `Op(_,((q1,q2),_))` típusa `((Int,Double) => Unit is Adj)`.
   Vegye figyelembe, hogy itt is alkalmazunk egy Egyrekordos egyenértékűséget.

Ha a részben alkalmazott hívható olyan paraméterekkel rendelkezik, amelyeket a fordító nem tud következtetni, meg kell adni azokat a Meghívási helyen.
A részleges alkalmazás nem rendelkezhet meghatározatlan típusú paraméterekkel.

Ha például `Op` típusa `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Rekurzió

A Q # callables közvetlenül vagy közvetve rekurzívak.
Ez azt is megteheti, hogy egy művelet vagy funkció meghívhatja magát, vagy meghívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.

A rekurzió használatának két fontos megjegyzése van, azonban:

- A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.
  Ez jelentős hatással lehet az algoritmus végrehajtási idejére.
- Ha tényleges kvantum-eszközön végez végrehajtást, előfordulhat, hogy a halmozott terület korlátozva van, ezért a mélyebb rekurzió hibát okozhat.
  A Q # Compiler és a Runtime nem azonosítja és optimalizálja a farok rekurzióját.

## <a name="tuple-expressions"></a>Rekordos kifejezések

A rekordos literál a megfelelő típusú elem-kifejezések sorozata, vesszővel elválasztva, `(` és `)`között.
A `(1, One)` például egy `(Int, Result)` kifejezés.

A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.

## <a name="user-defined-type-expressions"></a>Felhasználó által definiált típusú kifejezések

A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.
Ha például a `IntPair` felhasználó által definiált típus `(Int, Int)`alapján, akkor `IntPair(2,3)` a típus érvényes konstansa lesz.

A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.

## <a name="unwrap-expressions"></a>Kifejezések kicsomagolása

A Q #-ban a kicsomagolás operátor egy záró felkiáltójel `!`.
Ha például `IntPair` egy olyan felhasználó által definiált típus, amelynek típusa `(Int, Int)`, és a `s` `IntPair(2,3)`értékkel rendelkező változó volt, `s!` `(2,3)`lenne.

A felhasználó által definiált típusok esetében definiált más felhasználók által definiált típusok esetében. lehet, hogy a kicsomagolási operátor megismétlődik; a `s!!` például a `s`kétszeresen kicsomagolt értékét jelzi.
Így ha `WrappedPair` egy alapul szolgáló típusú `IntPair`felhasználó által definiált típus, és a `t` egy `WrappedPair(IntPair(1,2))`értékkel rendelkező változó, `t!!` `(1,2)`lenne.

A `!` operátor magasabb prioritású, mint az összes többi operátor, amely nem `[]` a tömb indexeléséhez és a szeleteléshez.
`!` és `[]` a kötés elhelyezése; Ez azt is megteheti, hogy a `a[i]![3]` `((a[i])!)[3]`ként kell olvasni: vegye fel a `i`"th elemét `a`, csomagolja ki, majd a nem burkolt érték harmadik elemét (amely tömbnek kell lennie).

A `!` operátor elsőbbsége egy olyan hatással van, amely esetleg nem nyilvánvaló.
Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.
Példa:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Tömb kifejezései

A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, `[` és `]`.
Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.

Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.
A tömb elemének típusa az összes elem által támogatott összes olyan futtatót támogatni fogja.
Ha például `Op1`, `Op2`és `Op3` mind `Qubit[] => Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja a `Controlled`, és `Op3` támogatja a következőket:

- a `[Op1, Op2]` `(Qubit[] => Unit)` műveletek tömbje.
- a `[Op1, Op3]` `(Qubit[] => Unit is Adj)` műveletek tömbje.
- a `[Op2, Op3]` `(Qubit[] => Unit is Ctl)` műveletek tömbje.

Az üres tömb literálok, `[]`ek nem engedélyezettek.
A `new ★[0]`használata helyett, ahol a `★` a megfelelő típus helyőrzője, lehetővé teszi a nulla hosszúságú kívánt tömb létrehozását.

Az azonos típusú két tömb esetében a bináris `+` operátor egy olyan új tömb létrehozásához használható, amely a két tömb összefűzése.
Például `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Tömb létrehozása

A megadott típus és `Int` kifejezés alapján a `new` operátor a megadott méretű új tömb kiosztására használható.
A `new Int[i+1]` például egy új `Int` tömböt foglal le `i+1` elemmel.

Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.
A legtöbb esetben ez a nulla valamilyen változata.

Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.
Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely futásidejű hiba nélkül nem használható.
Ez hasonló a más nyelveken (például C# vagy Java) található null hivatkozáshoz.
A qubits vagy callables tartalmazó tömböket megfelelően kell inicializálni a nem alapértelmezett értékekkel, mielőtt az elemek biztonságosan használhatók legyenek. A megfelelő inicializálási rutinok a <xref:microsoft.quantum.arrays>ban találhatók.

Az egyes típusok alapértelmezett értékei a következők:

Type (Típus) | Alapértelmezett
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

A rekord típusú típusok inicializálása elem-by-Element.


### <a name="jagged-arrays"></a>Szaggatott tömbök

Egy szaggatott tömb, más néven "tömbök tömbje", egy tömb, amelynek elemei tömbök. A szaggatott tömb elemei eltérő méretűek lehetnek. Az alábbi példa azt szemlélteti, hogyan deklarálható és inicializálható egy többrészes táblát jelképező szaggatott tömb.

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


### <a name="array-slices"></a>Tömb szeletek

Egy tömböt megadó kifejezés és egy `Range` kifejezés miatt a `[` és `]` tömb szelet operátor használatával új kifejezés hozható létre.
Az új kifejezés ugyanolyan típusú, mint a tömb, és a `Range`által definiált sorrendben tartalmazza a `Range`elemei által indexelt tömbös elemeket.
Ha például a `a` `Double`s tömbhöz van kötve, akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely a `a` első négy elemét tartalmazza, de a fordított sorrendben, ahogy az `a`ban szerepel.

Ha a `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú lesz.

Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell tenni a szelethez.
Ha például a `a` és az `b` a `Int`s tömbje, az összefűzésből származó szeletek a következőképpen lesznek kifejezve:

```qsharp
(a+b)[1..2..7]
```

A Q # összes tömbje nulla-alapú.
Vagyis a tömb `a` első eleme mindig `a[0]`.

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

## <a name="array-element-expressions"></a>Tömb elem kifejezései

Egy tömb kifejezése és egy `Int` kifejezés miatt a `[` és a `]` Array Element operátor használatával új kifejezés hozható létre.
Az új kifejezés ugyanolyan típusú lesz, mint a tömb elemének típusa.
Ha például a `a` `Double`s tömbhöz van kötve, akkor `a[4]` `Double` kifejezés.

Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell foglalni, hogy ki lehessen választani egy elemet.
Ha például a `a` és az `b` a `Int`s tömbje, az összefűzésből származó elemek a következőképpen lesznek kifejezve:

```qsharp
(a+b)[13]
```

A Q # összes tömbje nulla-alapú.
Vagyis a tömb `a` első eleme mindig `a[0]`.


## <a name="copy-and-update-expressions"></a>Másolás és frissítés kifejezések

Új tömbök hozhatók létre a meglévő példányokból másolás és frissítés kifejezések használatával.
A copy-Update kifejezés a `expression1 w/ expression2 <- expression3`űrlap kifejezése, amelyben a `expression1` típusa csak `T[]` lehet `T`. A második `expression2` meghatározza, hogy az elem (ek) milyen indexeket módosítson a `expression1` tömbhöz képest, és a típusnak `Int` vagy `Range`típusúnak kell lennie. Ha `expression2` `Int`típusú, a `expression3`nak `T`típusúnak kell lennie. Ha `expression2` `Range`típusú, a `expression3`nak `T[]`típusúnak kell lennie.

A copy-Update kifejezés `arr w/ idx <- value` egy új tömböt hoz létre, amely a `arr`megfelelő elemére van beállítva, kivéve a (z) `idx`elem (ek) et, amely a `value`ban található egy értékre van állítva. Ha például `arr` tartalmaz egy tömböt `[0,1,2,3]`, akkor 
- `arr w/ 0 <- 10` a tömb `[10,1,2,3]`.
- `arr w/ 2 <- 10` a tömb `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` a tömb `[10,1,12,3]`.

A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez. Vegyük például a típust 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Ha `c` a `Complex(1.,-1.)`típusú értéket tartalmazza, akkor a `c w/ Re <- 0.` egy `Complex` típusú kifejezés, amely kiértékeli a `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Feltételes kifejezések

Egy adott típus és egy logikai kifejezés két másik kifejezése alapján a feltételes kifejezés a kérdőjel `?` és a függőleges sáv `|`használatával hozható létre.
Például `a==b ? c | d`.
Ebben a példában a feltételes kifejezés értéke `c`, ha `a==b` igaz, és `d` hamis.

A két kifejezés kiértékelheti azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.
Ebben az esetben a feltételes kifejezés típusa olyan művelet, amely azokat a bemeneteket és kimeneteket támogatja, amelyek a mindkét kifejezés által támogatott összes feltételt támogatják.
Ha például `Op1`, `Op2`és `Op3` mind `Qubit[]=>Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja a `Controlled`, és `Op3` támogatja a következőket:

- a `flag ? Op1 | Op2` `(Qubit[] => Unit)` művelet.
- a `flag ? Op1 | Op3` `(Qubit[] => Unit is Adj)` művelet.
- a `flag ? Op2 | Op3` `(Qubit[] => Unit is Ctl)` művelet.

Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor ez a hívás csak akkor kerül sor, ha az eredmény a hívás értéke lesz.
Ha például a `a==b ? C(qs) | D(qs)`, ha `a==b` igaz, akkor a rendszer meghívja a `C` műveletet, és ha hamis, akkor csak `D` fog megjelenni.
Ez hasonló a más nyelvek rövid összekapcsolásához.


## <a name="operator-precedence"></a>Operátori prioritás

Minden bináris operátor megfelelő társítású, a `^`kivételével.

Zárójelek, `[` és `]`a tömb szeleteléséhez és indexeléséhez, az operátorok megkötése előtt.

Az operátorok a tömb indexelése után `Adjoint` és `Controlled` a kötést.

A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.

Az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:

Művelet | Aritása | Leírás | Operandusok típusai
---------|----------|---------|---------------
 záró `!` | Unáris | Kicsomagolása | Bármely felhasználó által definiált típus
 `-`, `~~~`, `not` | Unáris | Numerikus negatív, bitenkénti komplement, logikai tagadás | `Int`, `BigInt` vagy `Double` `-`, `Int` vagy `BigInt` esetében `~~~``Bool`
 `^` | Bináris | Egész számú Power | `Int` vagy `BigInt` az alaphoz, `Int` a kitevőhöz
 `/`, `*`, `%` | Bináris | Osztás, szorzás, egész szám modulusa | `Int`, `BigInt` vagy `Double` `/` és `*`, `Int` vagy `BigInt` számára `%`
 `+`, `-` | Bináris | Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás | `Int`, `BigInt` vagy `Double`, továbbá `String` vagy bármely tömb típusa `+`
 `<<<`, `>>>` | Bináris | Bal SHIFT, jobb SHIFT | `Int` vagy `BigInt`
 `<`, `<=`, `>`, `>=` | Bináris | Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás | `Int`, `BigInt` vagy `Double`
 `==`, `!=` | Bináris | egyenlő, nem egyenlő összehasonlítások | bármely primitív típus
 `&&&` | Bináris | Bitenkénti és | `Int` vagy `BigInt`
 `^^^` | Bináris | Bitenkénti XOR | `Int` vagy `BigInt`
 <code>\|\|\|</code> | Bináris | Bitenkénti vagy | `Int` vagy `BigInt`
 `and` | Bináris | Logikai és | `Bool`
 `or` | Bináris | Logikai vagy | `Bool`
 `..` | Bináris/Ternáris | Tartomány operátora | `Int`
 `?` `|` | Ternáris | Feltételes | a bal oldali `Bool`
`w/` `<-` | Ternáris | Másolás és frissítés | Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)
