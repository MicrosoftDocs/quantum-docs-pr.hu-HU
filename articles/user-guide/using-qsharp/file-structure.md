---
title: 'Q # fájl szerkezete'
description: 'A Q # fájl szerkezetét és szintaxisát ismerteti.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327458"
---
# <a name="q-file-structure"></a>Q # fájl szerkezete

Minden Q # művelet, függvény és felhasználó által definiált típus definiálva van egy névtéren belül.

A Q # fájl *névtér-deklarációk*sorozatából áll.
Minden névtér deklarációja a felhasználó által definiált típusokra, műveletekre és függvényekre vonatkozó deklarációkat tartalmaz.
A névtér-deklarációk tetszőleges számú deklarációt tartalmazhatnak, és bármilyen sorrendben megadhatók.
Az alábbi hivatkozásokra kattintva további részleteket tudhat meg a [felhasználó által definiált típusokról](xref:microsoft.quantum.guide.types#user-defined-types), [műveletekről](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)és [függvényekről](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) a névtéren belül.

A névtér deklarációján kívül megjelenő szöveg Megjegyzés.
A dokumentációval kapcsolatos megjegyzések (az alábbi további részletek) a deklaráció előtt találhatók a névtérhez.

## <a name="namespace-declarations"></a>Névtér-deklarációk

A Q # fájlnak általában pontosan egy névtér-deklarációja lesz, de a none (és nem lehet üres, vagy csak megjegyzéseket tartalmazhat), vagy több névteret is tartalmazhat.
Előfordulhat, hogy a névtér-deklarációk nem ágyazhatók egymásba.

Előfordulhat, hogy ugyanaz a névtér több, összeállított Q # fájlban van deklarálva, feltéve, hogy nincs ilyen nevű típus, művelet vagy függvény deklarációja.
Bizonyos esetben a több fájl azonos névterében lévő azonos típust nem lehet megadnia, még akkor is, ha a deklarációk azonosak.

A névtér deklarációja a kulcsszóból áll `namespace` , amelyet a névtér neve, egy nyitott kapcsos zárójel `{` , a névtérben található deklarációk és egy záró zárójel követ `}` .
A névterek nevei egy vagy több, ponttal elválasztott jogi szimbólum sorozatának .NET-mintáját követik `.` .
Például a `MyQuantumStuff` és az `Microsoft.Quantum.Intrinsic` érvényes névterek nevei.
Az egyezmény szerint a névtér nevében szereplő szimbólumok tőkésítve vannak, de ez nem kötelező.

A fájlokban lejjebb deklarált típusokra vagy callables mutató hivatkozások megfelelően vannak feloldva; nincs szükség a típus, a művelet vagy a függvény deklarációjának megírására a hivatkozás előtt.

## <a name="open-directives"></a>Megnyitási irányelvek

Egy névtér-blokkon belül az `open` direktíva egy adott névtérben deklarált összes típus és callables importálására használható, és nem minősített nevük alapján.
Egy ilyen `open` irányelv a `open` kulcsszóból áll, amelyet a megnyitandó névtér és a lezáró pontosvessző követ.

> [!NOTE] 
> `open`Az összes direktívának szerepelnie `function` kell `operation` `newtype` a névtér blokkjában, a vagy deklaráció előtt.

Ha szükséges, a megnyitott névtérhez tartozó rövid név is meghatározható úgy, hogy az adott névtérből származó összes elemet (és szükség esetén) a megadott rövid névvel kell minősíteni. Például a következő névtér-deklaráció és a megnyitási irányelvek miatt

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Ha a deklarált művelet egy műveletet használ `Op` a `Microsoft.Quantum.Intrinsic` alkalmazásból, akkor egyszerűen csak a használatával hívjuk meg `Op` .
Ha azonban egy bizonyos függvényt hív meg, akkor azt a `Fn` `Microsoft.Quantum.Math` használatával kell meghívni `Math.Fn` .

Az `open` irányelv a teljes névtér-blokkra vonatkozik egy fájlon belül.
Ezért ha egy további névteret definiálunk a fenti Q # fájlban `NS` , akkor a második névtérben definiált összes művelet/függvény/típus nem férhet hozzá a ( `Microsoft.Quantum.Intrinsic` vagy) nem a `Microsoft.Quantum.Math` nyílt irányelvek megismétléséhez, vagy nem. 

Egy másik névtérben definiált típust vagy meghívást, amelyet a jelenlegi névtérben *nem* nyitott meg, a teljes névvel kell hivatkozni.
Például a névtérből megnevezett műveletnek a `Op` `X.Y` teljesen minősített nevével kell hivatkoznia `X.Y.Op` , kivéve, ha a `X.Y` névteret az aktuális blokkban korábban megnyitották. Ahogy fent említettük, még akkor is, ha a `X` névteret megnyitották, nem lehet a műveletre hivatkozni `Y.Op` .
Ha egy rövid név `Z` `X.Y` van definiálva a névtérben és a fájlban, akkor a következőnek `Op` kell lennie: `Z.Op` . 

Általában jobb, ha egy direktíva segítségével egy névteret is tartalmaz `open` .
Teljesen minősített név használata kötelező, ha két névtér definiálja ugyanazt a nevet, és a jelenlegi forrás mindkettőből származó szerkezeteket használ.

A Q # ugyanazokat a szabályokat követi, mint az egyéb .NET-nyelvek elnevezése.
A Q # azonban nem támogatja a névterek relatív hivatkozásait.
Ha a névtér `a.b` meg lett nyitva, a nevű műveletre mutató hivatkozás `c.d` *nem* oldható fel teljes névvel rendelkező művelethez `a.b.c.d` .

## <a name="formatting"></a>Formátum

A legtöbb Q # utasítás és direktíva véget ér a záró pontosvesszővel `;` .
Az olyan utasítások és nyilatkozatok, mint a `for` és az `operation` egy utasítás blokkja (lásd alább) nem igénylik a megszakítást pontosvesszővel.
Minden utasítás leírása megállapítja, hogy kötelező-e lezáró pontosvessző.

Az utasítások, például a kifejezések, a deklarációk és az irányelvek több sorban is kibonthatók.
Az egyetlen sorban több utasítást kell elkerülni.

## <a name="statement-blocks"></a>Utasítások blokkja

A Q # utasítások utasítás blokkokba vannak csoportosítva.
Egy utasítás-blokk egy nyitó karakterrel kezdődik, `{` és egy zárással végződik `}` .

Egy másik blokkban található, lexikálisan zárt utasítási blokk a tartalmazó blokk alblokkjának tekintendő; a és az alblokkokat külső és belső blokkoknak is nevezik.

## <a name="comments"></a>Megjegyzések

A megjegyzések két továbbítási ferde vonallal kezdődnek, `//` és a sor végéig folytatódnak.
Egy Megjegyzés a Q # forrásfájlban bárhol megjelenhet.

## <a name="documentation-comments"></a>Dokumentációs megjegyzések

A három továbbítási perjeltel kezdődő megjegyzéseket `///` a fordító kifejezetten akkor kezeli, ha közvetlenül a névtér, a művelet, a specializáció, a függvény vagy a típus definíciója előtt jelennek meg.
Ebben az esetben a tartalmuk a definiált vagy felhasználó által definiált, a többi .NET-nyelvhez hasonlóan dokumentációként szolgál.

A `///` megjegyzéseken belül az API dokumentációjának részeként megjelenítendő szöveg [Markdown](https://daringfireball.net/projects/markdown/syntax)van formázva, és a dokumentáció különböző részeit a speciális névvel ellátott fejlécek jelölik.
A Markdown kiterjesztéseként a Q # által a műveletekre, a függvényekre és a felhasználó által definiált típusokra mutató kereszthivatkozások a (z) használatával is szerepelhetnek, ahol a a `@"<ref target>"` `<ref target>` hivatkozott kód objektum teljesen minősített nevével helyettesíti.
Szükség esetén a dokumentációs motor további Markdown-bővítményeket is támogat.

Például:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

A rendszer a következő neveket ismeri fel dokumentációs Megjegyzés fejlécként.

- **Összefoglalás**: egy függvény vagy művelet viselkedésének, vagy egy típus céljának rövid összefoglalása. Az összefoglalás első bekezdése a hover-információkhoz használatos. Egyszerű szövegnek kell lennie.
- **Leírás**: függvény vagy művelet viselkedésének vagy egy típusnak a leírása. Az összefoglalás és a Leírás össze van fűzve, hogy a generált dokumentációs fájlt hozza létre a függvényhez, a művelethez vagy a típushoz.
  A Leírás tartalmazhat beágyazott LaTeX-formátumú szimbólumokat és egyenleteket is.
- **Bemenet**: egy művelet vagy függvény bemeneti rekordjának leírása.
  Tartalmazhat további Markdown alszakaszokat is, amelyek a bemeneti rekord egyes elemeit jelzik.
- **Kimenet**: egy művelet vagy függvény által visszaadott rekord leírása.
- **Type Parameters**: üres szakasz, amely minden általános típusparaméter esetében egy további alszakaszt tartalmaz.
- **Példa**: egy rövid példa a művelet, a függvény vagy a típus használatban.
- **Megjegyzések**: a művelet, a függvény vagy a típus néhány aspektusát ismertető egyéb próza.
- **Lásd még**: a kapcsolódó függvényeket, műveleteket vagy felhasználó által meghatározott típusokat jelölő teljes nevek listája.
- **Hivatkozások**: a dokumentált elemre vonatkozó hivatkozások és idézetek listája.

## <a name="next-steps"></a>Következő lépések

További információ a Q #-ban [végzett műveletekről és függvényekről](xref:microsoft.quantum.guide.operationsfunctions) .