---
title: Fejlesztés Q#-alkalmazásokkal
description: Megtudhatja, hogyan hozhat létre olyan Q#-alkalmazást, amely a parancssorból fut.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834414"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="8a804-103">Fejlesztés Q#-alkalmazásokkal</span><span class="sxs-lookup"><span data-stu-id="8a804-103">Develop with Q# applications</span></span>

<span data-ttu-id="8a804-104">Kövesse a környezetéhez tartozó fülön található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8a804-104">Follow the instructions at the tab corresponding to your environment.</span></span>

<span data-ttu-id="8a804-105">A Q#-programok külön, illesztő nélkül futtathatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.</span><span class="sxs-lookup"><span data-stu-id="8a804-105">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a804-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8a804-106">Prerequisites</span></span>

- [<span data-ttu-id="8a804-107">.NET Core SDK 3.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="8a804-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="8a804-108">Telepítés</span><span class="sxs-lookup"><span data-stu-id="8a804-108">Installation</span></span>

<span data-ttu-id="8a804-109">Bár Q#-alkalmazásokat bármilyen IDE-ben buildelhet, javasoljuk, hogy a Q#-alkalmazások helyi fejlesztéséhez használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t.</span><span class="sxs-lookup"><span data-stu-id="8a804-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="8a804-110">A felhőben, webböngészőn keresztül történő fejlesztéshez a Visual Studio Codespaces használatát javasoljuk.</span><span class="sxs-lookup"><span data-stu-id="8a804-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="8a804-111">Ha ezekben a környezetekben fejleszt, hozzáférhet a QDK-bővítmény széleskörű funkcióihoz, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket.</span><span class="sxs-lookup"><span data-stu-id="8a804-111">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="8a804-112">A VS Code konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="8a804-112">To configure VS Code:</span></span>

1. <span data-ttu-id="8a804-113">Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="8a804-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="8a804-114">Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="8a804-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="8a804-115">A Visual Studio konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="8a804-115">To configure Visual Studio:</span></span>

1. <span data-ttu-id="8a804-116">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="8a804-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="8a804-117">Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="8a804-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="8a804-118">A Visual Studio Codespaces konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="8a804-118">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="8a804-119">Hozzon létre egy [Azure-fiókot](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="8a804-119">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="8a804-120">Hozzon létre egy Codespaces-környezetet.</span><span class="sxs-lookup"><span data-stu-id="8a804-120">Create a Codespaces environment.</span></span> <span data-ttu-id="8a804-121">Kövesse a [gyorsútmutatót](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="8a804-121">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="8a804-122">A Codespace létrehozásakor javasoljuk, hogy a QDK-specifikus beállítások betöltéséhez írja be a `microsoft/Quantum` elemet a „Git-adattár” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8a804-122">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="8a804-123">Most már elindíthatja az új környezetet, és megkezdheti a fejlesztést a böngészőben a [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)használatával.</span><span class="sxs-lookup"><span data-stu-id="8a804-123">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="8a804-124">Azt is megteheti, hogy a VS Code helyi telepítését használja, a Codespacest pedig [távoli környezetként](https://docs.microsoft.com/visualstudio/online/how-to/vscode) alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="8a804-124">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="8a804-125">A QDK egy másik környezetben való telepítéséhez írja a következőt a parancssorba:</span><span class="sxs-lookup"><span data-stu-id="8a804-125">To install the QDK for another environment, enter the following at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="8a804-126">Fejlesztés a Q# használatával</span><span class="sxs-lookup"><span data-stu-id="8a804-126">Develop with Q#</span></span>

<span data-ttu-id="8a804-127">Kövesse a környezetéhez tartozó fülön található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8a804-127">Follow the instructions on the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="8a804-128">VS Code</span><span class="sxs-lookup"><span data-stu-id="8a804-128">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="8a804-129">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="8a804-129">To create a new project:</span></span>

1. <span data-ttu-id="8a804-130">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a804-130">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="8a804-131">Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="8a804-131">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="8a804-132">Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a804-132">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="8a804-133">A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="8a804-133">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="8a804-134">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="8a804-134">Inspect the project.</span></span> <span data-ttu-id="8a804-135">Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8a804-135">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="8a804-136">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="8a804-136">To run the application:</span></span>

1. <span data-ttu-id="8a804-137">Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.</span><span class="sxs-lookup"><span data-stu-id="8a804-137">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="8a804-138">A terminál parancssorába írja be a következőt: `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="8a804-138">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="8a804-139">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8a804-139">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="8a804-140">A VS Code Q#-bővítménye jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="8a804-140">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="8a804-141">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8a804-141">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="8a804-142">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8a804-142">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="8a804-143">Ellenőrizze a Visual Studio telepítését egy Q# `Hello World`-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="8a804-143">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="8a804-144">Új Q#-alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a804-144">To create a new Q# application:</span></span>

1. <span data-ttu-id="8a804-145">Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.</span><span class="sxs-lookup"><span data-stu-id="8a804-145">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="8a804-146">A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást**, és kattintson a **Next (Tovább)** elemre.</span><span class="sxs-lookup"><span data-stu-id="8a804-146">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="8a804-147">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="8a804-147">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="8a804-148">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="8a804-148">Inspect the project.</span></span> <span data-ttu-id="8a804-149">Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8a804-149">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="8a804-150">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="8a804-150">To run the application:</span></span>

1. <span data-ttu-id="8a804-151">Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a804-151">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="8a804-152">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="8a804-152">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="8a804-153">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8a804-153">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="8a804-154">Egyéb, parancssorral rendelkező szerkesztők</span><span class="sxs-lookup"><span data-stu-id="8a804-154">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="8a804-155">Ellenőrizze a telepítést egy Q# `Hello World`-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="8a804-155">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="8a804-156">Telepítse a projektsablonokat.</span><span class="sxs-lookup"><span data-stu-id="8a804-156">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="8a804-157">Új alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="8a804-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="8a804-158">Navigáljon az alkalmazás könyvtárához:</span><span class="sxs-lookup"><span data-stu-id="8a804-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="8a804-159">A könyvtár tartalmaz egy `Program.qs` nevű fájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8a804-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="8a804-160">Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival.</span><span class="sxs-lookup"><span data-stu-id="8a804-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="8a804-161">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="8a804-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="8a804-162">A következő szövegnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8a804-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="8a804-163">További lépések</span><span class="sxs-lookup"><span data-stu-id="8a804-163">Next steps</span></span>

<span data-ttu-id="8a804-164">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="8a804-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
