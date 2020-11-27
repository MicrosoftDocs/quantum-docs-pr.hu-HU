---
title: A Microsoft Quantum Development Kit (QDK) beállítása
description: Megismerheti a Microsoft Quantum Development Kit különböző környezetekben való beállítását.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228830"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="3b9d6-103">A Microsoft Quantum Development Kit (QDK) beállítása</span><span class="sxs-lookup"><span data-stu-id="3b9d6-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="3b9d6-104">Ismerje meg a Microsoft Quantum Development Kit (QDK) saját környezetében történő beállításának módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="3b9d6-105">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="3b9d6-105">The QDK consists of:</span></span>

- <span data-ttu-id="3b9d6-106">A Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="3b9d6-106">The Q# programming language</span></span>
- <span data-ttu-id="3b9d6-107">Kódtárak, amelyek a Q# összetett funkcióit kivonatolják</span><span class="sxs-lookup"><span data-stu-id="3b9d6-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="3b9d6-108">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="3b9d6-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="3b9d6-109">A fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="3b9d6-109">Tools to facilitate your development</span></span>

<span data-ttu-id="3b9d6-110">A Q#-programok futhatnak önálló alkalmazásként a Visual Studio Code vagy a Visual Studio használatával, vagy Jupyter-notebookokon keresztül az IQ# Jupyter kernellel, illetve egy Python vagy .NET nyelven írt (C#-, F#-) gazdaprogrammal párban.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="3b9d6-111">A Q#-programok az interneten is futtathatók [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) vagy [Docker](#use-the-qdk-with-docker) használatával.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="3b9d6-112">A QDK beállításának lehetőségei</span><span class="sxs-lookup"><span data-stu-id="3b9d6-112">Options for setting up the QDK</span></span>

<span data-ttu-id="3b9d6-113">Háromféleképp használhatja a QDK-t:</span><span class="sxs-lookup"><span data-stu-id="3b9d6-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="3b9d6-114">A QDK helyi telepítése</span><span class="sxs-lookup"><span data-stu-id="3b9d6-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="3b9d6-115">A QDK online használata</span><span class="sxs-lookup"><span data-stu-id="3b9d6-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="3b9d6-116">Egy QDK Docker-rendszerkép használata</span><span class="sxs-lookup"><span data-stu-id="3b9d6-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="3b9d6-117">A QDK helyi telepítése</span><span class="sxs-lookup"><span data-stu-id="3b9d6-117">Install the QDK locally</span></span>

<span data-ttu-id="3b9d6-118">Kifejleszthet egy Q#-kódot a kedvenc IDE-k többségében, valamint integrálhatja a Q#-t más nyelvekkel, például a Pythonnal és a .NET-tel (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="3b9d6-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="3b9d6-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="3b9d6-119"><b>VS Code</span></span><br><span data-ttu-id="3b9d6-120">(2019 vagy újabb)</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="3b9d6-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b9d6-121"><b>Visual Studio</span></span><br><span data-ttu-id="3b9d6-122">(2019 vagy újabb)</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="3b9d6-123"><b>Jupyter-notebookok</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="3b9d6-124"><b>Parancssor</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="3b9d6-125"><b>Operációsrendszer-támogatás</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="3b9d6-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-127">Csak Windowson</span><span class="sxs-lookup"><span data-stu-id="3b9d6-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="3b9d6-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="3b9d6-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="3b9d6-130"><b>különálló Q#</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-131"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-132"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-133"><a href="xref:microsoft.quantum.install.jupyter">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-134"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="3b9d6-135"><b>Q# és Python</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-136"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-137"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-138"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-139"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="3b9d6-140"><b>Q# és .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="3b9d6-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="3b9d6-141"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-142"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="3b9d6-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="3b9d6-144"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="3b9d6-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="3b9d6-145">A QDK online használata</span><span class="sxs-lookup"><span data-stu-id="3b9d6-145">Use the QDK Online</span></span>

<span data-ttu-id="3b9d6-146">A következő beállításokkal anélkül fejleszthet Q#-kódot, hogy bármit helyileg telepítene:</span><span class="sxs-lookup"><span data-stu-id="3b9d6-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="3b9d6-147">Erőforrás</span><span class="sxs-lookup"><span data-stu-id="3b9d6-147">Resource</span></span>|<span data-ttu-id="3b9d6-148">Előnyök</span><span class="sxs-lookup"><span data-stu-id="3b9d6-148">Advantages</span></span>|<span data-ttu-id="3b9d6-149">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="3b9d6-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="3b9d6-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="3b9d6-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="3b9d6-151">Gazdag online fejlesztési környezet</span><span class="sxs-lookup"><span data-stu-id="3b9d6-151">A rich online development environment</span></span>  |<span data-ttu-id="3b9d6-152">Azure-előfizetés és -csomag szükséges hozzá</span><span class="sxs-lookup"><span data-stu-id="3b9d6-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="3b9d6-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="3b9d6-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="3b9d6-154">Ingyenes online jegyzetfüzet-élmény</span><span class="sxs-lookup"><span data-stu-id="3b9d6-154">Free online notebook experience</span></span> |<span data-ttu-id="3b9d6-155">Nincs perzisztencia</span><span class="sxs-lookup"><span data-stu-id="3b9d6-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="3b9d6-156">A QDK használata Dockerrel</span><span class="sxs-lookup"><span data-stu-id="3b9d6-156">Use the QDK with Docker</span></span>

<span data-ttu-id="3b9d6-157">A QDK Docker-rendszerképünket használhatja a helyi Docker-telepítésében vagy a felhőben, bármely olyan szolgáltatáson keresztül, amely támogatja a Docker-rendszerképeket, mint például az ACI.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="3b9d6-158">Innen letöltheti az IQ# Docker-rendszerképet: https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="3b9d6-159">A Dockert egy Visual Studio Code távoli fejlesztési tárolóval is használhatja a fejlesztési környezetek gyors meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="3b9d6-160">A VS Code fejlesztési tárolókkal kapcsolatos további tudnivalókért lásd: https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b9d6-161">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="3b9d6-161">Next steps</span></span>

<span data-ttu-id="3b9d6-162">Az egyes beállításokhoz tartozó munkafolyamatok leírása és összehasonlítása [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) című szakaszban olvasható.</span><span class="sxs-lookup"><span data-stu-id="3b9d6-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
