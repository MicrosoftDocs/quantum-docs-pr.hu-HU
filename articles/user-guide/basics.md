---
title: 'Q # alapjai'
description: 'A Q alapvető fogalmai #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415359"
---
# <a name="q-basics"></a>Q # alapjai

Ez a cikk röviden bemutatja a Q # alapszintű építőelemeit.

A Q #-ról és a Quantum Development Kit alapvető összetevőinek áttekintéséhez lásd: [Mi a q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Mi az a Quantum program?

Technikai szempontból a Quantum program a klasszikus alrutinok egy adott készlete, amely a híváskor bizonyos műveleteket hajt végre a kvantum-rendszeren.
Ennek a nézetnek a fontos következménye, hogy a Q # program nem qubits magukat közvetlenül, hanem leírja, hogyan kommunikál a klasszikusan vezérelt számítógépek a qubits.
A tervezés szerint a Q # nem határozza meg a kvantum-állapotokat vagy a kvantummechanika egyéb tulajdonságait közvetlenül.
Vegyük például a {0} {1} {2} [Quantum Computing fogalmakat](xref:microsoft.quantum.concepts.intro) ismertető útmutatóban a $ \ket{+} = \left (\ket + \ket \right)/\sqrt $ állapotot.
Ha ezt az állapotot a Q #-ban szeretné előkészíteni, kezdje azzal a ténnyel, hogy a qubits a $ \ket {0} $ állapotban inicializálják, és hogy a $ \ket{+} = H\ket {0} $, ahol a $H $ a [ `H` művelet](xref:microsoft.quantum.intrinsic.h)által megvalósított [Hadamard-transzformáció](xref:microsoft.quantum.glossary#hadamard). A qubit inicializálásához és átalakításához szükséges alapszintű Q # kód a következőképpen néz ki:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
A qubits inicializálásával és *lefoglalásával*kapcsolatos további információkért lásd: [a qubits használata](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-q"></a>Quantum állapotok a Q-ban #

Fontos, hogy az előző program nem hivatkozik kifejezetten a Q # állapotára, de azt is ismertette, hogy a program hogyan *alakította át* az állapotot.
Ezzel a megközelítéssel teljesen agnosztikus lehet arról, hogy mi *is az egyes* célszámítógépen a kvantum-állapot, ami eltérő értelmezésekkel rendelkezhet a számítógéptől függően. 

A Q # program nem tud betekintést kimutatni egy qubit állapotával.
Ehelyett egy program olyan műveleteket hívhat meg, mint például a [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit származó információk megismerése, és olyan műveletek hívása, mint például a [`X`](xref:microsoft.quantum.intrinsic.x) és a [`H`](xref:microsoft.quantum.intrinsic.h) qubit állapotának elvégzése.
Ezeket a műveleteket ténylegesen csak az adott Q # program futtatására használt *célszámítógép végzi.*
Ha például a programot a [teljes állapotú szimulátoron](xref:microsoft.quantum.machines.full-state-simulator)futtatja, a szimulátor a szimulált kvantum-rendszernek megfelelő matematikai műveleteket hajtja végre.
De a jövő irányába szemlélve, amikor a célszámítógép egy valódi kvantum-számítógép, a Q #-ban az ilyen műveletek meghívásával a kvantum-számítógép elvégzi a megfelelő *valós* műveleteket a *valós* kvantum-rendszeren, például pontosan időzített lézeres impulzusokat.

A Q # program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.
Így a Q # megkönnyíti a Quantum és a hibrid kvantum – klasszikus algoritmusok kiépítését, és egyúttal általános megoldást is biztosít a célszámítógép vagy a szimulátor struktúrájára vonatkozóan.

## <a name="q-operations-and-functions"></a>Q # műveletek és függvények

Konkrétan a Q # program a *műveleteket*, a *függvényeket*és a felhasználó által definiált típusokat tartalmazza. 

A műveletek a kvantum-rendszerek átalakításának leírására szolgálnak, és a Q # programok legalapvetőbb építőelemei. A Q # által meghatározott minden művelet hívhat meg tetszőleges számú egyéb műveletet.

A műveletekkel szemben a functions a tisztán *determinisztikus* klasszikus viselkedés leírására szolgál, és nem gyakorol semmilyen hatást a klasszikus számítástechnikai értékek mellett. Tegyük fel például, hogy egy program végén szeretné mérni a qubits, és hozzáadja a mérési eredményeket egy tömbhöz.
Ebben az esetben `Measure` egy *művelet* , amely arra utasítja a célszámítógépet, hogy a (valós vagy szimulált) qubits mérést végezzen. Ugyanakkor a *functions* kezeli a visszaadott eredmények tömbbe való felvételének klasszikus folyamatát.

A műveletek és a függvények együtt *callables*néven ismertek. A rendszer az alapul szolgáló struktúrát és viselkedést a [Q #-ban ismertetett műveletekben és funkciókban](xref:microsoft.quantum.guide.operationsfunctions)részletezi.


## <a name="q-syntax-overview"></a>Q # szintaxis – áttekintés

A nyelv szintaxisa a szintaktikai módon helyes programot alkotó szimbólumok különböző kombinációit írja le.
A Q #-ban a szintaktikai elemek három különböző csoportba sorolhatók: típusok, kifejezések és utasítások.

### <a name="types"></a>Típusok
A q # egy erősen gépelt nyelv, amely lehetővé teszi, hogy a típusok körültekintő használata segíthet a fordítónak a Q # programokkal kapcsolatos erős garanciák megadásában a fordítás ideje alatt.
A standard és a kvantum-specifikus beépített primitív típusok (például,,, `Int` `Bool` és) mellett a `Qubit` `Result` Q # támogatja a felhasználó által definiált típusokat.

Az összes primitív típus leírását, a tömb és a rekord típusának részleteit, valamint az új típusok Q # fájlon belüli definiálásának lépéseit lásd: [types in q #](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Kifejezések
A programozási nyelv kifejezése egy vagy több állandó, változó, operátor és függvény kombinációja, amelyet a programozási nyelv értelmez és kiértékel egy adott értékre.
A legtöbb esetben a nyelv minden típusához az adott típusú kifejezés lehet *literál* vagy szimbólum, amely egy adott típusú értékhez van kötve.
Például `5` egy `Int` literál (azaz típusú kifejezés `Int` ), és ha a szimbólum az `count` egész értékhez van kötve `5` , akkor az `count` egész szám kifejezés is.

Egy kifejezés továbbá tartalmazhat más, bizonyos operátorok által összevont kifejezéseket is.
Például egy másik `Int` kifejezés, amely kiértékeli a következőt: `5` `2+3` .

A Q # kifejezésekkel és kompatibilis operátorokkal kapcsolatos további információkért lásd: [kifejezések megadása a q #](xref:microsoft.quantum.guide.expressions)-ban. 

### <a name="statements"></a>Utasítások 
Az utasítás egy kötelező programozási nyelv szintaktikai egysége, amely némi művelet elvégzését fejezi ki. Az utasításokban szereplő kifejezések kontrasztja nem ad eredményül az eredményeket, és kizárólag azok mellékhatásait hajtja végre. A kifejezések azonban mindig visszaadnak egy eredményt, és gyakran nincsenek mellékhatásai. A short, a Q # utasítások végrehajtásakor a rendszer kiértékeli a kifejezéseket.

A Q # egyik utasításának egyszerű példája egy szimbólum társítása egy kifejezéshez:
```qsharp
let count = 5;
```

Érdekes példa az `for` iterációt támogató utasítás, amely egy *utasítási blokkot*tartalmaz.
Tegyük fel, `qubits` hogy a szimbólum a qubits (technika típusa `Qubit[]` vagy típusú tömb) egy regiszteréhez van kötve `Qubit` . Majd
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
a egy olyan utasítás, amely a regisztráció minden qubit megismétli a műveletet, és mindegyiken végrehajtja a `H` műveletet. Vegye figyelembe, hogy `H(qubit);` egy utasítás önmagában is szerepel.

Bármilyen típusú hívási kifejezést használhat `Unit` (a `Unit` típus nem ad vissza adatokat) utasításként.
Ez a típusú kifejezés akkor hasznos, ha olyan qubits-műveleteket hív meg, amelyek visszaadnak, `Unit` mert az utasítás célja az implicit kvantum állapotának módosítása.
A kifejezés-értékelési utasításokhoz pontosvesszőt kell lezárni.

Egy Q # program szinte minden aspektusának összeállításához utasításokkal kell elkészíteni, és egyetlen oldal sem terjedhet ki a rájuk vonatkozó összes információra.
További információ a lexikális szerkezetről és a formázásról: [Q # file Structure](xref:microsoft.quantum.guide.filestructure); a szimbólum-kötési hozzárendelés és a hatókör esetében lásd: [változók a Q #](xref:microsoft.quantum.guide.variables); és a vezérlési folyamathoz kapcsolódó hurkok `for` , például: [vezérlési folyamat a Q #-ban](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>További lépések

Megkezdheti [a Q #-beli típusok](xref:microsoft.quantum.guide.types)megismerését.

Ha többet szeretne megtudni az alapjairól és a Q # mögötti motivációról, olvassa el a [Miért van szükségünk q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)című témakört.
