---
title: 'Műveletek és függvények a Q-ban #'
description: Műveletek és függvények definiálása és hívása, valamint az ellenőrzött és adjoint műveletekre vonatkozó specializációk.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431070"
---
# <a name="operations-and-functions-in-q"></a>Műveletek és függvények a Q-ban #

## <a name="defining-new-operations"></a>Új műveletek definiálása

A műveletek a Q # legfontosabbak.
A deklarációt követően meghívhatók a klasszikus .NET-alkalmazásokból, például szimulátor használatával vagy a Q #-on belüli egyéb műveletekkel.
A Q # által meghatározott minden művelet hívhat meg tetszőleges számú egyéb műveletet, beleértve a nyelv által meghatározott beépített belső műveleteket is. A belső műveletek meghatározásának konkrét módja a célszámítógéptől függ.
A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.

A Q # forrásfájl tetszőleges számú műveletet meghatározhat.
A művelet nevének a névtéren belül egyedinek kell lennie, és nem ütközhet típus-vagy függvénynév-névvel.

A műveleti deklaráció a kulcsszóból áll, amelyet a művelet nevét, a művelethez tartozó `operation` argumentumokat definiáló típust, egy kettőspontot, egy Type jegyzetet ad meg, amely a művelet `:` eredményének típusát írja le, opcionálisan a művelet jellemzőit, a nyitó kapcsos zárójelet `{` , a műveleti deklaráció törzsét és egy záró záró zárójelet `}` .

Mindegyik művelet egy bemenetet hoz létre, kimenetet állít elő, és meghatározza egy vagy több műveleti specializáció megvalósítását.
A lehetséges szakosodások, valamint a definiálása/meghívása alább részletesebben olvashatók.
Egyelőre a következő műveletnek kell megfontolnia, amely csak az alapértelmezett szövegtörzset határozza meg, és egyetlen qubit használ a bemenetként, majd meghívja a beépített <xref:microsoft.quantum.intrinsic.x> műveletet a bemeneten:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A kulcsszó `operation` megkezdi a művelet definícióját, és ezt a nevet követi; itt: `BitFlip` .
Ezután a bemenet típusa a következőként van definiálva `Qubit` :, valamint egy név, amely az `target` új műveleten belüli bemenetre hivatkozik.
Hasonlóképpen, az `Unit` határozza meg, hogy a művelet kimenete üres.
Ezt hasonlóan a `void` C#-ban és más kötelező nyelvekhez használják, és ez egyenértékű az `unit` F # és más funkcionális nyelvek esetében.

A műveletek több érdekes típust is visszaadhatnak, mint a `Unit` .
A <xref:microsoft.quantum.intrinsic.m> művelet például egy típusú kimenetet ad vissza `Result` , amely a mérés végrehajtását jelöli. Egy művelet kimenetét átadhatja egy másik műveletnek, vagy használhatja azt a `let` kulcsszóval egy új változó definiálásához.

Ez lehetővé teszi a klasszikus számításokat, amelyek alacsony szinten működnek a kvantum-műveletekkel, például a [sűrűbb kódolásban](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

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
> Ezután több bemenet és kimenet is képviselteti magát a *rekordok*használatával, amely egyszerre több értéket gyűjt össze egyetlen értékkel.
> Informálisan azt mondjuk, hogy a Q # egy "rekordos kijelentkezés" nyelv.
> Ezt a fogalmat követve `()` az "üres" rekordnak kell szerepelnie, amelynek típusa a következő: `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Vezérelt és Adjoint műveletek

Ha egy művelet egy egységes átalakítást valósít meg, a Q # számos műveletének esetében, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen. Egy művelet *adjoint* -specializálása meghatározza, hogy a művelet milyen hatással van az "inverz" értékre, míg a *szabályozott* specializáció meghatározza, hogy a művelet hogyan működik, ha az alkalmazás egy adott kvantum-regiszter állapotára van feltétele.

A Adjoints elengedhetetlen a kvantum-számítási feladatok számos aspektusa szempontjából. Az alábbiakban a [conjugations](#conjugations) szakaszban talál egy ilyen helyzetet, amely egy hasznos Q # programozási technikával együtt tárgyalt.

Egy művelet ellenőrzött verziója olyan új művelet, amely hatékonyan alkalmazza az alapműveletet, ha az összes vezérlő qubits megadott állapotban van.
Ha a vezérlő qubits van, akkor az alapszintű műveletet a rendszer következetesen alkalmazza a Felfekvés megfelelő részére.
Így a rendszer gyakran használja az ellenőrzött műveleteket a felakadás létrehozásához.

Természetesen egy *vezérelt adjoint* specializáció is létezhet, amely meghatározza egy művelet adjoint vezérelt alkalmazását.

> [!NOTE]
> Ha $U $ egy művelet által megvalósított egységes átalakítás `U` , akkor `Adjoint U` az egységes átalakítást jelöli $U ^ \dagger $, amely a komplex konjugátum átültetése.
> Egy művelet egymást követő alkalmazása után a adjoint állapota változatlan marad, ahogy azt az a tény mutatja, hogy $UU ^ \dagger = U ^ \dagger U = \id $, az Identity Matrix.
> Egy vezérelt művelet egységes ábrázolása valamivel árnyaltabb, de további részleteket a [Quantum Computing-fogalmak: több qubits](xref:microsoft.quantum.concepts.multiple-qubits)is talál.

A következő szakasz azt ismerteti, hogyan hívhatja meg ezeket a különböző szakterületeket a Q # kódjában.
Az alábbiakban részletesen ismertetjük, hogyan definiálhat műveleteket a támogatáshoz.

### <a name="calling-operation-specializations"></a>Hívási művelet specializációi

A *Q # egy olyan* gyár, amely új műveletet határoz meg egy másik műveletből.
A Q # két standard, a és a `Adjoint` `Controlled` .

Az új művelet megvalósításának meghatározásakor az üzemben lévők az alapművelet megvalósításához férnek hozzá.
Így a fellépők összetettebb funkciókkal rendelkezhetnek, mint a hagyományos magasabb szintű függvények. A Q # Type rendszer nem rendelkezik képviselettel a következőben:. Ezért jelenleg nem lehet őket egy változóhoz kötni, vagy argumentumként átadni őket. 

A rendszer egy, a műveletre való alkalmazásával egy új műveletet ad vissza.
Például az a művelet, amely abból ered, hogy a rendszer a `Adjoint` `Y` műveletet a művelettel a műveletre alkalmazza `Adjoint Y` .
Előfordulhat, hogy az új művelet a többi művelethez hasonlóan hívható meg.
Ahhoz, hogy egy művelet támogassa a és/vagy az elhasználók alkalmazását `Adjoint` `Controlled` , a visszatérési típusának szükségszerűen kell lennie `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`nem aktív

Így `Adjoint Y(q1)` a Adjoint a `Y` művelethez alkalmazza az új művelet létrehozását, és az új műveletet alkalmazza a következőre: `q1` .
Az új művelet ugyanazzal az aláírással és típussal rendelkezik, mint az alapművelet `Y` .
Az új művelet azt is lehetővé teszi, hogy a `Adjoint` , és csak akkor engedélyezze, `Controlled` Ha az alapművelet volt.
A Adjoint-tulajdonos a saját inverze. vagyis `Adjoint Adjoint Op` mindig ugyanaz, mint a `Op` .

#### <a name="controlled-functor"></a>`Controlled`nem aktív

Hasonlóképpen `Controlled X(controls, target)` alkalmazza az ellenőrzött futtatót a `X` műveletre új művelet létrehozásához, és az új műveletet a és a értékre alkalmazza `controls` `target` .

> [!NOTE]
> A Q #-ban az ellenőrzött verziók mindig a vezérlési qubits egy tömbjét foglalják magukban, és a megadott állapot mindig az összes vezérlési qubits a számítási ( `PauliZ` ) `One` állapotban, a $ \ket $ értékben {1} .
> A más állapotokon alapuló vezérlést úgy érheti el, ha a megfelelő egységes műveletet alkalmazza a vezérlő qubits az ellenőrzött művelet előtt, majd az egységes művelet inverzét alkalmazza az ellenőrzött művelet után.
> Ha például egy `X` műveletet egy vezérlő qubit egy vezérelt művelet előtt és után alkalmaz, akkor a művelet az `Zero` adott qubit állapotára ($ \ket $) irányítja a műveletet {0} , és a művelet `H` előtt és után is szabályozni fogja az állapotot `PauliX` `One` , azaz az-1 sajátérték a Pauli X, a $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt $ helyett, nem pedig {2} az `PauliZ` `One` állapotot.

A művelet kifejezése miatt új műveleti kifejezés is létrehozható az elhasználó használatával `Controlled` .
Az új művelet aláírása az eredeti művelet aláírásán alapul.
Az eredmény típusa azonos, de a bemeneti típus egy kétrekordos qubit tömb, amely a vezérlő qubit (ka) t az első elemként, az eredeti művelet argumentumait pedig második elemként tárolja.
Az új művelet támogatja a- `Controlled` t, és csak akkor támogatja, `Adjoint` Ha az eredeti művelet megtörtént.

Ha az eredeti művelet csak egyetlen argumentumot vett igénybe, akkor a rendszer az önálló rekordos egyenértékűséget fogja itt lejátszani.
Például a a `Controlled X` művelet ellenőrzött verziója `X` . 
`X`típusa van `(Qubit => Unit is Adj + Ctl)` , ezért `Controlled X` a Type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; egypéldányos egyenértékűség miatt ez megegyezik a következővel: `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Ha az alapművelet több argumentumot is vett igénybe, ne felejtse el zárójelek közé helyezni a művelet ellenőrzött verziójának megfelelő argumentumait, hogy azok egy rekordba legyenek konvertálva.
Például a a `Controlled Rz` művelet ellenőrzött verziója `Rz` . 
`Rz`típusa van `((Double, Qubit) => Unit is Adj + Ctl)` , ezért `Controlled Rz` típusa van `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Tehát `Controlled Rz(controls, (0.1, target))` érvényes hívás lenne `Controlled Rz` (jegyezze fel a zárójeleket `0.1, target` ).

Egy másik példaként `CNOT(control, target)` a is megvalósítható `Controlled X([control], target)` . Ha egy célt 2 vezérlő qubits (CCNOT) kell vezérelni, használhatunk `Controlled X([control1, control2], target)` utasítást.

#### `Controlled Adjoint` 

A és a-elválasztók `Controlled` `Adjoint` ingázás, így nincs különbség a alkalmazása `Controlled Adjoint Op` vagy a `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Vezérelt és Adjoint implementációk meghatározása

Az első művelet deklarációjában a fenti példákban a műveletek és az aláírásokkal, illetve a-ben `BitFlip` `DecodeSuperdense` lettek definiálva `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .
A `DecodeSuperdense` mértékek beleszámítása nem egy egységes művelet, ezért nem léteznek szabályozott, nem adjoint specializációk (az ilyen művelet visszaadására vonatkozó követelmény visszahívása `Unit` ).
Mivel azonban `BitFlip` egyszerűen végrehajtja az egységes <xref:microsoft.quantum.intrinsic.x> műveletet, azt is megtehette, hogy mindkét specializációt meghatározta.

Itt részletesen ismertetjük, hogy miként lehet megtekinteni a szakosodások létezését a Q # művelet deklarációjában, így lehetővé teszi számukra, hogy a és/vagy az ellátottak együttes használatával is meghívják őket `Adjoint` `Controlled` .
Az [alábbiakban](#circumstances-for-validly-defining-specializations)néhány olyan helyzetet ismertetünk, amelyekben érvényes vagy érvénytelen, hogy deklaráljon bizonyos specializációkat.

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
Ezért ezt a példát úgy tudjuk megírni `DecodeSuperdense` , hogy a fenti példában tömörebb módon, a adjoint segítségével `PrepareEntangledPair` átalakítja a kusza állapotot egy nem összeillesztett qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

A deklarációban szereplő műveleti jellemzőkkel rendelkező Megjegyzés hasznos annak biztosításához, hogy a fordító automatikusan generáljon más specializációkat az alapértelmezett implementáció alapján. 

Számos fontos korlátozást kell figyelembe venni, amikor a rendszer megtervezi, hogy milyen műveleteket végeznek az üzemben.
A legtöbb kritikus jelentőséggel bír, ha egy olyan műveletre specializálódott, amely bármely más művelet kimeneti értékét használja, *nem* lehet automatikusan generálni a fordítótól, mert nem egyértelmű, hogy az ilyen műveletekben szereplő utasítások hogyan rendezhetők át ugyanezen hatás megszerzése érdekében.

Ezért gyakran érdemes explicit módon megadnia a különböző implementációkat.

### <a name="explicitly-specifying-implementations"></a>Implementációk explicit meghatározása

Abban az esetben, ha a fordító nem tudja létrehozni a megvalósítást, explicit módon megadható. Az ilyen explicit specializációs nyilatkozatok megfelelő *generációs irányelvből* vagy felhasználó által definiált implementációból állhatnak.
Itt biztosítjuk a lehetőségek teljes körét, az alábbi példákkal.


#### <a name="explicit-specialization-declarations"></a>Explicit specializációs deklarációk

A Q # műveletei a következő explicit specializációs deklarációkat tartalmazhatják:

- A `body` specializáció meghatározza a művelet végrehajtását, és nem alkalmazta a műveletet.
- A `adjoint` specializáció meghatározza a művelet megvalósítását az `Adjoint` alkalmazottal.
- A `controlled` specializáció meghatározza a művelet megvalósítását az `Controlled` alkalmazottal.
- A `controlled adjoint` specializáció meghatározza a művelet megvalósítását mind a, mind a által alkalmazott operációs rendszersel `Adjoint` `Controlled` .
  Ez a specializáció is elnevezhető `adjoint controlled` , mivel a két elválasztó.


A művelet specializáció a specializációs címkéből (például `body` vagy `adjoint` stb.) áll, amelyet az alábbiak egyike követ:

- Az alább leírtak szerint kifejezett nyilatkozat.
- Egy *irányelv* , amely közli a fordítóval, *Hogyan* hozhatja ki a specializációt, az egyik:
  - `intrinsic`, ami azt jelzi, hogy a specializációt a célszámítógép kapja meg.
  - `distribute`, amely a `controlled` és a `controlled adjoint` specializációkkal használható.
    A használatakor `controlled` azt jelzi, hogy a fordítónak ki kell számítania a specializációt úgy, hogy az `Controlled` összes műveletére alkalmazza a-t `body` .
    A használatakor `controlled adjoint` azt jelzi, hogy a fordítónak a `Controlled` specializáció összes műveletére alkalmazva kell kiszámítani a specializációt `adjoint` .
  - `invert`, ami azt jelzi, hogy a fordítónak ki kell számítania a `adjoint` specializációt a következő lépésekkel `body` , például a műveletek sorrendjének megfordításával és a adjoint alkalmazásával.
    A használatakor `adjoint controlled` Ez azt jelzi, hogy a fordítónak a specializáció megfordításával kell kiszámítani a specializációt `controlled` .
  - `self`, amely azt jelzi, hogy a adjoint specializáció megegyezik a `body` specializációval.
    Ez a `adjoint` és a `adjoint controlled` specializációra érvényes.
    A `adjoint controlled` esetében `self` azt jelenti, hogy a `adjoint controlled` specializáció ugyanaz, mint a `controlled` specializáció.
  - `auto`, jelezve, hogy a fordítónak ki kell választania egy megfelelő irányelvet az alkalmazáshoz.
    `auto`nem használható a `body` specializációhoz.

Az irányelvek és `auto` mind a záró pontosvesszőt igénylik `;` .
Az `auto` irányelv a következő generációs irányelvre lesz feloldva, ha a megadott explicit nyilatkozattal `body` rendelkezik:

- A `adjoint` specializáció a direktíva alapján jön létre `invert` .
- A `controlled` specializáció a direktíva alapján jön létre `distribute` .
- A `adjoint controlled` specializáció a direktíva alapján jön létre `invert` , ha explicit deklaráció `controlled` van megadva, de nem egyet `adjoint` , és `distribute` egyéb módon.

> [!TIP]   
> Ha egy művelet önadjoint, explicit módon megadhatja a adjoint vagy az irányított adjoint specializációt az `self` előállítási irányelv alapján, hogy a fordító felhasználhassa ezeket az információkat optimalizálási célokra.

A felhasználó által definiált implementációt tartalmazó specializációs nyilatkozat egy argumentummal, majd egy, a specializációt megvalósító Q # kóddal rendelkező utasítási blokkot tartalmaz.
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

A fenti kód `PrepareEntangledPair` például egyenértékű az alábbi kóddal, amely explicit specializációs deklarációkat tartalmaz: 

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

Ha a fordító nem tud automatikusan előállítani egy bizonyos specializáció megvalósítását, vagy ha hatékonyabb megvalósításra van lehetőség, akkor a megvalósítás manuálisan is megadható.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
A fenti példában `adjoint invert;` azt jelzi, hogy a adjoint specializációt úgy kell létrehozni, hogy visszaállítja a törzs megvalósítását, és `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint specializációt úgy kell létrehozni, hogy visszaállítja a szabályozott specializáció adott implementációját.

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

A adjoint vagy az ellenőrzött verziók nélküli műveletet kell megadnia. Például a mérési műveletek egyike sem, mert nem invertálható vagy ellenőrizhetők.

Egy művelet támogatja a `Adjoint` és/vagy a-t, `Controlled` Ha a nyilatkozata tartalmazza a megfelelő specializációk implicit vagy explicit nyilatkozatát.

Az explicit módon bejelentett adjoint/vezérelt specializáció egy adjoint/vezérelt specializáció létezését feltételezi. 

Egy olyan művelet esetében, amelynek a törzse ismétlődik, amíg-sikeres hurkokat tartalmaz, állítson be utasítások, mérések, visszaküldési utasítások vagy más olyan műveletekre irányuló hívásokat, amelyek nem támogatják az `Adjoint` adjoint-specializációt, és nem lehetséges, hogy automatikusan generáljon egy, az `invert` vagy az `auto` irányelvet követő specializáció

Egy olyan művelet esetében, amelynek a törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem támogatják az üzemen kívüli tevékenységet `Controlled` , nem lehetséges, hogy automatikusan generál egy szabályozott specializációt a `distribute` vagy a `auto` direktíva után.

#### <a name="controlled-adjoint"></a>Vezérelt Adjoint

Egy művelet ellenőrzött adjoint-verziója határozza meg, hogy a rendszer milyen módon implementálja a adjoint a művelethez.
Az adjoint-verzióval nem rendelkező műveletet kell megadnia. például a mérési műveletek nem rendelkeznek szabályozott adjoint-verzióval, mert nem ellenőrizhetők és nem invertálható.

Egy művelet vezérelt adjoint-specializációjának léteznie kell, ha a adjoint és a szabályozott specializáció is létezik. Ebben az esetben a vezérelt adjoint specializáció létezését következtetik ki, és a fordító a megfelelő specializációt hozza létre, ha nincs explicit módon definiált implementáció. 

Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem rendelkeznek szabályozott adjoint-verzióval, a adjoint-specializáció automatikus generálása a `invert` `distribute` vagy az `auto` direktíva nem lehetséges.


### <a name="type-compatibility"></a>Típus kompatibilitása

Egy olyan művelet, amelynél további felhasználók támogatottak, a rendszer bárhol használható egy kevesebb ellátott művelettel, de ugyanez az aláírás várható.
Előfordulhat például, hogy egy típusú műveletet `(Qubit => Unit is Adj)` kell használni, ahol egy típusú művelet `(Qubit => Unit)` várható.

A Q # *a* hívható visszatérési típusok tekintetében a következő: egy típust visszaadó meghívható, amely `'A` kompatibilis az ugyanazzal a bemeneti típussal és a (z `'A` ) rendszerrel kompatibilis eredményhalmaz típussal.

A Q # *contravariant típusparamétert* a bemeneti típusok tekintetében: egy olyan meghívót, amely bemenetként fogadja a típust, `'A` és kompatibilis az ugyanazzal az eredménnyel, és egy olyan bemeneti típussal, amely kompatibilis a szolgáltatással `'A` .

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

- Előfordulhat, hogy a függvény a `ConjugateInvertWith` vagy a `inner` argumentumával hívható meg `Invert` `ApplyUnitary` .
- Előfordulhat, hogy a függvényt `ConjugateUnitaryWith` egy argumentummal kell meghívni `inner` `ApplyUnitary` , de nem `Invert` .
- Lehet, hogy egy típusú érték `(Qubit[] => Unit is Adj + Ctl)` adható vissza `ConjugateInvertWith` .

> [!IMPORTANT]
> A Q # 0,3 jelentős változást vezetett be a felhasználó által definiált típusok viselkedésében.

A felhasználó által definiált típusokat az alapul szolgáló típus burkolt verziójaként, nem pedig altípusként kezeli a rendszer.
Ez azt jelenti, hogy a felhasználó által definiált típus értéke nem használható, ha a rendszer az alapul szolgáló típus értékét várta.


### <a name="conjugations"></a>Conjugations

A klasszikus BITS-vel szemben a kvantum-memória felszabadítása valamivel nagyobb mértékben történik, mivel a qubits vakon alaphelyzetbe állítása nem kívánt hatással lehet a fennmaradó számításra, ha a qubits továbbra is összefonódik. Ezt elkerülheti, ha a memóriát a memória felszabadítása előtt megfelelően elvégezte. A kvantum-számítástechnika általános mintája a következő: 

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

A 0,9-es verziótól kezdődően a fenti transzformációt megvalósító ragozás-utasítást támogatunk. Az utasítás használatával a művelet a `ApplyWith` következő módon valósítható meg:

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
Egy ilyen ragozó utasítás nyilvánvalóan sokkal hasznosabb lehet, ha a külső és belső átalakítás nem érhető el azonnal, hanem több utasításból álló blokk alapján. 

A blokkon belül definiált utasítások inverz átalakítását a fordító automatikusan hozza létre, és az Apply-Block befejeződése után hajtja végre.
Mivel a blokk részeként használt változó változók nem használhatók fel az alkalmazás-blokkban, a generált transzformáció garantált, hogy a adjoint a blokkon belül. 


## <a name="defining-new-functions"></a>Új függvények definiálása

A functions kizárólag determinisztikus, a klasszikus rutinok a Q #-ban, amelyek különböznek a műveletektől, és nem megengedett, hogy a kimeneti érték kiszámításán kívül más effektusok is legyenek.
Különösen a függvények nem hívhatnak meg műveleteket; qubits bevonása, lefoglalása vagy kölcsönzése; véletlenszerű számok mintavételezése; Ellenkező esetben a bemeneti értéken kívüli állapot függ egy függvénynek.
Ennek következményeként a Q # függvények *tisztán*vannak rendelve, hogy mindig ugyanazokat a bemeneti értékeket rendelik ugyanahhoz a kimeneti értékekhez.
Így a Q # fordító biztonságosan átrendezheti, hogyan és mikor hívja meg a függvényeket a műveleti specializációk létrehozásakor.

A Q # forrásfájl tetszőleges számú funkciót meghatározhat.
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

Ha ezt megteheti, hasznos lehet a klasszikus logikát kiírni a függvények helyett, hogy azok a műveletek során könnyebben használhatók legyenek.
Ha például a `Square` fenti deklarációt egy *műveletként*írta volna, akkor a fordító nem tudta garantálni, hogy ugyanazt a bemenetet ugyanazzal a kimenettel fogja létrehozni.

A függvények és a műveletek közötti különbség kihangsúlyozása érdekében vegye figyelembe, hogy egy véletlenszerűen kiválasztott számnak a Q #-műveletből való klasszikus mintavételezési problémája:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Minden egyes `U` híváskor egy másik művelet fog megjelenni `target` .
A fordító nem tudja garantálni, hogy ha felvettünk egy `adjoint auto` specializációs nyilatkozatot a alkalmazásba `U` , akkor az `U(target); Adjoint U(target);` identitásként viselkednek (azaz No-op).
Ez sérti a [vektorokban és mátrixokban](xref:microsoft.quantum.concepts.vectors)megjelenő adjoint definícióját, amely lehetővé teszi, hogy egy adjoint-specializációt egy olyan műveletben engedélyezzen, ahol a művelet meghívása <xref:microsoft.quantum.math.randomreal> megszegi a fordító által biztosított garanciákat; <xref:microsoft.quantum.math.randomreal> egy olyan művelet, amely esetében nem létezik adjoint vagy vezérelt verzió.

Másrészről, ami lehetővé teszi, hogy a függvényhívás, például a `Square` biztonságos, a fordító biztos lehet abban, hogy csak a bemenetet kell megőriznie ahhoz, hogy a `Square` kimenet stabil legyen.
Így a lehető legtöbb klasszikus logikát elkülönítheti a functions szolgáltatásban, így a logika más funkciókban és műveletekben is felhasználható.


## <a name="generic-type-parameterized-callables"></a>Általános (típus-paraméteres) Callables

Számos olyan függvény és művelet, amelyet érdemes lehet meghatározni, valójában nem támaszkodik a bemenetek típusaira, hanem csak egy másik függvény vagy művelet segítségével implicit módon használják a saját típusait.
Tegyük fel például, hogy a *Térkép* fogalma számos funkcionális nyelvhez közös. a függvény $f (x) $ és Values $ \{ x_1, x_2, \dots, x_n \} $, Map egy új gyűjteményt ad vissza: $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
Ha ezt a Q #-ban szeretné megvalósítani, kihasználhatjuk, hogy a függvények első osztályúak legyenek.
Tegyük fel, hogy egy rövid példa a `Map` ★ helyőrzőként való használatára, miközben kitaláljuk, hogy milyen típusokra van szükségünk.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vegye figyelembe, hogy ez a függvény ugyanúgy néz ki, mint amit a tényleges típusok helyettesítenek.
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

Elvileg írhatunk egy verziót `Map` minden olyan típushoz, amelyben találkozhatunk, de ez számos problémát jelent.
Ha például hibát talál a alkalmazásban `Map` , akkor biztosítani kell, hogy a javítás a összes verziójában egységesen legyen alkalmazva `Map` .
Emellett, ha új rekordot vagy UDT hozunk létre, most új típust is létre kell állítania `Map` .
Ez egy kis mennyiségű ilyen funkció esetében is megtartható, mivel az `Map` új típusok bevezetésének díja aránytalanul nagy, meglehetősen rövid sorrendbe kerül.

A nehézségek nagy része azonban azt eredményezi, hogy a fordító nem kapott olyan információt, amely a különböző verzióival kapcsolatos információk felismeréséhez szükséges `Map` .
Gyakorlatilag azt szeretnénk, hogy a fordító a `Map` q # *típusaitól* a q # függvényekig valamilyen matematikai függvényt kezelje.

Ezt a fogalmat úgy kell megfogalmazni, hogy a functions és a Operations függvények *Type paramétereket*, valamint a szokásos rekord paramétereit is használják.
A fenti példákban szeretnénk úgy gondolni, hogy `Map` `Int, Pauli` az első esetben és a második esetben a típus paramétereit kell beírni `Double, String` .
A legtöbb esetben ezek a típusú paraméterek a szokásos típusokként használhatók: paraméterek típusú értékeket használunk a tömbök és rekordok, a függvények és a műveletek hívásához, valamint a szokásos vagy változtatható változókhoz való hozzárendeléshez.

> [!NOTE]
> A közvetett függőség legszélsőségesebb esete a qubits, ahol a Q # program nem hivatkozhat közvetlenül a típus struktúrájára `Qubit` , de ezeket a típusokat más műveletekre és funkciókra **kell** átadnia.

A fenti példához visszatérve láthatjuk, hogy a `Map` Type paraméterrel kell rendelkeznie, az egyiket pedig a bemenetnek, a `fn` másikat pedig a kimenetének kell képviselnie `fn` .
A Q #-ban ez a szög zárójelek (azaz `<>` nem brakets $ \braket $!) hozzáadásával történik, {} a deklarációban szereplő függvény vagy művelet neve után, valamint az egyes típusparaméter-paraméterek listázásával.
Az egyes típusparaméter-paraméterek nevének egy kullancstal kell kezdődnie `'` , amely azt jelzi, hogy ez egy típusparaméter, nem pedig egy egyszerű típus (más néven *konkrét* típus).
Ezért a következőt `Map` írjuk:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vegye figyelembe, hogy a definíciója `Map<'Input, 'Output>` nagyon hasonlít a korábban megírt verziókhoz.
Az egyetlen különbség az, hogy kifejezetten tájékoztatjuk a fordítót, amely `Map` nem függ közvetlenül attól, hogy mi `'Input` és milyen `'Output` , de két típust is használ, ha közvetve használja őket `fn` .
Az ilyen módon történő Definiálás után meghívjuk, mintha `Map<'Input, 'Output>` egy szokványos függvény lenne:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Az általános függvények és műveletek írása egy olyan hely, ahol a "rekord-in rekord kijelentkezése" nagyon hasznos módszer a Q # függvények és műveletek gondolkodására.
> Mivel minden függvény pontosan egy bemenetet vesz át, és pontosan egy kimenetet ad vissza, a típus bemenete `'T -> 'U` *bármilyen* Q # függvénynek felel meg.
> Hasonlóképpen, minden művelet átadható egy típusú bemenetnek `'T => 'U` .

Második példaként vegye figyelembe, hogy milyen kihívással kell elírnia egy olyan függvényt, amely két másik függvény összeállítását adja vissza:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Itt pontosan meg kell határoznia, hogy mi, és milyen mértékben `A` `B` `C` korlátozza az új függvény hasznosságát `Compose` .
Az összes után `Compose` csak a, a és a, a `A` `B` és a `C` *használatával* függ `innerFn` `outerFn` .
Alternatív megoldásként hozzáadhatunk olyan típusú paramétereket, amelyek `Compose` azt jelzik, hogy a (z *any* ) és a (z) és a (z) a következő `A` `B` `C` paraméterekkel egyezik `innerFn` `outerFn` :

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

A `ourH` fenti kódrészletben szereplő változó értéke ezután a művelet <xref:microsoft.quantum.intrinsic.h> , például az, hogy meghívjuk ezt az értéket, mint bármely más művelet.
Ez lehetővé teszi olyan műveletek írását, amelyek a bemenetük részeként végzik a műveleteket, és a magasabb rendű vezérlési folyamatokra vonatkozó fogalmakat képeznek.
Tegyük fel például, hogy a "Square" műveletet úgy képzeli el, hogy kétszer ugyanazt a cél qubit alkalmazza.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Műveletek visszaküldése egy függvényből

Kiemeljük, hogy a kimenetek részeként is visszaadhatjuk a műveleteket, így a klasszikus feltételes logika valamilyen módon izolálható klasszikus függvényként, amely egy művelet formájában egy kvantum-program leírását adja vissza.
Egyszerű példaként tekintse meg a teleportálás példáját, amelyben a kétbites klasszikus üzenetet fogadó fél az üzenetet arra használja, hogy dekódolja a qubit a megfelelő teleportált állapotba.
Ezt egy olyan függvényben írhatjuk, amely a két klasszikus bitet veszi át, és visszaadja a megfelelő dekódolási műveletet.

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

Ez az új függvény valóban egy függvény, abban az esetben, ha a és az azonos értékeit `hereBit` hívjuk `thereBit` , mindig ugyanezt a műveletet fogjuk visszakapni.
Így a dekóder biztonságosan futtatható a műveletekben anélkül, hogy meg kellene indokolnia, hogy a dekódolási logika hogyan működjön együtt a különböző műveleti szakosodások definícióinak használatával.
Ez azt is megteheti, hogy elszigetelte a klasszikus logikát egy függvényen belül, garantálva azt a fordítót, hogy a függvény hívása büntetlenül rendezhető, feltéve, hogy a bevitel megmarad.


## <a name="partial-application"></a>Részleges alkalmazás

A műveleteknek a *részleges alkalmazás*használatával történő visszaadását lehetővé tehetjük, amelyekben a bemenet egy vagy több részének megadásával egy függvénynek vagy műveletnek a tényleges hívása nélkül is megadható. Például a fenti példa visszahívásával `ApplyTwice` jelezheti, hogy nem szeretnénk megadni, azonnal, hogy a bemeneti művelet melyik qubit vonatkozzon:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Ebben az esetben a helyi változó `twiceOp` a részlegesen alkalmazott műveletet tartalmazza `ApplyTwice(op, _)` , ahol a bemenetben még nem megadott részek szerepelnek `_` .
Ha a következő sorban hívja meg a hívást, a rendszer a `twiceOp` részlegesen alkalmazott művelethez továbbítja a bemenetet az eredeti művelethez.
Így a fenti kódrészlet gyakorlatilag azonos azzal, hogy közvetlenül meghívja őket, és a `ApplyTwice(op, target)` Mentés után egy új helyi változót vezettünk be, amely lehetővé teszi a hívás késleltetését, miközben a bemenet egyes részeit biztosítjuk.

Mivel egy részlegesen alkalmazott művelet valójában nem lett meghívva, amíg a teljes adatbevitel meg nem történt, akkor a függvényekből is biztonságosan részben alkalmazhatjuk a műveleteket.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Elméletileg a klasszikus logika `SquareOperation` sokkal jobban érintett, de továbbra is el van különítve a többi művelettől, mert az garantálja, hogy a fordító a functions szolgáltatással kapcsolatban tud nyújtani.
Ezt a megközelítést fogja használni a Q # standard könyvtárban a klasszikus vezérlési folyamat kifejezésére, amely a kvantum-programokban könnyen használható.


## <a name="recursion"></a>Rekurzió

A Q # callables közvetlenül vagy közvetve rekurzívak.
Ez azt is megteheti, hogy egy művelet vagy funkció meghívhatja magát, vagy meghívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.

A rekurzió használatának két fontos megjegyzése van, azonban:

- A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.
  Ez jelentős hatással lehet az algoritmus végrehajtási idejére.
- Ha tényleges kvantum-eszközön végez végrehajtást, előfordulhat, hogy a halmozott terület korlátozva van, ezért a mélyebb rekurzió hibát okozhat.
  A Q # Compiler és a Runtime nem azonosítja és optimalizálja a farok rekurzióját.

## <a name="whats-next"></a>Vajon mi a következő lépés?
További tudnivalók a Q #-ban található [változókról](xref:microsoft.quantum.guide.variables) .