---
title: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036508"
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

- [Q# telepítése C# nyelvhez:](xref:microsoft.quantum.install.cs) válassza ezt a környezetet, ha együtt szeretné használni a C#-t és a Q#-t egy C#-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.
- [Q# telepítése Python nyelvhez:](xref:microsoft.quantum.install.python) válassza ezt a környezetet, ha együtt szeretné használni a Pythont és a Q#-t egy Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.
- [Q# telepítése Jupyter-notebookokhoz:](xref:microsoft.quantum.install.jupyter) válassza ezt a környezetet Q#-kód beágyazott szöveggel rendelkező cellákban való végrehajtásához vagy kvantum-számítástechnikai interaktív oktatóanyagok létrehozásához. Ha a Q#-t egy külső klasszikus gazdaprogrammal szeretné használni, ne ezt a környezetet válassza.
