---
title: 'Fejlesztés a Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831018"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="ff519-102">Fejlesztés a Q # +C#</span><span class="sxs-lookup"><span data-stu-id="ff519-102">Develop with Q# + C#</span></span>

<span data-ttu-id="ff519-103">Telepítse a QDK a Q C# # műveletek hívására szolgáló gazdagép-programok fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="ff519-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="ff519-104">A Q # a .NET-nyelvekkel jól játszható – konkrétan C#.</span><span class="sxs-lookup"><span data-stu-id="ff519-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="ff519-105">Ezt a párosítást különböző fejlesztői környezetekben használhatja:</span><span class="sxs-lookup"><span data-stu-id="ff519-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="ff519-106">Q # + C# a Visual Studióval (Windows)</span><span class="sxs-lookup"><span data-stu-id="ff519-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="ff519-107">Q # + C# Visual Studio Code használata (Windows, Linux és Mac)</span><span class="sxs-lookup"><span data-stu-id="ff519-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="ff519-108">Q # + C# a `dotnet` parancssori eszköz használata</span><span class="sxs-lookup"><span data-stu-id="ff519-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="ff519-109">Fejlesztés a Q # + C# használatával a Visual Studióval<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="ff519-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="ff519-110">A Visual Studio sokoldalú környezetet kínál a Q # programok fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="ff519-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="ff519-111">A Q # Visual Studio bővítmény a Q # fájlokhoz és projektekhez tartozó sablonokat, valamint a szintaxis kiemelését, a kód befejezését és az IntelliSense támogatását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ff519-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="ff519-112">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ff519-112">Pre-requisites</span></span>

    - <span data-ttu-id="ff519-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével</span><span class="sxs-lookup"><span data-stu-id="ff519-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="ff519-114">Telepítse a Q# Visual Studio-bővítményt</span><span class="sxs-lookup"><span data-stu-id="ff519-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ff519-115">Töltse le és telepítse a [Visual Studio bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="ff519-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="ff519-116">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="ff519-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff519-117">Hozzon létre egy új Q#-alkalmazást</span><span class="sxs-lookup"><span data-stu-id="ff519-117">Create a new Q# application</span></span>

        - <span data-ttu-id="ff519-118">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="ff519-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="ff519-119">A keresőmezőbe írja be a következőt: `Q#`</span><span class="sxs-lookup"><span data-stu-id="ff519-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="ff519-120">Válassza a **Q#-alkalmazás** elemet</span><span class="sxs-lookup"><span data-stu-id="ff519-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="ff519-121">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="ff519-121">Select **Next**</span></span>
        - <span data-ttu-id="ff519-122">Válassza ki az alkalmazás nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="ff519-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="ff519-123">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="ff519-123">Select **Create**</span></span>

    - <span data-ttu-id="ff519-124">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="ff519-124">Inspect the project</span></span>

        <span data-ttu-id="ff519-125">Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="ff519-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="ff519-126">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="ff519-126">Run the application</span></span>

        - <span data-ttu-id="ff519-127">Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="ff519-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="ff519-128">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="ff519-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="ff519-129">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ff519-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="ff519-130">Fejlesztés a Q # + C# eszközzel a Visual Studio Code használatával<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="ff519-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="ff519-131">A Visual Studio Code (VS Code) sokoldalú környezetet kínál a Q # programok fejlesztéséhez Windows, Linux és Mac rendszereken.</span><span class="sxs-lookup"><span data-stu-id="ff519-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="ff519-132">A Q # VS Code bővítmény támogatja a Q # szintaxis kiemelését, a kód befejezését és a Q # kódrészleteket.</span><span class="sxs-lookup"><span data-stu-id="ff519-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="ff519-133">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ff519-133">Pre-requisites</span></span>

   - [<span data-ttu-id="ff519-134">VS Code</span><span class="sxs-lookup"><span data-stu-id="ff519-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="ff519-135">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="ff519-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ff519-136">Telepítse a Quantum VS Code-bővítményt</span><span class="sxs-lookup"><span data-stu-id="ff519-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ff519-137">Telepítse a [VS Code-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="ff519-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="ff519-138">Telepítse a Quantum-projektsablonokat:</span><span class="sxs-lookup"><span data-stu-id="ff519-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="ff519-139">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="ff519-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ff519-140">Válassza a **Q #: Project-sablonok telepítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="ff519-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="ff519-141">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="ff519-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ff519-142">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="ff519-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff519-143">Hozzon létre egy új projektet:</span><span class="sxs-lookup"><span data-stu-id="ff519-143">Create a new project:</span></span>

        - <span data-ttu-id="ff519-144">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="ff519-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="ff519-145">Válassza a **Q #: új projekt létrehozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="ff519-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="ff519-146">**Önálló konzolos alkalmazás** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="ff519-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="ff519-147">Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást</span><span class="sxs-lookup"><span data-stu-id="ff519-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="ff519-148">A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra</span><span class="sxs-lookup"><span data-stu-id="ff519-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="ff519-149">Ha még nincs telepítve a C# vs Code bővítmény, egy előugró ablak jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ff519-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="ff519-150">Telepítse a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="ff519-150">Install the extension.</span></span> 

    - <span data-ttu-id="ff519-151">Futtassa az alkalmazást:</span><span class="sxs-lookup"><span data-stu-id="ff519-151">Run the application:</span></span>

        - <span data-ttu-id="ff519-152">Ugrás a **terminal** -> **új terminálra**</span><span class="sxs-lookup"><span data-stu-id="ff519-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="ff519-153">Adja meg `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="ff519-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="ff519-154">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ff519-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="ff519-155">A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="ff519-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="ff519-156">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ff519-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="ff519-157">Fejlesztés a Q # + C# használatával a `dotnet` parancssori eszközzel<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="ff519-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="ff519-158">Természetesen a parancssorból is egyszerűen összeállíthat és futtathat Q#-programokat, ha telepíti a .NET Core SDK-t és a QDK-projektsablonokat.</span><span class="sxs-lookup"><span data-stu-id="ff519-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="ff519-159">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ff519-159">Pre-requisites</span></span>

    - [<span data-ttu-id="ff519-160">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="ff519-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ff519-161">Telepítse a .NET-hez tartozó Quantum-projektsablonokat</span><span class="sxs-lookup"><span data-stu-id="ff519-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="ff519-162">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="ff519-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ff519-163">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="ff519-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff519-164">Új alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="ff519-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="ff519-165">Lépjen az új alkalmazás könyvtárához</span><span class="sxs-lookup"><span data-stu-id="ff519-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="ff519-166">Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="ff519-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="ff519-167">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="ff519-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="ff519-168">A következő kimenetnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ff519-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="ff519-169">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="ff519-169">What's next?</span></span>

<span data-ttu-id="ff519-170">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="ff519-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
