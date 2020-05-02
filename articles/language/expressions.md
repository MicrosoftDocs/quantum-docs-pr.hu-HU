---
title: 'Q # kifejezések'
description: 'Megtudhatja, hogyan adhat meg, hivatkozhat és egyesíthet állandókat, változókat, operátorokat, műveleteket és függvényeket kifejezésként a Q #-ban.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683929"
---
# <a name="expressions"></a>Kifejezések

## <a name="grouping"></a>Csoportosítás

Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.
`(7)` `Int` Például egy `([1,2,3])` kifejezés, amely egy tömb `Int`típusú kifejezés, és `((1,2))` egy típusú `(Int, Int)`kifejezés.

A [típus modellben](xref:microsoft.quantum.language.type-model#tuple-types) leírt egyszerű értékek és egyelemes rekordok közötti egyenértékűség eltávolítja a kétértelműség `(6)` csoportot és `(6)` egy egyelemű rekordot.

## <a name="symbols"></a>Szimbólumok

Egy Type értékhez `'T` kötött vagy hozzárendelt szimbólum neve egy típusú `'T`kifejezés.
Ha például a szimbólum `count` az egész értékhez `5`van kötve, akkor `count` az egy egész szám kifejezés.

## <a name="numeric-expressions"></a>Numerikus kifejezések

A numerikus kifejezések a következő típusú `Int` `BigInt`kifejezések:, `Double`vagy.
Vagyis egész vagy lebegőpontos számok.

`Int`a Q # konstansai azonosak a C#-ban az egész szám literálokkal, azzal a különbséggel, hogy nincs szükség "l" vagy "L" értékre (vagy engedélyezett).
A hexadecimális és a bináris egész számok "0x" és "0b" előtaggal támogatottak.

`BigInt`a Q #-ban szereplő literálok azonosak a .NET-ben található Big Integer karakterláncokkal, amelyek egy "l" vagy "L" záró karakterrel rendelkeznek.
A hexadecimális nagy egész számok "0x" előtaggal támogatottak.
Így az alábbi `BigInt` értékek érvényesek a literálok összes érvényes használatára:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`a Q # konstansai a C#-ban dupla literálok, azzal a különbséggel, hogy a "d" vagy a "D" nem kötelező (vagy engedélyezett).

Egy adott elemtípus tömb `Int` kifejezése miatt a `Length` beépített függvénnyel létrehozható egy kifejezés, amely zárójelek közé foglalt tömb kifejezéssel `(` és. `)`
Ha `a` például egy tömbhöz van kötve, akkor `Length(a)` az egy egész szám kifejezés.
Ha `b` `Int[][]`az egész számokból álló tömbök tömbje, akkor `Length(b)` a-ben `b`az altömbök száma, a `Length(b[1])` pedig a második altömbben lévő egész számok száma. `b`

Az adott típus két numerikus kifejezése, a bináris operátorok `+` `-` `*`, a, és `/` az új numerikus kifejezéseket is felhasználhatja.
Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.

A két egész szám kifejezés miatt a bináris `^` operátor (Power) egy új egész kifejezés létrehozásához használható.
Hasonlóképpen, `^` két kettős kifejezéssel is használható, amelyek új dupla kifejezést alkotnak.
Végül a `^` bal oldalon egy nagy egész számmal, a jobb oldalon pedig egy egész számmal, egy új Big Integer típusú kifejezés létrehozásához is használható.
Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, a rendszer futásidejű hibát jelez.

A két egész vagy nagy egész szám típusú kifejezés esetében egy új egész vagy Big Integer kifejezés is létrehozható `%` a (modulus) `&&&` , (bitenkénti és) `|||` , (bitenkénti vagy), `^^^` vagy (bitenkénti XOR) operátorok használatával.

A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) `>>>` vagy (aritmetikai jobbra váltás) operátorok használhatók a bal oldali kifejezéssel megegyező típusú új kifejezés létrehozására.

A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.
A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, a rendszer futásidejű hibát jelez.
Ha a áthelyezhető szám egész szám, akkor a rendszer a eltolás mértékét értelmezi `mod 64`. Ez azt eredményezi, hogy az 1. és a 65 eltolása ugyanaz a hatása.

Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.
A negatív érték eltolása balra vagy jobbra is negatív számot eredményez.
Ez azt okozhatja, hogy az egyik lépés balra vagy jobbra való eltolása pontosan ugyanaz, mint a 2. számú szorzás vagy osztás.

Az egész szám és az Integer modulus ugyanazt a viselkedést követi a negatív számok esetében, mint a C#.
Ez azt eredményezi `a % b` , hogy mindig ugyanazzal a jellel `a`fog rendelkezni, `b * (a / b) + a % b` és `a`mindig egyenlő lesz.
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

A két `Bool` literális érték `true` a `false`és a.

Az azonos primitív típusú két kifejezés miatt a és `==` `!=` a bináris operátor is használható `Bool` kifejezés létrehozásához.
A kifejezés akkor igaz, ha a két kifejezés egyenlő, és hamis, ha nem.

A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani. Például a "kicsomagolás" operátor `!` használatával (amely a [Q # Type Model oldalon](xref:microsoft.quantum.language.type-model#user-defined-types)látható),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Az `Qubit` értékek egyenlőségének összehasonlítása az identitással egyenlő; Ez azt jelzi, hogy a két kifejezés ugyanazt a qubit azonosítja-e.
A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.

Az `Double` értékek egyenlőségének összehasonlítása a kerekítési hatások miatt félrevezető lehet.
Például: `49.0 * (1.0/49.0) != 1.0`.

A két numerikus kifejezéstől függően a bináris `>`operátorok `<` `>=`, a, `<=` és felhasználhatók egy olyan új logikai kifejezés létrehozására, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, mint a második kifejezés.

A két logikai kifejezés miatt a és `and` `or` a bináris operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha a két kifejezés mindkét (vagy mindkét) értéke igaz.

A logikai kifejezéseket megadva az `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.

## <a name="string-expressions"></a>Karakterlánc-kifejezések

A Q # lehetővé teszi a karakterláncok használatát `fail` az utasításban `Log` és a standard függvényben.

A Q # sztringek literálok vagy interpolált karakterláncok.
A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterlánc-literálokra: az Unicode-karakterek egy számsorozata `"`idézőjelek közé.
Egy karakterláncon belül a háttér `\` -perjel karakter felhasználható dupla idézőjelek kiírására, valamint egy új vonal `\n`beszúrására, a kocsivissza `\r`karaktert és a lapot. `\t`
Ilyenek például a következők:

```qsharp
"\"Hello world!\", she said.\n"
```

A Q # szintaxis a karakterlánc-interpolációhoz a C# 7,0 szintaxis részhalmaza. A Q # nem támogatja a Verbatim (többsoros) interpolált karakterláncokat.
Lásd: [*interpolált karakterláncok*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) a C# szintaxishoz.

Az interpolált karakterláncban szereplő kifejezések a Q # szintaxist követik, nem a C# szintaxist.
Bármely érvényes Q # kifejezés egy interpolált karakterláncban jelenhet meg.

## <a name="qubit-expressions"></a>Qubit kifejezések

Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékek vagy tömb elemeihez `Qubit` van kötve.
Nincsenek `Qubit` literálok.

## <a name="pauli-expressions"></a>Pauli-kifejezések

A négy `Pauli` érték `PauliI` `PauliX` `PauliY`:,,, és `PauliZ`, minden érvényes `Pauli` kifejezés.

Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékek vagy tömb elemeihez `Pauli` van kötve.

## <a name="result-expressions"></a>Eredmény kifejezései

A két `Result` érték ( `One` és `Zero`) érvényes `Result` kifejezés.

Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékek vagy tömb elemeihez `Result` van kötve.
Különösen fontos megjegyezni, hogy `One` nem ugyanaz, mint az egész szám `1`, és nincs közvetlen konverzió a közöttük.
Ugyanez érvényes a és `Zero` `0`a esetében is.

## <a name="range-expressions"></a>Tartomány kifejezései

Egy három `Int` kifejezés `start`, `step`a és `stop` `start .. step .. stop` a egy olyan tartomány kifejezése, amelynek első eleme `start`a, a második `start+step`elem, a harmadik `start+step+step`elem, stb., `stop` amíg a rendszer át nem adja.
A tartomány lehet üres, ha például `step` a pozitív és `stop < start`a.
A tartomány utolsó `stop` eleme lesz, ha a és `start` `stop` a közötti különbség a többszöröse; `step` vagyis a tartomány mindkét végén szerepel.

A két `Int` kifejezésnek `start` megfelelő `stop`, `start .. stop` és egy tartománybeli kifejezés, amely egyenlő `start .. 1 .. stop`.
Vegye figyelembe, hogy `step` a vélelmezett érték + 1 `stop` , még akkor `start`is, ha a értéke kisebb, mint; ilyen esetben a tartomány üres.

Néhány példa a tartományokra:

- `1..3`az 1., 2. és 3. tartomány.
- `2..2..5`a 2. és 4. tartomány.
- `2..2..6`a 2, 4, 6. tartomány.
- `6..-2..2`a 6, 4, 2 tartomány.
- `2..1`az üres tartomány.
- `2..6..7`a 2. tartomány.
- `2..2..1`az üres tartomány.
- `1..-1..2`az üres tartomány.

## <a name="callable-expressions"></a>Hívható kifejezések

A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.
`X` Például egy olyan műveleti literál, amely a szabványos könyvtári `X` műveletre hivatkozik, `Message` és egy függvény literál, amely a standard Library `Message` függvényre hivatkozik.

Ha egy művelet támogatja az `Adjoint` elválasztó műveletet `Adjoint op` , akkor egy művelet kifejezése.
Hasonlóképpen, ha a művelet támogatja az `Controlled` elválasztó műveletet `Controlled op` , akkor egy művelet kifejezése.
Ezeknek a kifejezéseknek a típusai a következőben vannak [megadva.](xref:microsoft.quantum.language.type-model#functors)

A (`Adjoint` és `Controlled`) az összes többi operátorral szorosabban kötődik, kivéve a kicsomagolási operátort `!` és a tömb `[]`indexelését.
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

Ha `Fun` például a függvény aláírása `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Hívható hívási kifejezések

Egy meghívásos (művelet vagy függvény) kifejezés és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos kifejezés úgy hozható létre, hogy hozzáfűzi a rekord kifejezését a meghívható kifejezéshez.
A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.

Ha `Op` például az egy `((Int, Qubit) => Double)`aláírással rendelkező művelet, `Op(3, qubit1)` a egy típusú `Double`kifejezés.
Hasonlóképpen, ha `Sin` az egy függvény az `(Double -> Double)`aláírással `Sin(0.1)` , egy típusú `Double`kifejezés.
Végül, ha `Builder` az a függvény az aláírással `(Int -> (Int -> Int))`, `Builder(3)` akkor a függvény a from int értékre.

Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.
Így az előző bekezdésből történő hívás `Builder` eredményének meghívásához a helyes szintaxis a következő:

```qsharp
(Builder(3))(2)
```

A típus-paraméteres metódus meghívásakor a tényleges Type paraméterek a szögletes zárójelben `<` és `>` a meghívásos kifejezés után is megadhatók.
Ez általában szükségtelen, mivel a Q # fordítóprogram a tényleges típusokat fogja kikövetkeztetni.
A részleges alkalmazáshoz szükséges (lásd alább), ha egy Type-paraméteres argumentum nincs megadva.
Időnként hasznos lehet, ha a különböző felállókkal rendelkező műveletek átadása meghívásos támogatással történik.

Ha `Func` `('T1, 'T2, 'T1) -> 'T2`például rendelkezik aláírással, `Op1` és `Op2` `(Qubit[] => Unit is Adj)`aláírással rendelkezik, és `Op3` aláírással `(Qubit[] => Unit)`rendelkezik, az `Func` első `Op1` argumentumként, `Op2` a másodikként és `Op3` a harmadikként való meghívásához:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A típus specifikációjának megadása kötelező `Op3` , `Op1` mert különböző típusok vannak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.

### <a name="partial-application"></a>Részleges alkalmazás

Egy meghívásos kifejezés miatt egy új hívható is létrehozható az argumentumok egy részhalmazának megadásával a meghívónak.
Ezt nevezzük _részleges alkalmazásnak_.

A Q #-ban a részlegesen alkalmazott meghívót egy normál meghívásos kifejezés megírásával, de aláhúzással `_`, a meghatározatlan argumentumok használatával fejezzük ki.
Az eredményül kapott meghívó ugyanazzal az eredménnyel rendelkezik, mint az alapszintű hívható, és ugyanazokat a specializációkat kell megadnia a műveletekhez.
A részleges alkalmazás bemeneti típusa egyszerűen az eredeti típus, ahol a megadott argumentumok el lettek távolítva.

Ha egy megváltoztathatatlan változót egy részleges alkalmazás létrehozásakor megadott argumentumként ad át, a rendszer a változó aktuális értékét használja.
A változó értékének módosítása később nem befolyásolja a részleges alkalmazást.

Például ha `Op` a típus `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))`típus `(((Qubit,Qubit), Double) => Unit is Adj)`, és így van `Op(5,_)`.
- `Op(_,(_,1.0))`típusa `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))`típusa `((Int,Double) => Unit is Adj)`.
   Vegye figyelembe, hogy itt is alkalmazunk egy Egyrekordos egyenértékűséget.

Ha a részben alkalmazott hívható olyan paraméterekkel rendelkezik, amelyeket a fordító nem tud következtetni, meg kell adni azokat a Meghívási helyen.
A részleges alkalmazás nem rendelkezhet meghatározatlan típusú paraméterekkel.

Például ha `Op` a típus `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

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

A rekordos literál a megfelelő típusú elemek sorozata, vesszővel elválasztva, a és `(` `)`a közé foglalt módon.
`(1, One)` Például egy `(Int, Result)` kifejezés.

A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.

## <a name="user-defined-type-expressions"></a>Felhasználó által definiált típusú kifejezések

A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.
Ha `IntPair` például a felhasználó által definiált típus a `(Int, Int)`(z) alapján, `IntPair(2,3)` akkor az adott típusú érvényes literál lenne.

A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.

## <a name="unwrap-expressions"></a>Kifejezések kicsomagolása

A Q # értéknél a kicsomagolás operátor egy záró felkiáltójel `!`.
`IntPair` Például, ha egy felhasználó által definiált típus, amely egy alapul `(Int, Int)`szolgáló típussal rendelkezik `s` , és egy `IntPair(2,3)`változó értékkel rendelkezik, akkor `s!` a következő lesz `(2,3)`:.

A felhasználó által definiált típusok esetében definiált más felhasználók által definiált típusok esetében. lehet, hogy a kicsomagolási operátor megismétlődik; például a kétszeresen kicsomagolt értéket `s!!` jelöli. `s`
Így `WrappedPair` ha a felhasználó által definiált típus egy alapul szolgáló típusú `IntPair`, és `t` egy változó értékkel `WrappedPair(IntPair(1,2))`, akkor `t!!` a következő lesz `(1,2)`:.

Az `!` operátor magasabb prioritású, mint az összes többi operátor `[]` , mint a tömb indexelése és a szeletelése.
`!`és `[]` a kötés elhelyezése; `a[i]![3]` azaz a következőt kell elolvasnia `((a[i])!)[3]`: a `i`"th elemének `a`kicsomagolása, majd a nem burkolt érték harmadik elemének beolvasása (tömbnek kell lennie).

Az `!` operátor elsőbbsége egy olyan hatással van, amely esetleg nem nyilvánvaló.
Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.
Például:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Tömb kifejezései

A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, a és `[` `]`a közé.
Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.

Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.
A tömb elemének típusa az összes elem által támogatott összes olyan futtatót támogatni fogja.
Például, ha `Op1` `Op2`, és `Op3` mind a `Qubit[] => Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja `Controlled`és `Op3` támogatja a következőket:

- `[Op1, Op2]`a a `(Qubit[] => Unit)` műveletek tömbje.
- `[Op1, Op3]`a a `(Qubit[] => Unit is Adj)` műveletek tömbje.
- `[Op2, Op3]`a a `(Qubit[] => Unit is Ctl)` műveletek tömbje.

Az üres tömb literálok `[]`nem engedélyezettek.
A használata `new ★[0]`helyett, `★` ahol a egy megfelelő típusú helyőrző, lehetővé teszi a nulla hosszúságú kívánt tömb létrehozását.

Mivel a két tömb azonos típusú, a bináris `+` operátor egy olyan új tömb létrehozásához használható, amely a két tömb összefűzése.
`[1,2,3] + [4,5,6]` Például: `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Tömb létrehozása

Adott típus és `Int` kifejezés alapján az `new` operátor felhasználható a megadott méretű új tömb kiosztására.
`new Int[i+1]` Például lefoglalhat egy új `Int` tömböt `i+1` elemekkel.

Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.
A legtöbb esetben ez a nulla valamilyen változata.

Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.
Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely futásidejű hiba nélkül nem használható.
Ez hasonló a más nyelveken (például C# vagy Java) található null hivatkozáshoz.
A qubits vagy callables tartalmazó tömböket megfelelően kell inicializálni a nem alapértelmezett értékekkel, mielőtt az elemek biztonságosan használhatók legyenek. A megfelelő inicializálási rutinok a következő címen <xref:microsoft.quantum.arrays>találhatók:.

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

Egy tömböt megadó kifejezés és `Range` egy kifejezés alapján egy új kifejezés is létrehozható a `[` és `]` a tömb szelet operátor használatával.
Az új kifejezés ugyanolyan típusú, mint a tömb, és a ( `Range` `Range`) elemei által indexelt tömb elemeket fogja tartalmazni a által definiált sorrendben.
`a` Ha `Double`például egy tömbhöz van kötve, akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely az első négy elemét tartalmazza, `a` de a fordított sorrendben, ahogy azok megjelennek a következőben: `a`.

Ha az `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú lesz.

Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell tenni a szelethez.
Ha `a` például a és `b` mindkét tömbje `Int`, az összefűzésből származó szeletek a következőképpen lesznek kifejezve:

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

Egy tömb kifejezése és egy `Int` kifejezés alapján egy új kifejezés is létrehozható a és `[` `]` a tömb elem operátor használatával.
Az új kifejezés ugyanolyan típusú lesz, mint a tömb elemének típusa.
Ha `a` például egy `Double`tömbhöz van kötve, akkor `a[4]` egy `Double` kifejezés.

Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell foglalni, hogy ki lehessen választani egy elemet.
Ha `a` például a és `b` mindkét tömbje, az összefűzésből származó elem a `Int`következőként lesz kifejezve:

```qsharp
(a+b)[13]
```

A Q # összes tömbje nulla-alapú.
Vagyis a tömb `a` első eleme mindig `a[0]`.


## <a name="copy-and-update-expressions"></a>Másolás és frissítés kifejezések

Új tömbök hozhatók létre a meglévő példányokból másolás és frissítés kifejezések használatával.
A copy-Update `expression1 w/ expression2 <- expression3`kifejezés az űrlap kifejezése, amelyben `expression1` valamilyen típusú típusnak kell lennie. `T[]` `T` A második `expression2` meghatározza, hogy az elem (ek) milyen indexeket módosítson a tömbhöz képest, `expression1` és a típusnak `Int` vagy típusúnak kell lennie `Range`. Ha `expression2` a típusa típusú `Int`, `expression3` a típusnak `T`kell lennie. Ha `expression2` a típusa típusú `Range`, `expression3` a típusnak `T[]`kell lennie.

`arr w/ idx <- value` A másolási és frissítési kifejezés egy új tömböt hoz létre `arr`, amely a megfelelő elemre van állítva, kivéve a (z) elem (ek) `idx`et, amely a (z) értékre van beállítva `value`. Ha `arr` például egy tömböt `[0,1,2,3]`tartalmaz, akkor 
- `arr w/ 0 <- 10`a tömb `[10,1,2,3]`.
- `arr w/ 2 <- 10`a tömb `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]`a tömb `[10,1,12,3]`.

A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez. Vegyük például a típust 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Ha `c` a érték tartalmazza a Type `Complex(1.,-1.)`értéket, `c w/ Re <- 0.` akkor a a következő típusú `Complex` kifejezést adja vissza: `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Feltételes kifejezések

Egy adott típus és egy logikai kifejezés két másik kifejezése alapján a feltételes kifejezés a kérdőjel `?` és a függőleges sáv `|`használatával hozható létre.
Például: `a==b ? c | d`.
Ebben a példában a feltételes kifejezés értéke TRUE (igaz) és `c` `d` false `a==b` (hamis) lesz.

A két kifejezés kiértékelheti azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.
Ebben az esetben a feltételes kifejezés típusa olyan művelet, amely azokat a bemeneteket és kimeneteket támogatja, amelyek a mindkét kifejezés által támogatott összes feltételt támogatják.
Például, ha `Op1` `Op2`, és `Op3` mind a `Qubit[]=>Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja `Controlled`és `Op3` támogatja a következőket:

- `flag ? Op1 | Op2`egy `(Qubit[] => Unit)` művelet.
- `flag ? Op1 | Op3`egy `(Qubit[] => Unit is Adj)` művelet.
- `flag ? Op2 | Op3`egy `(Qubit[] => Unit is Ctl)` művelet.

Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor ez a hívás csak akkor kerül sor, ha az eredmény a hívás értéke lesz.
Ha `a==b ? C(qs) | D(qs)` `a==b` például igaz, akkor a rendszer meghívja a `C` műveletet, és ha hamis, akkor csak `D` a rendszer hívja meg.
Ez hasonló a más nyelvek rövid összekapcsolásához.


## <a name="operator-precedence"></a>Operátori prioritás

Minden bináris operátor megfelelő társítású, kivéve a következőt `^`:.

Szögletes zárójelek `[` , `]`valamint a tömb szeleteléséhez és indexeléséhez minden operátor előtt kötést kell kötni.

A `Adjoint` kikapcsolók `Controlled` és a kötés a tömb indexelése után, de az összes többi operátor előtt.

A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.

Az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:

Művelet | Aritása | Leírás | Operandusok típusai
---------|----------|---------|---------------
 záró`!` | Unáris | Kicsomagolása | Bármely felhasználó által definiált típus
 `-`, `~~~`, `not` | Unáris | Numerikus negatív, bitenkénti komplement, logikai tagadás | `Int`, `BigInt` vagy `Double` `-` `BigInt` esetén a `Int` `~~~` `Bool``not`
 `^` | Bináris | Egész számú Power | `Int`vagy `BigInt` az alaphoz a `Int` kitevő esetében
 `/`, `*`, `%` | Bináris | Osztás, szorzás, egész szám modulusa | `Int`, `BigInt` vagy `Double` `/` `*` `Int` `BigInt``%`
 `+`, `-` | Bináris | Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás | `Int``BigInt` vagy `Double`, `String` vagy bármely tömb típusa a következőhöz:`+`
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
