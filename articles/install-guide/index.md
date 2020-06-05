---
title: A Microsoft Quantum Development Kit (QDK) telepítése
description: A Microsoft Quantum Development Kit telepítése különböző környezetekben.
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327567"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit (QDK) telepítése

Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek. A QDK a következőket tartalmazza:

- A Q# programozási nyelv
- Kódtárak, amelyek Q# összetett funkcióit kivonatolják
- Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához
- A fejlesztést megkönnyítő eszközök

A Q#-programok futhatnak önálló alkalmazásként a Visual Studio Code vagy a Visual Studio használatával, vagy Jupyter-notebookokon keresztül az IQ# Jupyter kernellel.

Társíthatók .NET (jellemzően C# nyelven) vagy Python nyelven írt gazdaprogrammal is, ez lehetővé teszi kvantumműveletek meghívását egy klasszikus programon belül.

A QDK számos fejlesztői környezethez elérhető. Válassza ki az Ön által előnyben részesített beállítást:

[Fejlesztés Q# nyelvű parancssori alkalmazásokkal](xref:microsoft.quantum.install.standalone) – Ezt a megközelítést választva a parancssorból használhatja a Q#-ot. Ehhez nincs szükség illesztőprogramra vagy gazdaprogramra, mint az alábbi lehetőségek esetében.

[Fejlesztés Q# Jupyter-notebookokkal](xref:microsoft.quantum.install.jupyter) – Ezt a környezetet választva Q#-kódot futtathat beágyazott szöveggel rendelkező cellákban vagy létrehozhat kvantum-számítástechnikai interaktív oktatóanyagokat. 

[Fejlesztés Q# és Python használatával](xref:microsoft.quantum.install.python) – Lehetővé teszi a Python és a Q# együttes használatát egy olyan Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.

[Fejlesztés Q# és .NET használatával](xref:microsoft.quantum.install.cs) – Kombinálhatja a C#, az F# vagy a VB.NET nyelvet a Q# nyelvvel egy olyan .NET-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.
