---
title: Szoftveres verem | Microsoft Docs
description: Szoftveres verem
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184729"
---
# <a name="software-stack-for-quantum-computing"></a>Szoftveres verem a kvantum-számítástechnika számára
Normál esetben, ha egy olyan számítógépet gondolunk, amely egy alkalmazást futtató egyetlen eszközt képzel el, de a modern számítástechnikai környezetek sokkal összetettebbek és fejlettebbek. Az alkalmazás, amelyet általában a több rétegben dolgozunk fel, az alkalmazás futtatását a hardver szintjén biztosítjuk. Ezek a szoftverek a teljes számítástechnikai rendszer összetettsége alapján elvonták az alkalmazási megoldások fejlesztését. Ha egy fejlesztőnek a Bus, a cache-architektúrák, a kommunikációs protokollok és több más egyszerű okostelefon-alkalmazás írásakor kellene meggondolnia, a feladat sokkal összetettebb lesz.  A *szoftveres verem* koncepcióját a klasszikus számítástechnikai szolgáltatás fejlesztette ki a problémák megoldásához.  A klasszikus koncepció alapján a szoftveres verem a kvantum-számítástechnika mögötti elképzelés kulcsfontosságú részét képezi a Q # megoldással.

## <a name="conventional-stack"></a>Hagyományos verem
A szoftveres verem mögötti legfontosabb elképzelés a rekurzió.  Több beágyazott rétegből áll, amelyek elvonták az eszköz alacsonyabb szintjeinek részleteit a fejlesztőtől.  A gyakran használt szoftverek például a ASP.NET (programozási nyelv) futtatását foglalják magukban az SQL Serveren (a kapcsolati adatbázis-kezelő rendszeren), amely a Windows Serveren futó Internet Information Services (egy webkiszolgálón) fut (a operációs rendszer), amely a számítógép hardverét irányítja.  Ha a szoftvereket hierarchiaként tekinti meg, az egyik a ASP.NET szoftvereket is írhat anélkül, hogy meg kellene ismernie az alatta lévő összes szoftver alacsony szintű részleteit.

## <a name="quantum-stack"></a>Quantum stack

A kvantum-számítástechnikai szoftveres verem elvileg nem különbözik egymástól, és a gyakorlatban a hagyományos stacknél alacsonyabb szinten működnek.  Mire hasonlít a Quantum stack?  A kvantum-számítógép nem helyettesíti a hagyományos (más néven klasszikus) számítógépeket.  Valójában a kvantum-számítógépek szinte természetesen a klasszikus számítógépekkel párhuzamosan működnek a számítási problémák megoldásához.  Ebben az esetben ez a kvantum-adatmennyiség bizonytalansága miatt fordul elő.  A kvantum-adatok annyira törékenyek, hogy ha még azt is észleli, hogy szinte biztosan megsérült a megfigyelt információ.  A kvantum-számítógépeket ezért a kvantum-hibák javításával kell tervezni, hogy a fizikai környezetből érkező kóbor interakciók ne okozzák véletlenül az információt és a számítást. Emiatt a Q # egyik természetes célpontja egy hiba-korrigált kvantum-számítógép (más néven hibatűrő kvantum *-* számítógép), amely fogadja a kvantum-utasítások (Gates vagy Gate művelet) listáját, és alkalmazza ezeket az utasításokat a kvantumra. a benne tárolt adatkészletek.  Vegye figyelembe, hogy ha egy Quantum algoritmusban vagy programban a qubits és a kapu műveleteinek száma elég kicsi, akkor előfordulhat, hogy a hibajavítás nem feltétlenül szükséges.  A qubits és a Gate-műveletek számának növekedésével azonban minden bizonnyal követelmény lesz, így a szoftveres verem és a Q # felépítése a hibajavítások és a skálázható, hibatűrő és rugalmasan méretezhető számítási feladatok hatékony kezelésére szolgál.

### <a name="error-correction"></a>Hibajavítás
A hibajavításhoz egy gyors és megbízható klasszikus számítógépnek kell futnia a kvantum-számítógéppel, hogy kijavítsa a hibákat, amint azok megjelennek a kvantum-számításokban.  A gyakorlatban az olyan összetevők, mint például a mező-programozható Gate-tömbök (FPGA-EK) vagy a gyors kriogén-processzorok, az olyan hibák azonosításához és kijavításához szükségesek, amelyek a kvantum-számítógépekben természetesen felhalmozódnak.  Ennek eredményeképpen a kvantum-számítógép olyan hibrid gép, amely számos különböző számítási eszközből áll, amelyek számos hőmérsékleten működnek.  Emiatt sokkal hasznosabb lehet a kvantum-számítógép programozása egy szoftveres verem segítségével, mivel a teljes mennyiségű hardveres és szoftveres (klasszikus és kvantum) réteg szükséges ahhoz, hogy végső soron a kvantum megvalósítását lehessen elérni. a kvantum-számítógép algoritmusa.

### <a name="quantum-conceptual-stack"></a>Quantum fogalmi verem
Alább látható egy fogalmi verem, amely bemutatja, hogy a 8704143553785700723 faktoring működési folyamata a kvantum-számítástechnikai környezetben a következő:

![Szoftveres verem](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Specifikáció és algoritmus
Az ilyen kvantum-számítások számos általános szakaszból állnak.  Az első, és vitathatatlanul a legnagyobb kihívást jelentő fázis a megoldás, amelyet az egyik meg kíván oldani.  Ebben az esetben a probléma az, hogy a 8704143553785700723-es számot egy két fő számból álló termékbe kell felvenni.  A következő lépés egy algoritmus megtervezését foglalja magában a számítási probléma megoldásához.  Ebben az esetben a rövid híres Quantum faktoring algoritmusa segítségével megtalálhatja a tényezőket.  Ez az algoritmus Q # értékben van kifejezve, majd a Quantum Operations sorozata kimenete, amely egy idealizált, hibamentes kvantum-számítógépen futtatható.  

### <a name="physical-gates"></a>Fizikai kapuk
Ebben a példában feltételezhető, hogy a természet nem olyan típusú, mint egy hibamentes kvantum-számítógép, így a következő lépés a Q # által kibocsátott műveleteket veszi át, és lefordítja őket a fizikai kapuk számára kiválasztott kvantum-hibajavítási módszer által megadott sablonok használatával. az alapszintű hardver végrehajtható.  Ez a folyamat magában foglalja az előző modellben leírt minden logikai qubit egy fizikai qubits való cseréjét, amely egy olyan redundáns módon tárolja és védik az adatokat, amely képes a helyi hibák elhárítására a fizikai környezeten belül az ilyen hibák észlelése és javítása qubits elég hosszú.  Ugyanúgy, ahogy a Q # kód által leírt logikai qubits le kell cserélni számos fizikai qubits, hasonlóképpen a kimenetben ismertetett összes kvantum-kaput le kell fordítani a fizikai qubits alapuló fizikai kapuk sorába.  Emiatt a Q # kimenete ritkán a kvantum-számítástechnika végső célja, és további absztrakciós szintek szükségesek ahhoz, hogy a kód a hardveren egy feledékeny módon fusson.

### <a name="control-computer"></a>Számítógép vezérlése
A rendszer ezután betölti a fizikai Gate-sorozatot egy olyan normál számítógépre, amely elküldi ezeket az utasításokat egy olyan vezérlő számítógépnek, amely közvetlenül a kvantum-számítógéppel csatlakozik.  A szoftveres veremben lévő réteget gyakran a kísérleti vezérlő szoftverek, például a [QCoDeS](http://qcodes.github.io/Qcodes/)kezelik.

### <a name="interface-computer"></a>Csatoló számítógép
A folyamat utolsó lépéseként a csatoló számítógépe először a kapukat a gyors vezérlésű számítógépnek megfelelően közvetíti. Ezután a gyors vezérlésű számítógép alkalmazza a szükséges feszültségeket (általában impulzusok) a szükséges kapuk megvalósításához a qubits. Ezt el kell végezni a kvantum-hibajavítás során észlelt hibák kijavítása során.  A kriogén FPGA vagy más egzotikus hardver szükséges lehet ezen lépések végrehajtásához a kvantum-számítógépen előforduló hibák száma alapján.  Az ezen a szinten található célnyelv gyakran [VHDL](https://en.wikipedia.org/wiki/VHDL), ami azt feltételezi, hogy a verem felső végén használt módszernek a Quantum algoritmus leírását kell elemezni.

### <a name="the-q-quantum-programming-language"></a>A Q # Quantum programozási nyelv
A Q # célja, hogy egy egyszerű nyelvet adjon meg, amely lehetővé teszi a fejlesztők számára, hogy olyan kódot írjanak elő, amely a felhasználó és a kvantum-eszköz között álló, beavatkozó réteggel rendelkező, a felhasználók és a kvantum-eszközök közötti adatmennyiséget célozza meg.  A nyelv megkönnyíti ezt azáltal, hogy bevezeti egy szoftver-verem fogalmát, és az alapul szolgáló kvantum-számítógép számos részletét kiveszi, miközben a verem más szintjein keresztül C#teszi elérhetővé a szükséges a Q # kód és az alapvető műveletek közötti fordítások.  Ez lehetővé teszi, hogy a fejlesztő a legjobban a legjobbra koncentráljon: algoritmusok tervezése és problémák megoldása.
