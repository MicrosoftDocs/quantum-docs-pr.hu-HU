---
title: Típusok Q#
description: Ismerje meg a programozási nyelvben használt különböző típusokat Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691609"
---
# <a name="types-in-no-locq"></a>Típusok Q#

Ez a cikk a Q# típus modelljét és a típusok megadásának és használatának szintaxisát ismerteti. Az ilyen típusú kifejezések létrehozásával és működésével kapcsolatos részletekért lásd: [kifejezések megadása](xref:microsoft.quantum.guide.expressions).

Fontos megjegyezni, hogy ez Q# egy *erősen gépelt* nyelv, amely az ilyen típusú alkalmazások körültekintő használatát segíti a fordítót, hogy erős garanciát nyújtson a Q# programoknak a fordítás ideje alatt.
A legerősebb garanciák biztosításához a típusok közötti konverziónak explicit módon kell megadnia a Q# függvényeknek a konverziót kifejező hívásait. 
Q# számos ilyen funkciót biztosít a névtér részeként <xref:Microsoft.Quantum.Convert> .
A kompatibilis típusokra való kivezetés viszont implicit módon történik. 

Q# a a közvetlen használatú primitív típusokat, valamint számos különböző módszert biztosít a más típusú új típusok létrehozásához.
Ezeket a cikk további részében ismertetjük.

## <a name="primitive-types"></a>Primitív típusok

A Q# nyelv a következő *primitív típusokat* biztosítja, amelyek mindegyike közvetlenül a Q# programokban használható. Ezeket a primitív típusokat új típusok létrehozására is használhatja.

- A `Int` típus 64 bites aláírt egész számot jelöl, például:,, `2` `107` `-5` .
- A `BigInt` típus tetszőleges méretű aláírt egész számot jelöl, például:,, `2L` `107L` `-5L` .
   Ez a típus a .NET-alapú <xref:System.Numerics.BigInteger>
   típusa.

- A `Double` típus egy dupla pontosságú lebegőpontos számot jelöl, például:,, `0.0` `-1.3` `4e-7` .
- A `Bool` típus a vagy a logikai értékét jelöli `true` `false` .
- A `Range` típus egy egész számokból álló sorozatot jelöl, amelyet a (a) jelöl, `start..step..stop` Ha a lépés megadása nem kötelező. 
   Például a megfelel a következőnek `start .. stop` `start..1..stop` , és `1..2..7` az \{ 1., 3, 5, 7 $ értéket jelöli \} .
- A `String` típus egy Unicode-karakterből álló sor, amely átlátszatlan a felhasználó számára a létrehozás után.
  `string`Hiba vagy diagnosztikai esemény esetén a típus használatával jelentheti az üzeneteket egy klasszikus gazdagépnek.
- A `Unit` típusnak csak egy értéke lehet `()` . 
  Ezzel a típussal jelezheti, hogy egy Q# függvény vagy művelet nem ad vissza adatokat. 
- A `Qubit` típus a Quantum bitet vagy a qubit jelöli.
   `Qubit`a (z) a felhasználó számára átlátszatlan. Az egyetlen lehetséges művelet, amely nem egy másik műveletnek, hanem az identitás (egyenlőség) tesztelésére szolgál.
   Végső soron olyan műveleteket hajt végre a s-ben, amelyek `Qubit` belső utasításokat kérnek a kvantum-processzoron (vagy egy kvantum-szimulátoron).
- A `Pauli` típus a négy egyqubites Pauli-operátor egyikét jelöli.
   Ezzel a típussal jelezheti a forgatások alapműveletét, és meghatározhatja a megfigyelhető mérési értéket.
   Ez egy enumerált típus, amely négy lehetséges értéket tartalmaz:,,, `PauliI` `PauliX` `PauliY` és `PauliZ` , amelyek típusú konstansok `Pauli` .
- A `Result` típus a mérték eredményét jelöli.
   Ez egy enumerált típus, amely két lehetséges értékkel rendelkezik: `One` és `Zero` , amelyek típusú konstansok `Result` .
   `Zero` azt jelzi, hogy a + 1 sajátérték mérése megtörténik; `One` azt jelzi, hogy a-1 sajátérték mérték.

A konstansok,,,,,,, `true` `false` és az `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` összes foglalt szimbólum szerepel a alkalmazásban Q# .

## <a name="array-types"></a>Tömbök típusai

* Bármely érvényes Q# típus esetében létezik egy típus, amely az adott típusú értékek tömbjét jelöli.
    Például az `Qubit[]` `(Bool, Pauli)[]` értékek és a rekord típusú értékek tömböket jelölik `Qubit` `(Bool, Pauli)` .

* Tömbök tömbje is érvényes. Az előző példát kiterjesztve a tömbök tömbjét `(Bool, Pauli)` jelöli `(Bool, Pauli)[][]` .

> [!NOTE] 
> Ez a példa `(Bool, Pauli)[][]` a tömbök potenciálisan szaggatott tömbjét jelöli, nem pedig egy téglalap alakú kétdimenziós tömböt. Q# a nem támogatja a négyszögletes többdimenziós tömböket.

* A tömb értéke a Q# forráskódban a tömb elemei körül szögletes zárójelek használatával is írható `[PauliI, PauliX, PauliY, PauliZ]` .
A tömbben lévő összes elem közös alaptípusa határozza meg egy tömb literál típusát. Ezért a tömb olyan elemekkel való létrehozása, amelyek nem rendelkeznek közös alaptípussal, hibát jeleznek.  
Példaként tekintse meg a [callables tömböket](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > A létrehozást követően a tömb elemei nem módosíthatók.
    > Módosított tömb létrehozásához használja a [Update-and-reassign utasításait](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) vagy a [másolási és frissítési kifejezéseket](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Azt is megteheti, hogy létrehoz egy tömböt a méretétől a `new` következő kulcsszó használatával:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* A Core függvénnyel `Length` megszerezheti az elemek számát egy tömbből `Int` .
* A tömbök a tömb elemeinek egy részhalmazát tartalmazó önálló elemek vagy új tömbök beszerzéséhez használhatók.
A tömbök alszkriptje nulla-alapú, és típusnak `Int` vagy típusnak kell lennie `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Rekord típusok

A rekordok egy hatékony koncepció, amellyel Q# az értékek összegyűjthetők egyetlen értékkel, így könnyebben átadhatók.
A rekordos jelölések használatával kipróbálhatja, hogy minden művelet és a hívó pontosan egy bemenetet fogadjon, és pontosan egy kimenetet ad vissza.

* Megadott nulla vagy több különböző típus `T0` , `T1` ,..., az `Tn` új  *rekord típusát* jelöli `(T0, T1, ..., Tn)` .
Az új bejegyzéstípus létrehozásához használt típusok maguk is rekordok, például: `(Int, (Qubit, Qubit))` .
Az ilyen beágyazás mindig véges, azonban a rekord típusú típusok semmilyen körülmények között nem tartalmazhatják magukat.

* Az új rekordok értékei a rekordban lévő egyes típusok értékeinek sorozatából jönnek létre.
Például `(3, false)` egy olyan rekord, amelynek típusa a rekord típusa `(Int, Bool)` .
Létrehozhatók rekordok, rekordok, rekordok, alrekordokek és így tovább.

* A 0,3-as és az Q# `Unit` üres rekord *típusának* neve az `()` üres rekord *értékéhez* használatos.

* A rekordos példányok nem változtathatók meg.
Q# a nem biztosít olyan mechanizmust, amely a létrehozott rekord tartalmát egyszer módosítja.



### <a name="singleton-tuple-equivalence"></a>Egyszeres rekord egyenértékűsége

Létrehozhat egy egyelemes (Single-Element) rekordot `('T1)` , például `(5)` vagy `([1,2,3])` .
Q#Az Egypéldányos rekordokat azonban a befoglalt típus értékével egyenértékűként kezeli.
Ez azt jelentheti, hogy nincs különbség a és a között, illetve a és a között, illetve a és a között `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .
Ugyanúgy írható, mint az írás, és a `(5)+3` `5+3` kifejezések kiértékelése is megtörténik `8` .

Ez az egyenértékűség minden célra érvényes, beleértve a hozzárendelést és a kifejezéseket is.
Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.
Például `(7)` egy típusú kifejezés, egy típusú kifejezés `Int` `([1,2,3])` `Int[]` , és `((1,2))` egy típusú kifejezés `(Int, Int)` .

Ez különösen azt jelenti, hogy megtekintheti azt a műveletet vagy függvényt, amelynek bemeneti vagy kimeneti rekordjának típusa egyetlen mező, vagy egyetlen értéket ad vissza.

Ezt a tulajdonságot egy különálló _rekord egyenértékűségének_ nevezzük.


## <a name="user-defined-types"></a>User-Defined típusok

A felhasználó által definiált típusú deklaráció a kulcsszóból áll `newtype` , amelyet a felhasználó által definiált típus, az a `=` , az érvényes típus-specifikáció és a megszakítási pontosvesszővel kell kiegészíteni.

Például:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Q#Előfordulhat, hogy minden forrásfájl tetszőleges számú felhasználó által definiált típust deklarál.
* A típus nevének egyedinek kell lennie a névtéren belül, és előfordulhat, hogy a művelet és a függvények nevei nem ütköznek egymással.
* A felhasználó által definiált típusok egyediek, még akkor is, ha az alaptípusok azonosak.
Különösen, ha az alapul szolgáló típusok azonosak, a felhasználó által definiált típusok értékei között nincs automatikus konverzió.

### <a name="named-vs-anonymous-items"></a>Névvel ellátott és névtelen elemek

Egy Q# fájl meghatározhatja a jogi típusok egyetlen értékét tartalmazó új elnevezett típust.
Bármilyen típusú rekord esetében `T` deklarálhat egy új, felhasználó által definiált típust, amely az utasítás altípusa `T` `newtype` .
A @"microsoft.quantum.math" névtérben például az összetett számok felhasználó által definiált típusként vannak meghatározva:

```qsharp
newtype Complex = (Double, Double);
```
Ez az utasítás egy új típust hoz létre két névtelen elem típussal `Double` .   

A névtelen elemektől eltekintve a felhasználó által definiált típusok a 0,7-es vagy újabb verzióként is támogatják az *elnevezett elemeket* Q# . Megadhatja például, hogy az elemek `Real` egy összetett szám valódi részét jelképező dupla érték legyen, a `Imag` képzeletbeli rész pedig: 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
Egy felhasználó által definiált típus egyik elemének elnevezése nem jelenti azt, hogy az összes elemet el kell nevezni – a nevesített és a nem nevezett elemek bármely kombinációja támogatott. Emellett a belső elemek is megadhatók.
Az `Nested` alább megadott típus például egy alapul szolgáló típussal rendelkezik `(Double, (Int, String))` , amelyből csak a `Int` nevű elem neve szerepel, és minden más elem névtelen. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Az elnevezett elemek előnye, hogy közvetlenül a *hozzáférési operátoron* keresztül érhetők el `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

Amellett, hogy rövid aliasokat biztosít a potenciálisan bonyolult rekordokhoz, az ilyen típusok meghatározásának jelentős előnye, hogy dokumentálni tudja egy adott érték szándékát.
A következő példára visszatérve egy `Complex` Polar koordináta-represenation is definiálhat felhasználó által definiált típusként:

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Bár mindkettő `Complex` és `ComplexPolar` mindkettő rendelkezik egy alapul szolgáló típussal `(Double, Double)` , a két típus teljesen inkompatibilis a-ben Q# , ami minimalizálja annak kockázatát, hogy véletlenül egy összetett matematikai függvényt hív meg a Polar koordinátákkal, és fordítva.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Névtelen elemek elérése a kicsomagolási operátorral

A névtelen elemek eléréséhez először bontsa ki a becsomagolt értéket a Postfix operátor használatával `!` .
A "kicsomagolás" operátor `!` használatával kinyerheti a felhasználó által definiált típusban található értéket.
A "kicsomagolás" kifejezés típusa a felhasználó által definiált típus alapjául szolgáló típus. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Egyetlen kibontott operátor kicsomagolja az egyik réteget. Több kibontható operátor használata egy szorzáshoz burkolt érték eléréséhez.

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

További információ a kicsomagolási operátorról: [kifejezések beírása Q# a alkalmazásban ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Felhasználó által definiált típusok értékeinek létrehozása

Hozzon létre egy felhasználó által definiált típus értékeit a megfelelő típusú konstruktor meghívásával:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Azt is megteheti, hogy a [Másolás és frissítés kifejezések](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)használatával új értékeket hoz létre a meglévők közül. Csakúgy, mint a tömbök esetében, a másolási és frissítési kifejezések az eredeti kifejezés összes elemét átmásolják, kivéve a megadott megnevezett elemeket. A kivételek esetében ezek az elemek a kifejezés jobb oldalán megadott értékek. A tömb elemeihez rendelkezésre álló más nyelvi szerkezetek, például az [Update-and-reassign utasítások](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)léteznek a felhasználó által definiált típusokban lévő névvel ellátott elemekhez is.

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

* A felhasználó által definiált típusokat bárhol használhatja bármilyen más típus használata esetén.
Egy felhasználó által definiált típus tömbjét lehet meghatározni, és egy felhasználó által definiált típust is felvenni egy rekord típusú elemként.

* Nem lehet rekurzív típusú struktúrákat létrehozni.
Vagyis a felhasználó által definiált típust definiáló típus nem lehet a felhasználó által definiált típusú elemet tartalmazó rekord típusa.
A felhasználó által definiált típusok általában nem lehetnek ciklikus függőségek egymástól, így a következő típusú definíciók érvénytelenek:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Művelet és függvények típusai

A típusok `'Tinput` és a `'Tresult` :

* `('Tinput => 'Tresult)` a *művelet* alapszintű típusa, például: `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` a *függvény* alapvető típusa, például: `(Int -> Int)` . 

Ezeket a meghívásos *aláírásnak* nevezzük.

* Minden Q# callables egyetlen értéket adjon meg bemenetként, és egyetlen értéket ad vissza kimenetként.
* A bemeneti és a kimeneti értékekhez egyaránt használhatja a rekordok.
* Olyan Callables, amelyeknek nincs eredménye, vissza `Unit` .
* Azok a Callables, amelyek nem rendelkeznek bemenettel, az üres rekordokat is be kell tölteni.

### <a name="functors"></a>Működők

A *függvények* típusát az aláírása teljesen megadja. Például egy olyan függvény, amely egy szög szinuszát számítja ki, típusnak kellene lennie `(Double -> Double)` . 

A *műveletek* bizonyos további jellemzőkkel rendelkeznek, amelyek a művelet típusának részeként vannak kifejezve. Ezek a tulajdonságok olyan információkat tartalmaznak *, amelyek a* művelet által támogatott operációs rendszerek.
Ha például a művelet egy másik qubits állapotára támaszkodik, akkor az a következőt támogatja:. `Controlled` Ha a műveletnek van inverze, akkor támogatnia kell az elválasztó szolgáltatást `Adjoint` .

> [!NOTE]
> Ez a cikk csak azt tárgyalja, hogyan változtatják meg a műveleti aláírást. További információ a-feladatokról és a műveletekről: [műveletek és Q# függvények a alkalmazásban ](xref:microsoft.quantum.guide.operationsfunctions). 

Ha a `Controlled` és/vagy az `Adjoint` üzemben lévőt egy művelet típusában szeretné támogatni, hozzá kell adnia egy jegyzetet, amely a megfelelő tulajdonságokat jelzi.
A jegyzet `is Ctl` (például `(Qubit => Unit is Ctl)` ) azt jelzi, hogy a művelet ellenőrizhető. Ez a Futtatás egy másik qubit vagy qubits állapotára támaszkodik. Hasonlóképpen, a jegyzet `is Adj` azt jelzi, hogy a műveletnek van egy adjoint, azaz "invertált" lehet, például egy művelet egymást követő alkalmazása, majd az állapot adjoint változatlan marad. 

Ha szeretné megkövetelni, hogy egy adott típusú művelet támogassa a és a-kezelőt is, ezt a következő `Adjoint` `Controlled` módon fejezheti ki: `(Qubit => Unit is Adj + Ctl)` . A beépített Pauli-művelet például a <xref:Microsoft.Quantum.Intrinsic.X> következőt írja be: `(Qubit => Unit is Adj + Ctl)` . 

Egy olyan Művelettípus, amely nem támogatja az egyiket sem, a bemeneti és a kimeneti típus szerint, külön megjegyzés nélkül adja meg.

### <a name="type-parameterized-functions-and-operations"></a>Type-Parameterized függvények és műveletek

A hívható típusok tartalmazhatnak *típusú paramétereket* .
Egy idézőjel által előre meghatározott szimbólumot használjon, amely egy type paramétert jelez; például `'A` egy jogi típusparaméter.
A típus-paraméteres callables definiálásával kapcsolatos további információkért lásd: [műveletek és függvények a alkalmazásban Q# ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Egy típusparaméter egynél többször is megjelenhet egyetlen aláírásban.
Például egy olyan függvény, amely egy tömb minden elemére egy másik függvényt alkalmaz, és az összegyűjtött eredményeket az aláírással adja vissza `(('A[], 'A->'A) -> 'A[])` .
Hasonlóképpen, egy függvény, amely két művelet összeállítását adja vissza, az aláírással rendelkezik `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Ha egy Type-paraméteres meghívást hív meg, az azonos típusú paraméterrel rendelkező összes argumentumnak azonos típusúnak kell lennie.

Q# a nem biztosít olyan mechanizmust, amely lehetővé teszi, hogy a felhasználók egy típusparaméter esetében helyettesíthetik a lehetséges típusokat.

## <a name="next-steps"></a>Következő lépések

Most, hogy megismerte a nyelvet alkotó összes típust Q# , tekintse meg a [kifejezések Q# beírása](xref:microsoft.quantum.guide.expressions) című témakört, amelyből megtudhatja, hogyan hozhat létre és kezelhet különféle típusú kifejezéseket.
