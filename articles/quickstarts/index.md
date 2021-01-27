---
title: A Microsoft Quantum Development Kit (QDK) beállítása
description: Megismerheti a Microsoft Quantum Development Kit különböző környezetekben való beállítását.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859026"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="e54be-103">A Microsoft Quantum Development Kit (QDK) beállítása</span><span class="sxs-lookup"><span data-stu-id="e54be-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="e54be-104">Ismerje meg a Microsoft Quantum Development Kit (QDK) saját környezetében történő beállításának módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="e54be-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="e54be-105">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="e54be-105">The QDK consists of:</span></span>

- <span data-ttu-id="e54be-106">A Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="e54be-106">The Q# programming language</span></span>
- <span data-ttu-id="e54be-107">Kódtárak, amelyek a Q# összetett funkcióit kivonatolják</span><span class="sxs-lookup"><span data-stu-id="e54be-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="e54be-108">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="e54be-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="e54be-109">A fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="e54be-109">Tools to facilitate your development</span></span>

<span data-ttu-id="e54be-110">A Q#-programok futhatnak önálló alkalmazásként a Visual Studio Code vagy a Visual Studio használatával, vagy Jupyter-notebookokon keresztül az IQ# Jupyter kernellel, illetve egy Python vagy .NET nyelven írt (C#-, F#-) gazdaprogrammal párban.</span><span class="sxs-lookup"><span data-stu-id="e54be-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="e54be-111">A Q#-programok az interneten is futtathatók [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) vagy [Docker](#use-the-qdk-with-docker) használatával.</span><span class="sxs-lookup"><span data-stu-id="e54be-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="e54be-112">A QDK beállításának lehetőségei</span><span class="sxs-lookup"><span data-stu-id="e54be-112">Options for setting up the QDK</span></span>

<span data-ttu-id="e54be-113">Háromféleképp használhatja a QDK-t:</span><span class="sxs-lookup"><span data-stu-id="e54be-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="e54be-114">A QDK helyi telepítése</span><span class="sxs-lookup"><span data-stu-id="e54be-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="e54be-115">A QDK online használata</span><span class="sxs-lookup"><span data-stu-id="e54be-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="e54be-116">Egy QDK Docker-rendszerkép használata</span><span class="sxs-lookup"><span data-stu-id="e54be-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="e54be-117">A QDK helyi telepítése</span><span class="sxs-lookup"><span data-stu-id="e54be-117">Install the QDK locally</span></span>

<span data-ttu-id="e54be-118">Kifejleszthet egy Q#-kódot a kedvenc IDE-k többségében, valamint integrálhatja a Q#-t más nyelvekkel, például a Pythonnal és a .NET-tel (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="e54be-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="e54be-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="e54be-119"><b>VS Code</span></span><br><span data-ttu-id="e54be-120">(2019 vagy újabb)</b></span><span class="sxs-lookup"><span data-stu-id="e54be-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="e54be-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e54be-121"><b>Visual Studio</span></span><br><span data-ttu-id="e54be-122">(2019 vagy újabb)</b></span><span class="sxs-lookup"><span data-stu-id="e54be-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="e54be-123"><b>Jupyter-notebookok</b></span><span class="sxs-lookup"><span data-stu-id="e54be-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="e54be-124"><b>Parancssor</b></span><span class="sxs-lookup"><span data-stu-id="e54be-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="e54be-125"><b>Operációsrendszer-támogatás</b></span><span class="sxs-lookup"><span data-stu-id="e54be-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="e54be-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="e54be-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="e54be-127">Csak Windowson</span><span class="sxs-lookup"><span data-stu-id="e54be-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="e54be-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="e54be-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="e54be-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="e54be-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="e54be-130"><b>különálló Q#</b></span><span class="sxs-lookup"><span data-stu-id="e54be-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="e54be-131"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-132"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-133"><a href="xref:microsoft.quantum.install.jupyter">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-134"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="e54be-135"><b>Q# és Python</b></span><span class="sxs-lookup"><span data-stu-id="e54be-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="e54be-136"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-137"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-138"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-139"><a href="xref:microsoft.quantum.install.python">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="e54be-140"><b>Q# és .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="e54be-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="e54be-141"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-142"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e54be-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="e54be-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="e54be-144"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></span><span class="sxs-lookup"><span data-stu-id="e54be-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="e54be-145">A QDK online használata</span><span class="sxs-lookup"><span data-stu-id="e54be-145">Use the QDK Online</span></span>

<span data-ttu-id="e54be-146">A következő beállításokkal anélkül fejleszthet Q#-kódot, hogy bármit helyileg telepítene:</span><span class="sxs-lookup"><span data-stu-id="e54be-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="e54be-147">Erőforrás</span><span class="sxs-lookup"><span data-stu-id="e54be-147">Resource</span></span>|<span data-ttu-id="e54be-148">Előnyök</span><span class="sxs-lookup"><span data-stu-id="e54be-148">Advantages</span></span>|<span data-ttu-id="e54be-149">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="e54be-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="e54be-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="e54be-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="e54be-151">Gazdag online fejlesztési környezet</span><span class="sxs-lookup"><span data-stu-id="e54be-151">A rich online development environment</span></span>  |<span data-ttu-id="e54be-152">Azure-előfizetés és -csomag szükséges hozzá</span><span class="sxs-lookup"><span data-stu-id="e54be-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="e54be-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="e54be-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="e54be-154">Ingyenes online jegyzetfüzet-élmény</span><span class="sxs-lookup"><span data-stu-id="e54be-154">Free online notebook experience</span></span> |<span data-ttu-id="e54be-155">Nincs perzisztencia</span><span class="sxs-lookup"><span data-stu-id="e54be-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="e54be-156">A QDK használata Dockerrel</span><span class="sxs-lookup"><span data-stu-id="e54be-156">Use the QDK with Docker</span></span>

<span data-ttu-id="e54be-157">A QDK Docker-rendszerképünket használhatja a helyi Docker-telepítésében vagy a felhőben, bármely olyan szolgáltatáson keresztül, amely támogatja a Docker-rendszerképeket, mint például az ACI.</span><span class="sxs-lookup"><span data-stu-id="e54be-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="e54be-158">Innen letöltheti az IQ# Docker-rendszerképet: https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="e54be-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="e54be-159">A Dockert egy Visual Studio Code távoli fejlesztési tárolóval is használhatja a fejlesztési környezetek gyors meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="e54be-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="e54be-160">A VS Code fejlesztési tárolókkal kapcsolatos további tudnivalókért lásd: https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="e54be-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e54be-161">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="e54be-161">Next steps</span></span>

<span data-ttu-id="e54be-162">Az egyes beállításokhoz tartozó munkafolyamatok leírása és összehasonlítása [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) című szakaszban olvasható.</span><span class="sxs-lookup"><span data-stu-id="e54be-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
