---
title: Fejlesztés Q#-alkalmazásokkal
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: a630b2307f5d95321fb26f480d7a441ddba846fc
ms.sourcegitcommit: d6ac6f4345be0dd68f1bcd944f44b08e7a3cf346
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358258"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="3d65f-102">Fejlesztés Q#-alkalmazásokkal</span><span class="sxs-lookup"><span data-stu-id="3d65f-102">Develop with Q# applications</span></span>

<span data-ttu-id="3d65f-103">A Q#-programok külön, illesztő nélkül is végrehajthatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.</span><span class="sxs-lookup"><span data-stu-id="3d65f-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d65f-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="3d65f-104">Prerequisites</span></span>

- [<span data-ttu-id="3d65f-105">.NET Core SDK 3.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="3d65f-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="3d65f-106">Telepítés</span><span class="sxs-lookup"><span data-stu-id="3d65f-106">Installation</span></span>

<span data-ttu-id="3d65f-107">Bár Q#-alkalmazásokat bármilyen IDE-ben buildelhet, javasoljuk, hogy a Q#-alkalmazások helyi fejlesztéséhez használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t.</span><span class="sxs-lookup"><span data-stu-id="3d65f-107">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="3d65f-108">A felhőben, webböngészőn keresztül történő fejlesztéshez a Visual Studio Codespaces használatát javasoljuk.</span><span class="sxs-lookup"><span data-stu-id="3d65f-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="3d65f-109">Ha ezekben a környezetekben fejleszt, hozzáférhet a QDK-bővítmény széleskörű funkcióihoz, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket.</span><span class="sxs-lookup"><span data-stu-id="3d65f-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="3d65f-110">A VS Code konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-110">To configure VS Code:</span></span>

1. <span data-ttu-id="3d65f-111">Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="3d65f-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="3d65f-112">Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="3d65f-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="3d65f-113">A Visual Studio konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="3d65f-114">Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="3d65f-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="3d65f-115">Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="3d65f-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="3d65f-116">A Visual Studio Codespaces konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="3d65f-117">Hozzon létre egy [Azure-fiókot](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="3d65f-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="3d65f-118">Hozzon létre egy Codespaces-környezetet.</span><span class="sxs-lookup"><span data-stu-id="3d65f-118">Create a Codespaces environment.</span></span> <span data-ttu-id="3d65f-119">Kövesse a [gyorsútmutatót](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="3d65f-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="3d65f-120">A Codespace létrehozásakor javasoljuk, hogy a QDK-specifikus beállítások betöltéséhez írja be a `microsoft/Quantum` elemet a „Git-adattár” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3d65f-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="3d65f-121">Most már elindíthatja az új környezetet, és megkezdheti a fejlesztést a böngészőben a [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)használatával.</span><span class="sxs-lookup"><span data-stu-id="3d65f-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="3d65f-122">Azt is megteheti, hogy a VS Code helyi telepítését használja, a Codespacest pedig [távoli környezetként](https://docs.microsoft.com/visualstudio/online/how-to/vscode) alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="3d65f-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="3d65f-123">A QDK egy másik környezetben való telepítéséhez írja a következőt a parancssorba:</span><span class="sxs-lookup"><span data-stu-id="3d65f-123">To install the QDK for another environment, enter at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="3d65f-124">Fejlesztés a Q# használatával</span><span class="sxs-lookup"><span data-stu-id="3d65f-124">Develop with Q#</span></span>

<span data-ttu-id="3d65f-125">Kövesse a környezetéhez tartozó fülön található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="3d65f-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="3d65f-126">VS Code</span><span class="sxs-lookup"><span data-stu-id="3d65f-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="3d65f-127">Új projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-127">To create a new project:</span></span>

1. <span data-ttu-id="3d65f-128">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3d65f-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="3d65f-129">Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="3d65f-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="3d65f-130">Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d65f-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="3d65f-131">A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="3d65f-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="3d65f-132">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="3d65f-132">Inspect the project.</span></span> <span data-ttu-id="3d65f-133">Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3d65f-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="3d65f-134">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-134">To run the application:</span></span>
1. <span data-ttu-id="3d65f-135">Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.</span><span class="sxs-lookup"><span data-stu-id="3d65f-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="3d65f-136">A terminál parancssorába írja be a következőt: `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="3d65f-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="3d65f-137">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="3d65f-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="3d65f-138">A VS Code Q#-bővítménye jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="3d65f-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="3d65f-139">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="3d65f-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="3d65f-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3d65f-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="3d65f-141">Ellenőrizze a Visual Studio telepítését egy Q# `Hello World`-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="3d65f-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="3d65f-142">Új Q#-alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="3d65f-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="3d65f-143">Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.</span><span class="sxs-lookup"><span data-stu-id="3d65f-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="3d65f-144">A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást**, és kattintson a **Next (Tovább)** elemre.</span><span class="sxs-lookup"><span data-stu-id="3d65f-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="3d65f-145">Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="3d65f-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="3d65f-146">Vizsgálja meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="3d65f-146">Inspect the project.</span></span> <span data-ttu-id="3d65f-147">Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3d65f-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="3d65f-148">Az alkalmazás futtatása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-148">To run the application:</span></span>
1. <span data-ttu-id="3d65f-149">Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3d65f-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="3d65f-150">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="3d65f-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="3d65f-151">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="3d65f-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="3d65f-152">Egyéb, parancssorral rendelkező szerkesztők</span><span class="sxs-lookup"><span data-stu-id="3d65f-152">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="3d65f-153">Ellenőrizze a telepítést egy Q# `Hello World`-alkalmazás létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="3d65f-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="3d65f-154">Telepítse a projektsablonokat.</span><span class="sxs-lookup"><span data-stu-id="3d65f-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="3d65f-155">Új alkalmazás létrehozása:</span><span class="sxs-lookup"><span data-stu-id="3d65f-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="3d65f-156">Navigáljon az alkalmazás könyvtárához:</span><span class="sxs-lookup"><span data-stu-id="3d65f-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="3d65f-157">A könyvtár tartalmaz egy `Program.qs` nevű fájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3d65f-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="3d65f-158">Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival.</span><span class="sxs-lookup"><span data-stu-id="3d65f-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="3d65f-159">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="3d65f-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="3d65f-160">A következő szövegnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="3d65f-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="3d65f-161">További lépések</span><span class="sxs-lookup"><span data-stu-id="3d65f-161">Next steps</span></span>

<span data-ttu-id="3d65f-162">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="3d65f-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
