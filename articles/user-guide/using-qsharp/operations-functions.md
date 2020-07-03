---
title: 'Műveletek és függvények a Q-ban #'
description: Műveletek és függvények definiálása és hívása, valamint az ellenőrzött és adjoint műveletekre vonatkozó specializációk.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 08eaf150a38afd789f8a23f567ff111d002bac07
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884213"
---
# <a name="operations-and-functions-in-q"></a>Műveletek és függvények a Q-ban #

## <a name="defining-new-operations"></a>Új műveletek definiálása

A műveletek a Q # legfontosabbak.
A bejelentést követően meghívhatók a klasszikus .NET-alkalmazásokból, például szimulátor használatával vagy a Q #-on belüli egyéb műveletekkel.
A Q # által definiált minden művelet tetszőleges számú egyéb műveletet hívhat meg, beleértve a nyelv által meghatározott beépített belső műveleteket is. A Q # konkrét módon határozza meg, hogy ezek a belső műveletek a célszámítógéptől függenek.
A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.

Minden Q # forrásfájl tetszőleges számú műveletet meghatározhat.
A művelet nevének a névtéren belül egyedinek kell lennie, és nem ütközhet a típus vagy a függvény nevével.

A műveleti deklaráció a kulcsszóból áll, amelyet a művelet nevét, a művelethez tartozó `operation` argumentumokat definiáló típust, egy kettőspontot, egy Type jegyzetet ad meg, amely a művelet `:` eredményének típusát írja le, opcionálisan megadhatja a műveleti jellemzőket, egy nyitó kapcsos zárójelet, majd a műveleti deklaráció törzsét kapcsos zárójelek közé `{ }` .

Mindegyik művelet egy bemenetet hoz létre, kimenetet állít elő, és meghatározza egy vagy több műveleti specializáció megvalósítását.
A lehetséges szakosodások, valamint az ezek meghatározása és meghívása a cikk különböző fejezeteiben olvasható.
Egyelőre a következő műveletnek kell megfontolnia, amely csak az alapértelmezett szövegtörzset határozza meg, és egyetlen qubit használ a bemenetként, majd meghívja a beépített <xref:microsoft.quantum.intrinsic.x> műveletet a bemeneten:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A kulcsszó `operation` megkezdi a művelet definícióját, amelyet a név követ, itt: `BitFlip` .
A következő lépés a bemenet típusa ( `Qubit` ), valamint egy név, amely az `target` új műveleten belüli bemenetre hivatkozik.
Végül `Unit` azt is meghatározza, hogy a művelet kimenete üres.
`Unit`a használata hasonlóan a `void` C#-ban és más, felszólító nyelvekhez, és az `unit` F # és más funkcionális nyelvekkel egyenértékű.

A műveletek több érdekes típust is visszaadhatnak, mint a `Unit` .
A <xref:microsoft.quantum.intrinsic.m> művelet például egy típusú kimenetet ad vissza `Result` , amely a mérés végrehajtását jelöli.  Átadhatja egy műveletből egy másik műveletnek, vagy felhasználhatja azt a `let` kulcsszóval egy új változó definiálásához.

Ez a megközelítés lehetővé teszi a klasszikus számítások használatát, amelyek alacsony szinten működnek a kvantum-műveletekkel, például a [sűrűbb kódolásban](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> A Q # minden művelete pontosan egy bemenetet vesz igénybe, és pontosan egy kimenetet ad vissza.
> Több bemenet és kimenet is szerepel a *rekordok*használatával, amely egyszerre több értéket gyűjt össze egyetlen értékkel.
> Ebben a tekintetben a Q # egy "rekordból álló rekord kijelentkezés" nyelv.
> Ezt a fogalmat követve az üres zárójelek egy halmaza, `()` amelynek a típusa "Empty" (üres `Unit` ) rekord.

## <a name="controlled-and-adjoint-operations"></a>Vezérelt és Adjoint műveletek

Ha egy művelet egy egységes átalakítást valósít meg, a Q # számos műveletének esetében, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen. Egy művelet *adjoint* -specializálása meghatározza, hogy a művelet milyen hatással van az "inverz" értékre, míg a *szabályozott* specializáció meghatározza, hogy a művelet hogyan működik, ha az alkalmazás egy adott kvantum-regiszter állapotára van feltétele.

A Adjoints elengedhetetlen a kvantum-számítási feladatok számos aspektusa szempontjából. Ha például egy hasznos Q # programozási technikával kapcsolatos példát tárgyal, tekintse meg a jelen cikk [conjugations](#conjugations) . 

Egy művelet ellenőrzött verziója olyan új művelet, amely hatékonyan alkalmazza az alapműveletet, ha az összes vezérlő qubits megadott állapotban van.
Ha a vezérlő qubits van, akkor az alapszintű műveletet a rendszer következetesen alkalmazza a Felfekvés megfelelő részére.
Így a rendszer gyakran használja az ellenőrzött műveleteket a felakadás létrehozásához.

Természetesen egy *vezérelt adjoint* specializáció is létezhet, amely meghatározza egy művelet adjoint vezérelt alkalmazását.

> [!NOTE]
> Ha $U $ egy művelet által megvalósított egységes átalakítás `U` , akkor `Adjoint U` az egységes átalakítást jelöli $U ^ \dagger $, amely a komplex konjugátum átültetése.
> Egy művelet egymást követő alkalmazása után a adjoint állapota változatlan marad, ahogy azt az a tény mutatja, hogy $UU ^ \dagger = U ^ \dagger U = \id $, az Identity Matrix.
> Egy vezérelt művelet egységes ábrázolása valamivel árnyaltabb, de további részleteket a [Quantum Computing-fogalmak: több qubits](xref:microsoft.quantum.concepts.multiple-qubits)is talál.

A következő szakasz ismerteti, hogyan hívhatja meg ezeket a különböző specializációkat a Q # kódjában, és hogyan határozhat meg műveleteket a támogatásához.

### <a name="calling-operation-specializations"></a>Hívási művelet specializációi

A *Q # egy olyan* gyár, amely új műveletet határoz meg egy másik műveletből.
A Q # két standard, a és a `Adjoint` `Controlled` .

Az új művelet megvalósításának meghatározásakor az üzemben lévők az alapművelet megvalósításához férnek hozzá.
Így a fellépők összetettebb funkciókkal rendelkezhetnek, mint a hagyományos magasabb szintű függvények. A Q # Type rendszer nem rendelkezik képviselettel a következőben:. Ezért jelenleg nem lehet őket egy változóhoz kötni, vagy argumentumként átadni őket. 

Használjon egy olyan műveletet, amely egy olyan műveletre alkalmazza, amely egy új műveletet ad vissza.
Ha például a műveletet a `Adjoint` művelettel alkalmazza, az `Y` új műveletet adja vissza `Adjoint Y` . Az új műveletet más műveletekhez hasonlóan hívhatja meg.
Ahhoz, hogy egy művelet támogassa a vagy a nem működő példányok alkalmazását `Adjoint` `Controlled` , szükségszerűen a visszatérési típusának kell lennie `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`nem aktív

Ennek megfelelően a `Adjoint Y(q1)` `Adjoint` rendszer a műveletre alkalmazza az `Y` új művelet létrehozását, és az új műveletet a következőre alkalmazza: `q1` .
Az új művelet ugyanazzal az aláírással és típussal rendelkezik, mint az alapművelet `Y` .
Ebben az esetben az új művelet is támogatja `Adjoint` , és csak akkor támogatja, `Controlled` Ha az alapművelet nem volt.
A kihasználó a `Adjoint` saját inverze, azaz `Adjoint Adjoint Op` mindig ugyanaz, mint `Op` .

#### <a name="controlled-functor"></a>`Controlled`nem aktív

Hasonlóképpen `Controlled X(controls, target)` alkalmazza a `Controlled` műveletet a `X` műveletre egy új művelet létrehozásához, és az új műveletet a és a rendszerre alkalmazza `controls` `target` .

> [!NOTE]
> A Q # esetében az ellenőrzött verziók mindig a vezérlési qubits tömbjét foglalják magukban, és az ellenőrzés mindig a számítási ( `PauliZ` ) `One` állapot, a $ \ket $ qubits összes vezérlője alapján történik {1} .
> A más állapotokon alapuló vezérlést úgy érheti el, hogy a megfelelő egységes műveletet alkalmazza a vezérlési qubits az ellenőrzött művelet előtt, majd alkalmazza az egységes művelet inverzét az ellenőrzött művelet után.
> Ha például egy `X` műveletet egy vezérlő qubit egy vezérelt művelet előtt és után alkalmaz, akkor a művelet az `Zero` adott qubit állapotára ($ \ket $) irányítja a műveletet, és az állapotra vonatkozó {0} `H` vezérlők előtt és után alkalmaz egy műveletet `PauliX` `One` , azaz az-1 sajátérték a Pauli X, a $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt $ helyett, nem pedig {2} az `PauliZ` `One` állapotot.

Egy műveleti kifejezés miatt új műveleti kifejezés is létrehozható az elválasztó használatával `Controlled` .
Az új művelet aláírása az eredeti művelet aláírásán alapul.
Az eredmény típusa azonos, de a bemeneti típus egy kétrekordos qubit tömb, amely a vezérlő qubit (ka) t az első elemként, az eredeti művelet argumentumait pedig második elemként tárolja.
Az új művelet támogatja a- `Controlled` t, és csak akkor támogatja, `Adjoint` Ha az eredeti művelet megtörtént.

Ha az eredeti művelet csak egyetlen argumentumot vett igénybe, akkor az önálló [rekordos egyenértékűség](xref:microsoft.quantum.guide.types) a játékba kerül.
Például a a `Controlled X` művelet ellenőrzött verziója `X` . 
`X`típusa van `(Qubit => Unit is Adj + Ctl)` , ezért `Controlled X` a Type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; egypéldányos egyenértékűség miatt ez megegyezik a következővel: `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Ha az alapművelet több argumentumot is vett igénybe, ne felejtse el zárójelek közé helyezni a művelet ellenőrzött verziójának megfelelő argumentumait, hogy azok egy rekordba legyenek konvertálva.
Például a a `Controlled Rz` művelet ellenőrzött verziója `Rz` . 
`Rz`típusa van `((Double, Qubit) => Unit is Adj + Ctl)` , ezért `Controlled Rz` típusa van `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Tehát `Controlled Rz(controls, (0.1, target))` érvényes hívás lenne `Controlled Rz` (jegyezze fel a zárójeleket `0.1, target` ).

Egy másik példaként `CNOT(control, target)` a is megvalósítható `Controlled X([control], target)` . Ha egy célt két vezérlő qubits (CCNOT) vezérel, használjon egy `Controlled X([control1, control2], target)` utasítást.

#### `Controlled Adjoint` 

A és a-elválasztók `Controlled` `Adjoint` ingázás, így nincs különbség a alkalmazása `Controlled Adjoint Op` vagy a `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Vezérelt és Adjoint implementációk meghatározása

Az előző példákban szereplő első művelet deklarációjában a műveletek és az aláírásokkal, illetve a műveletekkel `BitFlip` `DecodeSuperdense` lettek definiálva `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .
A `DecodeSuperdense` mértékek beleszámítása nem egy egységes művelet, ezért nem léteznek szabályozott, nem adjoint specializációk (az ilyen művelet visszaadására vonatkozó követelmény visszahívása `Unit` ).
Mivel azonban `BitFlip` egyszerűen végrehajtja az egységes <xref:microsoft.quantum.intrinsic.x> műveletet, megadhatja azt mindkét specializációval.

Ez a szakasz részletesen ismerteti, hogyan lehet felvenni a szakosodások létezését a Q # műveleti deklarációba, így lehetővé teszi számukra, hogy meghívják őket a vagy a-rel együtt `Adjoint` `Controlled` .
Ha további információt szeretne arról, hogy milyen helyzetek érvényesek, vagy nem érvényesek bizonyos specializációk bejelentésére, tekintse meg a jelen cikkben szereplő, [a specializációk érvényességét meghatározó körülményeket](#circumstances-for-validly-defining-specializations) .

A művelet jellemzői határozzák meg, hogy milyen típusú elválasztók alkalmazhatók a deklarált műveletre, és milyen hatással vannak rájuk. Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható, pontosabban a következő műveletekkel kapcsolatos megjegyzésekkel: vagy `is Adj` , `is Ctl` vagy `is Adj + Ctl` .
Az egyes specializációk tényleges implementációja *implicit módon* vagy *explicit módon* definiálva lehet.

### <a name="implicitly-specifying-implementations"></a>Implementációk implicit meghatározása

Ebben az esetben a műveleti deklaráció törzse kizárólag az alapértelmezett implementációból áll. Például:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Itt az egyes implicit módon deklarált specializációhoz tartozó implementációt automatikusan generálja a fordító, amelyet a vagy a rendszer `Adjoint` használatakor kell végrehajtani `Controlled` .

Így a hívása `Adjoint PrepareEntangledPair` azt eredményezi, hogy a fordító végrehajtja a adjoint, `CNOT` majd a adjoint `H` .
Ezek az egyéni műveletek önmagukban is adjoint, így az eredményül kapott `Adjoint PrepareEntangledPair` művelet csupán a alkalmazásból, majd a rendszerből áll `CNOT(here, there)` `H(here)` .
Ebből kifolyólag ezt az `DecodeSuperdense` előző példában több tömörítéssel is megírhatja, ha a adjoint segítségével `PrepareEntangledPair` átalakítja a kusza állapotot egy nem összeillesztett qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

A deklarációban szereplő műveleti jellemzőkkel rendelkező Megjegyzés hasznos annak biztosításához, hogy a fordító automatikusan generáljon más specializációkat az alapértelmezett implementáció alapján. 

Számos fontos korlátozást kell figyelembe venni, amikor a rendszer megtervezi, hogy milyen műveleteket kell megterveznie.
A legtöbb kritikus jelentőséggel bír, ha egy olyan műveletre specializálódott, amely bármely más művelet kimeneti értékét használja, *nem* lehet automatikusan generálni a fordítótól, mert nem egyértelmű, hogy az ilyen műveletekben szereplő utasítások hogyan rendezhetők át ugyanezen hatás megszerzése érdekében.

Ezért gyakran érdemes explicit módon megadnia a különböző implementációkat.

### <a name="explicitly-specifying-implementations"></a>Implementációk explicit meghatározása

Abban az esetben, ha a fordító nem tudja előállítani a megvalósítást, explicit módon megadhatja. Az ilyen explicit specializációs nyilatkozatok megfelelő *generációs irányelvből* vagy felhasználó által definiált implementációból állhatnak.
A következőkben a lehetőségek teljes köre látható, néhány példa a explicit specializációra. 


#### <a name="explicit-specialization-declarations"></a>Explicit specializációs deklarációk

A Q # műveletei a következő explicit specializációs deklarációkat tartalmazhatják:

- A `body` specializáció meghatározza a művelet végrehajtását, és nem alkalmazta a műveletet.
- A `adjoint` specializáció meghatározza a művelet megvalósítását az `Adjoint` alkalmazottal.
- A `controlled` specializáció meghatározza a művelet megvalósítását az `Controlled` alkalmazottal.
- A `controlled adjoint` specializáció meghatározza a művelet megvalósítását mind a, mind a által alkalmazott operációs rendszersel `Adjoint` `Controlled` .
  Ez a specializáció is elnevezhető `adjoint controlled` , mivel a két elválasztó.


A műveletek specializációja a specializációs címkéből (például vagy) áll, amelyet az alábbiak `body` `adjoint` egyike követ:

- Az alábbi módon leírt explicit deklaráció.
- Egy *irányelv* , amely közli a fordítóval, *Hogyan* hozhatja ki a specializációt, az egyik:
  - `intrinsic`, amely azt jelzi, hogy a célszámítógép biztosítja a specializációt.
  - `distribute`, a és a `controlled` `controlled adjoint` specializációk használatával.
    A használatakor `controlled` azt jelzi, hogy a fordítónak ki kell számítania a specializációt úgy, hogy az `Controlled` összes műveletére alkalmazza a-t `body` .
    A használatakor `controlled adjoint` azt jelzi, hogy a fordítónak a `Controlled` specializáció összes műveletére alkalmazva kell kiszámítani a specializációt `adjoint` .
  - `invert`, ami azt jelzi, hogy a fordítónak ki kell számítania a `adjoint` specializációt úgy, hogy visszaállítja a `body` műveletet, például megfordítja a műveletek sorrendjét, és alkalmazza a adjoint.
    A használatakor `adjoint controlled` Ez azt jelzi, hogy a fordítónak a specializáció megfordításával kell kiszámítani a specializációt `controlled` .
  - `self`, amely azt jelzi, hogy a adjoint specializáció megegyezik a `body` specializációval.
    `self`A használata jogi a `adjoint` és a `adjoint controlled` specializációhoz.
    A `adjoint controlled` esetében `self` azt jelenti, hogy a `adjoint controlled` specializáció ugyanaz, mint a `controlled` specializáció.
  - `auto`, jelezve, hogy a fordítónak ki kell választania egy megfelelő irányelvet az alkalmazáshoz.
    `auto`A specializációhoz nem használható `body` .

Az irányelvek és `auto` mind a záró pontosvesszőt igénylik `;` .
Az `auto` irányelv a következő létrehozott irányelvre lesz feloldva, ha a megadott explicit nyilatkozattal `body` rendelkezik:

- A `adjoint` specializáció a direktíva alapján jön létre `invert` .
- A `controlled` specializáció a direktíva alapján jön létre `distribute` .
- A `adjoint controlled` specializáció a direktíva alapján jön létre `invert` , ha explicit deklaráció `controlled` van megadva, de nem egyet `adjoint` , és `distribute` egyéb módon.

> [!TIP]   
> Ha egy művelet önadjoint, explicit módon megadhatja a adjoint vagy az irányított adjoint specializációt az `self` előállítási irányelv alapján, hogy a fordító felhasználhassa ezeket az információkat optimalizálási célokra.

A felhasználó által definiált implementációt tartalmazó specializációs nyilatkozat egy argumentumból áll, amelyet a specializációt megvalósító Q # kóddal rendelkező utasítási blokk követ.
A argumentumok listájában `...` a rendszer a művelet egészére vonatkozóan deklarált argumentumokat jelöli.
`body`És esetében `adjoint` az argumentumok listájának mindig a `(...)` következőnek kell lennie: és esetében `controlled` `adjoint controlled` az argumentumok listájának olyan szimbólumnak kell lennie, amely a vezérlési qubits tömbjét jelöli, majd a jelet `...` zárójelek közé kell tenni, például: `(controls,...)` .

### <a name="examples"></a>Példák

A művelet deklarációja olyan egyszerű lehet, mint a következő, amely meghatározza a primitív Pauli X műveletet:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Vegye figyelembe, hogy a Pauli X művelet adjoint a direktíva határozza meg, `self` mert a definíció szerint a `X` saját inverze.

A korábbi `PrepareEntangledPair` példában a kód egyenértékű a következő kóddal, amely explicit specializációs deklarációkat tartalmaz: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan kell előállítani a specializáció megvalósítását.

#### <a name="user-defined-specialization-implementation"></a>Felhasználó által definiált specializációs implementáció

Ha a fordító nem tud automatikusan létrehozni egy bizonyos specializáció megvalósítását, vagy ha hatékonyabb megvalósítást lehet megadni, manuálisan is meghatározhatja a megvalósítást.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
Az előző példában `adjoint invert;` azt jelzi, hogy a adjoint specializációt úgy kell létrehozni, hogy visszaállítja a törzs megvalósítását, és `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint specializációt úgy kell létrehozni, hogy visszaállítja a szabályozott specializáció adott implementációját.

Ha az alapértelmezett törzsön kívül egy vagy több specializációt is explicit módon kell deklarálni, akkor az alapértelmezett törzs megvalósítását megfelelő specializációs nyilatkozatba is kell becsomagolni:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>A specializációk érvényes meghatározásának körülményei

#### <a name="operation-declarations-with-adjointcontrolled"></a>Adjoint/vezérelt üzemeltetési nyilatkozatok

A adjoint vagy az ellenőrzött verziók nélküli műveletet kell megadnia. Például a mérési műveletek egyike sem invertálható, sem ellenőrizhető.

Egy művelet támogatja a `Adjoint` és a-kezelőket, `Controlled` Ha a nyilatkozata tartalmazza a megfelelő specializációk implicit vagy explicit nyilatkozatát.

Az explicit módon bejelentett adjoint/vezérelt specializáció egy adjoint/vezérelt specializáció létezését feltételezi. 

Egy olyan művelet esetében, amelynek a törzse ismétlődik, amíg-sikeres hurkokat tartalmaz, állítson be utasítások, mérések, visszaküldési utasítások vagy más olyan műveletekre irányuló hívásokat, amelyek nem támogatják az `Adjoint` adjoint-specializációt, és nem lehetséges, hogy automatikusan generáljon egy, az `invert` vagy az `auto` irányelvet követő specializáció

Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat is tartalmaz, amelyek nem támogatják az üzemen kívüli tevékenységet `Controlled` , nem lehetséges, hogy automatikusan generál egy szabályozott specializációt a `distribute` vagy a `auto` direktíva után.

#### <a name="controlled-adjoint"></a>Vezérelt Adjoint

Egy művelet ellenőrzött adjoint-verziója határozza meg, hogyan kell megvalósítani a művelet adjoint egy kvantum által vezérelt verzióját.
Az adjoint-verzióval nem rendelkező műveletet kell megadnia. például a mérési műveletek nem rendelkeznek szabályozott adjoint-verzióval, mert nem ellenőrizhetők és nem invertálható.

Egy művelet vezérelt adjoint-specializációjának léteznie kell, ha a adjoint és a szabályozott specializáció is létezik. Ebben az esetben az irányított adjoint specializáció létezését következtetik ki. Ha nincs explicit módon definiált implementáció, a fordítás a megfelelő specializációt hozza létre.

Egy olyan művelet esetében, amelynek a törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem rendelkeznek szabályozott adjoint-verzióval, a adjoint-specializációt automatikusan generálja a `invert` , `distribute` vagy az `auto` direktíva nem lehetséges.


### <a name="type-compatibility"></a>Típus kompatibilitása

Használjon olyan műveletet, amelyben további, a rendszer által támogatott, de az aláírással rendelkező művelet is használható. Ha például egy típusú műveletet használ, bárhol használhatja a `(Qubit => Unit is Adj)` típusú műveletet `(Qubit => Unit)` .

A Q # *a* hívható visszatérési típusok tekintetében a következő: egy típust visszaadó meghívható, amely `'A` kompatibilis az ugyanazzal a bemeneti típussal és a (z) rendszerrel kompatibilis eredményhalmaz típussal `'A` .

A Q # *contravariant típusparamétert* a bemeneti típusok tekintetében: egy olyan meghívót, amely bemenetként fogadja a típust, `'A` és kompatibilis az ugyanazzal az eredménnyel, és egy olyan bemeneti típussal, amely kompatibilis a szolgáltatással `'A` .

Ez a következő definíciók miatt történik.

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

képes vagy

- Hívja meg a függvényt az `ConjugateInvertWith` `inner` egyik vagy a argumentumával `Invert` `ApplyUnitary` .
- Hívja meg a függvényt `ConjugateUnitaryWith` egy `inner` argumentummal `ApplyUnitary` , de nem `Invert` .
- Egy típus értékének visszaadása a következőből: `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` .

> [!IMPORTANT]
> A Q # 0,3 jelentős változást vezetett be a felhasználó által definiált típusok viselkedésében.

A felhasználó által definiált típusokat az alapul szolgáló típus burkolt verziójaként, nem pedig altípusként kezeli a rendszer.
Ez azt jelenti, hogy a felhasználó által definiált típus értéke nem használható, ha a mögöttes típus értéke a várt érték.


### <a name="conjugations"></a>Conjugations

A klasszikus BITS-vel szemben a kvantum-memória felszabadítása valamivel nagyobb mértékben történik, mivel a qubits vakon alaphelyzetbe állítása nem kívánt hatással lehet a fennmaradó számításra, ha a qubits továbbra is összefonódik. Ezek a hatások elkerülhetők a memória felszabadítása előtt végrehajtott számítások megfelelő "visszavonása" esetén. A kvantum-számítástechnika általános mintája a következő: 

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

A 0,9-es kiadástól kezdve a Q # támogatja az előző transzformációt megvalósító ragozó utasítást. Az utasítás használatával a művelet a `ApplyWith` következő módon valósítható meg:

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
Egy ilyen ragozás-utasítás sokkal hasznosabb lehet, ha a külső és a belső átalakítások nem állnak rendelkezésre azonnal műveletekként, hanem sokkal kényelmesebbek egy több utasításból álló blokk leírására. 

A blokkon belül definiált utasítások inverz átalakítását a fordító automatikusan hozza létre, és az Apply-Block befejeződése után fut.
Mivel a blokk részeként használt változó változók nem használhatók fel az alkalmazás-blokkban, a generált transzformáció garantált, hogy a adjoint a blokkon belül. 


## <a name="defining-new-functions"></a>Új függvények definiálása

A functions kizárólag determinisztikus, a klasszikus rutinok a Q #-ban, amelyek különböznek a műveletektől, és nem megengedett, hogy a kimeneti érték kiszámításán kívül más effektusok is legyenek.
Különösen a függvények nem hívhatnak meg műveleteket; qubits bevonása, lefoglalása vagy kölcsönzése; véletlenszerű számok mintavételezése; Ellenkező esetben a bemeneti értéken kívüli állapot függ egy függvénynek.
Ennek következményeként a Q # függvények *tisztán*vannak rendelve, hogy mindig ugyanazokat a bemeneti értékeket rendelik ugyanahhoz a kimeneti értékekhez.
Ez a viselkedés lehetővé teszi, hogy a Q # fordítóprogram biztonságosan átrendezje a függvények meghívását a műveleti specializációk létrehozásakor.

Minden Q # forrásfájl tetszőleges számú funkciót meghatározhat.
A függvények nevének egyedinek kell lennie a névtéren belül, és nem ütközhet a művelet vagy a típus nevével.

A függvények definiálása hasonlóan működik a művelet definiálásához, azzal a kivétellel, hogy egy függvényhez nem lehet adjoint vagy vezérelt specializációt meghatározni.
Ilyenek például a következők:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

vagy 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Klasszikus Logic in functions = = jó

Ha ez lehetséges, hasznos lehet a klasszikus logikát kiírni a függvények helyett, hogy a műveletek könnyebben használhassák azt. Ha például a korábbi `Square` deklarációt *műveletként*írta volna, akkor a fordító nem tudta garantálni, hogy ugyanazt a bemenetet ugyanazzal a kimenettel fogja létrehozni.

A függvények és a műveletek közötti különbség kihangsúlyozása érdekében vegye figyelembe, hogy egy véletlenszerűen kiválasztott számnak a Q #-műveletből való klasszikus mintavételezési problémája:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Minden alkalommal `U` , amikor meghívja a szolgáltatást, egy másik művelettel rendelkezik `target` .
Különösen a fordító nem tudja garantálni, hogy ha egy `adjoint auto` specializációs nyilatkozatot ad hozzá a alkalmazáshoz `U` , akkor az `U(target); Adjoint U(target);` identitásként viselkedik (azaz No-op).
Ez sérti a [vektorokban és mátrixokban](xref:microsoft.quantum.concepts.vectors)definiált adjoint definícióját, amely lehetővé teszi, hogy a fordító automatikusan létrehozzon egy adjoint specializációt egy olyan műveletben, amelyben a művelet meghívása <xref:microsoft.quantum.math.randomreal> megszakítja a fordító által biztosított garanciákat; <xref:microsoft.quantum.math.randomreal> egy olyan művelet, amelynek nem létezik adjoint vagy vezérelt verziója.

Másfelől pedig lehetővé teszi, hogy a függvények olyan hívásokat engedélyezzenek, mint például `Square` a biztonságos, és biztosítja a fordító számára, hogy a kimenet stabilitásának megőrzése érdekében csak a bemenetet kell megőriznie `Square` .
Így a lehető legtöbb klasszikus logikát elkülönítheti a functions szolgáltatásban, így a logika más funkciókban és műveletekben is felhasználható.


## <a name="generic-type-parameterized-callables"></a>Általános (típus-paraméteres) Callables

Számos, a definiálni kívánt függvény és művelet ténylegesen nem támaszkodik a bemenetek típusaira, hanem csak egy másik függvényen vagy műveleten keresztül implicit módon használják a saját típusait.
Tegyük fel például, hogy a *Térkép* fogalma számos funkcionális nyelvhez közös. a függvény $f (x) $ és Values $ \{ x_1, x_2, \dots, x_n \} $, Map egy új gyűjteményt ad vissza: $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
Ha ezt a Q #-ban szeretné megvalósítani, használja ki azt a tényt, hogy a functions első osztályú.
Íme egy gyors példa, amely `Map` `T` helyőrzőként használja a szükséges típusokat.

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vegye figyelembe, hogy ez a függvény ugyanúgy néz ki, mint amit a ténylegesen helyettesít.
Az egész számokból a Paulis-ra történő leképezések például a lebegőpontos számok és a karakterláncok közötti térképre hasonlítanak.

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Elvileg írhat egy verziót `Map` minden olyan típushoz, amely találkozik, de ez számos nehézséget jelent.
Ha például hibát talál a alkalmazásban `Map` , akkor győződjön meg arról, hogy a javítást a összes verziójában egységesen alkalmazza `Map` .
Emellett, ha új rekordot vagy UDT hoz létre, akkor az új típussal együtt létre kell majd állítania egy újat is `Map` .
Ez egy kis mennyiségű ilyen funkció esetében is eltartható, mivel a több és több funkciója is ugyanolyan formában van, mint az `Map` , hogy az új típusok bevezetésének díja aránytalanul nagy lesz a meglehetősen rövid sorrendben.

A probléma nagy része azonban abból ered, hogy nem adta meg a fordítónak a különböző verzióinak felismeréséhez szükséges információkat `Map` .
Gyakorlatilag azt szeretné, hogy a fordító a `Map` q # *types* és a q # függvények közül valamilyen matematikai függvényt kezelje.

A Q # formalizes ezt a fogalmat azáltal, hogy lehetővé teszi a függvények és műveletek *típus paramétereit*, valamint a szokásos rekord paramétereit.
Az előző példákban úgy gondolja, hogy `Map` `Int, Pauli` az első esetben, a második esetben pedig a type paramétert adja meg `Double, String` .
A legtöbb esetben használja ezeket a típusú paramétereket, mintha a szokásos típusok lennének. Paraméterek típusú értékek használata tömbök és rekordok, a függvények és a műveletek hívásához, valamint a szokásos vagy változtatható változókhoz való hozzárendeléshez.

> [!NOTE]
> A közvetett függőség legszélsőségesebb esete a qubits, ahol a Q # program nem hivatkozhat közvetlenül a típus struktúrájára, `Qubit` azonban ezeket a típusokat más műveletekre és funkciókra **kell** átadnia.

Ha visszatér a korábbi példához, akkor láthatja, hogy a `Map` Type paraméterrel kell rendelkeznie, az egyik pedig a bemenet, a másik pedig a `fn` kimenetét jelöli `fn` .
A Q #-ban ez a szög zárójelek (azaz `<>` nem brakets $ \braket $!) hozzáadásával történik, {} a deklarációban szereplő függvény vagy művelet neve után, valamint az egyes típusparaméter-paraméterek listázásával.
Az egyes típusparaméter-paraméterek nevének egy kullancstal kell kezdődnie `'` , amely azt jelzi, hogy ez egy típusparaméter, nem pedig egy egyszerű típus (más néven *konkrét* típus).
Így `Map` van írva:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vegye figyelembe, hogy a definíciója `Map<'Input, 'Output>` nagyon hasonlít a previoius-verziókhoz.
Az egyetlen különbség, hogy explicit módon tájékoztatta a fordítót, amely `Map` nem függ közvetlenül attól, hogy mi `'Input` és milyen `'Output` , de két típust használ, ha közvetve használja őket `fn` .
Ha így lett meghatározva, akkor úgy `Map<'Input, 'Output>` hívhatja meg, mintha egy szokványos függvény lenne:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Az általános függvények és műveletek írása egy olyan hely, ahol a "rekord-in rekord kijelentkezése" nagyon hasznos módszer a Q # függvények és műveletek gondolkodására.
> Mivel minden függvény pontosan egy bemenetet vesz át, és pontosan egy kimenetet ad vissza, a típus bemenete `'T -> 'U` *bármilyen* Q # függvénynek felel meg.
> Hasonlóképpen bármilyen műveletet átadhat egy típusú bemenetnek `'T => 'U` .

Második példaként vegye figyelembe, hogy milyen kihívással kell elírnia egy olyan függvényt, amely két másik függvény összeállítását adja vissza:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Itt pontosan meg kell adnia `A` `B` `C` a következőt:, és így szigorúan korlátozza az új függvény segédprogramját `Compose` .
Az összes után `Compose` csak a, a és a, a `A` `B` és a `C` *használatával* függ `innerFn` `outerFn` .
Alternatív megoldásként hozzáadhat olyan típusú paramétereket, amelyek `Compose` azt jelzik, hogy a (z) *any* és a (z) és a (z) a következő `A` `B` `C` paraméterekkel `innerFn` egyezik `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

A Q # standard kódtárak számos ilyen típusú paraméterrel rendelkező műveletet és funkciót biztosítanak, hogy a magasabb rendű vezérlési folyamat könnyebben kifejezhető legyen.
Ezeket a [Q # standard Library útmutatóban](xref:microsoft.quantum.libraries.standard.intro)tovább tárgyaljuk.


## <a name="callables-as-first-class-values"></a>Callables első osztályú értékként

Az egyik kritikus módszer, amellyel a vezérlési folyamat és a klasszikus logika a függvények helyett functions használatával történik, hogy a Q # *első osztályú*műveleteit és funkcióit használják.
Ez azt eredményezi, hogy a nyelv minden értéke a saját jobb oldalán van.
Például a következőkben teljesen érvényes Q # kód van, ha egy kicsit indirekt:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Az `ourH` előző kódrészletben szereplő változó értéke ezután a művelet <xref:microsoft.quantum.intrinsic.h> , például a többi művelethez hasonló érték hívható meg.
Ezzel a képességgel olyan műveleteket írhat, amelyek a bemenetük részeként műveleteket hajtanak végre, és a magasabb rendű vezérlési folyamatokra vonatkozó fogalmakat alkotnak.
Képzelje el például, hogy a "Square" műveletet úgy szeretné használni, hogy kétszer alkalmazza azt ugyanarra a cél qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Műveletek visszaküldése egy függvényből

Fontos kiemelni, hogy a kimenetek részeként is visszatérhetnek a műveletekhez, így a klasszikus feltételes logika valamilyen módon elkülöníthető klasszikus függvényként, amely egy művelet formájában egy kvantum-program leírását adja vissza.
Egyszerű példaként tekintse meg a teleportálás példáját, amelyben a kétbites klasszikus üzenetet fogadó fél az üzenetet arra használja, hogy dekódolja a qubit a megfelelő teleportált állapotba.
Ezt megírhatja egy függvényben, amely a két klasszikus bitet veszi át, és visszaadja a megfelelő dekódolási műveletet.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Ez az új függvény valóban egy függvény, abban az esetben, ha a és az azonos értékeit hívja meg `hereBit` `thereBit` , mindig ugyanazt a műveletet kapja vissza.
Így a dekóder biztonságosan futhat a műveletekben anélkül, hogy meg kellene indokolnia, hogy a dekódolási logika hogyan működjön együtt a különböző műveleti szakosodások definíciói alapján.
Ez azt jelenti, hogy a függvényben található klasszikus logika el van különítve, és garantálva van, hogy a függvény hívása legyen büntetlenül, amíg a bevitel megmarad.


## <a name="partial-application"></a>Részleges alkalmazás

A műveleteknek a *részleges alkalmazás*használatával történő visszaadására szolgáló függvények sokkal nagyobb mértékben is megadhatók, amelyekben a bemenet egy vagy több részét egy függvénynek vagy műveletnek kell megadnia anélkül, hogy ténylegesen meghívja azt. A `ApplyTwice` fenti példában azt jelezheti, hogy nem kívánja megadni, azonnal, hogy a bemeneti művelet melyik qubit vonatkozzon:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Ebben az esetben a helyi változó `twiceOp` a részben alkalmazott műveletet tartalmazza `ApplyTwice(op, _)` , ahol `_` a a bemenet azon részeit jelzi, amelyek még nincsenek megadva.
Ha a következő sorban hívja meg a hívást, a rendszer a `twiceOp` részben alkalmazott művelethez továbbítja a bemenetet az eredeti művelethez.
Így az előző kódrészlet gyakorlatilag azonos ahhoz, hogy közvetlenül meghívja őket `ApplyTwice(op, target)` , mentse az új helyi változót, így késleltetheti a hívást, miközben a bemenet egyes részeit is megadja.

Mivel egy részlegesen alkalmazott művelet valójában nem lett meghívva, amíg a teljes bemenet meg nem lett biztosítva, nyugodtan részben is alkalmazhat műveleteket a függvényeken belül.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Elméletileg a klasszikus logika `SquareOperation` sokkal jobban érintett, de továbbra is el van különítve a többi művelettől, mert az garantálja, hogy a fordító a functions szolgáltatással kapcsolatban tud nyújtani. A Q # standard könyvtár ezt a módszert használja a klasszikus vezérlési folyamat kifejezésére, így a kvantum-programok könnyen használhatók.


## <a name="recursion"></a>Rekurzió

A Q # callables közvetlenül vagy közvetve rekurzívak.
Vagyis egy művelet vagy függvény meghívhatja önmagát, vagy hívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.

A rekurzió használatának két fontos megjegyzése van, azonban:

- A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.
  Ez az interferencia jelentős hatással lehet az algoritmus végrehajtási idejére.
- Ha a tényleges kvantum-eszközön fut, előfordulhat, hogy a rendelkezésre állási terület korlátozott, ezért a mélyebb rekurzió hibát okozhat.
  A Q # Compiler és a Runtime nem azonosítja és optimalizálja a farok rekurzióját.

## <a name="next-steps"></a>Következő lépések

További tudnivalók a Q #-ban található [változókról](xref:microsoft.quantum.guide.variables) .