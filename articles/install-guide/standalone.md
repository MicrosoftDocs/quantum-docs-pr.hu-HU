---
title: 'Fejlesztés Q # parancssori alkalmazásokkal'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630263"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="1ebe2-102">Fejlesztés Q # parancssori alkalmazásokkal</span><span class="sxs-lookup"><span data-stu-id="1ebe2-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="1ebe2-103">A Q # programok saját maguk is végrehajthatók a gazdagépen, például C#, F # vagy Python nyelven.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ebe2-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="1ebe2-104">Prerequisites</span></span>

- [<span data-ttu-id="1ebe2-105">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="1ebe2-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="1ebe2-106">Telepítés</span><span class="sxs-lookup"><span data-stu-id="1ebe2-106">Installation</span></span>

<span data-ttu-id="1ebe2-107">A Q # parancssori alkalmazásai bármilyen IDE-ben létrehozhatók, de a Q # alkalmazásaihoz a Visual Studio Code (VS Code) vagy a Visual Studio IDE használata javasolt.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="1ebe2-108">Az ezekben az eszközökben való fejlesztés a sokoldalú funkciók elérését teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="1ebe2-109">A VS Code konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-109">To configure VS Code:</span></span>

1. <span data-ttu-id="1ebe2-110">Töltse le és telepítse a [vs Code](https://code.visualstudio.com/download) -ot (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="1ebe2-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="1ebe2-111">Telepítse a [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)-hoz készült Microsoft-QDK.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="1ebe2-112">A Visual Studio konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="1ebe2-113">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3-es vagy újabb változatát, és engedélyezze a .net Core platformfüggetlen fejlesztési munkaterhelést.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="1ebe2-114">Töltse le és telepítse a [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="1ebe2-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="1ebe2-115">Fejlesztés a Q # segítségével VS Code használatával</span><span class="sxs-lookup"><span data-stu-id="1ebe2-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="1ebe2-116">A Q # Project-sablonok telepítése:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="1ebe2-117">Nyissa meg a VS Code-ot.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-117">Open VS Code.</span></span>
2. <span data-ttu-id="1ebe2-118">Kattintson **View**a  ->  **parancs paletta**megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="1ebe2-119">Válassza a **Q #: Project-sablonok telepítése**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="1ebe2-120">Ha a **Project templates telepítése sikeresen megtörtént** , a QDK készen áll a saját alkalmazásaival és könyvtáraival való használatra.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="1ebe2-121">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-121">To create a new project:</span></span>

1. <span data-ttu-id="1ebe2-122">Kattintson **View**  ->  a**parancs paletta** megtekintése elemre, és válassza a **Q #: új projekt létrehozása**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="1ebe2-123">Kattintson a **különálló konzol alkalmazás**lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="1ebe2-124">Navigáljon a projekt mentéséhez és a **projekt létrehozása**elemre.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="1ebe2-125">A projekt sikeres létrehozása után kattintson a jobb alsó sarokban található **új projekt megnyitása..** . elemre.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="1ebe2-126">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-126">Inspect the project.</span></span> <span data-ttu-id="1ebe2-127">Ekkor meg kell jelennie egy nevű forrásfájl `Program.qs` , amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1ebe2-128">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-128">To run the application:</span></span>
1. <span data-ttu-id="1ebe2-129">Kattintson a **terminál**  ->  **új terminál**elemre.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="1ebe2-130">A terminál parancssorába írja be a következőt: `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="1ebe2-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="1ebe2-131">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1ebe2-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="1ebe2-132">A VS Code Q # bővítmény jelenleg nem támogatja a több legfelső szintű mappával rendelkező munkaterületek használatát.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="1ebe2-133">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="1ebe2-134">Fejlesztés a Q # használatával a Visual Studióval</span><span class="sxs-lookup"><span data-stu-id="1ebe2-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="1ebe2-135">A Visual Studio telepítésének ellenőrzéséhez hozzon létre egy Q # `Hello World` alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="1ebe2-136">Új Q #-alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="1ebe2-137">Nyissa meg a Visual studiót, és kattintson a **fájl**  ->  **új**  ->  **projekt**elemre.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="1ebe2-138">Írja be `Q#` a keresőmezőbe a **Q # alkalmazás** elemet, és kattintson a **tovább**gombra.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="1ebe2-139">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Létrehozás**gombra.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="1ebe2-140">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-140">Inspect the project.</span></span> <span data-ttu-id="1ebe2-141">Ekkor meg kell jelennie egy nevű forrásfájl `Program.qs` , amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1ebe2-142">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="1ebe2-142">To run the application:</span></span>
1. <span data-ttu-id="1ebe2-143">Válassza a **hibakeresés**  ->  **indítása hibakeresés nélkül**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="1ebe2-144">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="1ebe2-145">Ha egy Visual Studio-megoldásban több projekt is van, a megoldásban szereplő összes projektnek ugyanabban a mappában kell lennie, mint a megoldásnak, vagy egy almappájában.</span><span class="sxs-lookup"><span data-stu-id="1ebe2-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="1ebe2-146">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="1ebe2-146">Next steps</span></span>

<span data-ttu-id="1ebe2-147">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="1ebe2-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
