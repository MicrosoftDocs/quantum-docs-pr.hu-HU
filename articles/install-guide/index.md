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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c83d1-103">A Microsoft Quantum Development Kit (QDK) telepítése</span><span class="sxs-lookup"><span data-stu-id="c83d1-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c83d1-104">Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="c83d1-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="c83d1-105">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="c83d1-105">The QDK consists of:</span></span>

- <span data-ttu-id="c83d1-106">a Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="c83d1-106">the Q# programming language</span></span>
- <span data-ttu-id="c83d1-107">kódtárak, amelyek összetett funkciókat választanak el a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="c83d1-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="c83d1-108">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="c83d1-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="c83d1-109">a fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="c83d1-109">tools to facilitate your development</span></span>

<span data-ttu-id="c83d1-110">A Q#-programok gyakran vannak párban egy .NET-nyelven (legtöbbször C#-ban) vagy Pythonban írt gazdaprogrammal.</span><span class="sxs-lookup"><span data-stu-id="c83d1-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="c83d1-111">Ez lehetővé teszi, hogy a kvantumműveleteket egy klasszikus programból hívjuk meg.</span><span class="sxs-lookup"><span data-stu-id="c83d1-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="c83d1-112">Ráadásul a QDK Q#-támogatást nyújt a Jupyter-notebookokhoz az IQ# Jupyter kernel révén.</span><span class="sxs-lookup"><span data-stu-id="c83d1-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="c83d1-113">A QDK számos fejlesztői környezethez elérhető.</span><span class="sxs-lookup"><span data-stu-id="c83d1-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="c83d1-114">Válassza ki az Ön által előnyben részesített beállítást az alábbi szakaszok közül:</span><span class="sxs-lookup"><span data-stu-id="c83d1-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="c83d1-115">[Q# nyelvű parancssori alkalmazás:](xref:microsoft.quantum.install.standalone) akkor válassza ezt a módszert, ha a Q#-ot szeretné használni a parancssorból.</span><span class="sxs-lookup"><span data-stu-id="c83d1-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="c83d1-116">Ehhez nincs szükség illesztőprogramra vagy gazdaprogramra, mint az alábbi lehetőségek esetében.</span><span class="sxs-lookup"><span data-stu-id="c83d1-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="c83d1-117">[Q# telepítése Jupyter-notebookokhoz:](xref:microsoft.quantum.install.jupyter) válassza ezt a környezetet Q#-kód beágyazott szöveggel rendelkező cellákban való végrehajtásához vagy kvantum-számítástechnikai interaktív oktatóanyagok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c83d1-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="c83d1-118">[Fejlesztés Q# és Python használatával:](xref:microsoft.quantum.install.python) ha együtt szeretné használni a Pythont és a Q#-ot egy Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="c83d1-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="c83d1-119">[Fejlesztés Q# és C# vagy F# használatával:](xref:microsoft.quantum.install.cs) ha együtt szeretné használni a C#-ot vagy az F#-ot és a Q#-ot egy .NET-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="c83d1-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
