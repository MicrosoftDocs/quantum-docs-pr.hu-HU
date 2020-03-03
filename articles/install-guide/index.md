---
title: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése
description: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése C#-, Python- és Jupyter Notebook-környezethez.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 5fafb736f34d27f9233370a0a8a66c0613606048
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904774"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="9b54e-103">A Microsoft Quantum Development Kit (QDK) telepítése</span><span class="sxs-lookup"><span data-stu-id="9b54e-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="9b54e-104">Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="9b54e-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="9b54e-105">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="9b54e-105">The QDK consists of:</span></span>

- <span data-ttu-id="9b54e-106">a Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="9b54e-106">the Q# programming language</span></span>
- <span data-ttu-id="9b54e-107">kódtárak, amelyek összetett funkciókat választanak el a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="9b54e-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="9b54e-108">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="9b54e-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="9b54e-109">a fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="9b54e-109">tools to facilitate your development</span></span>

<span data-ttu-id="9b54e-110">A Q#-programok gyakran vannak párban egy .NET-nyelven (legtöbbször C#-ban) vagy Pythonban írt gazdaprogrammal.</span><span class="sxs-lookup"><span data-stu-id="9b54e-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="9b54e-111">Ez lehetővé teszi, hogy a kvantumműveleteket egy klasszikus programból hívjuk meg.</span><span class="sxs-lookup"><span data-stu-id="9b54e-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="9b54e-112">Ráadásul a QDK Q#-támogatást nyújt a Jupyter-notebookokhoz az IQ# Jupyter kernel révén.</span><span class="sxs-lookup"><span data-stu-id="9b54e-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="9b54e-113">A QDK számos fejlesztői környezethez elérhető.</span><span class="sxs-lookup"><span data-stu-id="9b54e-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="9b54e-114">Válassza ki az Ön által előnyben részesített beállítást az alábbi szakaszok közül:</span><span class="sxs-lookup"><span data-stu-id="9b54e-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="9b54e-115">[Q# telepítése C# nyelvhez:](xref:microsoft.quantum.install.cs) válassza ezt a környezetet, ha együtt szeretné használni a C#-t és a Q#-t egy C#-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="9b54e-115">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="9b54e-116">[Q# telepítése Python nyelvhez:](xref:microsoft.quantum.install.python) válassza ezt a környezetet, ha együtt szeretné használni a Pythont és a Q#-t egy Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="9b54e-116">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="9b54e-117">[Q# telepítése Jupyter-notebookokhoz:](xref:microsoft.quantum.install.jupyter) válassza ezt a környezetet Q#-kód beágyazott szöveggel rendelkező cellákban való végrehajtásához vagy kvantum-számítástechnikai interaktív oktatóanyagok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9b54e-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="9b54e-118">Ha a Q#-t egy külső klasszikus gazdaprogrammal szeretné használni, ne ezt a környezetet válassza.</span><span class="sxs-lookup"><span data-stu-id="9b54e-118">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
