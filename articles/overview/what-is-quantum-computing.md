---
title: Mi az a kvantum-számítástechnika?
description: Megtudhatja, mi az a kvantum-számítástechnika, illetve mire képes egy kvantumszámítógép.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 77d027abec90274ed7147d2cd8f97b207360bdbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443970"
---
# <a name="what-is-quantum-computing"></a>Mi az a kvantum-számítástechnika?

Bizonyos problémák annyira hihetetlenül bonyolultak és hatalmasak, hogy még ha a világ összes szuperszámítógépe egyszerre dolgozna is rajtuk, akkor is végtelen sok időbe telne megoldani őket. A kvantumszámítógépekben ott rejlik a lehetőség bolygónk legnagyobb kihívásainak megoldására, legyen szó környezeti, mezőgazdasági, egészség-, energia- és klímaügyi, anyagtudományi vagy akár most még elképzelhetetlen területekről. A kvantumszámítógépek hatása legalább akkora lesz, mint a tranzisztor 1947-es feltalálása, ami kikövezte a mai digitális gazdasághoz vezető utat.

A kvantum-számítástechnika a kvantumfizika sajátos viselkedésére alapozva egy új és rendkívül hatékony számítástechnikai modellt kínál. A kvantumfizika elmélete szerint az anyag kvantumszinten többféle klasszikus állapot szuperpozíciójában létezhet. Ezek az állapotok pedig úgy interferálnak egymással, mint a hullámok a medencében.  Mérés után az anyag állapota rendszerint az egyik klasszikus állapottal „esik egybe”. Ezt követően ugyanannak a mérésnek a megismétlése ugyanazt a klasszikus eredményt adja.  Kvantum-összefonódás akkor fordul elő, ha a részecskék olyan módon lépnek kapcsolatba egymással, hogy a kvantumállapotuk nem jellemezhető teljes mértékben az egymástól való függetlenségükkel, még akkor sem, ha a részecskék fizikailag távol vannak egymástól.  

A kvantum-számítástechnika az anyag kvantumállapotában tárolja az információkat, valamint szuperpozíciójának kvantumtermészetét és az összefonódást használja az olyan kvantumműveletek elvégzéséhez, amelyek ezeken az információkon végeznek számításokat, így lehetővé teszi a kvantum-interferencia programozásának kiaknázását és elsajátítását.

A kvantum-számítástechnika ijesztőnek tűnhet, de a megfelelő erőforrásokkal már ma elkezdhet kvantumalkalmazásokat készíteni.

## <a name="the-qubit"></a>A qubit

A kvantum-számítástechnika olyan számítási fogalmakat határoz meg, amelyek a kvantumviselkedést tükrözik.  A kvantum-számítástechnika a qubit fogalmával kezdődik.  A kvantum-számítástechnikában a kvantumbit – **qubit** – a kvantuminformáció egysége, akár a hagyományos bit. Míg a hagyományos bit egyetlen bináris értéket hordoz, ami 0 vagy 1 lehet, a qubit állapota egyszerre lehet a 0 és az 1 érték közötti **szuperpozícióban**.  

A qubit mérésének ténye megváltoztatja a qubit állapotát. A mérés után a qubit a szuperpozícióból az egyik klasszikus állapotba kerül.  

Több qubit ezenfelül **össze is fonható**. Ha az összefonódott qubitek egyikéről mérést készítünk, a másik/többi állapotáról is információt kapunk.

## <a name="quantum-algorithms"></a>Kvantumalgoritmusok

A kvantumalgoritmusok arra lettek tervezve, hogy kihasználják a kvantumtermészetet és -viselkedést, így felgyorsíthatók a klasszikus algoritmusok, vagy fizikai rendszerek modellezésének teljesen új módjait valósíthatjuk meg.  Ezek az algoritmusok a qubit információkódolásának módját és az összefonódott qubitek szuperpozícióban történő működtetésének párhuzamos természetét aknázzák ki.  

A klasszikus számítógépek bitekben kódolják az információt, és minden bit 2 lehetséges értéket (0 vagy 1) kódol.  A qubit egyszerre kódol két értéket (0 és 1).  Két klasszikus bit 4 lehetséges érték (00, 01, 10, 11) egyikét kódolja, míg 2 qubit ennek a 4 értéknek bármely szuperpozícióját képes egyszerre kódolni, bár méréskor csak az egyik értéket kaphatjuk meg.  Négy bit 16 érték egyikét kódolja.  Négy qubit 16 érték bármely szuperpozícióját egyszerre kódolja és így tovább – exponenciálisan növelhető az érték.  100 qubit több információt képes kódolni, mint amennyi ma a legnagyobb számítógépes rendszerekben elérhető.  

Ha több összefonódott qubit koherensen viselkedik, több lehetőséget dolgozhatnak fel egyszerre. Ez lehetővé teszi, hogy az információt annak az időnek a töredéke alatt dolgozzák fel, mint amire akár a leggyorsabb nem kvantumalapú rendszernek szüksége volna.

Ezen kvantumattribútumok kiaknázása jelenti a kvantumalgoritmusok több évtizedes kutatásának célját, és számos olyan innovatív technika létezik, amelyek a klasszikus módszer idejének töredéke alatt oldják meg a problémákat.  

Az egyik leghíresebb kvantumalgoritmus a _Shor-algoritmus_, amely egy nagy szám két prímszámra történő felbontásának klasszikusan nehéz feladatát a hagyományos kriptográfia sebességével vetekedő gyorsasággal végzi el.

Konstruktívabb megközelítésben a biztonságos titkosításikulcs-disztribúció algoritmusainak létrehozását a szuperpozíció, a kvantum-összefonódás és a qubitek **klónozhatatlansága**, vagyis az észlelés nélküli másolást megakadályozó tulajdonsága teszi lehetővé.

A _Grover-algoritmus_ egy olyan kvantumalgoritmus-technikát helyez a középpontba, amely a strukturálatlan adatok hatványozottan gyorsabb keresését teszi lehetővé.


## <a name="quantum-hardware"></a>Kvantumhardver

A hagyományos számítógépek esetében a bitek az integrált áramkörök feszültségszintjének felelnek meg. A kvantumszámítógépek hardvere a qubitek számos különböző fizikai megvalósulása szerint implementálhatók: ioncsapda, szupravezető áramkör, semleges atomok, elektron spin, fénypolarizáció, topológiai qubitek. A kvantumhardver egy fejlesztés alatt álló technológia. A qubit természeténél fogva sérülékeny, és kevésbé koherens, ahogy interakcióba lép a környezetével. Ehhez a rendszer megbízhatóságának és skálázhatóságának kiegyensúlyozása szükséges. Minél nagyobb a méret (vagyis a qubitek száma), annál magasabb a hibaarány.

A Microsoft a topológiai qubitekre alapozva fejleszti a saját kvantumszámítógépét. Úgy véljük, hogy a topológiai qubit kevésbé van kitéve a környezetében bekövetkező változásoknak, így a külső hibák javításának mértéke kisebb lesz. A topológiai qubitek nagyobb stabilitással és ellenállással bírnak a környezeti zajokkal szemben, ami azt jelenti, hogy könnyeben méretezhetők és tovább maradnak megbízhatók.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Kvantum-számítástechnika: egy teljes hardver- és szoftverkészlet 

A Microsoft kvantumprogramja azért egyedi, mert a valódi kvantumhatás biztosítása érdekében a rendszer minden egyes összetevőjének skálázására koncentrál. Ez az átfogó megközelítés az alábbiakat foglalja magában: 
* egy kvantumszámítógép létrehozása megbízható, skálázható és hibatűrő topológiai qubitek használatával, 
* egy egyedi kriogenikai vezérlősík felépítése rendkívül alacsony áram- és hőveszteséggel, 
* valamint egy teljes szoftverkészlet kifejlesztése a kvantumszámítógép programozásához és a rendszer nagy léptékű vezérléséhez. 

A nyílt forráskódú Quantum Development Kit (QDK) azzal a céllal készült, hogy a kvantumprogramozást és az algoritmusfejlesztést szélesebb körben tegye hozzáférhetővé. Magas szintű programnyelvünk, a Q# a kvantumprogramozás kihívásait veszi célba.  A Q# nyelvet egy olyan magas szintű, kvantumközpontú programozási nyelvnek terveztük, amely az algoritmus- és alkalmazásfejlesztésre koncentrál. A Q#-fordító egy olyan szoftverkészlet része, amely lehetővé teszi a kvantumalgoritmus lefordítását a kvantumszámítógép primitív műveleteinek szintjére.  Bizonyos mértékig (kvantumbitekben mérve) a kvantum-számítástechnika egy hagyományos számítógépen is szimulálható. A szimuláció alkalmazásával már ma hozzáfoghat a kvantumprogramok írásához, amelyek a jövő kvantumhardverjén futhatnak majd.  A Q#-hoz mintákat, kódtárakat és tanulási gyakorlatokat is mellékeltünk, hogy minél könnyebben kezdhesse meg már ma a kvantumprogramozást. 

## <a name="next-steps"></a>További lépések

* [Mire használhatom a kvantumszámítógépet?](xref:microsoft.quantum.overview.computers)
* [Bevezetés a Microsoft Quantum Development Kit használatába](xref:microsoft.quantum.welcome)
* Tudjon meg többet a [Kvantum-számítástechnikai fogalmakról](xref:microsoft.quantum.concepts.intro).
