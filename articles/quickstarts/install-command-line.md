---
title: Fejlesztés Q#-alkalmazásokkal egy IDE-ben
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
ms.openlocfilehash: eeb567dedc1b8123b32faf7ed3a42bb51f16a7d2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228729"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="14ef8-103">Fejlesztés Q#-alkalmazásokkal egy IDE-ben</span><span class="sxs-lookup"><span data-stu-id="14ef8-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="14ef8-104">A Q#-programok külön, illesztő nélkül futtathatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.</span><span class="sxs-lookup"><span data-stu-id="14ef8-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="14ef8-105">Q#-alkalmazásokat a Visual Studio Code-ban (VS Code), a Visual Studióban, a Visual Studio Codespacesben vagy bármely szerkesztőben/IDE-ben is létrehozhat, és a .NET-konzolról futtathatja őket.</span><span class="sxs-lookup"><span data-stu-id="14ef8-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="14ef8-106">Az összes környezetre vonatkozó előfeltételek</span><span class="sxs-lookup"><span data-stu-id="14ef8-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="14ef8-107">.NET Core SDK 3.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="14ef8-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="14ef8-108">Telepítés</span><span class="sxs-lookup"><span data-stu-id="14ef8-108">Installation</span></span>

<span data-ttu-id="14ef8-109">Bár Q#-alkalmazásokat bármilyen IDE-ben buildelhet, javasoljuk, hogy a Q#-alkalmazások helyi fejlesztéséhez használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t.</span><span class="sxs-lookup"><span data-stu-id="14ef8-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="14ef8-110">A felhőben, webböngészőn keresztül történő fejlesztéshez a Visual Studio Codespaces használatát javasoljuk.</span><span class="sxs-lookup"><span data-stu-id="14ef8-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="14ef8-111">Ha ezekben a környezetekben fejleszt, kihasználhatja a QDK-bővítmény széles körű funkcióinak előnyeit, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket.</span><span class="sxs-lookup"><span data-stu-id="14ef8-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="14ef8-112">Konfigurálás VS Code-hoz:</span><span class="sxs-lookup"><span data-stu-id="14ef8-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="14ef8-113">Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="14ef8-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="14ef8-114">Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="14ef8-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="14ef8-115">Konfigurálás Visual Studióhoz:</span><span class="sxs-lookup"><span data-stu-id="14ef8-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="14ef8-116">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="14ef8-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="14ef8-117">Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="14ef8-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="14ef8-118">Konfigurálás másik környezethez:</span><span class="sxs-lookup"><span data-stu-id="14ef8-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="14ef8-119">Adja meg a következőt a parancssorban:</span><span class="sxs-lookup"><span data-stu-id="14ef8-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="14ef8-120">Konfigurálás Visual Studio Codespaceshez:</span><span class="sxs-lookup"><span data-stu-id="14ef8-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="14ef8-121">Hozzon létre egy [Azure-fiókot](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="14ef8-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="14ef8-122">Hozzon létre egy Codespaces-környezetet.</span><span class="sxs-lookup"><span data-stu-id="14ef8-122">Create a Codespaces environment.</span></span> <span data-ttu-id="14ef8-123">Kövesse a [gyorsútmutatót](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="14ef8-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="14ef8-124">A Codespace létrehozásakor javasoljuk, hogy a QDK-specifikus beállítások betöltéséhez írja be a `microsoft/Quantum` elemet a „Git-adattár” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="14ef8-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="14ef8-125">Most már elindíthatja az új környezetet, és megkezdheti a fejlesztést a böngészőben a [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)használatával.</span><span class="sxs-lookup"><span data-stu-id="14ef8-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="14ef8-126">Azt is megteheti, hogy a VS Code helyi telepítését használja, a Codespacest pedig [távoli környezetként](https://docs.microsoft.com/visualstudio/online/how-to/vscode) alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="14ef8-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="14ef8-127">Fejlesztés a Q# használatával</span><span class="sxs-lookup"><span data-stu-id="14ef8-127">Develop with Q#</span></span>

<span data-ttu-id="14ef8-128">Kövesse az alkalmazott fejlesztési környezetre vonatkozó fülön található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="14ef8-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="14ef8-129">VS Code</span><span class="sxs-lookup"><span data-stu-id="14ef8-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="14ef8-130">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="14ef8-130">To create a new project:</span></span>

1. <span data-ttu-id="14ef8-131">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14ef8-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="14ef8-132">Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="14ef8-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="14ef8-133">Lépjen a projekt mentési helyére.</span><span class="sxs-lookup"><span data-stu-id="14ef8-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="14ef8-134">Adja meg a projekt nevét, és kattintson a **Create project** (Projekt létrehozása) gombra.</span><span class="sxs-lookup"><span data-stu-id="14ef8-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="14ef8-135">A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="14ef8-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="14ef8-136">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="14ef8-136">Inspect the project.</span></span> <span data-ttu-id="14ef8-137">Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="14ef8-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="14ef8-138">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="14ef8-138">To run the application:</span></span>

1. <span data-ttu-id="14ef8-139">Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.</span><span class="sxs-lookup"><span data-stu-id="14ef8-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="14ef8-140">A terminál parancssorába írja be a következőt: `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="14ef8-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="14ef8-141">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="14ef8-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="14ef8-142">A VS Code Q#-bővítménye jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="14ef8-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="14ef8-143">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="14ef8-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="14ef8-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14ef8-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="14ef8-145">Ellenőrizze a Visual Studio telepítését egy Q# `Hello World`-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="14ef8-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="14ef8-146">Új Q#-alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="14ef8-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="14ef8-147">Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.</span><span class="sxs-lookup"><span data-stu-id="14ef8-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="14ef8-148">A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást**, és kattintson a **Next (Tovább)** elemre.</span><span class="sxs-lookup"><span data-stu-id="14ef8-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="14ef8-149">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="14ef8-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="14ef8-150">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="14ef8-150">Inspect the project.</span></span> <span data-ttu-id="14ef8-151">Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="14ef8-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="14ef8-152">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="14ef8-152">To run the application:</span></span>

1. <span data-ttu-id="14ef8-153">Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14ef8-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="14ef8-154">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="14ef8-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="14ef8-155">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="14ef8-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="14ef8-156">Egyéb, parancssorral rendelkező szerkesztők</span><span class="sxs-lookup"><span data-stu-id="14ef8-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="14ef8-157">Ellenőrizze a telepítést egy Q# `Hello World`-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="14ef8-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="14ef8-158">Új alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="14ef8-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="14ef8-159">Navigáljon az alkalmazás könyvtárához:</span><span class="sxs-lookup"><span data-stu-id="14ef8-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="14ef8-160">A könyvtár tartalmaz egy `Program.qs` nevű fájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="14ef8-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="14ef8-161">Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival.</span><span class="sxs-lookup"><span data-stu-id="14ef8-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="14ef8-162">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="14ef8-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="14ef8-163">A következő szövegnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="14ef8-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="14ef8-164">További lépések</span><span class="sxs-lookup"><span data-stu-id="14ef8-164">Next steps</span></span>

<span data-ttu-id="14ef8-165">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="14ef8-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
