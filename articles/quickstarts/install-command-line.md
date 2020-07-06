---
title: Fejlesztés Q# nyelvű parancssori alkalmazásokkal
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884282"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="2a89d-102">Fejlesztés Q# nyelvű parancssori alkalmazásokkal</span><span class="sxs-lookup"><span data-stu-id="2a89d-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="2a89d-103">A Q#-programok külön, illesztő nélkül is végrehajthatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.</span><span class="sxs-lookup"><span data-stu-id="2a89d-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a89d-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="2a89d-104">Prerequisites</span></span>

- [<span data-ttu-id="2a89d-105">.NET Core SDK 3.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="2a89d-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="2a89d-106">Telepítés</span><span class="sxs-lookup"><span data-stu-id="2a89d-106">Installation</span></span>

<span data-ttu-id="2a89d-107">Bár Q# parancssori alkalmazásokat bármilyen IDE-ben létrehozhat, javasoljuk, hogy Q#-alkalmazásokhoz használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t.</span><span class="sxs-lookup"><span data-stu-id="2a89d-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="2a89d-108">Ha ezekben a környezetekben fejleszt, hozzáférhet a QDK-bővítmény széleskörű funkcióihoz, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket.</span><span class="sxs-lookup"><span data-stu-id="2a89d-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="2a89d-109">A VS Code konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-109">To configure VS Code:</span></span>

1. <span data-ttu-id="2a89d-110">Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="2a89d-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="2a89d-111">Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="2a89d-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="2a89d-112">A Visual Studio konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="2a89d-113">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="2a89d-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="2a89d-114">Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="2a89d-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="2a89d-115">A QDK egy másik környezetben való telepítéséhez írja a következőt a parancssorba:</span><span class="sxs-lookup"><span data-stu-id="2a89d-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="2a89d-116">Fejlesztés a Q# használatával</span><span class="sxs-lookup"><span data-stu-id="2a89d-116">Develop with Q#</span></span>

<span data-ttu-id="2a89d-117">Kövesse a környezetéhez tartozó fülön található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="2a89d-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="2a89d-118">VS Code</span><span class="sxs-lookup"><span data-stu-id="2a89d-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2a89d-119">Telepítse a Q#-projektsablonokat:</span><span class="sxs-lookup"><span data-stu-id="2a89d-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="2a89d-120">Nyissa meg a VS Code-ot.</span><span class="sxs-lookup"><span data-stu-id="2a89d-120">Open VS Code.</span></span>
2. <span data-ttu-id="2a89d-121">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="2a89d-122">Válassza a **Q#: Install project templates (Q#: Projektsablonok telepítése)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a89d-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="2a89d-123">A **projektsablonok sikeres telepítése esetén** jelenik meg, a QDK kész az Ön alkalmazásaival és kódtáraival való használatra.</span><span class="sxs-lookup"><span data-stu-id="2a89d-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="2a89d-124">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-124">To create a new project:</span></span>

1. <span data-ttu-id="2a89d-125">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a89d-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="2a89d-126">Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="2a89d-127">Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="2a89d-128">A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="2a89d-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="2a89d-129">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="2a89d-129">Inspect the project.</span></span> <span data-ttu-id="2a89d-130">Látni fog egy `Program.qs` nevű forrásfájlt, amely egy olyan Q#-program, amely üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="2a89d-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="2a89d-131">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-131">To run the application:</span></span>
1. <span data-ttu-id="2a89d-132">Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="2a89d-133">A terminál parancssorába írja be a következőt: `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="2a89d-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="2a89d-134">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2a89d-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="2a89d-135">A VS Code Q#-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="2a89d-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="2a89d-136">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a89d-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="2a89d-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a89d-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="2a89d-138">Ellenőrizze a Visual Studio telepítését egy `Hello World` Q#-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="2a89d-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="2a89d-139">Új Q#-alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="2a89d-140">Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="2a89d-141">A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást**, és kattintson a **Next (Tovább)** elemre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="2a89d-142">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="2a89d-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="2a89d-143">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="2a89d-143">Inspect the project.</span></span> <span data-ttu-id="2a89d-144">Látni fog egy `Program.qs` nevű forrásfájlt, amely egy olyan Q#-program, amely üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="2a89d-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="2a89d-145">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-145">To run the application:</span></span>
1. <span data-ttu-id="2a89d-146">Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a89d-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="2a89d-147">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="2a89d-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="2a89d-148">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a89d-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="2a89d-149">Egyéb, parancssorral rendelkező szerkesztők</span><span class="sxs-lookup"><span data-stu-id="2a89d-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="2a89d-150">Ellenőrizze a telepítést egy `Hello World` Q#-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="2a89d-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="2a89d-151">Új alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="2a89d-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="2a89d-152">Navigáljon az alkalmazás könyvtárához:</span><span class="sxs-lookup"><span data-stu-id="2a89d-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="2a89d-153">A könyvtár egy `Program.qs` nevű fájlt fog tartalmazni, amely egy olyan Q#-program, amely az üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="2a89d-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="2a89d-154">Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival.</span><span class="sxs-lookup"><span data-stu-id="2a89d-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="2a89d-155">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="2a89d-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="2a89d-156">A következő szövegnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2a89d-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="2a89d-157">További lépések</span><span class="sxs-lookup"><span data-stu-id="2a89d-157">Next steps</span></span>

<span data-ttu-id="2a89d-158">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="2a89d-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
