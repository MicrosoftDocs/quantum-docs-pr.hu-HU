---
title: 'Fejlesztés Q # parancssori alkalmazásokkal'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426439"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="02a3c-102">Fejlesztés Q # parancssori alkalmazásokkal</span><span class="sxs-lookup"><span data-stu-id="02a3c-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="02a3c-103">A Q # programok saját maguk is végrehajthatók a gazdagépen, például C#, F # vagy Python nyelven.</span><span class="sxs-lookup"><span data-stu-id="02a3c-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="02a3c-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="02a3c-104">Pre-requisites</span></span>

- [<span data-ttu-id="02a3c-105">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="02a3c-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="02a3c-106">Telepítés</span><span class="sxs-lookup"><span data-stu-id="02a3c-106">Installation</span></span>

<span data-ttu-id="02a3c-107">A Q # parancssori alkalmazásai bármilyen IDE-ben létrehozhatók, de a Q # alkalmazásaihoz a Visual Studio Code (VS Code) vagy a Visual Studio IDE használata javasolt.</span><span class="sxs-lookup"><span data-stu-id="02a3c-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="02a3c-108">Az ezekben az eszközökben való fejlesztés a sokoldalú funkciók elérését teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="02a3c-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="02a3c-109">A VS Code konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="02a3c-109">To configure VS Code:</span></span>

1. <span data-ttu-id="02a3c-110">Töltse le és telepítse a [vs Code](https://code.visualstudio.com/download) -ot (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="02a3c-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="02a3c-111">Telepítse a [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)-hoz készült Microsoft-QDK.</span><span class="sxs-lookup"><span data-stu-id="02a3c-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="02a3c-112">A Visual Studio konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="02a3c-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="02a3c-113">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3-es vagy újabb változatát, és engedélyezze a .net Core platformfüggetlen fejlesztési munkaterhelést.</span><span class="sxs-lookup"><span data-stu-id="02a3c-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="02a3c-114">Töltse le és telepítse a [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="02a3c-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="02a3c-115">Fejlesztés a Q # segítségével VS Code használatával</span><span class="sxs-lookup"><span data-stu-id="02a3c-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="02a3c-116">A Q # Project-sablonok telepítése:</span><span class="sxs-lookup"><span data-stu-id="02a3c-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="02a3c-117">Nyissa meg a VS Code-ot.</span><span class="sxs-lookup"><span data-stu-id="02a3c-117">Open VS Code.</span></span>
2. <span data-ttu-id="02a3c-118">Kattintson **View**a  ->  **parancs paletta**megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="02a3c-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="02a3c-119">Válassza a **Q #: Project-sablonok telepítése**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02a3c-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="02a3c-120">Ha a **Project templates telepítése sikeresen megtörtént** , a QDK készen áll a saját alkalmazásaival és könyvtáraival való használatra.</span><span class="sxs-lookup"><span data-stu-id="02a3c-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="02a3c-121">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="02a3c-121">To create a new project:</span></span>

1. <span data-ttu-id="02a3c-122">Kattintson **View**  ->  a**parancs paletta** megtekintése elemre, és válassza a **Q #: új projekt létrehozása**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02a3c-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="02a3c-123">Kattintson a **különálló konzol alkalmazás**lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="02a3c-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="02a3c-124">Navigáljon a projekt mentéséhez és a **projekt létrehozása**elemre.</span><span class="sxs-lookup"><span data-stu-id="02a3c-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="02a3c-125">A projekt sikeres létrehozása után kattintson a jobb alsó sarokban található **új projekt megnyitása..** . elemre.</span><span class="sxs-lookup"><span data-stu-id="02a3c-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="02a3c-126">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="02a3c-126">Inspect the project.</span></span> <span data-ttu-id="02a3c-127">Ekkor meg kell jelennie egy nevű forrásfájl `Program.qs` , amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="02a3c-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="02a3c-128">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="02a3c-128">To run the application:</span></span>
1. <span data-ttu-id="02a3c-129">Kattintson a **terminál**  ->  **új terminál**elemre.</span><span class="sxs-lookup"><span data-stu-id="02a3c-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="02a3c-130">A terminál parancssorába írja be a következőt: `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="02a3c-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="02a3c-131">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="02a3c-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="02a3c-132">A VS Code Q # bővítmény jelenleg nem támogatja a több legfelső szintű mappával rendelkező munkaterületek használatát.</span><span class="sxs-lookup"><span data-stu-id="02a3c-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="02a3c-133">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="02a3c-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="02a3c-134">Fejlesztés a Q # használatával a Visual Studióval</span><span class="sxs-lookup"><span data-stu-id="02a3c-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="02a3c-135">A Visual Studio telepítésének ellenőrzéséhez hozzon létre egy Q # `Hello World` alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="02a3c-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="02a3c-136">Új Q #-alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="02a3c-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="02a3c-137">Nyissa meg a Visual studiót, és kattintson a **fájl**  ->  **új**  ->  **projekt**elemre.</span><span class="sxs-lookup"><span data-stu-id="02a3c-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="02a3c-138">Írja be `Q#` a keresőmezőbe a **Q # alkalmazás** elemet, és kattintson a **tovább**gombra.</span><span class="sxs-lookup"><span data-stu-id="02a3c-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="02a3c-139">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Létrehozás**gombra.</span><span class="sxs-lookup"><span data-stu-id="02a3c-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="02a3c-140">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="02a3c-140">Inspect the project.</span></span> <span data-ttu-id="02a3c-141">Ekkor meg kell jelennie egy nevű forrásfájl `Program.qs` , amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="02a3c-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="02a3c-142">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="02a3c-142">To run the application:</span></span>
1. <span data-ttu-id="02a3c-143">Válassza a **hibakeresés**  ->  **indítása hibakeresés nélkül**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02a3c-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="02a3c-144">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="02a3c-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="02a3c-145">Ha egy Visual Studio-megoldásban több projekt is van, a megoldásban szereplő összes projektnek ugyanabban a mappában kell lennie, mint a megoldásnak, vagy egy almappájában.</span><span class="sxs-lookup"><span data-stu-id="02a3c-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="02a3c-146">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="02a3c-146">Next steps</span></span>

<span data-ttu-id="02a3c-147">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="02a3c-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
