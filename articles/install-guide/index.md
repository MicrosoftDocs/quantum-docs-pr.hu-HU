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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a4eda-102">A Microsoft Quantum Development Kit (QDK) telepítése</span><span class="sxs-lookup"><span data-stu-id="a4eda-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a4eda-103">Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="a4eda-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="a4eda-104">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="a4eda-104">The QDK consists of:</span></span>

- <span data-ttu-id="a4eda-105">a Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="a4eda-105">the Q# programming language</span></span>
- <span data-ttu-id="a4eda-106">kódtárak, amelyek összetett funkciókat választanak el a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="a4eda-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="a4eda-107">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="a4eda-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="a4eda-108">a fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="a4eda-108">tools to facilitate your development</span></span>

<span data-ttu-id="a4eda-109">A Q#-programok gyakran vannak párban egy .NET-nyelven (legtöbbször C#-ban) vagy Pythonban írt gazdaprogrammal.</span><span class="sxs-lookup"><span data-stu-id="a4eda-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="a4eda-110">Ez lehetővé teszi, hogy a kvantumműveleteket egy klasszikus programból hívjuk meg.</span><span class="sxs-lookup"><span data-stu-id="a4eda-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="a4eda-111">Ráadásul a QDK Q#-támogatást nyújt a Jupyter-notebookokhoz az IQ# Jupyter kernel révén.</span><span class="sxs-lookup"><span data-stu-id="a4eda-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="a4eda-112">A QDK számos fejlesztői környezethez elérhető.</span><span class="sxs-lookup"><span data-stu-id="a4eda-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="a4eda-113">Válassza ki az Ön által előnyben részesített beállítást az alábbi szakaszok közül:</span><span class="sxs-lookup"><span data-stu-id="a4eda-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="a4eda-114">[Q# telepítése C# nyelvhez:](xref:microsoft.quantum.install.cs) válassza ezt a környezetet, ha együtt szeretné használni a C#-t és a Q#-t egy C#-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="a4eda-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="a4eda-115">[Q# telepítése Python nyelvhez:](xref:microsoft.quantum.install.python) válassza ezt a környezetet, ha együtt szeretné használni a Pythont és a Q#-t egy Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="a4eda-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="a4eda-116">[Q# telepítése Jupyter-notebookokhoz:](xref:microsoft.quantum.install.jupyter) válassza ezt a környezetet Q#-kód beágyazott szöveggel rendelkező cellákban való végrehajtásához vagy kvantum-számítástechnikai interaktív oktatóanyagok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a4eda-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="a4eda-117">Ha a Q#-t egy külső klasszikus gazdaprogrammal szeretné használni, ne ezt a környezetet válassza.</span><span class="sxs-lookup"><span data-stu-id="a4eda-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
