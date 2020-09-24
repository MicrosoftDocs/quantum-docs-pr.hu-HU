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
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834482"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ae6be-103">A Microsoft Quantum Development Kit (QDK) beállítása</span><span class="sxs-lookup"><span data-stu-id="ae6be-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ae6be-104">Ismerje meg a Microsoft Quantum Development Kit (QDK) saját környezetében történő beállításának módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="ae6be-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="ae6be-105">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="ae6be-105">The QDK consists of:</span></span>

- <span data-ttu-id="ae6be-106">A Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="ae6be-106">The Q# programming language</span></span>
- <span data-ttu-id="ae6be-107">Kódtárak, amelyek a Q# összetett funkcióit kivonatolják</span><span class="sxs-lookup"><span data-stu-id="ae6be-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="ae6be-108">Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához</span><span class="sxs-lookup"><span data-stu-id="ae6be-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="ae6be-109">A fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="ae6be-109">Tools to facilitate your development</span></span>

<span data-ttu-id="ae6be-110">A Q#-programok futhatnak önálló alkalmazásként a Visual Studio Code vagy a Visual Studio használatával, vagy Jupyter-notebookokon keresztül az IQ# Jupyter kernellel, illetve egy Python vagy .NET nyelven írt (C#-, F#-) gazdaprogrammal párban.</span><span class="sxs-lookup"><span data-stu-id="ae6be-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="ae6be-111">A Q#-programok az interneten is futtathatók [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) vagy [Docker](#use-the-qdk-with-docker) használatával.</span><span class="sxs-lookup"><span data-stu-id="ae6be-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="ae6be-112">A QDK beállításának lehetőségei</span><span class="sxs-lookup"><span data-stu-id="ae6be-112">Options for setting up the QDK</span></span>

<span data-ttu-id="ae6be-113">Háromféleképp használhatja a QDK-t:</span><span class="sxs-lookup"><span data-stu-id="ae6be-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="ae6be-114">A QDK helyi telepítése</span><span class="sxs-lookup"><span data-stu-id="ae6be-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="ae6be-115">A QDK online használata</span><span class="sxs-lookup"><span data-stu-id="ae6be-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="ae6be-116">Egy QDK Docker-rendszerkép használata</span><span class="sxs-lookup"><span data-stu-id="ae6be-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="ae6be-117">A QDK helyi telepítése</span><span class="sxs-lookup"><span data-stu-id="ae6be-117">Install the QDK locally</span></span>

<span data-ttu-id="ae6be-118">Kifejleszthet egy Q#-kódot a kedvenc IDE-k többségében, valamint integrálhatja a Q#-t más nyelvekkel, például a Pythonnal és a .NET-tel (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="ae6be-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="ae6be-119">**VS Code<br>(2019 vagy újabb verzió)**</span><span class="sxs-lookup"><span data-stu-id="ae6be-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="ae6be-120">**Visual Studio<br>(2019 vagy újabb verzió)**</span><span class="sxs-lookup"><span data-stu-id="ae6be-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="ae6be-121">**Jupyter-notebookok**</span><span class="sxs-lookup"><span data-stu-id="ae6be-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="ae6be-122">**Parancssor**</span><span class="sxs-lookup"><span data-stu-id="ae6be-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="ae6be-123">**OS**</span><span class="sxs-lookup"><span data-stu-id="ae6be-123">**OS**</span></span> |<span data-ttu-id="ae6be-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="ae6be-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="ae6be-125">Csak Windowson</span><span class="sxs-lookup"><span data-stu-id="ae6be-125">Windows only</span></span> |<span data-ttu-id="ae6be-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="ae6be-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="ae6be-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="ae6be-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="ae6be-128">**különálló Q#**</span><span class="sxs-lookup"><span data-stu-id="ae6be-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="ae6be-129">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="ae6be-130">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="ae6be-131">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="ae6be-132">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="ae6be-133">**Q# és Python**</span><span class="sxs-lookup"><span data-stu-id="ae6be-133">**Q#  and Python**</span></span> |[<span data-ttu-id="ae6be-134">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="ae6be-135">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="ae6be-136">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="ae6be-137">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="ae6be-138">**Q# és .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="ae6be-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="ae6be-139">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="ae6be-140">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="ae6be-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="ae6be-141">&#10006;</span></span> |[<span data-ttu-id="ae6be-142">Telepítse</span><span class="sxs-lookup"><span data-stu-id="ae6be-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="ae6be-143">A QDK online használata</span><span class="sxs-lookup"><span data-stu-id="ae6be-143">Use the QDK Online</span></span>

<span data-ttu-id="ae6be-144">A következő beállításokkal anélkül fejleszthet Q#-kódot, hogy bármit helyileg telepítene:</span><span class="sxs-lookup"><span data-stu-id="ae6be-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="ae6be-145">Erőforrás</span><span class="sxs-lookup"><span data-stu-id="ae6be-145">Resource</span></span>|<span data-ttu-id="ae6be-146">Előnyök</span><span class="sxs-lookup"><span data-stu-id="ae6be-146">Advantages</span></span>|<span data-ttu-id="ae6be-147">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="ae6be-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="ae6be-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="ae6be-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="ae6be-149">Gazdag online fejlesztési környezet</span><span class="sxs-lookup"><span data-stu-id="ae6be-149">A rich online development environment</span></span>  |<span data-ttu-id="ae6be-150">Azure-előfizetés és -csomag szükséges hozzá</span><span class="sxs-lookup"><span data-stu-id="ae6be-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="ae6be-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="ae6be-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="ae6be-152">Ingyenes online jegyzetfüzet-élmény</span><span class="sxs-lookup"><span data-stu-id="ae6be-152">Free online notebook experience</span></span> |<span data-ttu-id="ae6be-153">Nincs perzisztencia</span><span class="sxs-lookup"><span data-stu-id="ae6be-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="ae6be-154">A QDK használata Dockerrel</span><span class="sxs-lookup"><span data-stu-id="ae6be-154">Use the QDK with Docker</span></span>

<span data-ttu-id="ae6be-155">A QDK Docker-rendszerképünket használhatja a helyi Docker-telepítésében vagy a felhőben, bármely olyan szolgáltatáson keresztül, amely támogatja a Docker-rendszerképeket, mint például az ACI.</span><span class="sxs-lookup"><span data-stu-id="ae6be-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="ae6be-156">Innen letöltheti az IQ# Docker-rendszerképet: https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="ae6be-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="ae6be-157">A Dockert egy Visual Studio Code távoli fejlesztési tárolóval is használhatja a fejlesztési környezetek gyors meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="ae6be-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="ae6be-158">A VS Code fejlesztési tárolókkal kapcsolatos további tudnivalókért lásd: https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="ae6be-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae6be-159">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="ae6be-159">Next steps</span></span>

<span data-ttu-id="ae6be-160">Az egyes beállításokhoz tartozó munkafolyamatok leírása és összehasonlítása [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) című szakaszban olvasható.</span><span class="sxs-lookup"><span data-stu-id="ae6be-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
