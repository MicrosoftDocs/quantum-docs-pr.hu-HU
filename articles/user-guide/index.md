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
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231757"
---
# <a name="the-no-locq-user-guide"></a>A Q# használati útmutatója

Üdvözli Önt a Q# használati útmutatója! 

A jelen útmutató különböző témaköreiben ismertetjük a kvantumprogramok Q# használatával való fejlesztésének alapjait.

A Q# kvantumprogramozási nyelv teljes specifikációját és dokumentációját a [Q# nyelvi útmutatójában](xref:microsoft.quantum.qsharp.index) találja. 

## <a name="user-guide-contents"></a>A felhasználói útmutató tartalma

- [Q#-programok](xref:microsoft.quantum.guide.programs): Rövid bevezetés a Q# nyelvű kvantumprogramokba. 

- [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs): a Q#-programok futtatásának módját ismerteti, valamint áttekintést nyújt a program meghívásának különböző módjairól: a parancssorból, a Q# Jupyter-notebookokból vagy a Python vagy .NET nyelven írt klasszikus gazdaprogramokból.

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
