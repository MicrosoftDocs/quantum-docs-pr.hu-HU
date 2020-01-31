---
title: 'Megtudhatja, hogyan hozhat létre Q # projektet a Quantum Development Kit (QDK) használatával'
description: 'A QDK és a Q # értékkel rendelkező projekt inicializálásával kiválaszthatja az Ön által választott fejlesztési környezetet'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 5fa32f14291fa2070b49e4bb3b720cbf31ee614b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819892"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="7b021-103">Q # projekt létrehozása a fejlesztői környezetben</span><span class="sxs-lookup"><span data-stu-id="7b021-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="7b021-104">Megtudhatja, hogyan hozhat létre Q # projektet a QDK.</span><span class="sxs-lookup"><span data-stu-id="7b021-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="7b021-105">A Q # projekt a kvantum-kódot tartalmazó Q # fájlokat, valamint a Quantum program futtatására szolgáló gazda programot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="7b021-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="7b021-106">A gazda programot .NET-nyelveken C#, például a (z) vagy a Pythonban is megírhatja.</span><span class="sxs-lookup"><span data-stu-id="7b021-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="7b021-107">A Q # kódot egy Jupyter-jegyzetfüzetben is futtathatja az IQ # kernel használatával.</span><span class="sxs-lookup"><span data-stu-id="7b021-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="7b021-108">Válassza ki a fejlesztési környezetét és nyelvét az alábbi fejezetekben:</span><span class="sxs-lookup"><span data-stu-id="7b021-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="7b021-109">Python</span><span class="sxs-lookup"><span data-stu-id="7b021-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="7b021-110">Q # Jupyter notebookok</span><span class="sxs-lookup"><span data-stu-id="7b021-110">Q# Jupyter notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="7b021-111">C#a Visual Studióval</span><span class="sxs-lookup"><span data-stu-id="7b021-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="7b021-112">C#VS Code-val</span><span class="sxs-lookup"><span data-stu-id="7b021-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="7b021-113">C#a parancssorral</span><span class="sxs-lookup"><span data-stu-id="7b021-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="7b021-114">Python-projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="7b021-114">Create a Python project</span></span>

1. <span data-ttu-id="7b021-115">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7b021-115">Pre-requisites</span></span>

     * <span data-ttu-id="7b021-116">A [Pythonhoz készült Quantum Development Kit](xref:microsoft.quantum.install.python) telepítése</span><span class="sxs-lookup"><span data-stu-id="7b021-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="7b021-117">Hozzon létre egy mappát a projekt számára, és navigáljon a mappára</span><span class="sxs-lookup"><span data-stu-id="7b021-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="7b021-118">Hozzon létre egy `Operation.qs`nevű Q # fájlt, és adja hozzá a Q # kódját.</span><span class="sxs-lookup"><span data-stu-id="7b021-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="7b021-119">Példa:</span><span class="sxs-lookup"><span data-stu-id="7b021-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="7b021-120">Hozzon létre egy `host.py` nevű Python-gazdagépet a Q # művelet meghívásához.</span><span class="sxs-lookup"><span data-stu-id="7b021-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="7b021-121">Példa:</span><span class="sxs-lookup"><span data-stu-id="7b021-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="7b021-122">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="7b021-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="7b021-123">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="7b021-123">Verify the output.</span></span> <span data-ttu-id="7b021-124">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="7b021-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="7b021-125">Most már folytathatja a kvantum-program fejlesztését.</span><span class="sxs-lookup"><span data-stu-id="7b021-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="7b021-126">Q # Jupyter Notebook projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="7b021-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="7b021-127">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7b021-127">Pre-requisites</span></span>

    * <span data-ttu-id="7b021-128">A [Quantum Development Kit telepítése Jupyter notebookokhoz](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="7b021-128">Install the [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="7b021-129">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="7b021-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="7b021-130">Lépjen a parancssorban megjelenített URL-címre.</span><span class="sxs-lookup"><span data-stu-id="7b021-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="7b021-131">Például: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="7b021-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="7b021-132">Megjelenik egy Jupyter lap a böngészőben.</span><span class="sxs-lookup"><span data-stu-id="7b021-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="7b021-133">A **Files (fájlok** ) lapon válassza az **új** > **q #** lehetőséget, hogy Jupyter-jegyzetfüzetet hozzon létre a q # kernel használatával.</span><span class="sxs-lookup"><span data-stu-id="7b021-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="7b021-134">Adja hozzá a következő kódot az első jegyzetfüzet-cellához:</span><span class="sxs-lookup"><span data-stu-id="7b021-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="7b021-135">Válassza a **cella** > a **cellák futtatása** lehetőséget a jegyzetfüzet futtatásához.</span><span class="sxs-lookup"><span data-stu-id="7b021-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="7b021-136">`SayHello` hamarosan megjelennek a cella kimenetében:</span><span class="sxs-lookup"><span data-stu-id="7b021-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter-notebookcella Q#-kóddal](~/media/install-guide-jupyter.png)

    <span data-ttu-id="7b021-138">Jupyter-jegyzetfüzetekben való futtatáskor a Q # kód le van fordítva, és a jegyzetfüzet a megtalált művelet (ek) nevét adja meg.</span><span class="sxs-lookup"><span data-stu-id="7b021-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="7b021-139">Egy új cellában szimulálja a most létrehozott `%simulate`-művelet végrehajtását egy kvantumszámítógépen:</span><span class="sxs-lookup"><span data-stu-id="7b021-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter-notebookcella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="7b021-141">A képernyőn megjelenik az üzenet a meghívott művelet eredményével együtt (ebben az esetben üresen).</span><span class="sxs-lookup"><span data-stu-id="7b021-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="7b021-142">Mostantól további Q #-műveleteket is hozzáadhat a kvantum-fejlesztés folytatásához.</span><span class="sxs-lookup"><span data-stu-id="7b021-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="7b021-143">C# Projekt létrehozása Windows rendszeren a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="7b021-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="7b021-144">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7b021-144">Pre-requisites</span></span>

    * <span data-ttu-id="7b021-145">A [Quantum Development Kit bővítmény telepítése a Visual studióhoz](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="7b021-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="7b021-146">Hozzon létre egy új Q#-alkalmazást</span><span class="sxs-lookup"><span data-stu-id="7b021-146">Create a new Q# application</span></span>

    * <span data-ttu-id="7b021-147">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="7b021-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="7b021-148">A keresőmezőbe írja be a következőt: `Q#`</span><span class="sxs-lookup"><span data-stu-id="7b021-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="7b021-149">Válassza a **Q#-alkalmazás** elemet</span><span class="sxs-lookup"><span data-stu-id="7b021-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="7b021-150">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="7b021-150">Select **Next**</span></span>
    * <span data-ttu-id="7b021-151">Válassza ki az alkalmazás nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="7b021-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="7b021-152">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="7b021-152">Select **Create**</span></span>

1. <span data-ttu-id="7b021-153">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="7b021-153">Inspect the project</span></span>

    <span data-ttu-id="7b021-154">Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="7b021-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="7b021-155">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="7b021-155">Run the application</span></span>

    * <span data-ttu-id="7b021-156">Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="7b021-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="7b021-157">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="7b021-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="7b021-158">Most már folytathatja a kvantum-fejlesztést a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="7b021-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="7b021-159">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7b021-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="7b021-160">Projekt létrehozása C# a vs Code használatával</span><span class="sxs-lookup"><span data-stu-id="7b021-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="7b021-161">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7b021-161">Pre-requisites</span></span>

    * <span data-ttu-id="7b021-162">A [Quantum Development Kit bővítmény telepítése a vs Code](xref:microsoft.quantum.install.cs) -hoz</span><span class="sxs-lookup"><span data-stu-id="7b021-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="7b021-163">Hozzon létre egy új projektet:</span><span class="sxs-lookup"><span data-stu-id="7b021-163">Create a new project:</span></span>

    * <span data-ttu-id="7b021-164">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="7b021-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="7b021-165">Válassza a **Q #: új projekt létrehozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="7b021-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="7b021-166">**Önálló konzolos alkalmazás** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="7b021-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="7b021-167">Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást</span><span class="sxs-lookup"><span data-stu-id="7b021-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="7b021-168">A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra</span><span class="sxs-lookup"><span data-stu-id="7b021-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="7b021-169">Futtassa az alkalmazást:</span><span class="sxs-lookup"><span data-stu-id="7b021-169">Run the application:</span></span>

    * <span data-ttu-id="7b021-170">Ugrás a **terminal** -> **új terminálra**</span><span class="sxs-lookup"><span data-stu-id="7b021-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="7b021-171">Adja meg `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="7b021-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="7b021-172">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="7b021-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="7b021-173">Most már folytathatja a kvantum-fejlesztést a Visual Studio Code használatával.</span><span class="sxs-lookup"><span data-stu-id="7b021-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="7b021-174">A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="7b021-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="7b021-175">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7b021-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7b021-176">C# Projekt létrehozása a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="7b021-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7b021-177">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7b021-177">Pre-requisites</span></span>

    * <span data-ttu-id="7b021-178">A [Quantum Development Kit telepítése a parancssorba](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="7b021-178">Install the [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="7b021-179">Új alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="7b021-179">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="7b021-180">Lépjen az új alkalmazás könyvtárához</span><span class="sxs-lookup"><span data-stu-id="7b021-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="7b021-181">Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="7b021-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="7b021-182">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="7b021-182">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="7b021-183">A következő kimenetnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="7b021-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="7b021-184">Most folytassa a kvantum-fejlesztést a parancssori eszközök használatával.</span><span class="sxs-lookup"><span data-stu-id="7b021-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="7b021-185">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="7b021-185">What's next?</span></span>

<span data-ttu-id="7b021-186">Most, hogy létrehozott egy projektet az előnyben részesített környezetben, folytathatja a kvantum-fejlesztést.</span><span class="sxs-lookup"><span data-stu-id="7b021-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
