---
title: 'Q # fájl szerkezete'
description: 'A Q # fájl szerkezetét és szintaxisát ismerteti.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884177"
---
# <a name="q-file-structure"></a>Q # fájl szerkezete

A Q # fájl *névtér-deklarációk*sorozatából áll.
Minden névtér-deklaráció a felhasználó által definiált típusokra, műveletekre és függvényekre vonatkozó deklarációkat tartalmaz, és tetszőleges számú deklarációt és sorrendet is tartalmazhat.
A névtéren belüli deklarációkkal kapcsolatos további információkért lásd: [felhasználó által definiált típusok](xref:microsoft.quantum.guide.types#user-defined-types), [műveletek](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)és [függvények](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).

A névtér deklarációján kívül megjelenő szöveg Megjegyzés.
Különösen a deklaráció előtt a névtérhez tartozó dokumentációs megjegyzések szerepelnek. További információ: [dokumentációs megjegyzések](#documentation-comments) ebben a cikkben. 

## <a name="namespace-declarations"></a>Névtér-deklarációk

A Q # fájlnak általában csak egy névtér-deklarációja van, de a none (és nem lehet üres, vagy csak megjegyzéseket tartalmazhat), vagy több névteret tartalmazhat.
A névtér deklarációi nem ágyazhatók egymásba.

Megadhatja ugyanazt a névteret több, egymással összeállított Q #-fájlban, feltéve, hogy nincs ilyen nevű típus, művelet vagy függvény deklarációja.
Bizonyos esetben a több fájl azonos névterében lévő azonos típust nem lehet megadnia, még akkor is, ha a deklarációk azonosak.

A névtér deklarációja a kulcsszóból áll `namespace` , amelyet a névtér neve, valamint a névtérben található, kapcsos zárójelek közé tartozó deklarációk követnek `{ }` .
A névterek nevei egy vagy több, ponttal elválasztott jogi szimbólum sorozatának .NET-mintáját követik `.` .
Például `MyQuantumStuff` és `Microsoft.Quantum.Intrinsic` érvényes névterek nevei.
A (z) konvenció szerint kihasználja a névterek nevét, azonban ez nem kötelező.

A fájlokban a fájlban lejjebb szereplő típusokra vagy callables mutató hivatkozások megfelelően vannak deklarálva; nincs szükség a típus, a művelet vagy a függvény deklarációjának megírására a hivatkozás előtt.

## <a name="open-directives"></a>Megnyitási irányelvek

Egy névtérbeli blokkon belül a `open` direktívával importálhat egy adott névtérben deklarált összes típust és callables, és azok nem minősített nevük alapján is hivatkozhat rájuk.
Egy ilyen `open` irányelv a `open` kulcsszóból áll, amelyet a megnyitandó névtér és a lezáró pontosvessző követ.

> [!NOTE] 
> `open`Az összes direktívának szerepelnie `function` kell `operation` `newtype` a névtér blokkjában, a vagy deklaráció előtt.

Igény szerint megadhat egy rövid nevet a megnyitott névtérhez. Ha meg van adva egy rövid név, a megadott rövid névvel meg kell felelnie a névtér összes elemének. Például a következő névtér-deklaráció és a megnyitási irányelvek miatt

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Ha egy deklarált művelet `Op` a-ból származó műveletet használ `Microsoft.Quantum.Intrinsic` , egyszerűen hívja meg a következő használatával: `Op` .
Ahhoz azonban, hogy egy bizonyos függvényt meghívjon `Fn` `Microsoft.Quantum.Math` , azt a használatával kell meghívnia `Math.Fn` .

Az `open` irányelv a teljes névtér-blokkra vonatkozik egy fájlon belül.
Ezért ha egy további névteret határoz meg ugyanabban a Q # fájlban, mint `NS` korábban, akkor a második névtérben definiált összes művelet/függvény/típus nem fér hozzá semmihez, `Microsoft.Quantum.Intrinsic` vagy `Microsoft.Quantum.Math` csak abban az esetben, ha megismétli a megnyitott irányelveket. 

Ha olyan típusra vagy hívható hivatkozásra szeretne hivatkozni, amely *nem* az aktuális névtérben van megnyitva, akkor azt a teljesen minősített névvel kell megadnia.
Például `Op` a névtérből megnevezett művelet miatt `X.Y` :

* Ezt a teljes név alapján kell megadnia `X.Y.Op` , kivéve, ha a `X.Y` névteret már korábban megnyitották az aktuális blokkban. 
* Még ha a `X` névtér is meg van nyitva, a műveletre nem lehet hivatkozni `Y.Op` .
* Ha a rövid nevet adta meg `Z` a `X.Y` névtérben és a fájlban, a következőre kell hivatkoznia: `Op` `Z.Op` . 

Általában jobb, ha egy direktíva segítségével egy névteret is tartalmaz `open` .
Teljesen minősített név használata kötelező, ha két névtér definiálja ugyanazt a nevet, és a jelenlegi forrás mindkettőből származó szerkezeteket használ.

A Q # ugyanazokat a szabályokat követi, mint az egyéb .NET-nyelvek elnevezése.
A Q # azonban nem támogatja a névterek relatív hivatkozásait.
Ha például a névtér `a.b` meg van nyitva, egy nevű műveletre mutató hivatkozás `c.d` *nem* oldható fel teljes nevű műveletre `a.b.c.d` .

## <a name="formatting"></a>Formátum

A legtöbb Q # utasítás és direktíva véget ér a záró pontosvesszővel `;` .
Az olyan utasítások és deklarációk, mint a `for` és az `operation` egy utasítás blokkja (lásd a következő szakaszt) nem igénylik a megszakítást pontosvesszővel.
Minden utasítás leírása megállapítja, hogy kötelező-e lezáró pontosvessző.

Az utasítások, például a kifejezések, a deklarációk és az irányelvek több sorban is kibonthatók.
Kerülje a több utasítás egyetlen sorra való elhelyezését.

## <a name="statement-blocks"></a>Utasítások blokkja

A Q # utasítások a kapcsos zárójelek közé tartozó utasítási blokkokba vannak csoportosítva `{ }` . Egy utasítás-blokk egy nyitó karakterrel kezdődik, `{` és egy zárással végződik `}` .

Egy másik blokkban található, lexikálisan zárt utasítási blokk a tartalmazó blokk alblokkjának tekintendő; a és az alblokkokat külső és belső blokkoknak is nevezik.

## <a name="comments"></a>Megjegyzések

A megjegyzések két továbbítási perjeltel kezdődnek, `//` és a sor végéig folytatódnak.
A megjegyzések bárhol megjelenhetnek a Q # forrásfájlban.

## <a name="documentation-comments"></a>Dokumentációs megjegyzések

A három továbbítási perjeltel kezdődő megjegyzéseket `///` a fordító kifejezetten akkor kezeli, ha közvetlenül a névtér, a művelet, a specializáció, a függvény vagy a típus definíciója előtt jelennek meg.
Ebben az esetben a fordító dokumentációként kezeli őket a definiált vagy felhasználó által definiált típushoz, ugyanúgy, mint a többi .NET-nyelvre.

A `///` megjegyzéseken belül az API dokumentációjának részeként megjelenő szöveg [Markdown](https://daringfireball.net/projects/markdown/syntax)van formázva, a dokumentáció különböző részeivel, amelyeket a speciális névvel ellátott fejlécek jeleznek.
A Markdown használja a `@"<ref target>"` bővítményt a Q #-ban a kereszthivatkozási műveletekhez, a függvényekhez és a felhasználó által definiált típusokhoz. Cserélje le a helyére a `<ref target>` hivatkozott kód objektum teljes nevét.
A különböző dokumentációs motorok további Markdown-bővítményeket is támogatnak.

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

A következő nevek érvényesek a dokumentációs Megjegyzés fejlécei.

- **Összefoglalás**: egy függvény vagy művelet viselkedésének vagy egy típus célnak a rövid összefoglalása. Az összefoglalás első bekezdése a hover-információkhoz használatos. Egyszerű szövegnek kell lennie.
- **Leírás**: egy függvény vagy művelet viselkedésének vagy egy típus céljának a leírása. Az összefoglalás és a Leírás együttesen a függvény, művelet vagy típus számára létrehozott dokumentációs fájlt alkotja.
  A Leírás támogatja a beépített LaTeX formátumú szimbólumokat és egyenleteket.
- **Bemenet**: egy művelet vagy függvény bemeneti rekordjának leírása.
  Tartalmazhat további Markdown alszakaszokat is, amelyek a bemeneti rekord egyes elemeit jelzik.
- **Kimenet**: egy művelet vagy függvény által visszaadott rekord leírása.
- **Type Parameters**: üres szakasz, amely minden általános típusparaméter esetében egy további alszakaszt tartalmaz.
- **Példa**: a művelet, a függvény vagy a típus használatának rövid példája.
- **Megjegyzések**: a művelet, a függvény vagy a típus néhány aspektusát ismertető egyéb próza.
- **Lásd még**: a kapcsolódó függvényeket, műveleteket vagy felhasználó által meghatározott típusokat jelölő teljes nevek listája.
- **Hivatkozások**: a dokumentált elemre vonatkozó hivatkozások és idézetek listája.

## <a name="next-steps"></a>Következő lépések

További információ a Q #-ban [végzett műveletekről és függvényekről](xref:microsoft.quantum.guide.operationsfunctions) .