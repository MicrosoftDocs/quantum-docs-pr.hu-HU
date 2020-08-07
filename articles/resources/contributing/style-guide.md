---
title: Microsoft Q# stílusú útmutató
description: A programok és könyvtárak elnevezési, bemeneti, dokumentációs és formázási konvencióinak megismerése Q# .
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: 27a2ae5ae9d00329fc369268edae24228a9a9d0d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867589"
---
# <a name="no-locq-style-guide"></a>Q#Stílus útmutató #
## <a name="general-conventions"></a>Általános konvenciók ##

Az útmutatóban javasolt konvenciók célja, hogy megkönnyítse a programok és a kódtárak írását Q# és értelmezését.

## <a name="guidance"></a>Útmutató

Javasoljuk, hogy:

- Soha ne hagyja figyelmen kívül az egyezményt, hacsak nem ezt szándékosan teszi, hogy könnyebben olvasható és értelmezhető kódot nyújtson a felhasználók számára.

## <a name="naming-conventions"></a>Elnevezési konvenciók ##

A Quantum Development Kit szolgáltatásban a függvény-és műveleti nevekre törekszünk, amelyek segítenek a kvantum-fejlesztőknek olyan programok írásához, amelyek könnyen olvashatóak, és a lehető legkevesebb meglepetést okozzák.
Fontos része annak, hogy ha a függvények, műveletek és típusok neveit választjuk, a programozók a Quantum fogalmak kifejezéséhez használt *szókincset* hoznak létre. a választásunk során segítünk vagy meggátoljuk őket abban, hogy világosan kommunikáljanak.
Ez felelősséget vállal a számunkra, hogy megbizonyosodjon róla, hogy az általunk bevezetett nevek egyértelműek és nem homályosak.
Ebben a szakaszban részletesen ismertetjük, hogyan teljesítjük ezt a kötelezettséget olyan explicit útmutatás szempontjából, amely segít a fejlesztő Közösség által nyújtott legjobb megoldásban Q# .

### <a name="operations-and-functions"></a>Műveletek és függvények ###

Az egyik első dolog, amit a névnek meg kell állapítania, hogy egy adott szimbólum függvényt vagy műveletet jelöl.
A függvények és a műveletek közötti különbség elengedhetetlen a kód egy blokkjának megismeréséhez.
A függvények és a műveletek közötti különbségtételt a felhasználók számára is Q# felhasználjuk.
*Ez egy művelet végrehajtása* .

Ezzel szemben a függvények leírják az adatok közötti matematikai kapcsolatokat.
A kifejezés `Sin(PI() / 2.0)` *az* `1.0` , és nem jelent semmit a program vagy a qubits állapotáról.

Összefoglalva, a műveletek műveleteket végeznek, miközben a függvények a dolgok.
Ez a különbségtétel azt sugallja, hogy az Operations és a függvények neve a következő: nevek.

> [!NOTE]
> Felhasználó által definiált típus deklarálása esetén az adott típusú példányokat létrehozó új függvény implicit módon van definiálva egy időben.
> Ebből a szemszögből a felhasználó által definiált típusok neveként kell nevezni, hogy mind a típus, mind a konstruktor függvény konzisztens névvel rendelkezzen.

Ahol ésszerű, győződjön meg arról, hogy a műveleti nevek olyan műveletekkel kezdődnek, amelyek egyértelműen jelzik a művelet által végrehajtott hatást.
Például:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Egy eset, amely különleges említést érdemel, ha egy művelet bemenetként egy másik műveletet hajt végre, és meghívja azt.
Ilyen esetekben a bemeneti művelet által végrehajtott művelet nem egyértelmű, ha a külső művelet definiálva van, úgy, hogy a megfelelő művelet ne legyen azonnal egyértelmű.
A művelet a, a, a és a esetében ajánlott `Apply` `ApplyIf` `ApplyToEach` `ApplyToFirst` .
Ebben az esetben más igék is hasznosak lehetnek, mint a-ben `IterateThroughCartesianPower` .

| Művelet | Várt hatás |
| ---- | ------ |
| Alkalmaz | A bemenetként megadott műveletet nevezzük |
| Assert | A lehetséges kvantum-mérés eredményével kapcsolatos hipotézist egy szimulátor ellenőrzi |
| Becslés | Egy klasszikus értéket ad vissza, amely egy vagy több mérésből álló becslést jelöl. |
| Measure | A rendszer elvégzi a kvantum-mérést, és annak eredményét visszaadja a felhasználónak |
| Előkészítés | A qubits adott regisztrálása egy adott állapotba van inicializálva |
| Sample | Egy klasszikus értéket ad vissza véletlenszerűen egy bizonyos eloszlásból |

A függvények esetében javasoljuk, hogy kerülje a műveletek használatát a közös nevek mellett (lásd az alábbi, a földrajzi nevekkel kapcsolatos útmutatót) vagy a mellékneveket:

- `ConstantArray`
- `Head`
- `LookupFunction`

Különösen, ha szinte minden esetben azt javasoljuk, hogy a múltbeli táblázatos adatok használatával jelezze, hogy egy függvény neve erősen csatlakozik egy művelethez vagy egy mellékhatáshoz a kvantum-programban másutt.
Például a `ControlledOnInt` "vezérlő" művelet "Control" utasításának "a" kifejezés formája, amely azt jelzi, hogy a függvény melléknévként viselkedik az argumentumának módosításához.
Ennek a névnek a további előnye, hogy összefoglalja a beépített felépítmény szemantikai `Controlled` feltételeit, ahogy azt az alábbiakban tárgyaljuk.
Hasonlóképpen, az _ügynökök_ nevei a függvények és a UDT alapján is felhasználhatók a műveleti nevekből, például egy, a szolgáltatáshoz `Encoder` szorosan társított UDT neve esetén `Encode` .

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Műveletek neveihez használjon műveleteket.
- Nevek vagy melléknevek használata a függvények neveihez.
- A felhasználó által definiált típusokhoz és attribútumokhoz tartozó nevek használata.
- Az összes hívható név esetében használjon `CamelCase` erős preferenciát a `pascalCase` ,, vagy rendszerre `snake_case` `ANGRY_CASE` . Különösen ügyeljen arra, hogy a hívható nevek nagybetűvel kezdődjön.
- Az összes helyi változó esetében használjon `pascalCase` erős preferenciát a `CamelCase` ,, vagy rendszerre `snake_case` `ANGRY_CASE` . Különösen ügyeljen arra, hogy a helyi változók kisbetűkkel kezdődjön.
- Kerülje az aláhúzások használatát a `_` függvények és a műveletek neveiben; ahol további hierarchiára van szükség, használja a névtereket és a névterek aliasait.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Név | Leírás |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | A művelet hatásának jelzéséhez törölje a műveletet ("tükrözze"). |
| ☒ | <s>`operation XRotation`</s> | A főnévi kifejezés a művelet helyett a függvényt javasolja. |
| ☒ | <s>`operation search_oracle`</s> | `snake_case`Ellentétes Q# jelölés használata. |
| ☒ | <s>`operation Search_Oracle`</s> | A belső és a műveleti név közötti aláhúzások használatának Q# megjelölése. |
| ☑ | `function StatePreparationOracle` | A főnévi kifejezés használata azt sugallja, hogy a függvény egy műveletet ad vissza. |
| ☑ | `function EqualityFact` | A főnév ("Fact") egyértelmű használata annak jelzésére, hogy ez egy függvény, míg a melléknév. |
| ☒ | <s>`function GetRotationAngles`</s> | Az ige ("Get") használata azt jelzi, hogy ez egy művelet. |
| ☑ | `newtype GeneratorTerm` | A főnévi kifejezés használata egyértelműen a UDT konstruktor hívásának eredményét jelenti. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | A ige kifejezés használata azt sugallja, hogy a UDT konstruktora egy művelet. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | A főnévi kifejezés használata az attribútum használatát közli. |

***

### <a name="entry-points"></a>Belépési pontok

Egy belépési pont programba való definiálásakor Q# a Q# fordító felismeri az [ `@EntryPoint()` attribútumot](xref:microsoft.quantum.core.entrypoint) , ami azt igényli, hogy a belépési pontok egy adott névvel rendelkezzenek (például: `main` , `Main` , vagy `__main__` ).
Ez a fejlesztő szemszögéből a Q# beléptetési pontok a következőhöz fűzött általános műveletek: `@EntryPoint()` .
Emellett a Q# belépési pontok egy teljes alkalmazáshoz (például Q# önálló végrehajtható fájlokban), vagy a Q# program és az alkalmazáshoz tartozó gazda program (például a Python vagy a .net használata esetén) közötti illesztőfelületek lehetnek Q# , így a "Main" név félrevezető lehet, ha egy Q# belépési pontra alkalmazva van.

Javasoljuk, hogy az elnevezési belépési pontok használatával tükrözze az `@EntryPoint()` attribútum használatát a fent felsorolt elnevezési műveletek általános tanácsainak használatával.


# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Ne nevezze a belépési pont műveleteit "Main"-ként.
- A név belépési pont műveletei szokásos műveletként.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Név | Leírás |
|---|------|-------------|
| ☑ | `@EntryPoint() operation RunSimulation` | A művelet neve a belépési pont célját egyértelműen közli. |
| ☒ | <s>`@EntryPoint() operation Main`</s> | A használata `Main` nem jelent egyértelmű kommunikációt a belépési pont céljával, és redundáns az `@EntryPoint()` attribútummal. |

***

### <a name="shorthand-and-abbreviations"></a>Rövidítések és rövidítések ###

A fenti tanácsokban a Gyorsírás számos formája létezik, amely a kvantum-számítástechnika általános és átható használatát látja el.
Javasoljuk, hogy meglévő és közös gyorsírást használjon, ahol létezik, különösen olyan műveletek esetén, amelyek a célszámítógép működéséhez tartoznak.
Például a helyett a nevet választjuk `X` `ApplyX` `Rz` `RotateAboutZ` .
Ilyen rövidítés használatakor a művelet neve csak nagybetűs lehet (például: `MAJ` ).

Erre az egyezményre akkor van szükség, ha gyakran használt betűszók és nagybetűk, például "QFT" a "Quantum Fourier átalakítás" kifejezésre alkalmazzák.
Javasoljuk, hogy az általános .NET-konvenciókat a betűszók és a nagyszótárak teljes névben való használatára ajánljuk, amely az alábbiakat írja elő:

- a kétbetűs betűszók és a nagyvállalatok neve nagybetűs (például: `BE` "big-endian"),
- az összes további betűszó és a nagybetűk neve `CamelCase` (például: `Qft` "Quantum Fourier Transform")

Így a QFT megvalósító művelet lehet `QFT` rövidített vagy kiírva `ApplyQft` .

A gyakran használt műveletek és függvények esetében érdemes lehet egy rövidített nevet megadni egy hosszú űrlap _aliasként_ való megadásához:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Ha szükséges, tekintse meg a gyakran elfogadott és széles körben használt rövidített neveket.
- Kis-és nagybetűk használata a gyorsíráshoz.
- Rövid (kétbetűs) betűszók és nagybetűk használata.
- `CamelCase`Hosszabb (három vagy több betűs) rövidítéssel és nagybetűkkel is használható.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Név | Leírás |
|---|------|-------------|
| ☑ | `X` | Jól ismert Gyorsírás a "$X $ átalakítás alkalmazása" |
| ☑ | `CNOT` | Jól értelmezhető Gyorsírás a "vezérelt – nem" |
| ☒ | <s>`Cnot`</s> | A Gyorsírás nem lehet a-ben `CamelCase` . |
| ☑ | `ApplyQft` | A "QFT" általános inicializálás a hosszú formátumú név részeként jelenik meg. |
| ☑ | `QFT` | A "QFT" általános inicializálás egy rövidített név részeként jelenik meg. |



***


### <a name="proper-nouns-in-names"></a>Megfelelő nevek a névben ###

A fizikában gyakran előfordul, hogy az első személynek a róluk való közzétételét követően a legtöbb nem fizikus nem ismeri a mindenki nevét és az előzményeket.
A fizika elnevezési konvenciói alapján túl nagy mértékben támaszkodhat a beléptetésre, mivel a más hátterű felhasználóknak nagy mennyiségű látszólag átlátszatlan nevet kell megtanulniuk ahhoz, hogy közös műveleteket és fogalmakat lehessen használni.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Ezért azt javasoljuk, hogy ha ésszerű, a fogalmakat leíró általános nevek erős előnyben legyenek kitéve a fogalmak közzétételének előzményeit leíró földrajzi nevek iránt.
Ebben az esetben a nem megfelelően vezérelt SWAP-és kettős vezérlésű, nem műveleti műveleteket gyakran a tudományos irodalomban található "Fredkin" és "Toffoli" műveletnek nevezzük, de a rendszer elsősorban a és a esetében azonosítja őket Q# `CSWAP` `CCNOT` .
Az API-dokumentációs megjegyzések mindkét esetben a megfelelő neveken alapuló szinonimákat biztosítanak az összes megfelelő hivatkozással együtt.

Ez a beállítás különösen fontos, hogy a megfelelő főnevek bizonyos használata mindig kötelező legyen – Q# a számos klasszikus nyelv által meghatározott hagyományt követi, és a `Bool` típusokat a logikai logikára mutató hivatkozásokra utal, amely George Boole tiszteletben tartásával lett elnevezve.
Ehhez hasonló módon kell elnevezni néhány kvantum-fogalmat, például a `Pauli` nyelvhez beépített típust Q# .
A megfelelő főnevek használatának minimalizálása, ha az ilyen használat nem alapvető fontosságú, csökkentik annak a hatását, hogy a megfelelő földrajzi nevek ne legyenek ésszerűen elkerülhetők.

# <a name="guidance"></a>[Útmutató](#tab/guidance) 

Javasoljuk, hogy:

- Kerülje a nevekben a megfelelő nevek használatát.

# <a name="examples"></a>[Példák](#tab/examples)

***

### <a name="type-conversions"></a>Típus konverziója ###

Mivel a Q# egy erősen és statikusan beírt nyelv, az egyik típus értéke csak más típusú érték lehet, mint egy típus-átalakítási függvény kifejezett hívása.
Ez ellentétben áll azokkal a nyelvekkel, amelyek lehetővé teszik, hogy az értékek implicit módon módosítsák a típusokat (pl.: Type Promotion) vagy a casting használatával.
Ennek eredményeképpen a konvertálási függvények fontos szerepet játszanak a Q# kódtár fejlesztésében, és az elnevezéssel kapcsolatban leggyakrabban felmerülő döntések egyikét alkotják.
Azonban ez azt jelzi, hogy mivel a Type konverziók mindig _determinisztikus_, a függvények is megírhatók, ezért a fenti tanács alá tartoznak.
Különösen azt javasoljuk, hogy a Type konverziós függvények soha ne legyenek elnevezve műveleteknek (pl.: `ConvertToX` ) vagy a határozószók előírási kifejezéseknek ( `ToX` ), hanem a forrás és a cél típusokat () jelző, melléknévi előírási kifejezéseknek kell nevezni `XAsY` .
Ha a tömb típusait a konverziós függvények neveiben listázza, javasoljuk a gyorsírást `Arr` .
A kivételes körülmények korlátozásával azt javasoljuk, hogy az összes Type konverziós függvény neve legyen, hogy `As` gyorsan azonosítható legyen.

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Ha egy függvény Type típusú értéket alakít át `X` `Y` , használja a nevet vagy a értéket `AsY` `XAsY` .

# <a name="examples"></a>[Példák](#tab/examples)

|   | Név | Leírás |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | A "to" utasítás a művelethez tartozó kifejezést eredményez, és nem függvényt jelez. |
| ☒ | <s>`AsDouble`</s> | A bemeneti típus nem egyértelmű a függvény nevéből. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | A bemeneti és a kimeneti típusok nem megfelelő sorrendben jelennek meg. |
| ☑ | `ResultArrAsBoolArr` | A bemeneti típusok és a kimeneti típusok egyaránt törlődnek. |

***

### <a name="private-or-internal-names"></a>Magán-vagy belső nevek ###

Sok esetben a név kifejezetten a belső könyvtárakhoz vagy projektekhez való használatra szolgál, és nem a könyvtár által kínált API garantált részét képezi.
Hasznos lehet egyértelműen jelezni, hogy ez a helyzet az elnevezési függvények és műveletek esetében, hogy a csak belső kódok véletlen függőségei legyenek egyértelműek.
Ha egy művelet vagy függvény nem közvetlen használatra készült, hanem egy, a részleges alkalmazás által elvégezhető egyező meghívót kell használni, érdemes lehet egy olyan nevet használni, amely a `internal` részben alkalmazott hívható kulcsszóval kezdődik.

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Ha egy függvény, művelet vagy felhasználó által definiált típus nem része a nyilvános API-nak egy Q# könyvtár vagy program számára, győződjön meg arról, hogy belső jelöléssel van megjelölve, ha a `internal` , vagy a deklaráció előtt elhelyezi a kulcsszót `function` `operation` `newtype` .

# <a name="examples"></a>[Példák](#tab/examples)

|   | Név | Leírás |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | Ne használjon aláhúzást `_` annak jelzésére, hogy a művelet csak belső használatra szolgál. |
| ☑ | `internal operation ApplyDecomposedOperation` | Az `internal` elején lévő kulcsszó egyértelműen azt jelzi, hogy ez a művelet csak belső használatra szolgál. |

***
### <a name="variants"></a>Változatok ###

Bár ez a korlátozás nem szűnik meg a későbbi verzióiban Q# , jelenleg a kapcsolódó műveletek vagy függvények olyan csoportjai lesznek, amelyek megkülönböztetni a bemenetek támogatását, illetve az argumentumok konkrét típusait.
Ezek a csoportok megkülönböztetni ugyanazt a legfelső szintű nevet, majd egy vagy két betűt, amelyek jelzik a változatát.

| Utótag | Értelmezés |
|--------|---------|
| `A` | Várhatóan támogatott bemenet`Adjoint` |
| `C` | Várhatóan támogatott bemenet`Controlled` |
| `CA` | A várt támogatás `Controlled` és`Adjoint` |
| `I` | Bemenet vagy bemenet típusa`Int` |
| `D` | Bemenet vagy bemenet típusa`Double` |
| `L` | Bemenet vagy bemenet típusa`BigInt` |

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Ha egy függvény vagy művelet nem kapcsolódik hasonló funkciókhoz vagy műveletekhez a bemenetek típusai és a nem megfelelő működésének támogatásával, ne használjon utótagot.
- Ha egy függvény vagy művelet bármely hasonló függvényhez vagy művelethez kapcsolódik, és a bemenetek típusai és az azokon lévők is támogatják, a változatok megkülönböztetéséhez használja a fenti táblázatban szereplő utótagokat.

# <a name="examples"></a>[Példák](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumentumok és változók ###

Egy Q# függvény vagy művelet kódjának kulcsfontosságú célja, hogy könnyen olvasható és értelmezhető legyen.
Hasonlóképpen, a bemenetek és a Type argumentumok neveinek kell megadniuk, hogy a rendszer hogyan használja a függvényt vagy az argumentumot.


# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Az összes változó és bemeneti név esetében használjon `pascalCase` erős preferenciát a `CamelCase` ,, vagy rendszerhez `snake_case` `ANGRY_CASE` .
- A bemeneti névnek leírónak kell lennie. lehetőleg ne adjon meg egy vagy két betűt.
- A pontosan egy típusú argumentumot elfogadó műveletek és függvények a Type argumentumot jelölik, `T` Ha a szerepköre nyilvánvaló.
- Ha egy függvény vagy művelet több típusú argumentumot is igénybe vesz, vagy ha egy adott típusú argumentum szerepköre nem egyértelmű, érdemes lehet egy rövid, tőkésített szót `T` (például:) használni `TOutput` az egyes típusokhoz.
- Az argumentumban és a változók neveiben ne szerepeljenek a nevek. ezt az információt a fejlesztési környezetnek is meg kell adni.
- Skaláris típusokat jelöl a literális nevük ( `flagQubit` ) és a tömb típusa szerint egy többes szám ( `measResults` ) alapján.
  A qubits-tömbök esetében érdemes lehet olyan típusokat megjelölni, `Register` amelyek alapján a név olyan qubits-sorozatra hivatkozik, amely valamilyen módon szorosan összefügg egymással.
- A tömbökbe indexként használt változóknak a (z) értékkel kell kezdődnie, `idx` és csak néhány lehet (például: `things[idxThing]` ).
  Különösen érdemes elkerülni az egybetűs változók nevének indexként való használatát. ajánlott legalább a használata `idx` .
- A tömbök hosszának megtartására használt változóknak a (z) értékkel kell kezdődnie, `n` és a (z) számnak kell lennie (például: `nThings` ).

# <a name="examples"></a>[Példák](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Felhasználó által definiált típus, névvel ellátott elemek ###

A felhasználó által definiált típusokban megnevezett elemek neveként kell nevezni `CamelCase` , még a UDT konstruktorok számára is.
Ez segít az elnevezett elemek egyértelmű elkülönítésében a helyileg hatókörön belüli változókra mutató hivatkozásokkal a hozzáférési jelölés (például: `callable::Apply` ) vagy a másolási és frissítési jelölés ( `set arr w/= Data <- newData` ) használatakor.

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- A UDT konstruktorokban megnevezett elemek neveként kell nevezni, `CamelCase` azaz kezdeti nagybetűvel kell kezdődnie.
- A műveletekhez feloldani megnevezett elemek művelet fázisként kell nevezni.
- A műveleteknek nem feloldható megnevezett elemeknek főnévi kifejezéseknek kell lenniük.
- A műveleteket UDT egyetlen elnevezett elemnek kell `Apply` definiálni.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Snippet | Leírás |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | A név `Apply` egy `CamelCase` formázott igei kifejezés, amely arra utal, hogy az elnevezett elem egy művelet. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Az elnevezett elemeknek kezdeti nagybetűvel kell kezdődnie. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | A függvények feloldására szolgáló névvel ellátott elemeknek főnévi kifejezéseknek kell lenniük, nem pedig ige kifejezéseknek. |

***

## <a name="input-conventions"></a>Bemeneti konvenciók ##

Amikor egy fejlesztő meghívja a műveletet vagy a függvényt, az adott művelethez vagy függvényhez tartozó különböző bemeneteket egy adott sorrendben kell megadnia, ami növeli a fejlesztők által felhasználható kognitív terhelést, hogy használhassa a kódtárat.
A bemeneti sorrendek megemlékezésének feladata különösen az, ha a feladatból gyakran elkerülnek a következők: egy kvantum-algoritmus megvalósításának programozása.
Bár a gazdag IDE-támogatás nagy mértékben csökkentheti ezt a megoldást, a jó tervezés és a közös konvenciók betartása is segítheti az API-k által kiszabott kognitív terhelés minimalizálását.

Ahol lehetséges, hasznos lehet csökkenteni a művelet vagy a függvény által várt bemenetek számát, így az egyes bemenetek szerepe azonnal nyilvánvalóvá válik az adott művelethez vagy függvényhez tartozó fejlesztők számára, valamint a programkódot később olvasó fejlesztők számára.
Különösen, ha nem lehetséges vagy ésszerű az argumentumok számának csökkentése egy művelet vagy függvény számára, fontos, hogy konzisztens megrendelés álljon rendelkezésre, amely minimalizálja azt a meglepetést, amelyet a felhasználó a bemenetek sorrendjének előrejelzése során szembesül.

Javasoljuk, hogy olyan bemeneti rendezési konvenciókat ajánlunk, amelyek nagyrészt az f (x, y) ≡ f (x) (y).
Ezért az első argumentumok részleges alkalmazása olyan meghívót eredményezhet, amely a saját jogon hasznos, ha ésszerű.
Ezt az elvet követve érdemes lehet a következő argumentumokat használni:

- Klasszikus, nem hívható argumentumok, például szögek, hatáskörök vektorai stb.
- Hívható argumentumok (függvények és argumentumok).
  Ha a functions és a Operations is argumentumként van megadva, érdemes lehet műveleteket végrehajtani a függvények után.
- A gyűjtemények a,, és rendszerhez hasonló módon, meghívásos argumentumok alapján jártak el `Map` `Iter` `Enumerate` `Fold` .
- A vezérlőkként használt Qubit argumentumok.
- Qubit használt argumentumok.

Vegye fontolóra egy olyan művelet használatát, amellyel a `ApplyPhaseEstimationIteration` fázis becslése egy szöget és egy Oracle-t vesz igénybe, és a szöget átadja a `Rz` különböző skálázási tényezők tömbje által módosítottnak, majd az Oracle alkalmazásait vezérli.
A bemeneteket a következő módon kell megrendelni `ApplyPhaseEstimationIteration` :

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
A kis-és nagybetűk minimálisra csökkentése érdekében egyes függvények és műveletek a beépített és a rendszer működését utánozzák `Adjoint` `Controlled` .
`ControlledOnInt<'T>` `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` Ilyen például a típus, amely a következőhöz hasonló módon viselkedik:, `ControlledOnInt<Qubit[]>(5, _)` `Controlled` de abban a feltétellel, hogy a vezérlő regisztrálása a $ \ket {5} = \ket $ állapotot jelöli {101} .
Így a fejlesztő azt várja, hogy a `ControlledOnInt` meghívót a legutóbb átalakított értékre helyezze át, és hogy az eredményül kapott művelet a bemeneti---ugyanolyan sorrendben legyen, mint az ellátottak `(Qubit[], 'T)` kimenete `Controlled` .

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- A részleges alkalmazás használatával összhangban lévő bemeneti sorrendek használata.
- Beépített feladatokkal konzisztens bemeneti sorrendek használata.
- Helyezzen minden klasszikus bemenetet a kvantum-bevitel előtt.

# <a name="examples"></a>[Példák](#tab/examples)

***

## <a name="documentation-conventions"></a>Dokumentációs konvenciók ##

A Q# nyelv lehetővé teszi a dokumentáció csatolását a műveletekhez, a függvényekhez és a felhasználó által definiált típusokhoz a speciálisan formázott dokumentációs megjegyzések használatával.
A Triple-ferde ( `///` ) függvényekkel ezek a dokumentációs megjegyzések kisméretű, [DocFX Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) dokumentumok, amelyek az egyes műveletek, függvények és felhasználó által definiált típusok, valamint a várt bemeneti adatok céljának leírására használhatók.
A Quantum Development Kit által biztosított fordító kibontja ezeket a megjegyzéseket, és a segítségével a következőhöz hasonló dokumentációt videótartalmakban https://docs.microsoft.com/quantum .
Hasonlóképpen, a Quantum Development Kit által biztosított nyelvi kiszolgáló ezeket a megjegyzéseket használja, hogy segítséget nyújtson a felhasználóknak a kódban lévő szimbólumok fölé helyezve Q# .
A dokumentációs megjegyzések használata így segítheti a felhasználókat a kód értelmezésében azáltal, hogy a jelen dokumentum többi konvenciója alapján nem könnyen elérhetővé tett részletekre vonatkozó hasznos hivatkozást biztosítanak.

> [!div class="nextstepaction"]
> [Dokumentációs Megjegyzés szintaxisának leírása](xref:microsoft.quantum.guide.filestructure#documentation-comments).

Ahhoz, hogy hatékonyan használhassa ezt a funkciót a felhasználók számára, javasoljuk, hogy a dokumentációs megjegyzések írásakor ne feledje el néhány dolgot.

# <a name="guidance"></a>[Útmutató](#tab/guidance)

Javasoljuk, hogy:

- Minden nyilvános funkciót, műveletet és felhasználó által definiált típust közvetlenül a dokumentációs Megjegyzés előtt kell megadni.
- Az egyes dokumentációs megjegyzéseknek legalább a következő részeket kell tartalmazniuk:
    - Összefoglalás
    - Input (Bemenet)
    - Kimenet (ha van ilyen)
- Győződjön meg arról, hogy minden összefoglaló két mondat vagy kevesebb. Ha további helyiségre van szükség, adjon meg egy szakaszt, amely `# Description` azonnal követi a `# Summary` teljes részleteket.
- Ahol ésszerű, ne szerepeljenek a matematika az összefoglalókban, mivel nem minden ügyfél támogatja a TeX-jelöléseket az összefoglalók között. Vegye figyelembe, hogy a prózai dokumentumok (például a TeX vagy a Markdown) írásakor érdemes lehet hosszabb vonali hosszúságot használni.
- Adja meg az összes releváns matematikai kifejezést a `# Description` szakaszban.
- A bemenetek leírásakor ne ismételje meg az egyes bemenetek típusait, mivel ezek a fordító számára következtetni tudnak, és az inkonzisztencia bevezetését kockáztatják.
- Szükség szerint adjon meg példákat a saját `# Example` szakaszában.
- A kód listázása előtt röviden ismertesse az egyes példákat.
- Sorolja fel az összes releváns tanulmányi kiadványt (például: dokumentumok, eljárások, blogbejegyzések és alternatív implementációk) a `# References` szakaszokban a hivatkozások felsorolásával.
- Győződjön meg arról, hogy ha lehetséges, az összes hivatkozási hivatkozás állandó és megváltoztathatatlan azonosítók (DOIs vagy verziószámmal ellátott arXiv-számok).
- Ha egy művelet vagy függvény más műveletekhez vagy függvényekhez kapcsolódik, és az esetlegesen előforduló változatok is szerepelnek, a szakaszokban listajelként sorolja fel a többi változatot `# See Also` .
- Hagyjon üres megjegyzést a Level-1 ( `/// #` ) szakaszban, de ne hagyjon üres vonalat a 2. szint ( `/// ##` ) szakaszban.

# <a name="examples"></a>[Példák](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Formázási konvenciók ##

Az előző javaslatok mellett hasznos lehet a kód a lehető legkönnyebben felismerhetővé tétele a konzisztens formázási szabályok használatához.
A természet szerinti formázási szabályok általában némileg önkényesak és szigorúan személyes esztétikai jellegűek.
Ugyanakkor javasolt a formázási konvenciók egységes csoportjának fenntartása a közreműködők csoportjain belül, és különösen a nagy Q# projektek, például a Quantum Development Kit esetében.
Ezek a szabályok automatikusan alkalmazhatók a fordítóval integrált formázó eszköz használatával Q# .

# <a name="guidance"></a>[Útmutató](#tab/guidance) 

Javasoljuk, hogy:

- A hordozhatósághoz tabulátorok helyett négy szóközt használjon.
  Például a VS Code-ban:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- A sortörés 79 karakternél, ahol ésszerű.
- Használjon szóközöket a bináris operátorok köré.
- Használjon szóközöket a típushoz tartozó kettőspontok egyik oldalán.
- A tömbben és a rekordokban lévő literálokban (például a functions és a Operations műveletekben) használt vesszők után egyetlen helyet használjon.
- Ne használjon szóközt a függvény, a művelet vagy a UDT neve után, vagy a `@` in attribútum deklarációja után.
- Minden attribútum deklarációjának saját sorban kell lennie.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Snippet | Leírás |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Használjon szóközöket a bináris operátorok köré. |
| ☒ | <s>`target:Qubit`</s> | Használjon szóközt a típus megjegyzési kettőspontok használatával. |
| ☑ | `Example(a, b, c)` | A bemeneti rekordban lévő elemek megfelelően vannak elfoglalva az olvashatóság érdekében. |
| ☒ | <s>`Example (a, b, c)`</s> | A szóközöket a függvény, a művelet vagy a UDT neve után le kell tiltani. |

***
