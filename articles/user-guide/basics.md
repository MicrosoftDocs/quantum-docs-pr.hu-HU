---
title: 'Q # alapjai'
description: 'A Q alapvető fogalmai #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: e77b52d1a6eb7e2f62ab12dedd75d00ac8fec4be
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327322"
---
# <a name="q-basics"></a>Q # alapjai

Ebben a szakaszban röviden bemutatjuk a Q # alapszintű építőelemeit.

Ha gyors áttekintést szeretne arról, hogy mi a Q #, és hogyan illeszkedik a Quantum Development Kit alapvető összetevőjéhez, tekintse meg a következőt: [Mi a q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Mi az a Quantum program?

Technikai szempontból a kvantum-program a klasszikus alrutinok egy adott készletét láthatja, amely a híváskor bizonyos műveleteket hajt végre a kvantum-rendszeren.
Ennek a nézetnek a fontos következménye, hogy a Q #-ban írt program nem qubits magukat közvetlenül, hanem azt is leírja, hogyan kommunikál a klasszikus vezérlő számítógépek a qubits.
A tervezés szerint a Q # így nem határozza meg a kvantum-állapotokat vagy a kvantummechanika egyéb tulajdonságait közvetlenül.
Vegyük például a {0} {1} {2} [Quantum Computing fogalmakat](xref:microsoft.quantum.concepts.intro) ismertető útmutatóban a $ \ket{+} = \left (\ket + \ket \right)/\sqrt $ állapotot.
Ha ezt az állapotot Q #-ban szeretné felkészíteni, a qubits a $ \ket {0} $ állapotú, és a $ \ket{+} = H\ket {0} $, ahol a $H $ érték a [ `H` művelet] (] (xref: Microsoft. Quantum. belső. H) által megvalósított Hadamard átalakítást használja:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Quantum állapotok a Q-ban #

Fontos, hogy a fenti program írásakor nem kifejezetten a Q #-on belüli állapotra hivatkozunk, hanem azt is, hogy a program hogyan *alakította át* az állapotot.
Ez lehetővé teszi számunkra, hogy teljesen függetlenek legyenek attól, hogy milyen kvantum-állapotot biztosítanak *az egyes* célszámítógépeken, ami különböző értelmezésekkel rendelkezhet a gépen. 

A Q # programnak nincs lehetősége arra, hogy betekintést qubit az állapotba.
A program Ehelyett olyan műveleteket hívhat meg, mint például a [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit származó információk megismerése, és olyan műveletek hívása, mint a [`X`](xref:microsoft.quantum.intrinsic.x) és a [`H`](xref:microsoft.quantum.intrinsic.h) qubit állapotának elvégzése.
Ezeket a műveleteket ténylegesen csak az adott Q # program futtatásához használt célszámítógép *végzi el.*
Ha például a programot a [teljes állapotú szimulátoron](xref:microsoft.quantum.machines.full-state-simulator)futtatja, a szimulátor a szimulált Quantum rendszernek megfelelő matematikai műveleteket hajtja végre.
De a jövő irányába szemlélve, amikor a célszámítógép egy valódi kvantum-számítógép, a Q #-ban az ilyen műveletek meghívásával irányítja a kvantum-számítógépet, hogy végrehajtsa a megfelelő *valós* műveleteket a *valós* kvantum-rendszeren (például a pontosan időzített lézeres impulzusok esetében).

A Q # program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.
Így a Q # megkönnyíti a Quantum és a hibrid kvantum – klasszikus algoritmusok kiépítését, és egyúttal általános megoldást is biztosít a célszámítógép vagy a szimulátor struktúrájára vonatkozóan.

## <a name="q-operations-and-functions"></a>Q # műveletek és függvények

Konkrétan a Q # program *műveletekből*, *függvényekből*és bármely felhasználó által definiált típusból áll. 

A műveletek a kvantum-rendszerek átalakításának leírására szolgálnak, és a Q # programok legalapvetőbb építőelemei. A Q # által meghatározott minden művelet hívhat meg tetszőleges számú egyéb műveletet.

A műveletekkel szemben a functions a tisztán *determinisztikus* klasszikus viselkedés leírására szolgál, és nem gyakorol semmilyen hatást a klasszikus számítástechnikai értékek mellett. Tegyük fel például, hogy a qubits a program végén szeretnénk mérni, és a mérési eredményeket egy tömbhöz adja.
Ebben az esetben `Measure` egy *művelet* , amely arra utasítja a célszámítógépet, hogy végezzen el egy mérést a (valós vagy szimulált) qubits, és a visszaadott eredmények tömbbe való felvételének klasszikus folyamatát a *functions*fogja kezelni.

A műveletek és a függvények együttes használata a *callables*, és a mögöttes struktúra és viselkedés a [Q # lapon lévő műveleteken és függvényeken](xref:microsoft.quantum.guide.operationsfunctions) van bevezetve.


## <a name="q-syntax-overview"></a>Q # szintaxis – áttekintés

A nyelv szintaxisa a szintaktikai módon helyes programot alkotó szimbólumok különböző kombinációit írja le.
A Q #-ban három különböző csoportban is kategorizálhatja a szintaxisának elemeit: types, Expressions és utasítások.

### <a name="types"></a>Típusok
A q # egy erősen gépelt nyelv, amely lehetővé teszi, hogy a típusok körültekintő használata segíthet a fordítónak a Q # programokkal kapcsolatos erős garanciák megadásában a fordítás ideje alatt.
A standard és a kvantum-specifikus beépített primitív típusok (például,, `Int` `Bool` és) mellett a `Qubit` `Result` Q # támogatást nyújt a felhasználó által definiált típusokhoz.
Az összes Q # különböző primitív típusát a [q # oldalon található típusok](xref:microsoft.quantum.guide.types) írják le, valamint a tömb és a rekord típusának részleteit, valamint azt, hogy miként lehet új típusokat definiálni a q #-fájlokon belül.

### <a name="expressions"></a>Kifejezések
A programozási nyelv kifejezése egy vagy több állandó, változó, operátor és függvény kombinációja, amelyet a programozási nyelv értelmez és kiértékel egy adott értékre.
A legtöbb esetben a nyelv minden típusához az adott típusú kifejezés lehet *literál* vagy szimbólum, amely egy adott típusú értékhez van kötve.
Például `5` egy `Int` literál (azaz típusú kifejezés `Int` ), és ha a szimbólum az `count` egész értékhez van kötve `5` , akkor az `count` egész szám kifejezés is.

Emellett a kifejezések tartalmazhatnak más, bizonyos operátorokkal összevont kifejezéseket is.
Ezért egy másik példa egy `Int` kifejezésre, amely a következőt értékeli: `5` `2+3` .

A Q # oldalon található típusok lehetséges kifejezései, valamint a velük megalkotható kompatibilis operátorok részletesen szerepelnek a [q # lapon a Type kifejezésekben](xref:microsoft.quantum.guide.expressions) . 

### <a name="statements"></a>Utasítások 
Az utasítás egy kötelező programozási nyelv szintaktikai egysége, amely egy művelet elvégzését fejezi ki. Az utasításokban szereplő kifejezések kontrasztja nem ad eredményül az eredményeket, és kizárólag a rájuk vonatkozó hatásuk miatt hajtja végre a kifejezéseket, míg a kifejezések mindig egy eredményt adnak vissza, és gyakran nincsenek mellékhatásai.
Ez a különbségtétel gyakran megfigyelhető a szóhasználatban: egy kifejezés kiértékelése megtörtént, míg a rendszer egy utasítást hajt végre.

A Q # egyik utasításának nagyon egyszerű példája egy szimbólum társítása egy kifejezéshez:
```qsharp
let count = 5;
```

Egy kicsit érdekesebb példa az az `for` utasítás, amely támogatja az iterációt, és tartalmaz egy *utasítás blokkot*.
Tegyük fel, `qubits` hogy a szimbólum a qubits (a típus típusa `Qubit[]` , azaz egy tömb) egy regiszteréhez van kötve `Qubit` . Majd
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
a egy olyan utasítás, amely a regisztráció minden qubit megismétli, végrehajtja a `H` műveletet mindegyiken. Vegye figyelembe, hogy `H(qubit);` egy utasítás önmagában is szerepel.

Valójában bármely típusú hívás kifejezés `Unit` (ezek a callables, amelyek nem adnak vissza adatokat) utasításként is használhatók.
Ez elsősorban akkor használatos, ha olyan műveleteket hív meg a qubits, amelyek visszaadnak, `Unit` mert az utasítás célja az implicit kvantum állapotának módosítása.
A kifejezés-értékelési utasításokhoz pontosvesszőt kell lezárni.

A Q # program csaknem minden aspektusa utasítások használatával készült, így egyetlen oldal sem terjedhet ki a rájuk vonatkozó összes információra.
Azonban a saját lexikális szerkezete és formázása a [q # file Structure](xref:microsoft.quantum.guide.filestructure) oldalon, a Symbol kötési hozzárendelés és a hatókör a [q # változóknál](xref:microsoft.quantum.guide.variables), valamint a flow-hurkok vezérlése, például a `for` [Control flow in q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Következő lépések
A jelen útmutató további részében bemutatjuk, hogyan használhatók a Q # az összetett kvantum-programok létrehozásához a műveletek, függvények és típusok alapvető építőelemei alapján.

Első lépésként megkezdheti [a Q #-ban található típusok](xref:microsoft.quantum.guide.types)megismerését.

Ha szeretne többet megtudni az alapítványokról és a Q # mögötti motivációról, tekintse meg, [Miért van szükségünk q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)elemre.
