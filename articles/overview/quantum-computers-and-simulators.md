---
title: A kvantumszámítógépek és a kvantumszimulátorok
description: Megismerkedhet a kvantumhardverekkel, a kvantumszimulátorokkal és a kvantumműveletek működésével.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
ms.openlocfilehash: 04f90e9f88cf17259f96532617ef6f092b56b859
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430747"
---
# <a name="quantum-computers-and-quantum-simulators"></a>A kvantumszámítógépek és a kvantumszimulátorok

A kvantumszámítógépek fejlesztése még gyerekcipőben jár. A hardverek drágák, a karbantartás költséges, és a legtöbb rendszer egyetemeken és a kutatólaborokban található. A technológia azonban fejlődik, és néhány rendszer korlátozottan hozzáférhető nyilvánosan is.

A kvantumszimulátorok a klasszikus számítógépeken futó szoftverek, amelyek segítségével a kvantumprogramok egy olyan környezetben futtathatók és tesztelhetők, amely előre jelzi, hogy a qubitek hogyan fognak reagálni a különböző műveletekre.

## <a name="quantum-hardware"></a>Kvantumhardver

A kvantumszámítógépek három fő részből állnak: a qubiteket tároló területből, a jeleket a qubitek számára továbbító módszerből, valamint a programot futtató és utasításokat küldő klasszikus számítógépből.

- A qubitekhez használt kvantumanyag sérülékeny, és érzékenyen reagál a környezeti hatásokra. A qubitek tárolásának egyes módszerei esetében a qubiteket tároló egységet az abszolút nullát alig meghaladó hőmérsékleten tartják a koherencia maximalizálása érdekében. Más típusú qubittárolók egy vákuumkamra segítségével minimalizálják a rezgéseket és stabilizálják a qubiteket.  
- Jelek különböző módszerekkel küldhetők a qubiteknek, például mikrohullámok, lézer és feszültség használatával.

Ahhoz, hogy megfelelően működjenek, a kvantumszámítógépeknek számos kihívással kell szembenézniük. A hibajavítás a kvantumszámítógépek esetében jelentős feladat, és a vertikális felskálázás (további qubitek hozzáadása) növeli a hibák arányát. Ezen korlátozások következtében az otthoni, asztali kvantumszámítógépek a távoli jövőbe vesznek, de a kereskedelmi szempontból használható laboratóriumi kvantumszámítógépek közelebb vannak.

## <a name="quantum-simulators"></a>Kvantumszimulátorok

A klasszikus számítógépeken futó kvantumszimulátorok lehetővé teszik a kvantumalgoritmusok kvantumrendszereken történő végrehajtásának szimulálását.  A Microsoft Quantum Development Kit (QDK) eszköze teljes körű funkciókkal rendelkező vektorszimulátort és egyéb, speciális kvantumszimulátorokat is tartalmaz.

## <a name="topological-qubit"></a>Topológiai qubitek

A Microsoft a topológiai qubitekre alapozva fejleszti a saját kvantumszámítógépét. A topológiai qubitek kevésbé vannak kitéve a környezetében bekövetkező változásoknak, így a külső hibák szükséges javításának mértéke kisebb lesz.

A topológiai qubitek nagyobb stabilitással és ellenállással bírnak a környezeti zajokkal szemben, ami azt jelenti, hogy könnyeben méretezhetők és tovább maradnak megbízhatók.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>A Microsoft és kvantumhardver-gyártók partnerkapcsolatai

A Microsoft partneri együttműködést alakított ki az IonQ, a Honeywell és a QCI kvantumhardver-gyártókkal, hogy a kvantumszámítógépek a jövőben elérhetők legyenek a fejlesztők számára. Az Azure Quantum platform segítségével a fejlesztők a Microsoft Quantum Development Kit (QDK) és a Q# nyelv használatával kvantumprogramokat írhatnak, amelyeket távolról futtathatnak.

## <a name="quantum-computations"></a>Kvantumszámítások

A kvantumszámítógépeken vagy kvantumszimulátorokon a számítások elvégzése egy alapszintű folyamat szerint történik:

- Hozzáférés a qubitekhez
- A qubitek inicializálása a kívánt állapotba
- Műveletek elvégzése a qubitek állapotának átalakítására
- A qubitek új állapotának megmérése

A qubitek inicializálása és átalakítása **kvantumműveletekkel** (más néven kvantumkapukkal) történik. A kvantumműveletek a klasszikus számítástechnika logikai műveleteire hasonlítanak, például a következőkre: AND, OR, NOT, XOR. A műveletek lehetnek egyszerűek, például egy qubit állapotának átváltása 1-ről 0-ra vagy két qubit összefonása, de összetettebbek is, például több művelet használata egy sorozatban annak a valószínűségének a befolyásolására, hogy a szuperpozícióban lévő qubit az egyik vagy másik értékkel esik egybe.

> [!NOTE] 
> A [Q#-kódtárak](xref:microsoft.quantum.libraries) olyan beépített műveleteket biztosítanak, amelyek alacsonyabb szintű kvantumműveletek összetett kombinációit határozzák meg. A kódtár műveleteivel átalakíthatók a qubitek, valamint összetettebb felhasználói műveletek hozhatók létre.  

A számítás eredményének mérése megad egy választ, de egyes kvantumalgoritmusok esetében nem feltétlenül a megfelelő választ. Mivel egyes kvantumalgoritmusok eredménye a kvantumműveletek által konfigurált valószínűségen alapul, ezeket a számításokat többször futtatja a rendszer a valószínűségi eloszlás elérése és az eredmények pontosságának finomítása érdekében.  A garanciát, hogy egy művelet helyes választ ad vissza, kvantummegerősítésnek nevezzük, ami az egyik legnagyobb kihívást jelenti a kvantum-számítástechnikában.

## <a name="summary"></a>Összefoglalás

A kvantum-számítástechnika és a klasszikus számítástechnika néhány alapelve megegyezik, de a kvantum-számítástechnika új megközelítéseket is alkalmaz. Néhány kulcsfontosságú szempont:

- A kvantumhardverek drágák és sérülékenyek, ezért a programok írása és tesztelése kvantumszimulátorokkal történik.
- A klasszikus és a kvantumszámítógépek is logikai műveleteket (vagy kapukat) használnak a számítások előkészítéséhez.
- A kvantumszámítások valószínűségeket adnak vissza.

A kvantumhardverek és -technikák fejlesztései gyors ütemben alakítják át a kvantum-számítástechnika területét. Íme néhány az [aktuális fejlesztések](https://phys.org/search/?search=quantum+computer&s=0) közül.

## <a name="next-steps"></a>További lépések

> [!div class="nextstepaction"]
> [Mi az a Q# programozási nyelv és a QDK?](xref:microsoft.quantum.overview.q-sharp)