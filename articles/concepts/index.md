---
title: Kvantum-számítástechnikai fogalmak
description: Mi az a kvantum-számítástechnika?
author: QuantumWriter
ms.author: nawiebe@microsoft.com
uid: microsoft.quantum.concepts.intro
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 37f5181f2d9e4e11efa29811c24116ca7d64f81b
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2019
ms.locfileid: "72978956"
---
# <a name="what-is-quantum-computing"></a>Mi az a kvantum-számítástechnika?

Az elmúlt néhány évben számos újdonság jelent meg a számítástechnika terén, amelyek közül vitathatatlanul a kvantum-számítástechnika igényli a legnagyobb paradigmaváltást a fejlesztők részéről.  A kvantum-számítógépek ötletével [Richard Feynman](https://en.wikipedia.org/wiki/Richard_Feynman) és [Jurij Manyin](https://en.wikipedia.org/wiki/Yuri_Manin) állt elő az 1980-as években.  A kvantum-számítástechnika mögötti ösztönzőerő abból ered, amit sokan a fizika egyik legnagyobb szégyenének tartanak, vagyis hogy a jelentős tudományos fejlődés folyton beleütközik abba az akadályba, hogy még az egyszerű rendszereket sem tudjuk modellezni. Mint ismeretes, a kvantummechanikát 1900 és 1925 között fejlesztették ki, és azóta is ez jelenti a kémia, a kondenzáltanyag-fizika, illetve a számítógépektől a LED-világításig terjedő technológiai újítások alapját.  Mindezen sikerek ellenére azonban olykor még a legegyszerűbb rendszerek kvantummechanikai modellezése is meghaladta az emberi teljesítőképességet.  Ennek az oka az, hogy még néhány tucat egymással kommunikáló részecske szimulálása is nagyobb számítási teljesítményt igényel, mint ami bármely hagyományos számítógép több ezer évig tartó munkájával elérhető lenne.

A kvantummechanikai szimuláció nehézségeinek megértéséhez számos megközelítés áll rendelkezésre.  Talán a legegyszerűbb azt átlátni, hogy a kvantumelmélet egyik értelmezése szerint kvantumszinten az anyag ugyanabban az időben több különböző lehetséges konfigurációban (más néven *állapotban*) létezik egyszerre.  A klasszikus valószínűségelmélettől eltérően a kvantumállapot számos konfigurációja, amely potenciálisan megfigyelhető lehet, úgy interferál egymással, mint a hullámok a medencében.  Ez az interferencia megakadályozza, hogy statisztikai mintavétellel megállapíthatók legyenek a kvantumállapot konfigurációi.  Ehelyett nyomon kell követni a kvantumrendszer *minden lehetséges* konfigurációját, ha szeretnénk megérteni a kvantumevolúciót.  

Képzeljen el egy elektronokból álló rendszert, ahol az elektronok mondjuk $40$ pozíció bármelyikében lehetnek.  Az elektronok ezért $2^{40}$ konfiguráció bármelyikében lehetnek (minden egyes pozícióban vagy van elektron, vagy nincs). Egy hagyományos számítógépnél az elektronok kvantumállapotának tárolása $130$ GB-ot is meghaladó memóriát venne igénybe.  Ez jelentős ugyan, de néhány számítógép esetében kivitelezhető.  Ha feltesszük, hogy a részecskék $41$ pozíció bármelyikében lehetnek, $2^{41}$, azaz kétszer annyi konfigurációval kellene számolni, és így már több mint $260$ GB memóriára lenne szükség a kvantumállapot tárolásához. A pozíciók számának növelése nem folytatható a végtelenségig, ha hagyományos módon szeretnénk tárolni az állapotot, mivel gyorsan túllépnénk a világ legerősebb számítógépeinek kapacitását is.  Már néhány száz elektron esetében is meghaladja a rendszer tárolásához szükséges memória a világegyetemben jelen lévő részecskék számát; éppen ezért teljesen reménytelen, hogy a hagyományos számítógépekkel valaha is szimulálhassuk a kvantumdinamikájukat. A természetben azonban az ilyen rendszerek a kvantummechanikai törvények alapján minden további nélkül kialakulnak, és szerencsére nincsenek annak tudatában, hogy a hagyományos számítástechnikai eszközökkel nem lehet megtervezni és szimulálni a fejlődésüket.

Ez a megfigyelés elvezette a kvantum-számítástechnika első úttörőit ahhoz az egyszerű, mégis kulcsfontosságú kérdéshez, hogy vajon képesek vagyunk-e lehetőséget kovácsolni ebből az akadályból.  Pontosabban, ha a kvantumdinamikát nehéz szimulálni, mi történne, ha olyan hardvert hoznának létre, amelynek alapvető műveletei kvantumhatásokon alapulnának?  Vajon szimulálhatjuk-e az egymással interakcióba lépő részecskék rendszerét egy olyan rendszerrel, amely pontosan az ilyen interakciókat irányító természeti törvényeket aknázza ki? Vizsgálhatunk-e a természetben nem megtalálható jelenségeket, miközben a kvantummechanika természetes törvényeit követjük vagy aknázzuk ki?  Ezek a kérdések vezettek el a kvantum-számítástechnika megszületéséhez.

A kvantum-számítástechnika alapja, hogy az anyag kvantumállapotában tárolja az információkat, és kvantumkapu-műveletekkel végez számításokat ezeken az információkon a kvantum-interferencia kiaknázásával és annak az elsajátításával, hogyan lehet ezt az interferenciát „programozni”.  A hagyományos számítógépekkel nehezen kezelhető problémák megoldását célzó interferencia-programozás egyik korai példáját [Peter Shor](https://en.wikipedia.org/wiki/Peter_Shor) szolgáltatta 1994-ben az úgynevezett prímfelbontási problémával.  A prímfelbontás megoldása egyben lehetővé teszi számos olyan nyilvános kulcsú titkosítási rendszer feltörését, amelyeken a mai e-kereskedelem biztonsága alapszik; ilyen például az RSA vagy az elliptikus görbe alapú titkosítás.  Azóta sok olyan, hagyományosan nehéznek számító feladatra született már gyors és hatékony kvantumalgoritmus, mint a fizikai rendszerek szimulálása a kémiában, a fizikában és az anyagtudományban, a keresés a rendezetlen adatbázisokban, a lineáris egyenletrendszerek megoldása vagy a gépi tanulás.

Az interferencia kiaknázását célzó kvantumprogram tervezése elég ijesztő kihívásnak tűnhet, és bár valóban az, számos technika és eszköz készült azzal a céllal, köztük a Microsoft Quantum Development Kit (QDK) is, hogy a kvantumprogramozást és az algoritmusfejlesztést szélesebb körben is hozzáférhetővé tegye. Létezik néhány alapszintű stratégia, amely úgy teszi lehetővé a kvantuminterferencia számítástechnikai szempontból hasznos befolyásolását, hogy közben a megoldás nem vész el a kvantumlehetőségek útvesztőjében. A kvantumprogramozás más, mint a klasszikus programozás, és nagyon különböző eszközöket igényel a kvantumalgoritmusos gondolkodás megértéséhez és kifejezéséhez. A kvantumprogramozás elsajátításához szükséges általános eszközök biztosítása nélkül a kvantumalgoritmusos fejlesztés nem egyszerű feladat a kvantumfejlesztők számára.

A Microsoft Quantum Development Kit bevezetésével az a célunk, hogy az egyre gyarapodó közösség számára olyan eszközöket biztosítsunk, amelyek lehetővé teszik a kvantumforradalom kiaknázását a feladatok, problémák és megoldások terén. Magas szintű programnyelvünk, a Q#, a kvantuminformációk feldolgozásának kihívásait vállalja magára; egy olyan szoftverkészlet része, amely lehetővé teszi a kvantumalgoritmus lefordítását a kvantumszámítógép primitív műveleteinek szintjére.  A programozási nyelv megismerése előtt érdemes áttekinteni a kvantum-számítástechnika alapelveit. Itt a kvantum-számítástechnika alapvető szabályait axiómáknak tekintjük, és nem részletezzük a kvantummechanikában gyökerező elméleti hátterüket. Azt is feltételezzük, hogy a felhasználó rendelkezik a lineáris algebra (vektorok, mátrixok stb.) alapszintű ismeretével. Ha a kvantum-számítástechnika történetének és alapjainak részletei érdeklik, a [referenciák szakasza](xref:microsoft.quantum.more-information) további információkkal szolgál.