---
title: A Microsoft Quantum Development Kit (QDK) telepítése
description: A Microsoft Quantum Development Kit telepítése különböző környezetekben.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 6a52eb0a9cdf699e8bb37578ffa3d73fe96a990e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273486"
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