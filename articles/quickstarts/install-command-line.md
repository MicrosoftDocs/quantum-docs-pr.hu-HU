---
title: Fejlesztés Q# nyelvű parancssori alkalmazásokkal
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274122"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="ab559-102">Fejlesztés Q# nyelvű parancssori alkalmazásokkal</span><span class="sxs-lookup"><span data-stu-id="ab559-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="ab559-103">A Q#-programok külön, illesztő nélkül is végrehajthatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.</span><span class="sxs-lookup"><span data-stu-id="ab559-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab559-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ab559-104">Prerequisites</span></span>

- [<span data-ttu-id="ab559-105">.NET Core SDK 3.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="ab559-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="ab559-106">Telepítés</span><span class="sxs-lookup"><span data-stu-id="ab559-106">Installation</span></span>

<span data-ttu-id="ab559-107">Bár Q# parancssori alkalmazásokat bármilyen IDE-ben létrehozhat, javasoljuk, hogy Q#-alkalmazásokhoz használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t.</span><span class="sxs-lookup"><span data-stu-id="ab559-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="ab559-108">Ha ezekben az eszközökben fejleszt, számos funkcióhoz férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="ab559-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="ab559-109">A VS Code konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="ab559-109">To configure VS Code:</span></span>

1. <span data-ttu-id="ab559-110">Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="ab559-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="ab559-111">Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="ab559-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="ab559-112">A Visual Studio konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="ab559-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="ab559-113">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="ab559-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="ab559-114">Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="ab559-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="ab559-115">Fejlesztés a Q# és a VS Code használatával</span><span class="sxs-lookup"><span data-stu-id="ab559-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="ab559-116">Telepítse a Q#-projektsablonokat:</span><span class="sxs-lookup"><span data-stu-id="ab559-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="ab559-117">Nyissa meg a VS Code-ot.</span><span class="sxs-lookup"><span data-stu-id="ab559-117">Open VS Code.</span></span>
2. <span data-ttu-id="ab559-118">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab559-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="ab559-119">Válassza a **Q#: Install project templates (Q#: Projektsablonok telepítése)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab559-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="ab559-120">A **projektsablonok sikeres telepítése esetén** jelenik meg, a QDK kész az Ön alkalmazásaival és kódtáraival való használatra.</span><span class="sxs-lookup"><span data-stu-id="ab559-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="ab559-121">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="ab559-121">To create a new project:</span></span>

1. <span data-ttu-id="ab559-122">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab559-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="ab559-123">Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab559-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="ab559-124">Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab559-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="ab559-125">A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="ab559-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="ab559-126">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="ab559-126">Inspect the project.</span></span> <span data-ttu-id="ab559-127">Látni fog egy `Program.qs` nevű forrásfájlt, amely egy olyan Q#-program, amely üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="ab559-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="ab559-128">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="ab559-128">To run the application:</span></span>
1. <span data-ttu-id="ab559-129">Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab559-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="ab559-130">A terminál parancssorába írja be a következőt: `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="ab559-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="ab559-131">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ab559-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="ab559-132">A VS Code Q#-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="ab559-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="ab559-133">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab559-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="ab559-134">Fejlesztés a Q# és a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="ab559-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="ab559-135">Ellenőrizze a Visual Studio telepítését egy `Hello World` Q#-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="ab559-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="ab559-136">Új Q#-alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="ab559-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="ab559-137">Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.</span><span class="sxs-lookup"><span data-stu-id="ab559-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="ab559-138">A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást**, és kattintson a **Next (Tovább)** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab559-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="ab559-139">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab559-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="ab559-140">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="ab559-140">Inspect the project.</span></span> <span data-ttu-id="ab559-141">Látni fog egy `Program.qs` nevű forrásfájlt, amely egy olyan Q#-program, amely üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="ab559-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="ab559-142">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="ab559-142">To run the application:</span></span>
1. <span data-ttu-id="ab559-143">Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab559-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="ab559-144">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="ab559-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="ab559-145">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab559-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="ab559-146">További lépések</span><span class="sxs-lookup"><span data-stu-id="ab559-146">Next steps</span></span>

<span data-ttu-id="ab559-147">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="ab559-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
