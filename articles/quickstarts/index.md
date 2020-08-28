---
title: A Microsoft Quantum Development Kit (QDK) telepítése
description: A Microsoft Quantum Development Kit telepítése különböző környezetekben.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863713"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="bc32a-103">A Microsoft Quantum Development Kit (QDK) telepítése</span><span class="sxs-lookup"><span data-stu-id="bc32a-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="bc32a-104">Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="bc32a-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="bc32a-105">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="bc32a-105">The QDK consists of:</span></span>

- <span data-ttu-id="bc32a-106">A Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="bc32a-106">The Q# programming language</span></span>
- <span data-ttu-id="bc32a-107">Kódtárak, amelyek a Q# összetett funkcióit kivonatolják</span><span class="sxs-lookup"><span data-stu-id="bc32a-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="bc32a-108">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="bc32a-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="bc32a-109">A fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="bc32a-109">Tools to facilitate your development</span></span>

<span data-ttu-id="bc32a-110">A Q#-programok futhatnak önálló alkalmazásként a Visual Studio Code vagy a Visual Studio használatával, vagy Jupyter-notebookokon keresztül az IQ# Jupyter kernellel.</span><span class="sxs-lookup"><span data-stu-id="bc32a-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="bc32a-111">Társíthatók .NET (jellemzően C# nyelven) vagy Python nyelven írt gazdaprogrammal is, ez lehetővé teszi kvantumműveletek meghívását egy klasszikus programon belül.</span><span class="sxs-lookup"><span data-stu-id="bc32a-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="bc32a-112">Az egyes beállításokhoz tartozó munkafolyamatok leírása és összehasonlítása [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) című szakaszban olvasható.</span><span class="sxs-lookup"><span data-stu-id="bc32a-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="bc32a-113">A QDK telepítéséhez és a Q#-projektek létrehozásához válassza ki az Ön által előnyben részesített beállítást:</span><span class="sxs-lookup"><span data-stu-id="bc32a-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="bc32a-114">[Fejlesztés Q#-alkalmazásokkal](xref:microsoft.quantum.install.standalone) – Ezt a megközelítést választva a parancssorból használhatja a Q#-ot.</span><span class="sxs-lookup"><span data-stu-id="bc32a-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="bc32a-115">Ehhez nincs szükség illesztőprogramra vagy gazdaprogramra, mint az alábbi lehetőségek esetében.</span><span class="sxs-lookup"><span data-stu-id="bc32a-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="bc32a-116">[Fejlesztés Q# Jupyter-notebookokkal](xref:microsoft.quantum.install.jupyter) – Ezt a környezetet választva Q#-kódot futtathat beágyazott szöveggel rendelkező cellákban, vagy létrehozhat kvantum-számítástechnikai interaktív oktatóanyagokat.</span><span class="sxs-lookup"><span data-stu-id="bc32a-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="bc32a-117">[Fejlesztés Q# és Python használatával](xref:microsoft.quantum.install.python) – Lehetővé teszi a Python és a Q# együttes használatát egy olyan Python-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="bc32a-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="bc32a-118">[Fejlesztés Q# és .NET használatával](xref:microsoft.quantum.install.cs) – Kombinálhatja a C#, az F# vagy a VB.NET nyelvet a Q# nyelvvel egy olyan .NET-gazdaprogram létrehozásához, amely Q#-műveleteket hív meg.</span><span class="sxs-lookup"><span data-stu-id="bc32a-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
