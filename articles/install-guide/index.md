---
title: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799160"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b0201-102">A Microsoft Quantum Development Kit (QDK) telepítése</span><span class="sxs-lookup"><span data-stu-id="b0201-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b0201-103">Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek.</span><span class="sxs-lookup"><span data-stu-id="b0201-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="b0201-104">A QDK a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="b0201-104">The QDK consists of:</span></span>

- <span data-ttu-id="b0201-105">a Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="b0201-105">the Q# programming language</span></span>
- <span data-ttu-id="b0201-106">kódtárak, amelyek összetett funkciókat választanak el a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="b0201-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="b0201-107">gazdaalkalmazás (Python vagy .NET nyelven írva), amely a Q# nyelven írt kvantumműveleteket futtatja</span><span class="sxs-lookup"><span data-stu-id="b0201-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="b0201-108">a fejlesztést megkönnyítő eszközök</span><span class="sxs-lookup"><span data-stu-id="b0201-108">tools to facilitate your development</span></span>

<span data-ttu-id="b0201-109">A választott fejlesztési környezettől függően a telepítés lépései eltérnek.</span><span class="sxs-lookup"><span data-stu-id="b0201-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="b0201-110">Válassza ki a környezetet az alábbi szakaszok közül.</span><span class="sxs-lookup"><span data-stu-id="b0201-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="b0201-111">Fejlesztés a Pythonnal</span><span class="sxs-lookup"><span data-stu-id="b0201-111">Develop with Python</span></span>

<span data-ttu-id="b0201-112">A Pythonhoz készült qsharp csomag megkönnyíti a Q#-műveletek és -függvények Pythonon belüli szimulálását.</span><span class="sxs-lookup"><span data-stu-id="b0201-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="b0201-113">Az IQ# elsősorban a Jupyter és a Python által használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.</span><span class="sxs-lookup"><span data-stu-id="b0201-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="b0201-114">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b0201-114">Pre-requisites</span></span>

    - <span data-ttu-id="b0201-115">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="b0201-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="b0201-116">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="b0201-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="b0201-117">.NET Core SDK 3.0 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="b0201-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b0201-118">Telepítse a(z) `qsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="b0201-118">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="b0201-119">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="b0201-119">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b0201-120">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="b0201-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b0201-121">Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="b0201-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="b0201-122">Hozzon létre egy `hello_world.py` nevű Python-programot a Q# `SayHello()` műveletének meghívásához:</span><span class="sxs-lookup"><span data-stu-id="b0201-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="b0201-123">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="b0201-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="b0201-124">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="b0201-124">Verify the output.</span></span> <span data-ttu-id="b0201-125">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="b0201-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="b0201-126">Fejlesztés a Jupyter-notebookokkal</span><span class="sxs-lookup"><span data-stu-id="b0201-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="b0201-127">Az oktatási területeken, tudományos laborokban és az internetes, együttműködése alapuló programozásban kedvenc Jupyter-notebookok helyszíni kódvégrehajtást tesznek lehetővé (most már Q#-kóddal is) utasításokkal, megjegyzésekkel és egyéb tartalmakkal együtt.</span><span class="sxs-lookup"><span data-stu-id="b0201-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="b0201-128">Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="b0201-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="b0201-129">Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.</span><span class="sxs-lookup"><span data-stu-id="b0201-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="b0201-130">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b0201-130">Pre-requisites</span></span>

    - <span data-ttu-id="b0201-131">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="b0201-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="b0201-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b0201-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="b0201-133">.NET Core SDK 3.0 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="b0201-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b0201-134">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="b0201-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b0201-135">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="b0201-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b0201-136">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="b0201-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="b0201-137">Lépjen a parancssorban megjelenített URL-címre.</span><span class="sxs-lookup"><span data-stu-id="b0201-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="b0201-138">Például: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="b0201-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="b0201-139">Hozzon létre egy Jupyter-notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:</span><span class="sxs-lookup"><span data-stu-id="b0201-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="b0201-140">Futtassa a notebook következő celláját:</span><span class="sxs-lookup"><span data-stu-id="b0201-140">Run this cell of the notebook:</span></span>

        ![Jupyter-notebookcella Q#-kóddal](~/media/install-guide-jupyter.png)

        <span data-ttu-id="b0201-142">A cella kimenetében a következőnek kell megjelennie: `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="b0201-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="b0201-143">A Jupyter-notebookokban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.</span><span class="sxs-lookup"><span data-stu-id="b0201-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="b0201-144">Egy új cellában szimulálja a most létrehozott `%simulate`-művelet végrehajtását egy kvantumszámítógépen:</span><span class="sxs-lookup"><span data-stu-id="b0201-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Jupyter-notebookcella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="b0201-146">A képernyőn megjelenik az üzenet a meghívott művelet eredményével együtt (ebben az esetben üresen).</span><span class="sxs-lookup"><span data-stu-id="b0201-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="b0201-147">Fejlesztés C#-pal Windows rendszeren, a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="b0201-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="b0201-148">A Visual Studio gazdag környezetet nyújt a Q#-programok fejlesztéséhez, nagyszerű funkciókkal, például kódkiegészítéssel és szintaxiskiemeléssel, amelyek végigvezetik a fejlesztőt az alkalmazások összeállításán.</span><span class="sxs-lookup"><span data-stu-id="b0201-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="b0201-149">A Q# Visual Studio-bővítmény Q#-fájlok és -projektek sablonjait, valamint szintaxiskiemelést és IntelliSense-támogatást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b0201-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="b0201-150">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b0201-150">Pre-requisites</span></span>

    - <span data-ttu-id="b0201-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével</span><span class="sxs-lookup"><span data-stu-id="b0201-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="b0201-152">Telepítse a Q# Visual Studio-bővítményt</span><span class="sxs-lookup"><span data-stu-id="b0201-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="b0201-153">Töltse le a [Visual Studio-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="b0201-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="b0201-154">Adja a bővítményt a Visual Studióhoz</span><span class="sxs-lookup"><span data-stu-id="b0201-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="b0201-155">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="b0201-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b0201-156">Hozzon létre egy új Q#-alkalmazást</span><span class="sxs-lookup"><span data-stu-id="b0201-156">Create a new Q# application</span></span>

        - <span data-ttu-id="b0201-157">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="b0201-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="b0201-158">A keresőmezőbe írja be a következőt: `Q#`</span><span class="sxs-lookup"><span data-stu-id="b0201-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="b0201-159">Válassza a **Q#-alkalmazás** elemet</span><span class="sxs-lookup"><span data-stu-id="b0201-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="b0201-160">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="b0201-160">Select **Next**</span></span>
        - <span data-ttu-id="b0201-161">Válassza ki az alkalmazás nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="b0201-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="b0201-162">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="b0201-162">Select **Create**</span></span>

    - <span data-ttu-id="b0201-163">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="b0201-163">Inspect the project</span></span>

        <span data-ttu-id="b0201-164">Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="b0201-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="b0201-165">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="b0201-165">Run the application</span></span>

        - <span data-ttu-id="b0201-166">Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="b0201-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b0201-167">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="b0201-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="b0201-168">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b0201-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="b0201-169">Fejlesztés C# nyelven a Visual Studio Code használatával</span><span class="sxs-lookup"><span data-stu-id="b0201-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="b0201-170">A Visual Studio Code (VS Code) gazdag környezetet nyújt a Q#-programok fejlesztéséhez számos különféle számítógépes környezethez, beleértve a Windows, Linux és Mac rendszereket, és nagyszerű funkciókat tartalmaz, például kódkiegészítést és szintaxiskiemelést, amelyek végigvezetik a fejlesztőt az alkalmazások összeállításán.</span><span class="sxs-lookup"><span data-stu-id="b0201-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="b0201-171">A Q# VS Code-bővítmény szintaxiskiemelést és Q#-kódrészleteket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b0201-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="b0201-172">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b0201-172">Pre-requisites</span></span>

   - [<span data-ttu-id="b0201-173">VS Code</span><span class="sxs-lookup"><span data-stu-id="b0201-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="b0201-174">.NET Core SDK 3.0 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="b0201-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b0201-175">Telepítse a Quantum VS Code-bővítményt</span><span class="sxs-lookup"><span data-stu-id="b0201-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="b0201-176">Telepítse a [VS Code-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="b0201-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="b0201-177">Telepítse a Quantum-projektsablonokat:</span><span class="sxs-lookup"><span data-stu-id="b0201-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="b0201-178">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="b0201-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="b0201-179">Válassza a **Q#: Projektsablonok telepítése** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="b0201-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="b0201-180">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="b0201-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b0201-181">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="b0201-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b0201-182">Hozzon létre egy új projektet:</span><span class="sxs-lookup"><span data-stu-id="b0201-182">Create a new project:</span></span>

        - <span data-ttu-id="b0201-183">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="b0201-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="b0201-184">Válassza a **Q#: Új projekt létrehozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="b0201-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="b0201-185">Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást</span><span class="sxs-lookup"><span data-stu-id="b0201-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="b0201-186">A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra</span><span class="sxs-lookup"><span data-stu-id="b0201-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="b0201-187">Futtassa az alkalmazást:</span><span class="sxs-lookup"><span data-stu-id="b0201-187">Run the application:</span></span>

        - <span data-ttu-id="b0201-188">Lépjen a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="b0201-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b0201-189">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b0201-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="b0201-190">A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="b0201-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="b0201-191">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b0201-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="b0201-192">Fejlesztés a C# és a(z) `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="b0201-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="b0201-193">Természetesen a parancssorból is egyszerűen összeállíthat és futtathat Q#-programokat, ha telepíti a .NET Core SDK-t és a QDK-projektsablonokat.</span><span class="sxs-lookup"><span data-stu-id="b0201-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="b0201-194">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b0201-194">Pre-requisites</span></span>

    - [<span data-ttu-id="b0201-195">.NET Core SDK 3.0 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="b0201-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b0201-196">Telepítse a .NET-hez tartozó Quantum-projektsablonokat</span><span class="sxs-lookup"><span data-stu-id="b0201-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="b0201-197">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="b0201-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b0201-198">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="b0201-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b0201-199">Új alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="b0201-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="b0201-200">Lépjen az új alkalmazás könyvtárához</span><span class="sxs-lookup"><span data-stu-id="b0201-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="b0201-201">Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="b0201-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="b0201-202">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="b0201-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="b0201-203">A következő kimenetnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b0201-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="b0201-204">A következő lépések</span><span class="sxs-lookup"><span data-stu-id="b0201-204">What's next?</span></span>

<span data-ttu-id="b0201-205">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="b0201-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
