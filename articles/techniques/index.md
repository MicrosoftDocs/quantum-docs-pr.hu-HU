---
title: Kvantumfejlesztési módszerek
description: Megismerheti a Q#-programfejlesztés alapjait, műveleteket, függvényeket, változókat és qubiteket használhat, és létrehozhat egy egyszerű kvantumprogramot.
keywords: Ne adjon hozzá kulcsszavakat és ne szerkessze azokat a keresőoptimalizálást végző szakemberrel való egyeztetés nélkül.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907715"
---
# <a name="quantum-development-techniques"></a>Kvantumfejlesztési módszerek

A dokumentáció ezen szakasza részletesen ismerteti a kvantumprogramok Q#-ban történő létrehozásakor alkalmazott alapvető fogalmakat, valamint az ezen programok hagyományos alkalmazásokból történő használatának módját.
Feltételezzük a kvantum-számítástechnikai fogalmak *bizonyos mértékű* ismeretét, amelyeket például a [Kvantum-számítástechnikai fogalmak](xref:microsoft.quantum.concepts.intro) című cikkben ismertettünk, de nem szükséges szakértőnek lennie ahhoz, hogy hasznos információkat tudjon meg ezekből a szakaszokból.

A szakaszok a következőket tartalmazzák.

- A [Q#-program áttekintése](xref:microsoft.quantum.techniques.file-structure) szakasz áttekintést nyújt a Q# programozási nyelv céljáról és funkciójáról. 
    Ez leginkább azt tisztázza, hogy a Q# *nem* elsősorban a kvantummechanika szimulálását szolgáló nyelv – bár ezt a funkciót a teljes állapotú szimulátorunk biztosítja. 
    A Q# valójában a jövőbe tekintve lett tervezve, és a programjai azt írják le, hogyan *működik együtt* a klasszikus vezérlésű számítógép a qubitekkel. 

- A [Műveletek és a függvények](xref:microsoft.quantum.techniques.opsandfunctions) a Q# nyelv két hívható típusát részletezi: ezek a *műveletek*, amelyek magukba foglalják a qubitek és a kvantumrendszerek műveleteit, és a *függvények*, amelyek kizárólag a klasszikus információkkal működnek. 
    A klasszikus és a kvantuminformáció párhuzamos használata nélkül a kvantum-számítástechnika továbbra is elérhetetlen marad. 
    Ez a szakasz ezen meghívható elemek meghatározását és használatát ismerteti a Q# programok átvitelvezérlésén belül.

- A [Helyi változók](xref:microsoft.quantum.techniques.local-variables) szakasz a Q#-programokban lévő változók szerepét és hatékony kihasználását ismerteti. 
    Elsősorban a nem módosítható és módosítható változók közötti különbségről fog tanulni, illetve a hozzárendelésükről és az újbóli hozzárendelésükről.

- A [Munkavégzés qubitekkel](xref:microsoft.quantum.techniques.qubits) a Q# azon funkcióit ismerteti, amelyek az egyes qubitekhez és qubitrendszerekhez használhatók. 
    A szakasz kitér a kiosztásukra, a rajtuk végzett műveletekre és a mérésükre. 
    Ráadásul elsajátíthat néhány hasznos átvitelvezérlési módszert is.

- A [Végső összeállítás](xref:microsoft.quantum.techniques.puttingittogether) szakaszban a fenti részekben ismertetett módszereket használva olyan programot hozhat létre, amely **kvantumteleportációt** hajt végre: két klasszikus bitet használva „teleportálja” egy qubit teljes állapotát egy másikba.

- A [Továbblépés](xref:microsoft.quantum.techniques.going-further) szakasz olyan gyakorlott felhasználóknak szóló módszereket mutat be, amelyek hasznosak lehetnek az összetettebb kvantumprogramozásra való áttérés során. 
    Kiemelten tárgyaljuk a *típusparaméteres* műveletek és függvények használatát a Q#-ban, amelyek lehetővé teszik a magasabb rendű átvitelvezérlést azáltal, hogy függetlenek maradnak a kimenet-/bemenettípusoktól, valamint qubiteket *kölcsönöznek*. 
    Az utóbbi eltér az alapszintű qubitkiosztástól abban, hogy egy Q#-művelet használhat „szabálytalan” qubiteket – olyan qubiteket, amelyeket nem feltétlenül inicializáltak ismert állapotba – a számítások támogatásához.

- A [Tesztelés és hibakeresés](xref:microsoft.quantum.techniques.testing-and-debugging) szakasz részletesen ismertet néhány módszert, amelyek segítségével meggyőződhet róla, hogy a kódja úgy működik, ahogyan kell. 
    A kvantuminformációk általános átlátszatlansága miatt egy kvantumprogram hibakereséséhez speciális módszerekre lehet szükség. 
    Szerencsére a Q# támogat számos, a programozok által alkalmazott klasszikus hibakeresési módszert, valamint kvantumspecifikus módszereket is. Ilyenek például az egységtesztek létrehozása/futtatása Q#-ban, a kódban szereplő értékekre és valószínűségekre vonatkozó *helyességi feltételek* beágyazása, valamint azok a `Dump` függvények, amelyek a célszámítógép állapotát adják vissza. 
    Az utóbbi használható a teljes állapotú szimulátor mellett a számítások bizonyos részeinek hibakereséséhez, bizonyos kvantumkorlátozások (például a másolhatatlansági tétel) megkerülésével.


![Kvantum](~/media/mobius_strip_preview.png)
