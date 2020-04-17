---
title: Mire képesek a kvantumszámítógépek?
description: Tudjon meg többet a kvantum-számítástechnika hatásáról, az új kvantumalgoritmusoktól a klasszikus számítógépeken futó kvantum ihlette algoritmusokig.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2020
ms.locfileid: "73529953"
---
# <a name="what-can-a-quantum-computer-do"></a>Mire képesek a kvantumszámítógépek?

Mit tud egy kvantumszámítógép, amit egy klasszikus nem?

A világ legnagyobb kihívást okozó problémáira a jelenlegi számítógépek több milliárd év után szolgáltatnának megoldást, míg egy kvantumszámítógép napok, órák vagy csupán percek alatt képes ugyanerre.

A kvantum-számítástechnika segít a kutatóknak kifejleszteni új katalizátorokat és anyagokat, fokozni a gyógyszerek hatását, gyorsítani a mesterséges intelligencia előrehaladását, és megválaszolni az alapvető kérdéseket a világegyetem eredetéről.

## <a name="quantum-simulation"></a>Kvantumszimuláció

A kvantumprogramok kvantumrendszerek modellezéséhez történő használata hatalmas potenciállal rendelkezik ahhoz, hogy innovációhoz vezető megállapításokat tegyen elérhetővé számos iparágban. A fotoszintézis, a szupravezetők és az összetett molekulák például olyan kvantumrendszerek, amelyek a kvantumprogramok segítségével szimulálhatók.

Meglehetősen drága az olyan mikroszkopikus rendszerek szimulálása, amelyek a kvantummechanika törvényei szerint viselkednek. Figyelembe kell vennünk minden lehetséges állapotot, amelyek a szuperpozíciókban lehetnek, és az állapotok száma exponenciálisan növekszik a rendszer méretével. Egy kvantumszámítógépnek nincs szüksége a rendszer minden állapotának lemodellezésére. Ehelyett magába a számítógép qubitjébe ágyazzuk a szimulálandó rendszer kvantumállapotát, majd lefuttatjuk a szimulációt kvantumkapuk egy megadott készletével. Más szóval kvantum-számítástechnikát alkalmazunk egy kvantumrendszer szimulálására.

A vegyi molekulák kvantumrendszerek, így ilyen módon lehetőség nyílik az elemezésükre. Egy ilyesfajta vegyület a _nitrogenáz_ enzim, amely – a tulajdonságai teljesebb megértésével – a jelenlegi műtrágyák energiafelhasználását és az üvegházhatású gázok kibocsátását képes potenciálisan csökkenteni.

## <a name="cryptography"></a>Titkosítás

A kvantumszámítógépek leghíresebb alkalmazási területe valószínűleg a kriptográfia, amellyel kapcsolatban Peter Shor 1994-ben megállapította, hogy egy skálázható kvantumszámítógép az összes széles körben használt titkosítási technikát fel tudja törni.  A klasszikus kriptográfia a nagy számokkal végrehajtott műveletek megoldhatatlanságán alapszik, ilyen például a nagy számok két prímszámra történő prímfelbontása.

A kvantum-számítástechnika ezeket a műveleteket elméletben (Shor algoritmusán keresztül) megoldhatóvá teszi. Bár az algoritmus implementálása fizikai akadályokba ütközik a kvantumhardverek jelenlegi keretei között, elindította a kvantumrezisztens algoritmusok fejlesztését a jövőálló adatbiztonság terén, beleértve a titkosításhoz és a kriptográfiai kulcselosztáshoz használatos új kvantumalgoritmusok megalkotását.

A Microsoft világelső posztkvantum-kriptográfiai és biztonsági csapata kvantumrezisztens algoritmusok kifejlesztésén dolgozik.

## <a name="optimization"></a>Optimalizálás

Az optimalizálás egy olyan feladat, amely során a rendszer nagy léptékű keresést hajt végre egy magas dimenziójú térben egy olyan megoldás után kutatva, amely minimalizálja az adott költségfüggvényt.   A kvantumszámítógépeken fel tudjuk gyorsítani az optimalizálási algoritmusokat, így olyan megoldásokra találhatunk rá, amelyekre egyébként képtelenek lettünk volna. Alkalmazásuk történhet szállítmányozási és logisztikai, egészségügyi, diagnosztikai és anyagtudományi területen. és ezen iparágak hatékonyabbá válására jelentős hatást gyakorolhatnak.

A kvantum-számítástechnikával történő optimalizálás olyan módon teszi lehetővé a szállítmányozás és a logisztika innovációját, ahogy a jelenlegi klasszikus rendszerek képtelenek lennének.

A forgalom áramlásának optimalizálása csökkentheti a torlódást.  Az útvonaltervezés mellett számos más funkciót tölthet be, például egy repülőtéri kapu hozzárendelését, a csomagszállítást vagy a feladatütemezést. Az anyagtudomány áttöréseinek köszönhetően az energia új formái, nagyobb teljesítményű akkumulátorok, valamint könnyebb és erősebb anyagok válnak elérhetővé.

## <a name="machine-learning"></a>Gépi tanulás

A klasszikus számítástechnikában a numerikus számítások nagy része lineáris egyenletrendszerek megoldásából áll, különösen a gépi tanulás területén, ahol a legtöbb számítási költséget a hatalmas mátrixok inverzének kiszámítása okozza.

Szerencsére létezik olyan kvantumalgoritmus, amellyel a klasszikus számítógépeknél exponenciálisan gyorsabban oldhatjuk meg hozzávetőlegesen a rendszert. Ezzel az algoritmussal lényegesen gyorsabban oldható meg minden olyan probléma, amelyben lineáris egyenletrendszereket kell megoldani.

Az említett területeken felmerülő problémák megoldásai lehetővé teszik az energiaválság, a klímaváltozás és az élelmiszerhiány kezelését, valamint a személyes és precíz orvosi diagnózisok felállítását.

## <a name="quantum-inspired-computing"></a>Kvantum által ihletett számítástechnika

A kvantum által ihletett algoritmusok implementációja hagyományos szoftverekkel történik, de kvantumalapelveket használnak a nagyobb sebesség és pontosság érdekében.

A kvantum által ihletett algoritmusokat az orvosi kutatásokban használják, például a mágnesesrezonancia-vizsgálatok (MRI) pontosságának javításához. Kvantum által ihletett számítástechnikát használnak az MRI-gépek konfigurációjának adott betegségek felismerését célzó optimalizálásához.

## <a name="next-steps"></a>Következő lépések

* [Miért érdemes kvantum-számítástechnikát tanulnom?](xref:microsoft.quantum.overview.why)
* [Bevezetés a Microsoft Quantum Development Kit használatába](xref:microsoft.quantum.welcome)
