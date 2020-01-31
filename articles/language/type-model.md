---
title: 'Q # Type Model | Microsoft Docs'
description: A Q#-modelltípus
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871634"
---
# <a name="the-type-model"></a>A típus modellje

Ez a szakasz a Q # type modellt ismerteti, és leírja a típusok megadásának és használatának szintaxisát.
Fontos megjegyezni, hogy a Q # egy *erősen gépelt* nyelv, így az ilyen típusú alkalmazások körültekintő használata segíthet a fordítónak a q # programokkal kapcsolatos erős garanciák megadásában a fordítási idő alatt.

Ahhoz, hogy a lehető legerősebb garanciát nyújtson, a Q # típusok közötti konverziónak explicit módon kell megadnia az átalakítást kifejező függvények hívásait. Számos ilyen függvényt a <xref:microsoft.quantum.convert> névtér részeként biztosítunk.
A kompatibilis típusok egymásra való átadása implicit módon történik. 

A Q # egyszerű típusokat biztosít, amelyek közvetlenül is használhatók, és számos különböző módon hozhatók létre más típusú új típusok.
Ezeket a szakasz további részében ismertetjük.

## <a name="primitive-types"></a>Primitív típusok

A Q # nyelv számos *primitív típust*biztosít, amelyekből más típusok is létrehozhatók:

- A `Int` típus egy 64 bites előjeles egész számot jelöl, például: `2`, `107`, `-5`.
- A `BigInt` típus tetszőleges méretű aláírt egész számot jelöl, például `2L`, `107L`, `-5L`.
   Ez a típus a .NET-<xref:System.Numerics.BigInteger>on alapul.
   típusa.
- A `Double` típus egy kétszeres pontosságú lebegőpontos számot jelöl, például: `0.0`, `-1.3`, `4e-7`.
- A `Bool` típus olyan logikai értéket jelöl, amely lehet `true` vagy `false`.
- A `Qubit` típus a Quantum bitet vagy a qubit jelöli.
   `Qubit`s a felhasználó számára átlátszatlan; az egyetlen lehetséges művelet, amely nem egy másik műveletnek, hanem az identitás (egyenlőség) tesztelésére szolgál.
   Végső soron a `Qubit`s műveleteit a rendszer belső utasítások meghívásával valósítja meg a kvantum-processzoron (vagy annak szimulációján).
- A `Pauli` típus a négy egyqubites Pauli-operátor egyikét jelöli.
   Ez a típus az alapművelet elforgatására, valamint a megfigyelhető mérések megadására szolgál.
   Ez egy enumerált típus, amely négy lehetséges értékkel rendelkezik: `PauliI`, `PauliX`, `PauliY`és `PauliZ`, amely `Pauli`típusú konstansok.
- A `Result` típus a mérték eredményét jelöli.
   Ez egy enumerált típus, amely két lehetséges értékkel rendelkezik: `One` és `Zero`, amelyek `Result`típusú konstansok.
   `Zero` azt jelzi, hogy a + 1 sajátérték mérése megtörténik; `One` az-1 sajátérték jelöli.
- A `Range` típus az egész számokból álló sorozatot jelöli, amelyet a `start..step..stop`jelöl, amelyben a lépés a következő: beállítások. 
   Ez `start .. stop` megfelel a `start..1..stop`nak, és például `1..2..7` a $\{1, 3, 5, 7\}$ sorozatot jelöli.
- A `String` típus olyan Unicode-karakterekből álló sor, amely a felhasználó számára a létrehozás után átlátszatlan.
  Ez a típus egy klasszikus gazdagép üzeneteinek jelentésére szolgál hiba vagy diagnosztikai esemény esetén.
- A `Unit` típus az a típus, amely csak egy értéket engedélyez `()`. 
  Ez a típus azt jelzi, hogy a Q # függvény vagy művelet nem ad vissza információt. 

Az állandók `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`és `Zero` a Q # összes fenntartott szimbóluma.

## <a name="array-types"></a>Tömbök típusai

Bármely érvényes Q # típus `'T`, amely egy `'T`típusú értékek tömbjét jelöli.
Ez a tömb típusa `'T[]`; például `Qubit[]` vagy `Int[][]`.
Az egész számok gyűjteménye például `Int[]`, a `(Bool, Pauli)` értékek tömbje pedig `(Bool, Pauli)[][]`t jelöl.

A második példában látható, hogy ez a tömbök potenciálisan szaggatott tömbjét jelöli, nem pedig egy téglalap alakú kétdimenziós tömböt.
A Q # nem nyújt támogatást a négyszögletes többdimenziós tömbökhöz.

A tömb értékét Q # forráskódban lehet megírni, ha szögletes zárójeleket használ egy tömb elemei körül, ahogy az `[PauliI, PauliX, PauliY, PauliZ]`.
A tömb literál típusát a tömbben lévő összes elem közös alaptípusa határozza meg. 

> [!WARNING]
> Egy tömb elemei nem módosíthatók a tömb létrehozása után.
> Módosított tömb létrehozásához a frissítés és az ismételt hozzárendelés utasítások és/vagy a másolási és frissítési kifejezések használhatók.

Azt is megteheti, hogy létrehoz egy tömböt a méretétől a `new` kulcsszó használatával:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Mindkét esetben a tömb kiépítése után a `Length` fő funkciója használható az elemek számának `Int`ként való beszerzéséhez.
A tömböket szögletes zárójelek használatával lehet előírni, és az alszkriptek `Int` vagy Type `Range`típussal rendelkeznek, hogy a tömb elemeinek egy részhalmazát tartalmazó egyetlen elemet vagy új tömböket szerezzenek be.
A tömbök alszkriptje nulla-alapú:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Rekord típusok

Megadott nulla vagy több különböző típus `T0`, `T1`,..., `Tn`, egy új *rekord típust* jelölünk `(T0, T1, ..., Tn)`ként.
Az új bejegyzéstípus létrehozásához használt típusok maguk is rekordok, mint a `(Int, (Qubit, Qubit))`.
Az ilyen beágyazás mindig véges, azonban a rekord típusú típusok semmilyen körülmények között nem tartalmazhatják magukat.

Az új rekord típusának értékeit a rekordban lévő egyes típusok értékeinek rekordok alkotják.
A `(3, false)` például egy olyan rekord, amelynek típusa a rekord típusa `(Int, Bool)`.
A rekordok, a rekordok, a rekordok és az alrekordokok tömbje is létrehozható.

A Q # 0,3 esetében `Unit` az üres rekord *típusának* neve; az üres rekord *értékéhez*`()` van használatban.

A rekordos példányok nem változtathatók meg.
A Q # nem biztosít olyan mechanizmust, amely a létrehozott rekord tartalmának módosítását végzi.

A rekordok hatékony koncepciót használ a Q #-ban az értékek egyetlen értékkel való összegyűjtéséhez, így könnyebben átadhatja őket.
A rekordos jelölések használatával kifejezhető, hogy minden művelet és a hívó pontosan egy bemenetet fogad, és pontosan egy kimenetet ad vissza.

### <a name="singleton-tuple-equivalence"></a>Egyszeres rekord egyenértékűsége

Létre lehet hozni egy egyelemes (Single-Element) rekordot, `('T1)`, például `(5)` vagy `([1,2,3])`.
A Q # azonban egy egyszeres rekordot teljesen egyenértékűként kezel a befoglalt típus értékével.
Ez nem különbözik a `5` és a `(5)`között, illetve `5` és `(((5)))`között, illetve `(5, (6))` és `(5, 6)`között.

Ez az egyenértékűség minden célra érvényes, beleértve a hozzárendelést és a kifejezéseket is.
Éppen úgy írható, hogy `(5)+3` írni `5+3`, és mindkét kifejezés kiértékelése `8`ra történik.
Ez különösen azt jelenti, hogy egy olyan művelet vagy függvény, amelynek bemeneti vagy kimeneti rekordjának típusa egyetlen mező, egyetlen argumentumként vagy egyetlen érték visszaadása esetén lehet.

Ezt a tulajdonságot egy különálló _rekord egyenértékűségének_nevezzük.

## <a name="user-defined-types"></a>Felhasználó által definiált típusok

A Q #-fájlok meghatározhatnak egy olyan új névvel ellátott típust, amely bármely jogi típus egyetlen értékét tartalmazza.
Bármely rekord típusú `T`deklarálhat egy új, felhasználó által definiált típust, amely az `newtype` utasítással `T` altípusa.
A @"microsoft.quantum.math" névtérben például az összetett számok felhasználó által definiált típusként vannak meghatározva:

```qsharp
newtype Complex = (Double, Double);
```

Ez az utasítás egy új típust hoz létre, amelyben két, `Double`típusú névtelen elem szerepel.   
A névtelen elemektől eltekintve a felhasználó által definiált típusok az elnevezett elemeket is támogatják a Q # 0,7-es vagy újabb verziójával. Előfordulhat például, hogy elnevezte az `Re` elemet a következőhöz, amely egy összetett szám valódi részét jelöli, és `Im` a képzeletbeli részhez: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Egy felhasználó által definiált típus egyik elemének elnevezése nem jelenti azt, hogy minden elemet el kell nevezni – a nevesített és a névvel ellátott elemek bármely kombinációja támogatott. Emellett a belső elemek is megadhatók.
Az alább megadott típus `Nested` például egy alapul szolgáló típusú `(Double, (Int, String))`, amelyből csak `Int` típusú elemnek van neve, és minden más elem névtelen. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Az elnevezett elemek előnye, hogy közvetlenül a hozzáférési operátor `::`keresztül érhetők el. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

A névtelen elemek egymáshoz való eléréséhez először ki kell kinyerni a becsomagolt értéket a Postfix operátor `!`használatával.
A "kicsomagolás" operátor, `!`, lehetővé teszi a felhasználó által definiált típusban található értékek kinyerését.
A "kicsomagolás" kifejezés típusa a felhasználó által definiált típus alapjául szolgáló típus. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

A kicsomagolási operátor kicsomagolja pontosan a burkoló rétegét.
Több kibontható operátor is használható egy szorzáshoz burkolt érték eléréséhez.

Például:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

További részletekért tekintse meg a [kicsomagolási kifejezések](xref:microsoft.quantum.language.expressions#unwrap-expressions) és a [kezelők prioritása](xref:microsoft.quantum.language.expressions#operator-precedence) című szakaszt.

A felhasználó által definiált típus értékeit a megfelelő típusú konstruktor meghívásával lehet létrehozni:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Másik lehetőségként új értékeket is létrehozhat a meglévő [példányokból másolás és frissítés kifejezések](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)használatával. A tömbökhöz hasonlóan az ilyen kifejezések az eredeti kifejezés összes elemét is átmásolják, a megadott megnevezett elemek kivételével. Ezeknél az értékek a kifejezés jobb oldalán definiált értékekre vannak beállítva. Más nyelvi szerkezetek, például az [Update-and-reassign utasítások](xref:microsoft.quantum.language.statements#update-and-reassign-statement), amelyek tömb elemek számára elérhetők a felhasználó által definiált típusokban is.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

A felhasználó által definiált típusok bármely más típus használata esetén használhatók.
Egy felhasználó által definiált típus tömbjét lehet meghatározni, és egy felhasználó által definiált típust is felvenni egy rekord típusú elemként.

Nem lehet rekurzív típusú struktúrákat létrehozni.
A felhasználó által definiált típust definiáló típus nem lehet olyan rekord típusú, amely a felhasználó által definiált típus elemét tartalmazza.
A felhasználó által definiált típusok általában nem lehetnek ciklikus függőségek egymással, így a következő típusú definíciók érvénytelenek lesznek:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Amellett, hogy rövid aliasokat biztosít a potenciálisan bonyolult rekordokhoz, az ilyen típusú típusok egyik jelentős előnye, hogy dokumentálni tudja egy adott érték szándékát.
Ha visszatér a `Complex`re, az egyik felhasználó által definiált típusként is meghatározhatja a 2D poláris koordinátákat:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Annak ellenére, hogy mindkét `Complex` és `Polar` egyaránt rendelkezik egy alapul szolgáló típussal `(Double, Double)`, a két típus teljes mértékben inkompatibilis a Q #-ban, ami minimalizálja annak kockázatát, hogy véletlenül egy összetett matematikai függvényt hív meg a Polar koordinátákkal, és fordítva.
Így a felhasználó által definiált típusokhoz hasonló szerepkör tartozik, mint például a F# rekordok. 


## <a name="operation-and-function-types"></a>Művelet és függvények típusai

A Q # _művelet_ egy Quantum alrutin.
Vagyis meghívható rutinok, amelyek kvantumműveleteket tartalmaznak.

A Q # _függvény_ egy kvantum-algoritmuson belül használt klasszikus alrutin.
Előfordulhat, hogy klasszikus kódot tartalmaz, de nincs Quantum művelet.
A függvények nem foglalhatnak le vagy nem kölcsönözhetnek qubits, és nem hívhatnak meg műveleteket.
Azonban lehetséges, hogy át kell adni a műveleteket vagy a qubits a feldolgozáshoz.
A functions így teljes mértékben determinisztikus, és ugyanazokkal az argumentumokkal hívja meg ugyanazt az eredményt. 

A műveletek és a függvények együttes neve _callables_.  Alább néhány [példát](#examples) láthat.

Az összes Q # callables egyetlen értéket vesz fel bemenetként, és egyetlen értéket ad vissza kimenetként.
A bemeneti és a kimeneti értékek is rekordok.
Olyan Callables, amelyeknek nincs eredmény `Unit`.
Azok a Callables, amelyek nem rendelkeznek bemenettel, az üres rekordokat is be kell tölteni.

Bármely meghívható alaptípusa `('Tinput => 'Tresult)` vagy `('Tinput -> 'Tresult)`ként van írva, ahol a `'Tinput` és a `'Tresult` típus is.
A műveletekhez az első, `=>`tel rendelkező űrlap használatos. a függvényekhez tartozó második űrlap `->`.
A `((Qubit, Pauli) => Result)` például a lehetséges qubit mérési művelet aláírását jelöli.

A függvények típusát az aláírása teljesen megadja.
Egy adott szög szinuszát kiszámító függvénynek például a következő típusúnak kell lennie: `(Double -> Double)`.

Az Operations – de not functions – tartalmaz bizonyos további _jellemzőket_ , amelyek a művelet típusának részeként vannak kifejezve. Ezek a jellemzők a művelet által támogatott operációs rendszerekből származó információkat tartalmazzák.
A kiindulási műveletek olyan metaadatok, amelyek alapműveletek specializációját eredményezik; lásd [alább a](#functors)következőt:.

A műveleti típusokat a bemeneti típusuk, a kimeneti típusuk és azok jellemzői határozzák meg.    
Ahhoz, hogy a `Controlled` és/vagy `Adjoint` a művelet típusának támogatását igényli, hozzá kell adnia egy jegyzetet, amely a megfelelő tulajdonságokat jelzi.
A jegyzet `is Ctl` például azt jelzi, hogy a művelet ellenőrizhető. Ha szeretné megkövetelni, hogy egy adott típusú művelet támogassa a `Adjoint` és a `Controlled`-kezelőt is, ezt `(Qubit => Unit is Adj + Ctl)`ként is kifejezzük. A használatban lévő működés jellemzői `Adj` és `Ctl` szigorúan beszélő két előre definiált készlet, ahol minden címke egy adott működési jellemzőt jelez, például egy adott felhasználó támogatását.
Ezért a `+` a két készlet Uniójának jelölésére szolgál, és `*` a metszéspontot, azaz a mindkét halmazhoz közös címkéket jelöli.  

Például a Pauli `X` művelet típusa `(Qubit => Unit is Adj + Ctl)`.
Egy olyan Művelettípus, amely nem támogatja az egyiket sem, a bemeneti és a kimeneti típus szerint, külön megjegyzés nélkül adja meg.


### <a name="type-parameterized-functions-and-operations"></a>Type-paraméteres függvények és műveletek

A hívható típusok tartalmazhatnak típusú paramétereket.
A Type paramétereket egy adott idézőjel által előre meghatározott szimbólum jelöli. a `'A` például egy jogi típusparaméter.

Egy típusparaméter egynél többször is megjelenhet egyetlen aláírásban.
Például egy függvény, amely egy tömb egyes elemein egy másik függvényt alkalmaz, és az összegyűjtött eredményeket az aláírási `(('A[], 'A->'A) -> 'A[])`adja vissza.
Hasonlóképpen, egy függvény, amely két művelet összetételét adja vissza, lehet, hogy van aláírás `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.

A típus-paraméteres metódus hívásakor az azonos típusú paraméterrel rendelkező összes argumentumnak azonos típusúnak kell lennie.

A Q # nem biztosít olyan mechanizmust, amely lehetővé teszi a Type paraméterhez helyettesíthető lehetséges típusok korlátozását.

### <a name="type-compatibility"></a>Típus kompatibilitása

Egy olyan művelet, amelynél további felhasználók támogatottak, a rendszer bárhol használható egy kevesebb ellátott művelettel, de ugyanez az aláírás várható.
Előfordulhat például, hogy egy `(Qubit => Unit is Adj)` típusú művelet is használható, `(Qubit => Unit)` típusú művelettel.

A Q # a hívható visszatérési típusok tekintetében: egy olyan meghívót, amely egy típust ad vissza, `'A` kompatibilis ugyanazzal a bemeneti típussal és olyan eredmény típussal, amelyet a `'A` kompatibilis.

A Q # contravariant típusparamétert a bemeneti típusok tekintetében: egy meghívható, amely egy típust `'A` a bemenetnek, és kompatibilis egy ugyanazzal az eredménnyel, és egy olyan bemeneti típussal, amely kompatibilis a `'A`val.

Ez a következő definíciók miatt:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

a következők teljesülnek:

- A `ConjugateInvertWith` függvény a `Invert` vagy `ApplyUnitary``inner` argumentumával hívható meg.
- A `ConjugateUnitaryWith` függvény a `ApplyUnitary``inner` argumentumával hívható meg, de nem `Invert`.
- `(Qubit[] => Unit is Adj + Ctl)` típusú érték adható vissza `ConjugateInvertWith`ból.

> [!IMPORTANT]
> A Q # 0,3 jelentős eltérést mutat be a felhasználó által definiált típusok viselkedésében.

A felhasználó által definiált típusokat az alapul szolgáló típus burkolt verziójaként, nem pedig altípusként kezeli a rendszer.
Ez azt jelenti, hogy a felhasználó által definiált típus értéke nem használható, ha a rendszer az alapul szolgáló típus értékét várta.

### <a name="functors"></a>Működők

A Q # egy olyan gyár, amely új műveletet határoz meg egy másik műveletből.
Az új művelet megvalósításának meghatározásakor az üzemben lévők az alapművelet megvalósításához férnek hozzá.
Így a fellépők összetettebb funkciókkal rendelkezhetnek, mint a hagyományos magasabb szintű függvények.

A Q # Type rendszer nem rendelkezik képviselettel a következőben:. Ezért jelenleg nem lehet őket egy változóhoz kötni, vagy argumentumként átadni őket. 

A rendszer egy, a műveletre való alkalmazásával egy új műveletet ad vissza.
Például az `Adjoint`t futtató műveletnek a `Y` művelethez való alkalmazásának eredményét `Adjoint Y`ként kell írni.
Előfordulhat, hogy az új művelet a többi művelethez hasonlóan hívható meg.
Így a `Adjoint Y(q1)` alkalmazza a Adjoint-futtatót a `Y` műveletre új művelet létrehozásához, és az új műveletet `q1`re alkalmazza.

Hasonlóképpen, a `Controlled X(controls, target)` a `X` műveletre alkalmazza az ellenőrzött munkafolyamatot egy új művelet létrehozásához, és az új műveletet `controls` és `target`re alkalmazza.

A Q # két standard szintű el`Adjoint` és `Controlled`.

#### <a name="adjoint"></a>Adjoint

A Quantum Computing szolgáltatásban a művelet adjoint a művelet összetett konjugált átültetése.
Az egységes operátort megvalósító műveletek esetében a adjoint a művelet inverze.
Egy olyan egyszerű művelet esetében, amely csak a többi önálló művelet egy sorozatát hívja meg egy qubits, a adjoint kiszámítható úgy, hogy az Alműveletek adjoints alkalmazza ugyanazon a qubits, a fordított sorrendben.

A művelet kifejezése miatt új műveleti kifejezés is létrehozható a `Adjoint`-felhasználó használatával.
A `Adjoint QFT` például a `QFT` művelet adjoint jelöli.
Az új művelet ugyanazzal az aláírással és típussal rendelkezik, mint az alapművelet.
Az új művelet azt is lehetővé teszi, hogy `Adjoint`, és csak akkor engedélyezze a `Controlled`, ha az alapművelet volt.

A Adjoint-tulajdonos a saját inverze. Ez a `Adjoint Adjoint Op` mindig ugyanaz, mint `Op`.

#### <a name="controlled"></a>Ellenőrzött

Egy művelet ellenőrzött verziója olyan új művelet, amely hatékonyan alkalmazza az alapműveletet, ha az összes vezérlő qubits megadott állapotban van.
Ha a vezérlő qubits van, akkor az alapszintű műveletet a rendszer következetesen alkalmazza a Felfekvés megfelelő részére.
Így a rendszer gyakran használja az ellenőrzött műveleteket a felakadás létrehozásához.

A Q # esetében az ellenőrzött verziók mindig a vezérlési qubits egy tömbjét foglalják magukban, és a megadott állapot mindig az összes vezérlési qubits a számítási (`PauliZ`) `One` állapot, a $ \ket{1}$ értéknél.
A más állapotokon alapuló vezérlést úgy érheti el, ha a megfelelő egységes műveletet alkalmazza a vezérlő qubits az ellenőrzött művelet előtt, majd az egységes művelet inverzét alkalmazza az ellenőrzött művelet után.
Ha például egy `X` műveletet egy vezérelt művelet előtt és után qubit egy vezérlőre, akkor a művelet az adott qubit `Zero` állapotának ($ \ket{0}$) vezérlését eredményezi. egy `H` művelet alkalmazása előtt és után a `PauliX` `One` állapotot fogja vezérelni, amely-1 sajátérték a Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ helyett `PauliZ` `One` állapotban.

A művelet kifejezése miatt új műveleti kifejezés is létrehozható a `Controlled`-felhasználó használatával.
Az új művelet aláírása az eredeti művelet aláírásán alapul.
Az eredmény típusa azonos, de a bemeneti típus egy kétrekordos qubit tömb, amely a vezérlő qubit (ka) t az első elemként, az eredeti művelet argumentumait pedig második elemként tárolja.
Az új művelet támogatja a `Controlled`t, és csak akkor támogatja a `Adjoint`, ha az eredeti művelet végrehajtása megtörtént.

Ha az eredeti művelet csak egyetlen argumentumot vett igénybe, akkor a rendszer az önálló rekordos egyenértékűséget fogja itt lejátszani.
`Controlled X` például a `X` művelet ellenőrzött verziója.
a `X` típusa `(Qubit => Unit is Adj + Ctl)`, ezért `Controlled X` típusa `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; az egyszeres rekordos egyenértékűség miatt ez ugyanaz, mint a `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Ha az alapművelet több argumentumot is vett igénybe, ne felejtse el zárójelek közé helyezni a művelet ellenőrzött verziójának megfelelő argumentumait, hogy azok egy rekordba legyenek konvertálva.
`Controlled Rz` például a `Rz` művelet ellenőrzött verziója.
a `Rz` típusa `((Double, Qubit) => Unit is Adj + Ctl)`, ezért `Controlled Rz` típusa `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.
Így `Controlled Rz(controls, (0.1, target))` a `Controlled Rz` érvényes meghívása lenne (jegyezze fel a `0.1, target`zárójeleit).

Egy másik példa, `CNOT(control, target)` `Controlled X([control], target)`ként is megvalósítható. Ha egy célt 2 vezérlő qubits (CCNOT) kell vezérelni, a `Controlled X([control1, control2], target)` utasítást is használhatjuk.

### <a name="examples"></a>Példák

Ez a példa a Q # műveletre a [mérési](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) mintából származik. A műveleteken belül lefoglalhatjuk a qubits, és használhatjuk azokat a qubits, mint például a `H` és a `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

A függvényhez tartozó példa a [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) mintából származik. Tisztán klasszikus kódot tartalmaz. Láthatja, hogy a fenti példától eltérően a rendszer nem foglal le qubits, és nem használ Quantum műveletet.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Azt is megteheti, hogy a függvény átadja a qubits a feldolgozáshoz, ahogy az a [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) -minta példája. A rendszer átadja a qubits a függvénynek, és feldolgozásra használja, de a qubit-állapotok nem is módosulnak.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
