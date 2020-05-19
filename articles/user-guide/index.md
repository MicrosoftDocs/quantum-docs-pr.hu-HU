---
title: A Q# használati útmutatója
description: A felhasználói útmutató céljának és tartalmának áttekintése
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430611"
---
# <a name="the-q-user-guide"></a>A Q# használati útmutatója

Üdvözli Önt a Q# használati útmutatója! 

Itt részletesen ismertetjük a Q# nyelv alapvető fogalmait és az összes olyan információt, amelyre szükség lehet kvantumprogramok írásához.

## <a name="user-guide-contents"></a>A felhasználói útmutató tartalma

- A [Q# alapjai](xref:microsoft.quantum.guide.basics) szakasz a Q# programozási nyelv célját és funkcióját bemutató áttekintés. 

### <a name="q-language"></a>A Q# nyelv

- A [Típusok Q#-ban](xref:microsoft.quantum.guide.types) szakasz ismerteti a Q#-típusmodellt és bemutatja a típusok megadásának és használatának szintaxisát.

- A [Típuskifejezések](xref:microsoft.quantum.guide.expressions) szakasz részletesen ismerteti az értékek megadását, hivatkozását, összevonását és üzemeltetését a Q# minden típusához. 

### <a name="using-q"></a>A Q# használata

- A [Q#-fájlstruktúra](xref:microsoft.quantum.guide.filestructure) szakasz egy `*.qs` Q#-fájl struktúráját és szintaxisát ismerteti.

- A [Műveletek és a függvények](xref:microsoft.quantum.guide.operationsfunctions) szakasz a Q# nyelv két hívható típusát részletezi: ezek a *műveletek*, amelyek magukba foglalják a qubitregiszterek műveleteit és a *függvények*, amelyek kizárólag a klasszikus információkkal működnek. 
    Itt láthatja, hogyan határozhatja meg és hívhatja meg őket, beleértve a kvantumműveletek kapcsolt és vezérelt verzióit.

- A [Változók](xref:microsoft.quantum.guide.variables) szakasz a Q#-programokban lévő változók szerepét és hatékony kihasználását ismerteti. 
    Talál például információt a hatókörök kötéséről, valamint a nem módosítható és módosítható változók közötti különbségről, illetve a hozzárendelésükről és az újbóli hozzárendelésükről.

- A [Munkavégzés qubitekkel](xref:microsoft.quantum.guide.qubits) szakasz a Q# azon funkcióit ismerteti, amelyek az egyes qubitekhez és qubitrendszerekhez használhatók. 
    A szakasz kitér a kiosztásukra, a rajtuk végzett műveletekre és a mérésükre. 

- Az [Átvitelvezérlés](xref:microsoft.quantum.guide.controlflow) szakasz részletesen bemutatja a Q#-ban elérhető programozás-átvitelvezérlési mintákat, amelybe beletartozik számos standard technika (feltételes végrehajtás, for hurkok, while hurkok stb.), valamint a kvantumspecifikus „sikerességig ismétlődő” mintát.

- A [Tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging) szakasz részletesen ismertet néhány módszert, amelyek segítségével meggyőződhet róla, hogy a kódja úgy működik, ahogyan kell. 
    A kvantuminformációk általános átlátszatlansága miatt egy kvantumprogram hibakereséséhez speciális módszerekre lehet szükség. 
    Szerencsére a Q# támogat számos, a programozok által alkalmazott klasszikus hibakeresési módszert, valamint kvantumspecifikus módszereket is. Ilyenek például az egységtesztek létrehozása/futtatása Q#-ban, a kódban szereplő értékekre és valószínűségekre vonatkozó *helyességi feltételek* beágyazása, valamint azok a `Dump` függvények, amelyek a célszámítógép állapotát adják vissza. 
    Az utóbbi használható a teljes körű funkciókkal rendelkező szimulátor mellett a számítások bizonyos részeinek hibakereséséhez, bizonyos kvantumkorlátozások (például a másolhatatlansági tétel) megkerülésével.

### <a name="quantum-simulators-and-resource-estimators"></a>Kvantumszimulátorok és erőforrásbecslők

- [Kvantumszimulátorok és gazdaalkalmazások](xref:microsoft.quantum.machines): a különböző elérhető szimulátorok, valamint a gazdaprogram és a célgépek közötti általános végrehajtási modell áttekintése.

- [Teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator): a teljes kvantumállapotot szimuláló célgép. Hasznos a kisebb méretezésű (kevesebb mint pár tucat qubitból álló) programok teljes végrehajtásához vagy hibakereséséhez

- [Erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator): megbecsüli a Q#-művelet adott példányának a kvantumszámítógépen való futtatásához szükséges erőforrásokat.

- [Nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro): végrehajt egy kvantumprogramot a kvantumszámítógép állapotának tényleges szimulálása nélkül, ezáltal végrehajthat több ezer qubitet használó kvantumprogramokat. Hasznos kvantumprogramban lévő klasszikus kódok hibakeresésekor, valamint a szükséges erőforrások megbecsülésekor.

- [Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator): egy speciális célú kvantumszimulátor, amely használható több millió qubittel, de csak korlátozott kvantumművelet-készletet (X, CNOT és több elem által vezérelt X műveleteket) tartalmazó programok esetében.

### <a name="quick-reference-pages"></a>Gyorsútmutató-oldalak

- [IQ# Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp): IQ# Magic parancsok Q# Jupyter-notebookokhoz – Gyorsútmutató-oldal.
