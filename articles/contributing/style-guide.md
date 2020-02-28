---
title: 'Microsoft Q # Style útmutató'
description: 'A Q # programok és könyvtárak elnevezési, bemeneti, dokumentációs és formázási konvencióinak megismerése.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 3c8e432378ec563a197a5b87000c3e90cadb8e18
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907443"
---
# <a name="q-style-guide"></a>Q # Style útmutató #
## <a name="general-conventions"></a>Általános konvenciók ##

Az ebben az útmutatóban javasolt konvenciók célja, hogy a Q # könnyebben olvasható és értelmezhető programokat és kódtárakat segítse.

## <a name="guidance"></a>Útmutatás

Javasoljuk, hogy:

- Soha ne hagyja figyelmen kívül az egyezményt, hacsak nem ezt szándékosan teszi, hogy könnyebben olvasható és értelmezhető kódot nyújtson a felhasználók számára.

## <a name="naming-conventions"></a>Elnevezési konvenciók ##

A Quantum Development Kit szolgáltatásban a függvény-és műveleti nevekre törekszünk, amelyek segítenek a kvantum-fejlesztőknek olyan programok írásához, amelyek könnyen olvashatóak, és a lehető legkevesebb meglepetést okozzák.
Fontos része annak, hogy ha a függvények, műveletek és típusok neveit választjuk, a programozók a Quantum fogalmak kifejezéséhez használt *szókincset* hoznak létre. a választásunk során segítünk vagy meggátoljuk őket abban, hogy világosan kommunikáljanak.
Ez felelősséget vállal a számunkra, hogy megbizonyosodjon róla, hogy az általunk bevezetett nevek egyértelműek és nem homályosak.
Ebben a szakaszban részletesen ismertetjük, hogyan teljesítjük ezt a kötelezettséget olyan explicit útmutatás szempontjából, amely segít a legjobb megoldás a Q # fejlesztői közösség számára.

### <a name="operations-and-functions"></a>Műveletek és függvények ###

Az egyik első dolog, amit a névnek meg kell állapítania, hogy egy adott szimbólum függvényt vagy műveletet jelöl.
A függvények és a műveletek közötti különbség elengedhetetlen a kód egy blokkjának megismeréséhez.
A függvények és a műveletek a felhasználók közötti megkülönböztetésének közléséhez a Q # modellek kvantum-műveleteire támaszkodunk a mellékhatások használatával.
*Ez egy művelet végrehajtása* .

Ezzel szemben a függvények leírják az adatok közötti matematikai kapcsolatokat.
A `Sin(PI() / 2.0)` kifejezés `1.0`, és semmit *sem jelent a* program vagy a qubits állapotával kapcsolatban.

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
A `ApplyIf`, a `ApplyToEach`és a `ApplyToFirst`esetében a `Apply`művelet használatát javasoljuk.
Ebben az esetben más műveletek is hasznosak lehetnek, mint a `IterateThroughCartesianPower`.

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
A `ControlledOnInt` például a "vezérlő" művelet "vezérlőelem" kifejezésének "a" kifejezést használja annak jelzésére, hogy a függvény melléknévként viselkedik az argumentumának módosításához.
Ennek a névnek a további előnye, hogy a beépített `Controlled`-inaktívnak megfelelő szemantikai feltételnek felel meg, ahogy azt az alábbiakban tárgyaljuk.
Hasonlóképpen, az _ügynökök_ nevei a függvények és a UDT nevéből is felhasználhatók a műveleti nevekből, ahogy a neve `Encoder` a `Encode`hoz szorosan társított UDT esetében.

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- Műveletek neveihez használjon műveleteket.
- Nevek vagy melléknevek használata a függvények neveihez.
- A felhasználó által definiált típusokhoz és attribútumokhoz tartozó nevek használata.
- Az összes hívható név esetén a `CamelCase` erős preferencia alapján `pascalCase`, `snake_case`vagy `ANGRY_CASE`. Különösen ügyeljen arra, hogy a hívható nevek nagybetűvel kezdődjön.
- Az összes helyi változó esetében a `pascalCase` erős preferencia használatával `CamelCase`, `snake_case`vagy `ANGRY_CASE`. Különösen ügyeljen arra, hogy a helyi változók kisbetűkkel kezdődjön.
- Az aláhúzások használatának elkerülése a függvények és a műveletek neveiben `_` Ha további hierarchiára van szükség, használja a névtereket és a névterek aliasait.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Name (Név) | Leírás |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | A művelet hatásának jelzéséhez törölje a műveletet ("tükrözze"). |
| ☒ | <s>`operation XRotation`</s> | A főnévi kifejezés a művelet helyett a függvényt javasolja. |
| ☒ | <s>`operation search_oracle`</s> | `snake_case` ellentétes Q # jelölés használata. |
| ☒ | <s>`operation Search_Oracle`</s> | A belső és a műveleti név közötti aláhúzás használata a Q # jelöléssel ellentétes. |
| ☑ | `function StatePreparationOracle` | A főnévi kifejezés használata azt sugallja, hogy a függvény egy műveletet ad vissza. |
| ☑ | `function EqualityFact` | A főnév ("Fact") egyértelmű használata annak jelzésére, hogy ez egy függvény, míg a melléknév. |
| ☒ | <s>`function GetRotationAngles`</s> | Az ige ("Get") használata azt jelzi, hogy ez egy művelet. |
| ☑ | `newtype GeneratorTerm` | A főnévi kifejezés használata egyértelműen a UDT konstruktor hívásának eredményét jelenti. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | A ige kifejezés használata azt sugallja, hogy a UDT konstruktora egy művelet. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | A főnévi kifejezés használata az attribútum használatát közli. |

***

### <a name="shorthand-and-abbreviations"></a>Rövidítések és rövidítések ###

A fenti tanácsokban a Gyorsírás számos formája létezik, amely a kvantum-számítástechnika általános és átható használatát látja el.
Javasoljuk, hogy meglévő és közös gyorsírást használjon, ahol létezik, különösen olyan műveletek esetén, amelyek a célszámítógép működéséhez tartoznak.
Például a `ApplyX`helyett `X` nevet választjuk, `RotateAboutZ`helyett pedig `Rz`.
Az ilyen rövidítések használatakor a művelet neve csak nagybetűs lehet (például: `MAJ`).

Erre az egyezményre akkor van szükség, ha gyakran használt betűszók és nagybetűk, például "QFT" a "Quantum Fourier átalakítás" kifejezésre alkalmazzák.
Javasoljuk, hogy az általános .NET-konvenciókat a betűszók és a nagyszótárak teljes névben való használatára ajánljuk, amely az alábbiakat írja elő:

- a kétbetűs mozaikszavak és a nagyvállalatok neve nagybetűs (pl.: `BE` a "big-endian" esetében),
- minden további betűszó és nagybetűk neve `CamelCase` (például: `Qft` a "Quantum Fourier Transform")

Ennek megfelelően a QFT megvalósító művelet vagy `QFT` lehet gyorsírásként, vagy `ApplyQft`ként kiírva.

A gyakran használt műveletek és függvények esetében érdemes lehet egy rövidített nevet megadni egy hosszú űrlap _aliasként_ való megadásához:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- Ha szükséges, tekintse meg a gyakran elfogadott és széles körben használt rövidített neveket.
- Kis-és nagybetűk használata a gyorsíráshoz.
- Rövid (kétbetűs) betűszók és nagybetűk használata.
- A hosszabb (három vagy több betűs) betűszók és a nagybetűk használatát `CamelCase` használhatja.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Name (Név) | Leírás |
|---|------|-------------|
| ☑ | `X` | Jól ismert Gyorsírás a "$X $ átalakítás alkalmazása" |
| ☑ | `CNOT` | Jól értelmezhető Gyorsírás a "vezérelt – nem" |
| ☒ | <s>`Cnot`</s> | A Gyorsírás nem lehet `CamelCase`ban. |
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
Ebben az esetben az "Fredkin" és a "Toffoli" műveletet gyakran nevezik a tudományos irodalomban, de a Q # elsődlegesen a `CSWAP` és `CCNOT`.
Az API-dokumentációs megjegyzések mindkét esetben a megfelelő neveken alapuló szinonimákat biztosítanak az összes megfelelő hivatkozással együtt.

Ez a beállítás különösen fontos, mivel a megfelelő főnevek bizonyos használata mindig szükséges: a Q # a számos klasszikus nyelv által meghatározott hagyományt követi, és a logikai logikára hivatkozó `Bool` típusokra hivatkozik, amely a George Boole tiszteletben tartásával van elnevezve.
Ehhez hasonló módon kell elnevezni néhány kvantum-fogalmat, például a Q # nyelvhez beépített `Pauli` típust.
A megfelelő főnevek használatának minimalizálása, ha az ilyen használat nem alapvető fontosságú, csökkentik annak a hatását, hogy a megfelelő földrajzi nevek ne legyenek ésszerűen elkerülhetők.

# <a name="guidance"></a>[Útmutatás](#tab/guidance) 

Javasoljuk, hogy:

- Kerülje a nevekben a megfelelő nevek használatát.

# <a name="examples"></a>[Példák](#tab/examples)

***

### <a name="type-conversions"></a>Típus konverziója ###

Mivel a Q # egy erősen és statikusan beírt nyelv, az egyik típusú érték csak egy másik típusú értékként használható egy típus-átalakítási függvény kifejezett hívásával.
Ez ellentétben áll azokkal a nyelvekkel, amelyek lehetővé teszik, hogy az értékek implicit módon módosítsák a típusokat (pl.: Type Promotion) vagy a casting használatával.
Ennek eredményeképpen az átalakítási függvények fontos szerepet játszanak a Q # könyvtár fejlesztésében, és az elnevezéssel kapcsolatban leggyakrabban felmerülő döntések egyikét alkotják.
Azonban ez azt jelzi, hogy mivel a Type konverziók mindig _determinisztikus_, a függvények is megírhatók, ezért a fenti tanács alá tartoznak.
Különösen azt javasoljuk, hogy a Type Conversion functions soha ne legyen elnevezve műveletként (pl.: `ConvertToX`) vagy a határozószók előírási kifejezésekkel (`ToX`), hanem a forrás-és a rendeltetési típusokat (`XAsY`) jelző, melléknévi előírási kifejezéseknek kell nevezni.
A típus átalakítási függvények neveiben szereplő tömb típusok listázásakor ajánlott a Gyorsírás `Arr`.
A kivételes körülmények korlátozásával azt javasoljuk, hogy az összes típus-átalakítási függvényt `As` használatával lehessen elnevezni, hogy gyorsan azonosíthatóak legyenek.

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- Ha egy függvény `X` típusú értéket konvertál `Y`típusú értékre, használja a `AsY` vagy a `XAsY`nevet.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Name (Név) | Leírás |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | A "to" utasítás a művelethez tartozó kifejezést eredményez, és nem függvényt jelez. |
| ☒ | <s>`AsDouble`</s> | A bemeneti típus nem egyértelmű a függvény nevéből. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | A bemeneti és a kimeneti típusok nem megfelelő sorrendben jelennek meg. |
| ☑ | `ResultArrAsBoolArr` | A bemeneti típusok és a kimeneti típusok egyaránt törlődnek. |

***

### <a name="private-or-internal-names"></a>Magán-vagy belső nevek ###

Sok esetben a név kifejezetten a belső könyvtárakhoz vagy projektekhez való használatra szolgál, és nem a könyvtár által kínált API garantált részét képezi.
Hasznos lehet egyértelműen jelezni, hogy ez a helyzet az elnevezési függvények és műveletek esetében, hogy a csak belső kódok véletlen függőségei legyenek egyértelműek.
Ha egy művelet vagy függvény nem közvetlen használatra készült, hanem egy, a részleges alkalmazás által elvégezhető egyező meghívónak kell használnia, érdemes lehet olyan nevet használni, amely a részben alkalmazott hívható `_`.

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- Ha egy függvény, művelet vagy felhasználó által definiált típus nem része a Q # függvénytárának vagy programjának a nyilvános API-nak, akkor győződjön meg arról, hogy a neve kezdő aláhúzással (`_`) kezdődik.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Name (Név) | Leírás |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | Az aláhúzás `_` nem szerepelhet a név végén. |
| ☑ | `_ApplyDecomposedOperation` | Az aláhúzás `_` az elején egyértelműen azt jelzi, hogy ez a művelet csak belső használatra szolgál. |

***

### <a name="variants"></a>Változatok ###

Bár ez a korlátozás nem szűnik meg a Q # jövőbeli verzióiban, jelenleg a kapcsolódó műveletek vagy függvények olyan csoportjai lesznek, amelyek megkülönböztetni egymástól a bemenők által támogatott, illetve az argumentumok konkrét típusait.
Ezek a csoportok megkülönböztetni ugyanazt a legfelső szintű nevet, majd egy vagy két betűt, amelyek jelzik a változatát.

| Utótag | Jelentés |
|--------|---------|
| `A` | A `Adjoint` támogatásához szükséges bemenet |
| `C` | A `Controlled` támogatásához szükséges bemenet |
| `CA` | A `Controlled` és `Adjoint` támogatásához szükséges bemenet |
| `I` | A bemenet vagy bemenet típusa `Int` |
| `D` | A bemenet vagy bemenet típusa `Double` |
| `L` | A bemenet vagy bemenet típusa `BigInt` |

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- Ha egy függvény vagy művelet nem kapcsolódik hasonló funkciókhoz vagy műveletekhez a bemenetek típusai és a nem megfelelő működésének támogatásával, ne használjon utótagot.
- Ha egy függvény vagy művelet bármely hasonló függvényhez vagy művelethez kapcsolódik, és a bemenetek típusai és az azokon lévők is támogatják, a változatok megkülönböztetéséhez használja a fenti táblázatban szereplő utótagokat.

# <a name="examples"></a>[Példák](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumentumok és változók ###

Egy függvény vagy művelet Q # kódjának fő célja, hogy könnyen olvasható és értelmezhető legyen.
Hasonlóképpen, a bemenetek és a Type argumentumok neveinek kell megadniuk, hogy a rendszer hogyan használja a függvényt vagy az argumentumot.


# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- A változó és a bemeneti nevek esetében a `pascalCase` erős preferencia használatával `CamelCase`, `snake_case`vagy `ANGRY_CASE`.
- A bemeneti névnek leírónak kell lennie. lehetőleg ne adjon meg egy vagy két betűt.
- A pontosan egy típusú argumentumot elfogadó műveletek és függvények a típus argumentumát `T`, ha a szerepköre nyilvánvaló.
- Ha egy függvény vagy művelet több típusú argumentumot is igénybe vesz, vagy ha egy adott típusú argumentum szerepköre nem egyértelmű, érdemes lehet egy rövid, `T` (például: `TOutput`) típusú tőkésített szót használni az egyes típusokhoz.
- Az argumentumban és a változók neveiben ne szerepeljenek a nevek. ezt az információt a fejlesztési környezetnek is meg kell adni.
- A skaláris típusokat a literális nevük szerint (`flagQubit`), a tömböket pedig többes szám (`measResults`) alapján jelöli.
  A qubits esetében érdemes megfontolni az ilyen típusok jelölését `Register`, ha a név olyan qubits-sorozatra hivatkozik, amely valamilyen módon szorosan összefügg egymással.
- A tömbökben indexként használt változóknak `idx` kell kezdődnie, és csak számnak kell lennie (például: `things[idxThing]`).
  Különösen érdemes elkerülni az egybetűs változók nevének indexként való használatát. legalább a `idx`t kell használnia.
- A tömbök hosszának tárolására használt változóknak `n` kell kezdődnie, és a következőnek kell lennie: (például `nThings`).

# <a name="examples"></a>[Példák](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>A felhasználó által definiált típusú elemek neve ###

A felhasználó által definiált típusok elnevezett elemeinek `CamelCase`nak kell lenniük, még a UDT konstruktorok bemenetében is.
Ez segít az elnevezett elemek egyértelmű elkülönítésében a helyileg hatókörön belüli változókra mutató hivatkozásokon, ha a hozzáférési jelölést (például: `callable::Apply`) vagy a másolás és frissítés jelölését (`set arr w/= Data <- newData`) használja.

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- A UDT konstruktorokban megnevezett elemek neve `CamelCase`; tehát a kezdeti nagybetűvel kell kezdődnie.
- A műveletekhez feloldani megnevezett elemek művelet fázisként kell nevezni.
- A műveleteknek nem feloldható megnevezett elemeknek főnévi kifejezéseknek kell lenniük.
- A műveleteket UDT egy `Apply` nevű, egyetlen névvel ellátott elemnek kell definiálni.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Részlet | Leírás |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | A `Apply` neve `CamelCase`formázott kifejezés, amely arra utal, hogy az elnevezett elem egy művelet. |
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
- A gyűjtemények a meghívásos argumentumok alapján `Map`, `Iter`, `Enumerate`és `Fold`hoz hasonló módon jártak el.
- A vezérlőkként használt Qubit argumentumok.
- Qubit használt argumentumok.

Vegye fontolóra egy művelet `ApplyPhaseEstimationIteration` a fázis-becslésben való használathoz, amely egy szöget és egy Oracle-t használ, átadja a szöget úgy, hogy a különböző skálázási tényezők tömbje `Rz` módosítsa, majd az Oracle alkalmazásait vezérli.
A bemeneteket a következő módon `ApplyPhaseEstimationIteration`juk:

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
A kis-és nagybetűk minimálisra csökkentése érdekében egyes függvények és műveletek a beépített elhasználók viselkedését utánozzák `Adjoint` és `Controlled`.
A `ControlledOnInt<'T>` például `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`típust tartalmaz, így a `ControlledOnInt<Qubit[]>(5, _)` például a `Controlled`-kezelőhöz hasonlóan viselkedik, de a vezérlő regisztrálása a \ket{5} = \ket{101}$ állapotot jelöli.
Így a fejlesztő azt várja, hogy a `ControlledOnInt` helyezze át a meghívót az utolsó értékre, és hogy az eredményül kapott művelet ugyanolyan sorrendben legyen, mint a bemeneti `(Qubit[], 'T)`---, ahogyan az a `Controlled`-futtató kimenete.

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- A részleges alkalmazás használatával összhangban lévő bemeneti sorrendek használata.
- Beépített feladatokkal konzisztens bemeneti sorrendek használata.
- Helyezzen minden klasszikus bemenetet a kvantum-bevitel előtt.

# <a name="examples"></a>[Példák](#tab/examples)

***

## <a name="documentation-conventions"></a>Dokumentációs konvenciók ##

A Q # nyelv lehetővé teszi a dokumentáció csatolását a műveletekhez, a függvényekhez és a felhasználó által definiált típusokhoz a speciálisan formázott dokumentációs megjegyzések használatával.
A Triple-perjel (`///`) által megjelenített megjegyzések olyan kis [DocFX-stílusú Markdown-](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) dokumentumok, amelyek az egyes műveletek, függvények és felhasználó által definiált típusok, valamint a várt bemeneti adatok céljának leírására használhatók.
A Quantum Development Kit által biztosított fordító kibontja ezeket a megjegyzéseket, és felhasználja őket a https://docs.microsoft.com/quantumhoz hasonló dokumentációk videótartalmakban.
Hasonlóképpen, a Quantum Development Kit által biztosított nyelvi kiszolgáló ezeket a megjegyzéseket használja, hogy segítséget nyújtson a felhasználóknak a Q # kódjában lévő szimbólumok fölé helyezve.
A dokumentációs megjegyzések használata így segítheti a felhasználókat a kód értelmezésében azáltal, hogy a jelen dokumentum többi konvenciója alapján nem könnyen elérhetővé tett részletekre vonatkozó hasznos hivatkozást biztosítanak.

<div class="nextstepaction">
    [Dokumentációs Megjegyzés szintaxisának hivatkozása](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

Ahhoz, hogy hatékonyan használhassa ezt a funkciót a felhasználók számára, javasoljuk, hogy a dokumentációs megjegyzések írásakor ne feledje el néhány dolgot.

# <a name="guidance"></a>[Útmutatás](#tab/guidance)

Javasoljuk, hogy:

- Minden nyilvános funkciót, műveletet és felhasználó által definiált típust közvetlenül a dokumentációs Megjegyzés előtt kell megadni.
- Az egyes dokumentációs megjegyzéseknek legalább a következő részeket kell tartalmazniuk:
    - Összegzés
    - Input (Bemenet)
    - Kimenet (ha van ilyen)
- Győződjön meg arról, hogy minden összefoglaló két mondat vagy kevesebb. Ha további helyiségre van szükség, adjon meg egy `# Description` szakaszt közvetlenül a `# Summary` után, a teljes részletességgel.
- Ahol ésszerű, ne szerepeljenek a matematika az összefoglalókban, mivel nem minden ügyfél támogatja a TeX-jelöléseket az összefoglalók között. Vegye figyelembe, hogy a prózai dokumentumok (például a TeX vagy a Markdown) írásakor érdemes lehet hosszabb vonali hosszúságot használni.
- Adja meg az összes releváns matematikai kifejezést a `# Description` szakaszban.
- A bemenetek leírásakor ne ismételje meg az egyes bemenetek típusait, mivel ezek a fordító számára következtetni tudnak, és az inkonzisztencia bevezetését kockáztatják.
- Szükség szerint adjon meg példákat a saját `# Example` szakaszában.
- A kód listázása előtt röviden ismertesse az egyes példákat.
- Tekintse meg az összes releváns tanulmányi kiadványt (pl.: dokumentumok, eljárások, blogbejegyzések és alternatív implementációk) egy `# References` szakaszban a hivatkozások felsorolásával.
- Győződjön meg arról, hogy ha lehetséges, az összes hivatkozási hivatkozás állandó és megváltoztathatatlan azonosítók (DOIs vagy verziószámmal ellátott arXiv-számok).
- Ha egy művelet vagy függvény más műveletekhez vagy függvényekhez kapcsolódik, és az esetlegesen előforduló változatok vannak, akkor a `# See Also` szakaszban található felsorolásjelként sorolja fel a többi változatot.
- Hagyjon üres megjegyzést a Level-1 (`/// #`) szakaszban, de ne hagyjon üres vonalat a 2. szintű (`/// ##`) szakaszban.

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
Ugyanakkor javasolt a formázási konvenciók egységes csoportjának fenntartása a közreműködők csoportjain belül, és különösen a nagy Q # projektekhez, például a Quantum Development Kit-hoz.
Ezek a szabályok automatikusan alkalmazhatók a Q # fordítóprogrammal integrált formázó eszköz használatával.

# <a name="guidance"></a>[Útmutatás](#tab/guidance) 

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
- Ne használjon szóközt a függvény, a művelet vagy a UDT neve után, vagy a `@` az attribútum deklarációjában.
- Minden attribútum deklarációjának saját sorban kell lennie.

# <a name="examples"></a>[Példák](#tab/examples)

|   | Részlet | Leírás |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Használjon szóközöket a bináris operátorok köré. |
| ☒ | <s>`target:Qubit`</s> | Használjon szóközt a típus megjegyzési kettőspontok használatával. |
| ☑ | `Example(a, b, c)` | A bemeneti rekordban lévő elemek megfelelően vannak elfoglalva az olvashatóság érdekében. |
| ☒ | <s>`Example (a, b, c)`</s> | A szóközöket a függvény, a művelet vagy a UDT neve után le kell tiltani. |

***

