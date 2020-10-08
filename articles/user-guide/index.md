---
title: A Q# használati útmutatója
description: A felhasználói útmutató céljának és tartalmának áttekintése
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771383"
---
# <a name="the-no-locq-user-guide"></a>A Q# használati útmutatója

Üdvözli Önt a Q# használati útmutatója! 

A jelen útmutató különböző témaköreiben részletesen ismertetjük a Q# nyelv alapvető fogalmait és az összes olyan információt, amelyre szükség lehet kvantumprogramok írásához.

## <a name="user-guide-contents"></a>A felhasználói útmutató tartalma

- [A Q# alapjai](xref:microsoft.quantum.guide.basics): A Q# programozási nyelv célját és funkcióit bemutató áttekintés. 

- [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs): a Q#-programok futtatásának módját ismerteti, valamint áttekintést nyújt a program meghívásának különböző módjairól: a parancssorból, a Q# Jupyter-notebookokból vagy a Python vagy .NET nyelven írt klasszikus gazdaprogramokból.

### <a name="no-locq-language"></a>Q# nyelv

- [Típusok a Q#-ban](xref:microsoft.quantum.guide.types): Ismerteti a Q#-típusmodellt, és bemutatja a típusok megadásának és használatának szintaxisát.

- [Típuskifejezések](xref:microsoft.quantum.guide.expressions): Részletesen ismerteti az értékek megadását, hivatkozását, összevonását és a rajtuk végzett műveletek végrehajtását a Q# minden típusához. 

### <a name="using-no-locq"></a>Az Q# használata

- [Q#-fájlstruktúra](xref:microsoft.quantum.guide.filestructure): Egy `*.qs` Q#-fájl struktúráját és szintaxisát ismerteti.

- [Műveletek és függvények](xref:microsoft.quantum.guide.operationsfunctions): A Q# nyelv két hívható típusát részletezi: ezek a *műveletek*, amelyek magukba foglalják a qubitregiszterek műveleteit, és a *függvények*, amelyek kizárólag a klasszikus információkkal működnek. 
    Itt láthatja, hogyan határozhatja meg és hívhatja meg őket, beleértve a kvantumműveletek kapcsolt és vezérelt verzióit.

- [Változók](xref:microsoft.quantum.guide.variables): A Q#-programokban lévő változók szerepét és hatékony kihasználását ismerteti. 
    Talál például információt a hatókörök kötéséről, valamint a nem módosítható és módosítható változók közötti különbségről, illetve a hozzárendelésükről és az újbóli hozzárendelésükről.

- [Munkavégzés qubitekkel](xref:microsoft.quantum.guide.qubits): A Q# azon funkcióit ismerteti, amelyek az egyes qubitekhez és qubitrendszerekhez használhatók, különös tekintettel a kiosztásukra, a rajtuk végzett műveletekre és a mérésükre. 

- [Átvitelvezérlés](xref:microsoft.quantum.guide.controlflow): Részletesen bemutatja a Q#-ban elérhető programozás-átvitelvezérlési mintákat, amelyekbe beletartozik számos alaptechnika (pl. feltételes feldolgozás, *for* és *while* hurkok), valamint a kvantumspecifikus *sikerességig ismétlődő* minta.

- [Tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging): Részletesen ismertet néhány módszert, amelyek segítségével meggyőződhet róla, hogy a kódja úgy működik, ahogyan kell. 
    A kvantuminformációk általános átlátszatlansága miatt egy kvantumprogram hibakereséséhez speciális módszerekre lehet szükség. 
    Szerencsére a Q# számos, a programozok által jól ismert klasszikus hibakeresési módszert is támogat a kvantumspecifikus módszerek mellett. Ilyenek például az egységtesztek létrehozása és futtatása Q#-ban, a kódban szereplő értékekre és valószínűségekre vonatkozó *helyességi feltételek* beágyazása, valamint azok a `Dump` függvények, amelyek a célszámítógépek állapotát adják vissza. 
    Az utóbbi használható a teljes körű funkciókkal rendelkező szimulátor mellett a számítások bizonyos részeinek hibakereséséhez, bizonyos kvantumkorlátozások – például a [másolhatatlansági tétel](xref:microsoft.quantum.concepts.pauli) – megkerülésével.

### <a name="quantum-simulators-and-resource-estimators"></a>Kvantumszimulátorok és erőforrásbecslők

- [Kvantumszimulátorok és gazdaalkalmazások](xref:microsoft.quantum.machines): A különböző elérhető szimulátorok, valamint a gazdaprogramok és a célgépek Q#-programok futtatásához való együttműködésének áttekintése.

- [Teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator): A teljes kvantumállapotot szimuláló célgép. Hasznos a kisebb méretezésű (kevesebb mint pár tucat qubitból álló) programok teljes futtatásához vagy hibakereséséhez.

- [Erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator): Megbecsüli a Q#-művelet adott példányának a kvantumszámítógépen való futtatásához szükséges erőforrásokat.

- [Nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro): A kvantumszámítógép állapotának tényleges szimulálása nélkül futtat kvantumprogramokat, így több ezer qubitet használó kvantumprogramok futtatására is képes. Hasznos kvantumprogramban lévő klasszikus kódok hibakeresésekor, valamint a szükséges erőforrások megbecsülésekor.

- [Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator): Egy speciális célú kvantumszimulátor, amely használható több millió qubittel, de csak korlátozott kvantumművelet-készletet – X, CNOT, több elem által vezérelt X műveletek – tartalmazó programok esetében.

### <a name="quick-reference-pages"></a>Gyorsútmutató-oldalak

- [IQ# Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp): IQ# Magic parancsok Q# Jupyter-notebookokhoz – Gyorsútmutató-oldal.
