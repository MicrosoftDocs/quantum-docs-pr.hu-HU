---
title: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035283"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c891f-102">A Microsoft Quantum Development Kit (QDK) telepítése</span><span class="sxs-lookup"><span data-stu-id="c891f-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c891f-103">Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="c891f-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="c891f-104">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="c891f-104">The QDK consists of:</span></span>

- <span data-ttu-id="c891f-105">a Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="c891f-105">the Q# programming language</span></span>
- <span data-ttu-id="c891f-106">kódtárak, amelyek összetett funkciókat választanak el a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="c891f-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="c891f-107">gazdaalkalmazás (Python vagy .NET nyelven írva), amely a Q# nyelven írt kvantumműveleteket futtatja</span><span class="sxs-lookup"><span data-stu-id="c891f-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="c891f-108">a fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="c891f-108">tools to facilitate your development</span></span>

<span data-ttu-id="c891f-109">A választott fejlesztési környezettől függően a telepítés lépései eltérnek.</span><span class="sxs-lookup"><span data-stu-id="c891f-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="c891f-110">Válassza ki a környezetet az alábbi szakaszok közül.</span><span class="sxs-lookup"><span data-stu-id="c891f-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="c891f-111">Fejlesztés a Pythonnal</span><span class="sxs-lookup"><span data-stu-id="c891f-111">Develop with Python</span></span>

1. <span data-ttu-id="c891f-112">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c891f-112">Pre-requisites</span></span>

    - <span data-ttu-id="c891f-113">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="c891f-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="c891f-114">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="c891f-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="c891f-115">.NET Core SDK 2.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="c891f-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="c891f-116">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="c891f-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c891f-117">Telepítse a(z) `qsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="c891f-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="c891f-118">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="c891f-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c891f-119">Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="c891f-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="c891f-120">Hozzon létre egy `hello_world.py` nevű Python-programot a Q# `SayHello()` műveletének meghívásához:</span><span class="sxs-lookup"><span data-stu-id="c891f-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="c891f-121">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="c891f-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="c891f-122">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="c891f-122">Verify the output.</span></span> <span data-ttu-id="c891f-123">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="c891f-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="c891f-124">Fejlesztés a Jupyter-notebookokkal</span><span class="sxs-lookup"><span data-stu-id="c891f-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="c891f-125">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c891f-125">Pre-requisites</span></span>

    - <span data-ttu-id="c891f-126">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="c891f-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="c891f-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="c891f-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="c891f-128">.NET Core SDK 2.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="c891f-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="c891f-129">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="c891f-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c891f-130">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="c891f-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c891f-131">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="c891f-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="c891f-132">Lépjen a parancssorban megjelenített URL-címre.</span><span class="sxs-lookup"><span data-stu-id="c891f-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="c891f-133">Például: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="c891f-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="c891f-134">Hozzon létre egy Jupyter-notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:</span><span class="sxs-lookup"><span data-stu-id="c891f-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="c891f-135">Futtassa a notebook következő celláját:</span><span class="sxs-lookup"><span data-stu-id="c891f-135">Run this cell of the notebook:</span></span>

        ![Jupyter-notebookcella](~/media/install-guide-jupyter.png)

        <span data-ttu-id="c891f-137">A cella kimenetében a következőnek kell megjelennie: `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="c891f-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="c891f-138">A Jupyter-notebookokban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.</span><span class="sxs-lookup"><span data-stu-id="c891f-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="c891f-139">Fejlesztés C#-pal Windows rendszeren, a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="c891f-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="c891f-140">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c891f-140">Pre-requisites</span></span>

    - <span data-ttu-id="c891f-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével</span><span class="sxs-lookup"><span data-stu-id="c891f-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="c891f-142">Telepítse a Q# Visual Studio-bővítményt</span><span class="sxs-lookup"><span data-stu-id="c891f-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c891f-143">Töltse le a [Visual Studio-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="c891f-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c891f-144">Adja a bővítményt a Visual Studióhoz</span><span class="sxs-lookup"><span data-stu-id="c891f-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="c891f-145">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="c891f-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c891f-146">Hozzon létre egy új Q#-alkalmazást</span><span class="sxs-lookup"><span data-stu-id="c891f-146">Create a new Q# application</span></span>

        - <span data-ttu-id="c891f-147">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="c891f-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="c891f-148">A keresőmezőbe írja be a következőt: `Q#`</span><span class="sxs-lookup"><span data-stu-id="c891f-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="c891f-149">Válassza a **Q#-alkalmazás** elemet</span><span class="sxs-lookup"><span data-stu-id="c891f-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="c891f-150">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="c891f-150">Select **Next**</span></span>
        - <span data-ttu-id="c891f-151">Válassza ki az alkalmazás nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="c891f-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="c891f-152">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="c891f-152">Select **Create**</span></span>

    - <span data-ttu-id="c891f-153">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="c891f-153">Inspect the project</span></span>

        <span data-ttu-id="c891f-154">Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="c891f-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="c891f-155">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="c891f-155">Run the application</span></span>

        - <span data-ttu-id="c891f-156">Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c891f-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="c891f-157">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="c891f-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="c891f-158">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c891f-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="c891f-159">Fejlesztés a C# és a VS Code használatával</span><span class="sxs-lookup"><span data-stu-id="c891f-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="c891f-160">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c891f-160">Pre-requisites</span></span>

   - [<span data-ttu-id="c891f-161">VS Code</span><span class="sxs-lookup"><span data-stu-id="c891f-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="c891f-162">.NET Core SDK 2.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="c891f-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="c891f-163">Telepítse a Quantum VS Code-bővítményt</span><span class="sxs-lookup"><span data-stu-id="c891f-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c891f-164">Telepítse a [VS Code-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="c891f-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="c891f-165">Telepítse a Quantum-projektsablonokat:</span><span class="sxs-lookup"><span data-stu-id="c891f-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="c891f-166">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="c891f-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c891f-167">Válassza a **Q#: Projektsablonok telepítése** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c891f-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="c891f-168">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="c891f-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="c891f-169">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="c891f-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c891f-170">Hozzon létre egy új projektet:</span><span class="sxs-lookup"><span data-stu-id="c891f-170">Create a new project:</span></span>

        - <span data-ttu-id="c891f-171">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="c891f-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="c891f-172">Válassza a **Q#: Új projekt létrehozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c891f-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="c891f-173">Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást</span><span class="sxs-lookup"><span data-stu-id="c891f-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="c891f-174">A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra</span><span class="sxs-lookup"><span data-stu-id="c891f-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="c891f-175">Futtassa az alkalmazást:</span><span class="sxs-lookup"><span data-stu-id="c891f-175">Run the application:</span></span>

        - <span data-ttu-id="c891f-176">Lépjen a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="c891f-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="c891f-177">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c891f-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="c891f-178">A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="c891f-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="c891f-179">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c891f-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c891f-180">Fejlesztés a C# és a(z) `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="c891f-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c891f-181">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c891f-181">Pre-requisites</span></span>

    - [<span data-ttu-id="c891f-182">.NET Core SDK 2.1 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="c891f-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="c891f-183">Telepítse a .NET-hez tartozó Quantum-projektsablonokat</span><span class="sxs-lookup"><span data-stu-id="c891f-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="c891f-184">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="c891f-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="c891f-185">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="c891f-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c891f-186">Új alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="c891f-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="c891f-187">Lépjen az új alkalmazás könyvtárához</span><span class="sxs-lookup"><span data-stu-id="c891f-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="c891f-188">Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="c891f-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="c891f-189">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="c891f-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="c891f-190">A következő kimenetnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c891f-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="c891f-191">A következő lépések</span><span class="sxs-lookup"><span data-stu-id="c891f-191">What's next?</span></span>

<span data-ttu-id="c891f-192">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="c891f-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
