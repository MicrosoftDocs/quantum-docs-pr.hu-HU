---
title: Típusok a Q#-ban
description: 'A Q # programozási nyelvben használt különböző típusok megismerése.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327288"
---
# <a name="types-in-q"></a>Típusok a Q#-ban

Ez a lap a Q # type modellt mutatja be, és leírja a típusok megadásának és használatának szintaxisát.
A következő lapon [írja be a kifejezések kifejezést](xref:microsoft.quantum.guide.expressions), és adja meg, hogyan kell létrehozni és használni az ilyen típusú kifejezéseket.

Fontos megjegyezni, hogy a Q # egy *erősen gépelt* nyelv, így az ilyen típusú alkalmazások körültekintő használata segíthet a fordítónak a q # programokkal kapcsolatos erős garanciák megadásában a fordítási idő alatt.
Ahhoz, hogy a lehető legerősebb garanciát nyújtson, a Q # típusok közötti konverziónak explicit módon kell megadnia az átalakítást kifejező függvények hívásait. Számos ilyen függvény a névtér részeként van megadva <xref:microsoft.quantum.convert> .
A kompatibilis típusok egymásra való átadása implicit módon történik. 

A Q # egyszerű típusokat biztosít, amelyek közvetlenül is használhatók, és számos különböző módon hozhatók létre más típusú új típusok.
Ezeket a szakasz további részében ismertetjük.

## <a name="primitive-types"></a>Primitív típusok

A Q # nyelv számos *primitív típust*biztosít, amelyekből más típusok is létrehozhatók:

- A `Int` típus 64 bites aláírt egész számot jelöl, például: `2` , `107` , `-5` .
- A `BigInt` típus tetszőleges méretű aláírt egész számot jelöl, például:, `2L` `107L` `-5L` .
   Ez a típus a .NET-alapú<xref:System.Numerics.BigInteger>
   típusa.
- A `Double` típus egy dupla pontosságú lebegőpontos számot jelöl, például: `0.0` , `-1.3` , `4e-7` .
- A `Bool` típus olyan logikai értéket jelöl, amely vagy lehet `true` `false` .
- A `Range` típus egy egész számokból álló sorozatot jelöl, amelyet a (a) jelöl, `start..step..stop` Ha a lépés megadása nem kötelező. 
   Ez `start .. stop` megfelel a-nek `start..1..stop` , és például `1..2..7` az \{ 1., 3., 5., 7 $-os sorozatot jelöli \} .
- A `String` típus egy Unicode-karakterből álló sor, amely átlátszatlan a felhasználó számára a létrehozás után.
  Ez a típus egy klasszikus gazdagép üzeneteinek jelentésére szolgál hiba vagy diagnosztikai esemény esetén.
- A `Unit` típus az a típus, amely csak egy értéket engedélyez `()` . 
  Ez a típus azt jelzi, hogy a Q # függvény vagy művelet nem ad vissza információt. 
- A `Qubit` típus a Quantum bitet vagy a qubit jelöli.
   `Qubit`a (z) a felhasználó számára átlátszatlan; az egyetlen lehetséges művelet, amely nem egy másik műveletnek, hanem az identitás (egyenlőség) tesztelésére szolgál.
   Végső soron az s-műveletek `Qubit` megvalósítása a kvantum-processzoron (vagy annak szimulációján) alapuló belső utasítások meghívásával valósítható meg.
- A `Pauli` típus a négy egyqubites Pauli-operátor egyikét jelöli.
   Ez a típus az alapművelet elforgatására, valamint a megfigyelhető mérések megadására szolgál.
   Ez egy enumerált típus, amely négy lehetséges értékkel rendelkezik:,,, `PauliI` `PauliX` `PauliY` és `PauliZ` , amelyek típusú konstansok `Pauli` .
- A `Result` típus a mérték eredményét jelöli.
   Ez egy enumerált típus, amely két lehetséges értékkel rendelkezik: `One` és `Zero` , amelyek típusú konstansok `Result` .
   `Zero`azt jelzi, hogy a + 1 sajátérték mérése megtörténik; `One`az-1 sajátérték jelöli.

A konstansok,,,,,,, `true` `false` és a `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # összes fenntartott szimbóluma.

## <a name="array-types"></a>Tömbök típusai

Az érvényes Q # típusnak megfelelő típus `'T` esetén a rendszer egy típusú értékek tömbjét jelöli `'T` .
Ez a tömb típusa a következő `'T[]` :, például `Qubit[]` vagy `Int[][]` .
Egy egész számokból álló gyűjteményt például a rendszer az `Int[]` értékek tömbök tömbjét jelöli `(Bool, Pauli)` `(Bool, Pauli)[][]` .

A második példában látható, hogy ez a tömbök potenciálisan szaggatott tömbjét jelöli, nem pedig egy téglalap alakú kétdimenziós tömböt.
A Q # nem nyújt támogatást a négyszögletes többdimenziós tömbökhöz.

A tömb értéke Q # forráskódban is megadható, ha szögletes zárójeleket használ egy tömb elemei körül `[PauliI, PauliX, PauliY, PauliZ]` .
A tömb literál típusát a tömbben lévő összes elem közös alaptípusa határozza meg. Ezért egy olyan tömb létrehozásával próbálkozhat, amely nem rendelkezik közös alaptípussal.  
Ehhez a [callables tömbökben](xref:microsoft.quantum.guide.expressions#arrays-of-callables) talál példát.

> [!WARNING]
> Egy tömb elemei nem módosíthatók a tömb létrehozása után.
> Módosított tömb létrehozásához a [frissítés és az ismételt hozzárendelés utasítások](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) és/vagy [a másolási és frissítési kifejezések](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) használhatók.

Azt is megteheti, hogy létrehoz egy tömböt a méretétől a `new` következő kulcsszó használatával:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Mindkét esetben a tömb kiépítése után az alapfunkció használatával `Length` megszerezhető az elemek száma `Int` .
A tömbök a szögletes zárójelek használatával, a típus vagy a típus beírásával, a tömb `Int` `Range` elemeinek egy részhalmazát tartalmazó önálló elemek vagy új tömbök beszerzésére is alkalmasak.
A tömbök alszkriptje nulla-alapú:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Rekord típusok

Megadott nulla vagy több különböző típus `T0` , `T1` ,..., `Tn` egy új *rekord típusát* jelöli `(T0, T1, ..., Tn)` .
Az új bejegyzéstípus létrehozásához használt típusok maguk is rekordok, például: `(Int, (Qubit, Qubit))` .
Az ilyen beágyazás mindig véges, azonban a rekord típusú típusok semmilyen körülmények között nem tartalmazhatják magukat.

Az új rekord típusának értékeit a rekordban lévő egyes típusok értékeinek rekordok alkotják.
Például `(3, false)` egy olyan rekord, amelynek típusa a rekord típusa `(Int, Bool)` .
A rekordok, a rekordok, a rekordok és az alrekordokok tömbje is létrehozható.

A Q # 0,3-tól kezdve a (z) `Unit` üres rekord *típusának* neve, `()` amelyet az üres rekord *értékéhez*használ a rendszer.

A rekordos példányok nem változtathatók meg.
A Q # nem biztosít olyan mechanizmust, amely a létrehozott rekord tartalmának módosítását végzi.

A rekordok hatékony koncepciót használ a Q #-ban az értékek egyetlen értékkel való összegyűjtéséhez, így könnyebben átadhatja őket.
A rekordos jelölések használatával kifejezhető, hogy minden művelet és a hívó pontosan egy bemenetet fogad, és pontosan egy kimenetet ad vissza.

### <a name="singleton-tuple-equivalence"></a>Egyszeres rekord egyenértékűsége

Létre lehet hozni egy egyelemes (Single-Element) rekordot, `('T1)` például `(5)` vagy `([1,2,3])` .
A Q # azonban egy egyszeres rekordot teljesen egyenértékűként kezel a befoglalt típus értékével.
Ez azt jelentheti, hogy nincs különbség a és a között, illetve a és a között, illetve a és a között `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .
Ugyanúgy írható `(5)+3` , mint az írás `5+3` , és mindkét kifejezés kiértékelése a következőre történik: `8` .

Ez az egyenértékűség minden célra érvényes, beleértve a hozzárendelést és a kifejezéseket is.
Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.
Például `(7)` egy `Int` kifejezés, amely `([1,2,3])` egy tömb típusú kifejezés, `Int` és `((1,2))` egy típusú kifejezés `(Int, Int)` .

Ez különösen azt jelenti, hogy egy olyan művelet vagy függvény, amelynek bemeneti vagy kimeneti rekordjának típusa egyetlen mező, egyetlen argumentumként vagy egyetlen érték visszaadása esetén lehet.

Ezt a tulajdonságot egy különálló _rekord egyenértékűségének_nevezzük.


## <a name="user-defined-types"></a>Felhasználó által definiált típusok

A felhasználó által definiált típusú deklaráció a kulcsszóból áll `newtype` , amelyet a felhasználó által definiált típus, az a `=` , az érvényes típus-specifikáció és a megszakítási pontosvesszővel kell kiegészíteni.

Például:

```qsharp
newtype PairOfInts = (Int, Int);
```

Minden Q # forrásfájl tetszőleges számú felhasználó által definiált típust deklarálhat.
A típus nevének egyedinek kell lennie a névtéren belül, és előfordulhat, hogy a művelet és a függvények nevei nem ütköznek egymással.

A felhasználó által definiált típusok akkor is eltérőek, ha az alaptípusok azonosak.
Különösen, ha az alapul szolgáló típusok azonosak, a felhasználó által definiált típusok értékei között nincs automatikus konverzió.

### <a name="named-vs-anonymous-items"></a>Névvel ellátott és névtelen elemek

A Q #-fájlok meghatározhatnak egy olyan új névvel ellátott típust, amely bármely jogi típus egyetlen értékét tartalmazza.
Bármilyen típusú rekord esetében `T` deklarálhat egy új, felhasználó által definiált típust, amely az utasítás altípusa `T` `newtype` .
A @"microsoft.quantum.math" névtérben például az összetett számok felhasználó által definiált típusként vannak meghatározva:

```qsharp
newtype Complex = (Double, Double);
```
Ez az utasítás egy új típust hoz létre két névtelen elem típussal `Double` .   

A névtelen elemektől eltekintve a felhasználó által definiált típusok az *elnevezett elemeket* is támogatják a Q # 0,7-es vagy újabb verziójával. Tegyük fel például, hogy elnevezte az elemet a Double elemnek, amely `Re` egy komplex szám valódi részét jelképezi, és `Im` a képzeletbeli részhez: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Egy felhasználó által definiált típus egyik elemének elnevezése nem jelenti azt, hogy az összes elemet el kell nevezni – a nevesített és a nem nevezett elemek bármely kombinációja támogatott. Emellett a belső elemek is megadhatók.
Az `Nested` alább definiált típus például egy alapul szolgáló típussal rendelkezik `(Double, (Int, String))` , amelyből csak a nevű elem `Int` neve és minden más elem névtelen. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Az elnevezett elemek előnye, hogy közvetlenül a *hozzáférési operátoron* keresztül érhetők el `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Amellett, hogy rövid aliasokat biztosít a potenciálisan bonyolult rekordokhoz, az ilyen típusú típusok egyik jelentős előnye, hogy dokumentálni tudja egy adott érték szándékát.
A példára való visszatéréshez a `Complex` 2D poláris koordinátákat is definiálhatja felhasználó által definiált típusként:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Bár mindkettő `Complex` és `Polar` mindkettő egy alapul szolgáló típussal rendelkezik `(Double, Double)` , a két típus teljes mértékben inkompatibilis a Q #-ban, ami minimalizálja annak kockázatát, hogy a komplex matematikai függvények véletlenül hívása a Polar koordinátákkal és fordítva.
Így a felhasználó által definiált típusokhoz hasonló szerepkör tartozik, mint például az F # rekord. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Névtelen elemek elérése a kicsomagolási operátorral

A névtelen elemek eléréséhez a beburkolt értéket először a Postfix operátor használatával kell kinyerni `!` .
A "kicsomagolás" operátor `!` lehetővé teszi, hogy kinyerje a felhasználó által definiált típusban található értéket.
A "kicsomagolás" kifejezés típusa a felhasználó által definiált típus alapjául szolgáló típus. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

A kicsomagolási operátor kicsomagolja pontosan a burkoló rétegét.
Több kibontható operátor is használható egy szorzáshoz burkolt érték eléréséhez.

Ilyenek például a következők:

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

A kicsomagolással foglalkozó operátorral kapcsolatos további részletek a [Q # típus kifejezések kifejezésében](xref:microsoft.quantum.guide.expressions)találhatók.

### <a name="creating-values-of-user-defined-types"></a>Felhasználó által definiált típusok értékeinek létrehozása

A felhasználó által definiált típus értékeit a megfelelő típusú konstruktor meghívásával lehet létrehozni:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Másik lehetőségként új értékeket is létrehozhat a meglévő [példányokból másolás és frissítés kifejezések](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)használatával. A tömbökhöz hasonlóan az ilyen kifejezések az eredeti kifejezés összes elemét is átmásolják, a megadott megnevezett elemek kivételével. Ezeknél az értékek a kifejezés jobb oldalán definiált értékekre vannak beállítva. Más nyelvi szerkezetek, például az [Update-and-reassign utasítások](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), amelyek a tömb elemei számára elérhetők a felhasználó által definiált típusokban is.

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

Megjegyzés: rekurzív típusú struktúrákat nem lehet létrehozni.
A felhasználó által definiált típust definiáló típus nem lehet olyan rekord típusú, amely a felhasználó által definiált típus elemét tartalmazza.
A felhasználó által definiált típusok általában nem lehetnek ciklikus függőségek egymással, így a következő típusú definíciók érvénytelenek lesznek:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Művelet és függvények típusai

Az összes meghívóhoz tartozó alaptípust a vagy a értékre kell írni `('Tinput => 'Tresult)` `('Tinput -> 'Tresult)` , ahol mindkettő `'Tinput` és `'Tresult` típus szerepel.
Ezeket a meghívásos *aláírásnak* nevezzük.

Az összes Q # callables egyetlen értéket vesz fel bemenetként, és egyetlen értéket ad vissza kimenetként.
A bemeneti és a kimeneti értékek is rekordok.
Callables, amelyek nem adnak vissza eredményt `Unit` .
Azok a Callables, amelyek nem rendelkeznek bemenettel, az üres rekordokat is be kell tölteni.

> [!NOTE]
> A rendszer az első űrlapot `=>` használja a műveletekhez, a második pedig a `->` függvényekhez.
> Például `((Qubit, Pauli) => Result)` az egy lehetséges qubit mérési művelet aláírását jelöli.
A *függvények* típusát az aláírása teljesen megadja.
Például egy olyan függvény, amely egy szög szinuszát számítja ki, típusnak kellene lennie `(Double -> Double)` .

Az *operations*---, de a függvények nem---vannak olyan további jellemzők, amelyek a Művelettípus részeként vannak kifejezve. Ezek *a jellemzők* a művelet által támogatott operációs rendszerekből származó információkat tartalmazzák.
Ha például a művelet végrehajtása más qubits állapotára is felhasználható, akkor támogatnia kell az elválasztó `Controlled` . Ha a művelet inverz, akkor támogatnia kell a következőt: `Adjoint` . A műveletek és a műveletek a [Q # műveletekben](xref:microsoft.quantum.guide.operationsfunctions)részletesen tárgyalnak, de itt egyszerűen megbeszéljük, hogy ez hogyan változtatja meg a művelet aláírását.

Ahhoz, hogy egy Művelettípus támogassa a `Controlled` és/vagy az operátort `Adjoint` , hozzá kell adnia egy jegyzetet, amely a megfelelő tulajdonságokat jelzi.
`is Ctl`A jegyzet (például `(Qubit => Unit is Ctl)` ) azt jelzi, hogy a művelet---, azaz egy másik qubit vagy qubits állapotára vonatkozó végrehajtásra van állítva. Hasonlóképpen `is Adj` azt is jelzi, hogy a művelet rendelkezik egy adjoint, vagy egyszerűen "invertálva" lehet, hogy egy művelet egymást követő alkalmazása, majd az állapot adjoint változatlan marad. 

Ha szeretné megkövetelni, hogy egy adott típusú művelet támogassa a és a-kezelőt is, ezt a típust `Adjoint` `Controlled` is kinyilváníthatja `(Qubit => Unit is Adj + Ctl)` . A beépített Pauli-művelet például a <xref:microsoft.quantum.intrinsic.x> következőt írja be: `(Qubit => Unit is Adj + Ctl)` . 

Egy olyan Művelettípus, amely nem támogatja az egyiket sem, a bemeneti és a kimeneti típus szerint, külön megjegyzés nélkül adja meg.

### <a name="type-parameterized-functions-and-operations"></a>Type-paraméteres függvények és műveletek

A hívható típusok tartalmazhatnak típusú paramétereket.
A Type paramétereket egy adott idézőjel által előre meghatározott szimbólum jelöli. például `'A` egy jogi típusparaméter.
A Type-paraméteres callables definiálásával kapcsolatos részletek a [Q # oldalon található műveletek és függvények esetében](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) találhatók.

Egy típusparaméter egynél többször is megjelenhet egyetlen aláírásban.
Például egy függvény, amely egy tömb minden elemére egy másik függvényt alkalmaz, és az összegyűjtött eredményeket az aláírással adja vissza `(('A[], 'A->'A) -> 'A[])` .
Hasonlóképpen, egy függvény, amely két művelet összetételét adja vissza, aláírással rendelkezhet `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

A típus-paraméteres metódus hívásakor az azonos típusú paraméterrel rendelkező összes argumentumnak azonos típusúnak kell lennie.

A Q # nem biztosít olyan mechanizmust, amely lehetővé teszi a Type paraméterhez helyettesíthető lehetséges típusok korlátozását.

## <a name="next-steps"></a>Következő lépések

Most, hogy megismerte a Q # nyelvét alkotó összes típust, [írja be a kifejezéseket a q # szövegbe](xref:microsoft.quantum.guide.expressions) , hogy megtudja, hogyan hozhat létre és kezelhet a különböző típusú kifejezéseket.


