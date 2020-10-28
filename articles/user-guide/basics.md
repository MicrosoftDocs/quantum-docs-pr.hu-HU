---
title: Q# Alapjai
description: Alapvető fogalmak Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: b3bc0841eabeac5d3968776f9dab3a02b1a1eef9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691641"
---
# <a name="no-locq-basics"></a>Q# Alapjai

Ez a cikk röviden bemutatja a alapszintű építőelemeit Q# .

A mi Q# [az Q# ?](xref:microsoft.quantum.overview.q-sharp)című témakörből megtudhatja, hogy mi az, és hol illeszkedik a Quantum Development Kit alapvető összetevőjéhez. 

## <a name="what-is-a-quantum-program"></a>Mi az a Quantum program?

Technikai szempontból a Quantum program a klasszikus alrutinok egy adott készlete, amely a híváskor bizonyos műveleteket hajt végre a kvantum-rendszeren.
Ennek a nézetnek a fontos következménye, hogy egy Q# program nem maga közvetlenül modellezi a qubits, hanem azt is leírja, hogyan kommunikál a klasszikusan vezérelt számítógépek a qubits.
A kialakítás szerint a nem Q# határozza meg a kvantum-állapotokat vagy a kvantummechanika egyéb tulajdonságait közvetlenül.
Vegyük például a {0} {1} {2} [Quantum Computing fogalmakat](xref:microsoft.quantum.concepts.intro) ismertető útmutatóban a $ \ket{+} = \left (\ket + \ket \right)/\sqrt $ állapotot.
Ha ezt az állapotot szeretné előkészíteni a alkalmazásban Q# , kezdje azzal a ténnyel, hogy a qubits a $ \ket {0} $ állapotban inicializálják, és hogy a $ \ket{+} = H\ket {0} $, ahol a $H $ a [ `H` művelet](xref:Microsoft.Quantum.Intrinsic.H)által megvalósított [Hadamard-transzformáció](xref:microsoft.quantum.glossary#hadamard). A Q# qubit inicializálásához és átalakításához szükséges alapszintű kód a következőképpen néz ki:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
A qubits inicializálásával és *lefoglalásával* kapcsolatos további információkért lásd: [a qubits használata](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-no-locq"></a>Quantum állapotok a-ben Q#

Fontos, hogy az előző program nem hivatkozik explicit módon az állapotra, Q# de azt is ismerteti, hogy a program hogyan *alakította át* az állapotot.
Ezzel a megközelítéssel teljesen agnosztikus lehet arról, hogy mi *is az egyes* célszámítógépen a kvantum-állapot, ami eltérő értelmezésekkel rendelkezhet a számítógéptől függően. 

Egy Q# program nem tud betekintést qubit állapotára.
Ehelyett egy program olyan műveleteket hívhat meg, mint például a [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) qubit származó információk megismerése, és olyan műveletek hívása, mint például a [`X`](xref:Microsoft.Quantum.Intrinsic.X) és a [`H`](xref:Microsoft.Quantum.Intrinsic.H) qubit állapotának elvégzése.
Ezeket a *műveleteket ténylegesen csak* az adott program futtatására használt célszámítógép végzi Q# .
Ha például a programot a [teljes állapotú szimulátoron](xref:microsoft.quantum.machines.full-state-simulator)futtatja, a szimulátor a szimulált kvantum-rendszernek megfelelő matematikai műveleteket hajtja végre.
De a jövő irányába szemlélve, amikor a célszámítógép egy valódi kvantum-számítógép, az ilyen műveletek meghívásával a Q# kvantum-számítógép a *valódi* kvantumrendszer megfelelő *valós* műveleteinek elvégzésére, például pontosan időzített lézeres impulzusokra irányítja a rendszert.

A Q# program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.
Ily módon megkönnyíti Q# a Quantum és a hibrid kvantum – klasszikus algoritmusok kiépítését, valamint a célszámítógép vagy szimulátor struktúrájára vonatkozó általános szempontokat is.

## <a name="no-locq-operations-and-functions"></a>Q# műveletek és függvények

Konkrétan a Q# program a *műveleteket* , a *függvényeket* és bármely felhasználó által definiált típust magában foglalja. 

A műveletek a kvantum-rendszerek átalakításának leírására szolgálnak, és a programok legalapvetőbb építőelemei Q# . Előfordulhat, hogy a ben definiált minden művelet Q# tetszőleges számú egyéb műveletet hív meg.

A műveletekkel szemben a functions a tisztán *determinisztikus* klasszikus viselkedés leírására szolgál, és nem gyakorol semmilyen hatást a klasszikus számítástechnikai értékek mellett. Tegyük fel például, hogy egy program végén szeretné mérni a qubits, és hozzáadja a mérési eredményeket egy tömbhöz.
Ebben az esetben `Measure` egy *művelet* , amely arra utasítja a célszámítógépet, hogy a (valós vagy szimulált) qubits mérést végezzen. Ugyanakkor a *functions* kezeli a visszaadott eredmények tömbbe való felvételének klasszikus folyamatát.

A műveletek és a függvények együtt *callables* néven ismertek. A rendszer az alapul szolgáló struktúrát és viselkedést is bevezeti és részletezi a [alkalmazásban Q# ](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="no-locq-syntax-overview"></a>Q# szintaxis áttekintése

A nyelv szintaxisa a szintaktikai módon helyes programot alkotó szimbólumok különböző kombinációit írja le.
A alkalmazásban a Q# szintaktikai elemek három különböző csoportba sorolhatók: típusok, kifejezések és utasítások.

### <a name="types"></a>Típusok
Q# a egy erősen gépelt nyelv, amely lehetővé teszi, hogy a típusok körültekintő használata segíthet a fordítónak a programokkal kapcsolatos erős garanciák biztosításában a Q# fordítási idő alatt.
A standard és a kvantum-specifikus beépített primitív típusok (például,,, `Int` `Bool` és) mellett a `Qubit` `Result` Q# felhasználó által definiált típusokhoz is támogatást biztosít.

Az összes primitív típus leírását, a tömb-és a rekordos típusok részleteit, valamint az új típusok fájlon belüli definiálásának lépéseit a következő Q# témakörben talál [ Q# ](xref:microsoft.quantum.guide.types):.

### <a name="expressions"></a>Kifejezések
A programozási nyelv kifejezése egy vagy több állandó, változó, operátor és függvény kombinációja, amelyet a programozási nyelv értelmez és kiértékel egy adott értékre.
A legtöbb esetben a nyelv minden típusához az adott típusú kifejezés lehet *literál* vagy szimbólum, amely egy adott típusú értékhez van kötve.
Például `5` egy `Int` literál (azaz típusú kifejezés `Int` ), és ha a szimbólum az `count` egész értékhez van kötve `5` , akkor az `count` egész szám kifejezés is.

Egy kifejezés továbbá tartalmazhat más, bizonyos operátorok által összevont kifejezéseket is.
Például egy másik `Int` kifejezés, amely kiértékeli a következőt: `5` `2+3` .

A kifejezésekkel és a kompatibilis operátorokkal kapcsolatos további információkért Q# lásd: [kifejezések Q# beírása a alkalmazásban ](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Utasítások 
Az utasítás egy kötelező programozási nyelv szintaktikai egysége, amely némi művelet elvégzését fejezi ki. Az utasításokban szereplő kifejezések kontrasztja nem adja vissza az eredményeket, és kizárólag azok mellékhatásait futtatja. A kifejezések azonban mindig visszaadnak egy eredményt, és gyakran nincsenek mellékhatásai. Röviden, az Q# utasítások futnak, míg a kifejezések kiértékelése megtörténik.

Egy utasítás egyszerű példája egy Q# szimbólum társítása egy kifejezéshez:
```qsharp
let count = 5;
```

Érdekes példa az `for` iterációt támogató utasítás, amely egy *utasítási blokkot* tartalmaz.
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

A utasítások segítségével szinte minden aspektusát felépítheti egy Q# programba, és egyetlen oldal sem terjedhet ki a rájuk vonatkozó összes információra.
További információ a lexikális szerkezetről és a formázásról: a [ Q# fájl szerkezete](xref:microsoft.quantum.guide.filestructure); a szimbólum-kötési hozzárendeléshez és a hatókörhöz lásd: [változók Q# a ](xref:microsoft.quantum.guide.variables)alkalmazásban, valamint vezérlési folyamati hurkok `for` , például: [ Q# vezérlési ](xref:microsoft.quantum.guide.controlflow)folyamat.

## <a name="next-steps"></a>Következő lépések

Megkezdheti [a típusok Q# megismerését a alkalmazásban ](xref:microsoft.quantum.guide.types).

További információ az alapokról és a motivációról Q# : [Miért van szükségünk Q# ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
