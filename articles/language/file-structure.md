---
title: Fájl szerkezete | Microsoft Docs
description: 'Q # fájl szerkezete'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185188"
---
# <a name="file-structure"></a>Fájlstruktúra

A Q # fájl névtér-deklarációk sorozatából áll.
Minden névtér deklarációja a felhasználó által definiált típusokra, műveletekre és függvényekre vonatkozó deklarációkat tartalmaz.
A névtér-deklarációk tetszőleges számú deklarációt tartalmazhatnak, és bármilyen sorrendben megadhatók.
A névtér deklarációján kívül megjelenő szöveg Megjegyzés.
Különösen a deklaráció előtt a névtérhez tartozó dokumentációs megjegyzések szerepelnek.

## <a name="namespace-declarations"></a>Névtér-deklarációk

A Q # fájlnak általában pontosan egy névtér-deklarációja lesz, de a none (és nem lehet üres, vagy csak megjegyzéseket tartalmazhat), vagy több névteret is tartalmazhat.
Előfordulhat, hogy a névtér-deklarációk nem ágyazhatók egymásba.

Előfordulhat, hogy ugyanaz a névtér több, összeállított Q # fájlban van deklarálva, feltéve, hogy nincs ilyen nevű típus, művelet vagy függvény deklarációja.
Bizonyos esetben a több fájl azonos névterében lévő azonos típust nem lehet megadnia, még akkor is, ha a deklarációk azonosak.

A névtér deklarációja a következő kulcsszóból áll: `namespace`, majd a névtér neve, egy nyitott kapcsos zárójel `{`, a névtérben található deklarációk és egy záró kapcsos zárójel `}`.
A névterek nevei egy vagy több, ponttal elválasztott jogi szimbólum sorozatának .NET-mintázatát követik `.`.
Például `MyQuantumStuff` és `Microsoft.Quantum.Canon` érvényes névterek nevei.
Az egyezmény szerint a névtér nevében szereplő szimbólumok tőkésítve vannak, de ez nem kötelező.

A deklarációk bármilyen sorrendben szerepelhetnek a névtér deklarációjában.
A fájlokban lejjebb deklarált típusokra vagy callables mutató hivatkozások megfelelően vannak feloldva; nincs szükség a típus, a művelet vagy a függvény deklarációjának megírására a hivatkozás előtt.

## <a name="open-directives"></a>Megnyitási irányelvek

Egy névtér-blokkon belül a `open` direktíva használható az adott névtérben definiált összes típus és callables importálására, és azok nem minősített nevük alapján. 

Egy ilyen `open` irányelv a `open` kulcsszóból áll, amelyet a megnyitni kívánt névtér és a megszakítási pontosvesszővel kell elválasztani.

Például:

```qsharp
open Microsoft.Quantum.Canon;
```

Ha szükséges, a megnyitott névtérhez tartozó rövid név is meghatározható úgy, hogy az adott névtérből származó összes elemet (és szükség esetén) a megadott rövid névvel kell minősíteni. Az ilyen rövid név meghatározása úgy történik, hogy hozzáadja a kulcsszót `as` a kívánt rövid nevet, majd a pontosvesszőt a `open` direktívában:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Minden `open` direktívának szerepelnie kell a névtérbeli blokkban `function`, `operation`vagy `newtype` deklaráció előtt.
A `open` direktíva a teljes névtér-blokkra vonatkozik a fájlban.

## <a name="user-defined-type-declarations"></a>Felhasználó által definiált típusú deklarációk

A q # lehetővé teszi a felhasználók számára, hogy új, felhasználó által definiált típusokat állapítsanak meg a [q # Type Model](xref:microsoft.quantum.language.type-model) című szakaszban leírtak szerint.
A felhasználó által definiált típusok akkor is eltérőek, ha az alaptípusok azonosak.
Különösen, ha az alapul szolgáló típusok azonosak, a felhasználó által definiált típusok értékei között nincs automatikus konverzió.

A felhasználó által definiált típusú deklaráció a kulcsszó `newtype`, majd a felhasználó által definiált típus neve, egy `=`, egy érvényes típus-specifikáció és egy megszakítási pontosvessző.

Példa:

```qsharp
newtype PairOfInts = (Int, Int);
```

Minden Q # forrásfájl tetszőleges számú felhasználó által definiált típust deklarálhat.
A típus nevének egyedinek kell lennie a névtéren belül, és előfordulhat, hogy a művelet és a függvények nevei nem ütköznek egymással.

Nem lehet körkörös függőségeket definiálni a felhasználó által definiált típusok között. A rekurzív típusok ezért nem lehetségesek a Q #-on belül.

## <a name="operation-declarations"></a>Műveleti deklarációk

A műveletek a Q # magja, ami nagyjából hasonló a függvények más nyelveken való működéséhez.
A Q # forrásfájl tetszőleges számú műveletet meghatározhat.

A művelet nevének a névtéren belül egyedinek kell lennie, és nem ütközhet a típus és a függvény nevével.

A műveleti deklarációk a `operation`kulcsszóból állnak, amelyet a művelet nevét, a művelet argumentumait definiáló gépelt azonosító rekordot, egy kettőspont `:`, egy típus típusú jegyzetet határoznak meg, amely leírja a művelet eredményének típusát, opcionálisan a művelet jellemzőit, egy nyitott kapcsos zárójelet `{`, a műveleti deklaráció törzsét és egy záró zárójelet `}`.

A műveleti nyilatkozat törzse az alapértelmezett implementációból vagy a specializációk listájából áll.
Az alapértelmezett implementáció közvetlenül is megadható a deklarációban, ha csak az alapértelmezett szövegtörzs-specializáció megvalósítását explicit módon kell megadni.
Ebben az esetben a deklarációban szereplő műveleti jellemzőkkel rendelkező Megjegyzés hasznos annak biztosítására, hogy a fordító automatikusan generáljon más specializációkat az alapértelmezett implementáció alapján. 

Példa: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

A művelet jellemzői határozzák meg, hogy milyen típusú elválasztók alkalmazhatók a deklarált műveletre, és milyen hatással vannak rájuk. Ha egy művelet egy egységes átalakítást valósít meg, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen.
Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható. Ezután a fordító létrehozza a megfelelő implementációt minden ilyen implicit módon deklarált specializációhoz. A fenti példában egy adjoint, egy vezérelt és egy vezérelt adjoint-specializációt generál a fordító. 

Abban az esetben, ha a fordító nem tudja létrehozni a megvalósítást, explicit módon megadható. Az ilyen explicit specializációs nyilatkozatok egy megfelelő generációs irányelvből állhatnak, amelyből megtudhatja, hogy egy adott specializáció hogyan épül fel, vagy egy felhasználó által meghatározott implementáció. A fenti `PrepareEntangledPair` található kód például az alábbi kóddal egyenértékű, explicit specializációs deklarációkat tartalmaz: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan hozhatja ki a specializáció megvalósítását.
Ha a fordító nem tud létrehozni egy bizonyos specializáció megvalósítását további utasítások nélkül – például egy pontosabb létrehozási irányelv –, vagy ha hatékonyabb megvalósítást lehet megadni, akkor a megvalósítás manuálisan is meghatározható.

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

A fenti példában a `adjoint invert;` azt jelzi, hogy a adjoint specializációt a törzs megvalósításának visszafordításával kell létrehozni, és `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint-specializációt úgy kell létrehozni, hogy a megadott implementációját visszaállítja a irányított specializáció.

Ahhoz, hogy egy művelet támogassa a `Adjoint` és/vagy a `Controlled`-munkafolyamatot, a visszatérési típust szükségszerűen `Unit`kell lennie. 


### <a name="explicit-specialization-declarations"></a>Explicit specializációs deklarációk

A Q # műveletei a következő explicit specializációs deklarációkat tartalmazhatják:

- A `body` specializáció meghatározza a művelet végrehajtását, és nem alkalmazta a műveletet.
- A `adjoint` specializáció meghatározza a művelet végrehajtását a `Adjoint`-felhasználó alkalmazással.
- A `controlled` specializáció meghatározza a művelet végrehajtását a `Controlled`-felhasználó alkalmazással.
- A `controlled adjoint` specializáció a művelet megvalósítását határozza meg a `Adjoint` és az `Controlled` alkalmazott operációs rendszersel együtt.
  Ez a specializáció `adjoint controlled`néven is elnevezhető, mivel a két elválasztó.


A művelet specializáció a specializációs címkéből (például `body`vagy `adjoint`stb.) áll, amelyet a következők egyike követ:

- Az alább leírtak szerint kifejezett nyilatkozat.
- Egy irányelv, amely közli a fordítóval, hogyan hozhatja ki a specializációt, az egyik:
  - `intrinsic`, amely azt jelzi, hogy a specializációt a célszámítógép kapja meg.
  - `distribute`, amelyek felhasználhatók a `controlled` és `controlled adjoint` specializációkkal.
    A `controlled`használatakor azt jelzi, hogy a fordítónak a `body`összes műveletére alkalmaznia kell `Controlled` a specializáció kiszámításához.
    A `controlled adjoint`használatakor azt jelzi, hogy a fordítónak ki kell számítania a specializációt úgy, hogy a `adjoint` specializáció összes műveletére alkalmazza a `Controlled`.
  - `invert`, amely azt jelzi, hogy a fordítónak a `body`lefordításával kell kiszámítani a `adjoint` specializációt, például a műveletek sorrendjét és a adjoint alkalmazását.
    `adjoint controlled`használata esetén ez azt jelenti, hogy a fordítónak a `controlled` specializáció megfordításával kell kiszámítani a specializációt.
  - `self`azt jelzi, hogy a adjoint specializáció megegyezik a `body` specializációval.
    Ez a `adjoint` és az `adjoint controlled` specializációra érvényes.
    `adjoint controlled`esetén `self` azt jelenti, hogy a `adjoint controlled` specializáció megegyezik a `controlled` specializációval.
  - `auto`azt jelzi, hogy a fordítónak ki kell választania egy megfelelő irányelvet az alkalmazáshoz.
    Előfordulhat, hogy a `auto` nem használható a `body` specializációhoz.

Az irányelvek és a `auto` mind a záró pontosvesszővel elválasztott `;`szükségesek.
A `auto` irányelv a következő generációs irányelvre lesz feloldva, ha a `body` explicit nyilatkozata van megadva:

- A `adjoint` specializáció a `invert`direktíva alapján jön létre.
- A `controlled` specializáció a `distribute`direktíva alapján jön létre.
- Az `adjoint controlled` specializáció az irányelv alapján jön létre `invert` ha a `controlled` kifejezett nyilatkozata van megadva, de nem `adjoint`, és `distribute` másként.

> [!TIP]   
> Ha egy művelet önadjoint, explicit módon megadhatja a adjoint vagy az irányított adjoint specializációt az előállítási irányelv alapján `self`, hogy lehetővé tegye a fordító számára ezen információk használatát optimalizálási célokra.

A felhasználó által definiált implementációt tartalmazó specializációs nyilatkozat egy argumentummal, majd egy, a specializációt megvalósító Q # kóddal rendelkező utasítási blokkot tartalmaz.
A argumentumok listájában `...` a művelet egészének deklarált argumentumait jelöli.
`body` és `adjoint`esetén az argumentumok listájának mindig `(...)`nak kell lennie; `controlled` és `adjoint controlled`esetében az argumentumok listájának olyan szimbólumnak kell lennie, amely a vezérlési qubits tömbjét jelöli, amelyet a `...`követ, zárójelek közé. például `(controls,...)`.

Ha az alapértelmezett törzsön kívül egy vagy több specializációt is explicit módon kell deklarálni, akkor az alapértelmezett törzs megvalósítását megfelelő specializációs nyilatkozatba is kell becsomagolni:

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Adjoint

Egy művelet adjoint megadhatja, hogyan történjen a művelet összetett konjugált áttelepítése, azaz hogyan működik a művelet, ha a "Futtatás fordított".
Adjoint nélküli műveletet kell megadnia. például a mérési műveletek nem rendelkeznek adjoint, mert nem invertálható.
Egy művelet támogatja a `Adjoint`-kezelőt, ha a deklarációja egy adjoint-specializáció implicit vagy explicit deklarációját tartalmazza.
A kifejezetten bejelentett, szabályozott adjoint specializáció egy adjoint specializáció létezését jelenti. 

Olyan művelet esetében, amelynek a törzse ismétlődik, amíg a sikerességi hurkok, beállítja a kimutatásokat, a méréseket, a visszaküldési utasításokat vagy a más olyan műveletekre irányuló hívásokat, amelyek nem támogatják a `Adjoint`-indítót, automatikusan generál egy adjoint specializációt a `invert` vagy @no__ után a t_2_ direktíva nem lehetséges.

### <a name="controlled"></a>Ellenőrzött

Egy művelet ellenőrzött verziója határozza meg, hogy a rendszer hogyan alkalmazza a művelet egy kvantum által vezérelt verzióját, azaz azt, hogy egy adott művelet hogyan viselkedik, ha a rendszer a kvantum-regiszter állapotára alkalmazza a feltételt.
Az [ellenőrzött](xref:microsoft.quantum.language.type-model#controlled) szakasz részletesebb leírást tartalmaz.

A művelet nem érvényes a szabályozott verzió nélküli műveletek megadására; például a mérési műveletek nem rendelkeznek szabályozott verzióval, mert nem ellenőrizhetők.
Egy művelet támogatja a `Controlled`-kezelőt, ha és csak akkor, ha a deklarációja egy szabályozott specializáció implicit vagy explicit deklarációját tartalmazza.
Az explicit módon deklarált, szabályozott adjoint specializáció egy vezérelt specializáció létezését feltételezi. 

Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem támogatják a `Controlled`t, nem lehetséges, hogy a `distribute` vagy `auto` direktíva után automatikusan generáljon egy szabályozott specializációt.

### <a name="controlled-adjoint"></a>Vezérelt Adjoint

Egy művelet ellenőrzött adjoint-verziója határozza meg, hogy a rendszer milyen módon implementálja a adjoint a művelethez.
Az adjoint-verzióval nem rendelkező műveletet kell megadnia. például a mérési műveletek nem rendelkeznek szabályozott adjoint-verzióval, mert nem ellenőrizhetők és nem invertálható.

Egy művelet vezérelt adjoint-specializációjának léteznie kell, ha a adjoint és a szabályozott specializáció is létezik. Ebben az esetben a vezérelt adjoint specializáció létezését következtetik ki, és a fordító a megfelelő specializációt hozza létre, ha nincs explicit módon definiált implementáció. 

Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem rendelkeznek szabályozott adjoint-verzióval, a `invert`t követő, `distribute` vagy `auto` direktíva nem lehet automatikusan generálni egy adjoint specializációt.


### <a name="examples"></a>Példák

A művelet deklarációja olyan egyszerű lehet, mint a következő, amely meghatározza a primitív Pauli X műveletet:

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

A következő határozza meg a teleport műveletet.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Függvények deklarációi

A függvények tisztán klasszikus rutinok a Q #-ban.
A Q # forrásfájl tetszőleges számú funkciót meghatározhat.

A függvények deklarációja a `function`kulcsszóból áll, amelyet a függvény neve, egy begépelt azonosító rekord, egy Type Megjegyzés, amely leírja a függvény visszatérési típusát, valamint egy olyan utasítási blokkot, amely leírja a függvény.

A függvényt definiáló utasítás blokkjának `{` és `}` kell lennie, mint bármely más utasítás blokkja.

A függvények nevének egyedinek kell lennie a névtéren belül, és nem ütközhet a művelet és a típus nevével.
A függvények nem foglalhatnak le és nem kölcsönözhetnek qubits, vagy nem hívhatnak meg műveleteket. A műveletek részleges alkalmazása vagy a begépelt műveletekben szereplő értékek meghaladása rendben van.

Például:

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
