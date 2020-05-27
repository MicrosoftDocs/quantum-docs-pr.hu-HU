---
title: Bevezetés a kvantum-számítástechnikába
description: Megismerkedhet a kvantum-számítástechnikával, a kvantumszámítógépek által biztosított képességekkel, valamint a kvantum-számítástechnika elsajátításához szükséges lépésekkel.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
ms.openlocfilehash: 7c55420bd35f9b6e0e7ec80ddffe8a861cb7df39
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430781"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>A kvantum-számítástechnika és a Quantum Development Kit bemutatása

A Microsoft Quantum Development Kit (QDK) egy nyílt forráskódú eszközkészlet, amelynek segítségével a fejlesztők megismerhetik a kvantumalgoritmusokat és kvantumprogramokat írhatnak. A kvantum-számítástechnikában ott rejlik a lehetőség bolygónk legnagyobb kihívásainak megoldására, legyen szó környezeti, mezőgazdasági, egészség-, energia- és klímaügyi, anyagtudományi vagy akár egyelőre még ismeretlen területről.  

Ezen területek néhány feladata esetében még a legnagyobb teljesítményű számítógépek is problémákba ütköznek. Habár a kvantum-számítástechnika hatása még csak most kezd megjelenni a számítástechnika világában, ez a hatás messzemenő lehet, és megváltoztathatja a számítástechnikával kapcsolatos gondolkodásmódunkat.

## <a name="what-is-quantum-computing"></a>Mi az a kvantum-számítástechnika?

Modern használatban a kvantum egy fizikai tulajdonság legkisebb lehetséges különálló egységét jelenti, és általában atomi vagy szubatomi részecskék tulajdonságára vonatkozik. A kvantumszámítógépek tényleges kvantumrészecskéket, mesterséges atomokat vagy kollektív kvantumrészecske-tulajdonságokat használnak feldolgozási egységként, továbbá nagy, összetett és drága eszközök.

A kvantumfizika egyedi működésének kiaknázása és a számítástechnikában történő alkalmazása során a kvantumszámítógépek új fogalmakat vezetnek be a hagyományos programozási módszerekbe, kihasználva az olyan kvantumfizikai viselkedéseket, mint a szuperpozíció, az összefonódás és a kvantuminterferencia.

## <a name="what-can-a-quantum-computer-do"></a>Mire képesek a kvantumszámítógépek?

A kvantumszámítógépek nem olyan szuperszámítógépek, amelyek bármilyen műveletet gyorsabban végeznek el, azonban néhány területen kiemelkedően jól teljesítenek.

- [Kvantumszimuláció](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Titkosítás](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Search](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Optimalizálás](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Gépi tanulás](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Kvantumszimuláció

Mivel a kvantumszámítógépek kvantumjelenségeket használnak a számításokhoz, ezért a segítségükkel jól modellezhetők más kvantumrendszerek. A fotoszintézis, a szupravezetés és az összetett molekulák kialakulása például olyan kvantummechanizmusok, amelyeket a kvantumprogramok képesek szimulálni.

## <a name="cryptography-and-shors-algorithm"></a>Titkosítás és a Shor-algoritmus

Peter Shor 1994-ben megállapította, hogy egy skálázható kvantumszámítógép fel tudná törni a széles körben használt titkosítási technikákat, például az RSA-algoritmust. A klasszikus kriptográfia a problémák megoldhatatlanságán alapszik, ilyen például a prímfelbontás vagy a különálló algoritmusok. Ezek közül sok hatékonyabban megoldható kvantumszámítógépek használatával.

## <a name="search-and-grovers-algorithm"></a>Keresés és a Grover-algoritmus

1996-ban Lov Grover kifejlesztett egy olyan kvantumalgoritmust, amely drasztikusan felgyorsította a strukturálatlan adatok keresését, mivel a keresést kevesebb lépésből hajtotta végre, mint bármely klasszikus algoritmus.

## <a name="quantum-inspired-computing-and-optimization"></a>Kvantum által ihletett számítástechnika és optimalizálás

A kvantum által ihletett algoritmusok kvantumalapelveket használnak a nagyobb sebesség és pontosság érdekében, de klasszikus számítógéprendszereken vannak implementálva. Ez a megközelítés lehetővé teszi a fejlesztők számára, hogy anélkül használják ki az új kvantumtechnológiák képességeit, hogy várniuk kellene a még egy fejlődő iparág részét képező kvantumhardverekre.

Az optimalizálás az a folyamat, amelynek célja egy probléma legjobb megoldásának megtalálása a kívánt kimenet és a korlátozások tekintetében. A költségek, a minőség és a termelési idő olyan tényezők, amelyek szerepet játszanak az ipar és a tudomány terén meghozott kritikus döntésekben. A mai klasszikus számítógépeken futó, kvantum ihlette optimalizálási algoritmusok olyan megoldásokat találnak, amelyek eddig nem voltak lehetségesek. A forgalom áramlásának optimalizálásával csökkenthetik a torlódást, és emellett számos más funkciót tölthetnek be, például egy repülőtéri kapu hozzárendelését, a csomagszállítást vagy a feladatütemezést. Az anyagtudomány áttöréseinek köszönhetően az energia új formái, nagyobb teljesítményű akkumulátorok, valamint könnyebb és tartósabb anyagok válnak elérhetővé.

> [!NOTE]
> Ismerje meg, hogyan használják a Microsoft kvantum ihlette számítástechnikáját az [anyagtudomány](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), a [kockázatkezelés](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) és az [orvostudomány](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/) területén.

## <a name="quantum-machine-learning"></a>Kvantum gépi tanulás

A klasszikus számítógépekkel végzett gépi tanulás forradalmasítja a tudományos és az üzleti világot. A modellek betanításának magas számítási költségei azonban akadályozzák a terület fejlesztését és alkalmazásának hatókörét. A kvantum gépi tanulás területe azt vizsgálja, hogy miként lehet olyan kvantumszoftvert kialakítani és alkalmazni, amely gyorsabb gépi tanulást tesz lehetővé, mint amire a klasszikus számítógépek képesek.

A Quantum Development Kit tartalmaz egy [kvantum gépi tanulási kódtárat](xref:microsoft.quantum.machine-learning.concepts.intro), amely segítségével hibrid kvantum/klasszikus gépi tanulási kísérletek futtathatók. A kódtár mintákat és oktatóanyagokat is tartalmaz, továbbá biztosítja a szükséges eszközöket az új hibrid kvantum/klasszikus algoritmus, a körközpontú kvantumosztályozó implementálásához, amely a felügyelt osztályozási problémák megoldására szolgál.

## <a name="q-and-the-microsoft-quantum-development-kit-qdk"></a>A Q# nyelv és a Microsoft Quantum Development Kit (QDK)

A Q# a Microsoft nyílt forráskódú programozási nyelve, amely kvantumalgoritmusok fejlesztésére és futtatására szolgál. A [QDK](https://docs.microsoft.com/quantum/) része, amely egy, a Q# nyelvhez készült teljes körű fejlesztői készlet, amelyet általános eszközökkel és nyelvekkel együtt használhat a különböző környezetekben, például a beépített, teljes körű funkciókkal rendelkező kvantumszimulátoron futtatható kvantumalkalmazások fejlesztéséhez.

Rendelkezésre állnak bővítmények a Visual Studióhoz és a VS Code-hoz, valamint a Python és Jupyter Notebookokhoz használható csomagok is elérhetők.

A QDK egy szabványos kódtárat, továbbá speciális kémiai, gépi tanulási és numerikus kódtárakat is tartalmaz.

A dokumentációban útmutatókat, oktatóanyagokat és mintakódokat is talál a Q# nyelvhez, amelyekkel gyorsan megteheti az első lépéseket. Emellett a dokumentáció részletes cikkeket is biztosít, amelyek segítségével alaposabban megismerheti a kvantum-számítástechnika fogalmait.  

## <a name="microsoft-quantum-hardware-partners"></a>A Microsoft kvantumhardverpartnerei

A Microsoft partneri együttműködést alakított ki több kvantumhardver-gyártó vállalattal annak érdekében, hogy a fejlesztők hozzáférhessenek a kvantumhardverekhez a felhőn keresztül. Az [Azure Quantum](https://azure.microsoft.com/services/quantum/) platform és a Q# nyelv használatával a fejlesztők megismerhetik a kvantumalgoritmusokat, és különböző típusú kvantumhardvereken futtathatják a kvantumprogramokat.

A [IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) és a [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) egy elektromos mezőben csapdába ejtett egyedi ionokat használó, **ioncsapda-alapú** processzorokat, míg a [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) szupravezető áramköröket alkalmaz.

## <a name="next-steps"></a>További lépések

[A kvantum-számítástechnika legfontosabb alapelvei](xref:microsoft.quantum.overview.understanding)
[Gyorsútmutatók](xref:microsoft.quantum.welcome)