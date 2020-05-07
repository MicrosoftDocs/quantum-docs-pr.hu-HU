---
title: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése
description: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése C#-, Python- és Jupyter Notebook-környezethez.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680191"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit (QDK) telepítése

Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek. A QDK a következőket tartalmazza:

- a Q# programozási nyelv
- kódtárak, amelyek összetett funkciókat választanak el a Q#-ban
- Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához
- a fejlesztést megkönnyítő eszközök

A Q#-programok gyakran vannak párban egy .NET-nyelven (legtöbbször C#-ban) vagy Pythonban írt gazdaprogrammal. Ez lehetővé teszi, hogy a kvantumműveleteket egy klasszikus programból hívjuk meg.
Ráadásul a QDK Q#-támogatást nyújt a Jupyter-notebookokhoz az IQ# Jupyter kernel révén.

A QDK számos fejlesztői környezethez elérhető. Válassza ki az Ön által előnyben részesített beállítást az alábbi szakaszok közül:

- [Q# nyelvű parancssori alkalmazás:](xref:microsoft.quantum.install.standalone) akkor válassza ezt a módszert, ha a Q#-ot szeretné használni a parancssorból. Ehhez nincs szükség illesztőprogramra vagy gazdaprogramra, mint az alábbi lehetőségek esetében.
- [Q# telepítése Jupyter-notebookokhoz:](xref:microsoft.quantum.install.jupyter) válassza ezt a környezetet Q#-kód beágyazott szöveggel rendelkező cellákban való végrehajtásához vagy kvantum-számítástechnikai interaktív oktatóanyagok létrehozásához. 
- [Fejlesztés Q# és Python használatával:](xref:microsoft.quantum.install.python) ha együtt szeretné használni a Pythont és a Q#-ot egy Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.
- [Fejlesztés Q# és C# vagy F# használatával:](xref:microsoft.quantum.install.cs) ha együtt szeretné használni a C#-ot vagy az F#-ot és a Q#-ot egy .NET-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.
