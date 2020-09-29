---
title: A kvantum-számítástechnika ismertetése
description: Mik a kvantumszámítógépek, és hogyan használják a kvantummechanika alapelveit?
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
no-loc:
- Q#
- $$v
ms.openlocfilehash: 332afb4ea7de01da5d8f22fee6517032ed4f9fc1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834992"
---
# <a name="understanding-quantum-computing"></a>A kvantum-számítástechnika ismertetése

A kvantum-számítástechnikában a kvantummechanika alapelveit alkalmazva dolgozzák fel az adatokat. Ezért a kvantum-számítástechnikához más megközelítésre van szükség, mint a hagyományos számítástechnikához. Erre a különbségre egy példa a kvantum-számítógépekben használt processzor. Míg a klasszikus számítógépek ismerős, szilíciumalapú chipeket használnak, a kvantum-számítógépek kvantumrendszereket használnak, például atomokat, ionokat, fotonokat vagy elektronokat. A kvantumtulajdonságaik révén különböző, a 0 és az 1 értéket egyszerre lefedő kvantum-szuperpozícióban lévő biteket képesek előkészíteni.  

A kvantumanyagok a kvantummechanika törvényei szerint viselkednek, olyan alapelveket kihasználva, mint a valószínűségszámítás, a szuperpozíció és az összefonódás. Ezek az alapelvek olyan kvantumalgoritmusok alapját képezik, amelyek a kvantum-számítástechnika hatékonyságát használják összetett problémák megoldásához. Ez a cikk a kvantummechanika néhány olyan lényeges alapelvét írja le, amelyre a kvantum-számítástechnika is épül.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>A kvantummechanika madártávlatból

A kvantummechanika, más néven a kvantumelmélet a fizika olyan ága, amely atomi és szubatomi szinten foglalkozik a részecskékkel. A kvantum szintjén azonban a mechanika sok biztosnak vélt törvénye nem érvényes. A szuperpozíció, a kvantummérés és az összefonódás a kvantum-számítástechnika három központi jelensége.  

### <a name="superposition-vs-binary-computing"></a>Szuperpozíció és bináris számítástechnika

Tegyük fel, hogy Ön a nappalijában edz. Teljesen elfordul balra, majd teljesen jobbra. Most forduljon egyszerre balra és jobbra. Nem tudja megcsinálni (legalábbis anélkül nem, hogy ketté ne osztódna).  Nyilvánvaló, hogy egyszerre nem lehet mindkét helyzetben – nem tud ugyanabban a pillanatban balra és jobbra is nézni.

Ha viszont Ön egy kvantumrészecske, akkor a **szuperpozíció** (más néven **koherencia**) néven ismert jelenség révén bizonyos valószínűséggel *balra néz*, ÉS bizonyos valószínűséggel *jobbra néz*.

A kvantumrészecskéknek, például az elektronoknak megvannak a maguk „balra néző vagy jobbra néző” tulajdonságaik, mint amilyen a **pörgés**, amelyhez a felfelé és a lefelé tulajdonság társítható, de a klasszikus bináris számítástechnikánál maradva mondjuk, hogy 1 vagy 0 lehet az értékük. Amikor egy kvantumrészecske szuperpozícióban van, akkor az az 1 és 0 közötti végtelen számú állapot lineáris kombinációja, de nem tudni, hogy melyik, amíg ténylegesen meg nem nézzük, ami a következő jelenséghez vezet, a **kvantumméréshez**.

### <a name="quantum-measurement"></a>Kvantummérés

Most tegyük fel, hogy a barátja meglátogatja, és készíteni szeretne egy fényképet arról, ahogy Ön edz. A legvalószínűbb, hogy egy homályos képet készít, amelyen a teljesen balra és teljesen jobbra forduló állapot között látható.

De ha Ön egy kvantumrészecske, érdekes dolog történik. Függetlenül attól, hogy Ön milyen pozícióban van a kép készítésekor, mindig vagy teljesen balra, vagy teljesen jobbra fordul majd rajta – nem jelenik meg köztes állapotban.

Ennek az az oka, hogy a kvantumrészecskék megfigyelése vagy mérése **összeomlasztja** a szuperpozíciós állapotot (más néven **dekoherencia** történik), a részecske pedig a klasszikus 1 vagy 0 bináris állapotba kerül.

Ez a bináris állapot hasznos számunkra, mert a számítástechnikában sok mindenre lehet használni az 1-eseket és a 0-kat. Egy kvantumrészecske megmérése után azonban örökké abban az állapotban marad, amellyel végül egybeesett (hasonlóan a fényképhez), és mindig 1 vagy 0 lesz. Ahogy azonban később látni fogja, a kvantum-számítástechnikában vannak olyan műveletek, amelyek „vissza tudják állítani” a részecskéket a szuperpozíciós állapotba, hogy ismét használhatók legyenek a kvantumszámításokhoz.

### <a name="entanglement"></a>Összefonódás

A kvantummechanika valószínűleg legérdekesebb jelensége, hogy két vagy több kvantumrészecske **össze tud fonódni** egymással. Amikor részecskék fonódnak össze, egyetlen rendszert alkotnak, így egyetlen részecske kvantumállapota sem írható le a többi részecske kvantumállapotától függetlenül. Ez azt jelenti, hogy bármilyen műveletet vagy folyamatot alkalmaz az egyik részecskére, az a többi részecskére is hat.

Az egymástól való függőség mellett a részecskék akkor is képesek megőrizni ezt a kapcsolatot, ha hihetetlenül nagy távolság, akár fényévek választják el őket egymástól. A kvantummérés hatásai az összefonódott részecskékre is érvényesek, tehát amikor egy részecskét megmérnek, és felvesz egy állapotot, akkor a másik részecskével ugyanez történik. Mivel az összefonódott qubitek között korreláció van, egy qubit állapotának megmérése a többi qubit állapotáról is információt nyújt – ez a tulajdonság nagyon hasznos a kvantum-számítástechnikában.

### <a name="qubits-and-probability"></a>Qubitek és valószínűség

A hagyományos számítógépek bitekben tárolják és dolgozzák fel az információkat, amelyek állapota 1 vagy 0 lehet, de mindkettő soha. A kvantum-számítástechnikában ennek a **qubit** felel meg, amely egy kvantumrészecske állapotát képviseli. A szuperpozíció miatt a qubitek értéke 1 vagy 0, illetve ezek között bármi lehet. A konfigurációtól függően van egy bizonyos *valószínűsége* annak, hogy a qubit 1-gyel vagy 0-val esik egybe. A **kvantum-interferencia** határozza meg annak valószínűséget, hogy a qubit az egyik vagy a másik értékkel esik-e egybe. 

Emlékszik a barátjára, aki a képet készítette? Tegyük fel, hogy a fényképezőgépén speciális szűrők vannak, úgynevezett *interferenciaszűrők*. Ha a *70/30* szűrőt választja, és elkezd fényképezni, a képek 70%-án balra fog nézni, a 30%-ukon pedig jobbra. A szűrő módosította a fényképezőgép szokásos állapotát a viselkedése valószínűségének befolyásolása érdekében.

A kvantum-interferencia ugyanilyen hatással van a qubitek állapotára, hogy a mérés során befolyásolja bizonyos eredmények valószínűségét, és a kvantum-számítástechnika ennek a valószínűségi állapotnak a terén remekel.

Egy hagyományos számítógépen például két bit esetén az egyes bitek 1 vagy 0 értékkel rendelkezhetnek, együtt tehát négy lehetséges értéket tárolhat velük (**00**, **01**, **10** és **11**), de egyszerre csak az egyiket. Két, szuperpozícióban lévő qubit esetén azonban mindkét qubit lehet 1, 0 vagy *mindkettő*, így egyszerre jelölhetik ugyanazt a négy értéket. Három qubittel nyolc értéket jelölhet, négy qubittel 16-ot és így tovább.

## <a name="summary"></a>Összefoglalás

Ezek a fogalmak csak a kvantummechanika felszínét súrolják, de alapvető fontosságúak a kvantum-számítástechnikában.

- **Szuperpozíció** – A kvantumrészecskék azon képessége, amellyel az összes lehetséges állapot kombinációja lehetnek.
- **Kvantummérés** – A szuperpozícióban lévő kvantumrészecskék megfigyelése, amely a lehetséges állapotok egyikét eredményezi.
- **Összefonódás** – A kvantumrészecskék azon képessége, amellyel korrelálni tudják egymással a mérési eredményeiket.
- **Qubit** – Az információk alapegysége a kvantum-számítástechnikában. Egy qubit egy kvantumrészecskét képvisel az összes lehetséges állapot szuperpozíciójában.
- **Interferencia** – A qubit a szuperpozíció miatti eredendő viselkedése, amellyel az egyik vagy másik értékkel való egybeesés valószínűsége befolyásolható.

## <a name="next-steps"></a>Következő lépések

[A kvantumszámítógépek és a kvantumszimulátorok](xref:microsoft.quantum.overview.simulators)
