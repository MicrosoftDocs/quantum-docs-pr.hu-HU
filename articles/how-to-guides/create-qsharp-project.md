---
title: 'Megtudhatja, hogyan hozhat létre Q # projektet a Quantum Development Kit (QDK) használatával'
description: 'A QDK és a Q # értékkel rendelkező projekt inicializálásával kiválaszthatja az Ön által választott fejlesztési környezetet'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444174"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="8c437-103">Q # projekt létrehozása a fejlesztői környezetben</span><span class="sxs-lookup"><span data-stu-id="8c437-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="8c437-104">Megtudhatja, hogyan hozhat létre Q # projektet a QDK.</span><span class="sxs-lookup"><span data-stu-id="8c437-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="8c437-105">A Q # projekt a kvantum-kódot tartalmazó Q # fájlokat, valamint a Quantum program futtatására szolgáló gazda programot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="8c437-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="8c437-106">A gazda programot .NET-nyelveken C#, például a (z) vagy a Pythonban is megírhatja.</span><span class="sxs-lookup"><span data-stu-id="8c437-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="8c437-107">A Q # kódot egy Jupyter-jegyzetfüzetben is futtathatja az IQ # kernel használatával.</span><span class="sxs-lookup"><span data-stu-id="8c437-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="8c437-108">Válassza ki a fejlesztési környezetét és nyelvét az alábbi fejezetekben:</span><span class="sxs-lookup"><span data-stu-id="8c437-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="8c437-109">Python</span><span class="sxs-lookup"><span data-stu-id="8c437-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="8c437-110">Jupyter notebookok</span><span class="sxs-lookup"><span data-stu-id="8c437-110">Jupyter notebooks</span></span>](#create-a-jupyter-notebook-project)
* [<span data-ttu-id="8c437-111">C#a Visual Studióval</span><span class="sxs-lookup"><span data-stu-id="8c437-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="8c437-112">C#VS Code-val</span><span class="sxs-lookup"><span data-stu-id="8c437-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="8c437-113">C#a parancssorral</span><span class="sxs-lookup"><span data-stu-id="8c437-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="8c437-114">Python-projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c437-114">Create a Python project</span></span>

1. <span data-ttu-id="8c437-115">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8c437-115">Pre-requisites</span></span>

     * <span data-ttu-id="8c437-116">A [Pythonhoz készült Quantum Development Kit](xref:microsoft.quantum.install#develop-with-python)</span><span class="sxs-lookup"><span data-stu-id="8c437-116">The [Quantum Development Kit for Python](xref:microsoft.quantum.install#develop-with-python)</span></span>

1. <span data-ttu-id="8c437-117">Hozzon létre egy mappát a projekt számára, és navigáljon a mappára</span><span class="sxs-lookup"><span data-stu-id="8c437-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="8c437-118">Hozzon létre egy `Operation.qs`nevű Q # fájlt, és adja hozzá a Q # kódját.</span><span class="sxs-lookup"><span data-stu-id="8c437-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="8c437-119">Példa:</span><span class="sxs-lookup"><span data-stu-id="8c437-119">For example:</span></span>

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

1. <span data-ttu-id="8c437-120">Hozzon létre egy `host.py` nevű Python-gazdagépet a Q # művelet meghívásához.</span><span class="sxs-lookup"><span data-stu-id="8c437-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="8c437-121">Példa:</span><span class="sxs-lookup"><span data-stu-id="8c437-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="8c437-122">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="8c437-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="8c437-123">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="8c437-123">Verify the output.</span></span> <span data-ttu-id="8c437-124">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="8c437-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="8c437-125">Most már folytathatja a kvantum-program fejlesztését.</span><span class="sxs-lookup"><span data-stu-id="8c437-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-jupyter-notebook-project"></a><span data-ttu-id="8c437-126">Jupyter Notebook projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c437-126">Create a Jupyter Notebook project</span></span>

1. <span data-ttu-id="8c437-127">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8c437-127">Pre-requisites</span></span>

    * <span data-ttu-id="8c437-128">A [Jupyter notebookokhoz készült Quantum Development Kit](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span><span class="sxs-lookup"><span data-stu-id="8c437-128">The [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span></span>

1. <span data-ttu-id="8c437-129">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="8c437-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="8c437-130">Lépjen a parancssorban megjelenített URL-címre.</span><span class="sxs-lookup"><span data-stu-id="8c437-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="8c437-131">Például: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="8c437-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="8c437-132">Megjelenik egy Jupyter lap a böngészőben.</span><span class="sxs-lookup"><span data-stu-id="8c437-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="8c437-133">A **Files (fájlok** ) lapon válassza az **új** > **q #** lehetőséget, hogy Jupyter-jegyzetfüzetet hozzon létre a q # kernel használatával.</span><span class="sxs-lookup"><span data-stu-id="8c437-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="8c437-134">Adja hozzá a következő kódot az első jegyzetfüzet-cellához:</span><span class="sxs-lookup"><span data-stu-id="8c437-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="8c437-135">Válassza a **cella** > a **cellák futtatása** lehetőséget a jegyzetfüzet futtatásához.</span><span class="sxs-lookup"><span data-stu-id="8c437-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="8c437-136">`SayHello` hamarosan megjelennek a cella kimenetében:</span><span class="sxs-lookup"><span data-stu-id="8c437-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter notebook-cella Q # kóddal](~/media/install-guide-jupyter.png)

    <span data-ttu-id="8c437-138">Jupyter-jegyzetfüzetekben való futtatáskor a Q # kód le van fordítva, és a jegyzetfüzet a megtalált művelet (ek) nevét adja meg.</span><span class="sxs-lookup"><span data-stu-id="8c437-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="8c437-139">Egy új cellában szimulálja a végrehajtást az imént létrehozott művelet kvantum-számítógépén a `%simulate` Magic használatával:</span><span class="sxs-lookup"><span data-stu-id="8c437-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter notebook-cella%-os szimulálása varázslattal](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="8c437-141">Ekkor meg kell jelennie a képernyőn kinyomtatott üzenetnek a meghívott művelet eredményével együtt (ebben az esetben üres).</span><span class="sxs-lookup"><span data-stu-id="8c437-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="8c437-142">Mostantól további Q #-műveleteket is hozzáadhat a kvantum-fejlesztés folytatásához.</span><span class="sxs-lookup"><span data-stu-id="8c437-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="8c437-143">C# Projekt létrehozása Windows rendszeren a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="8c437-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="8c437-144">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8c437-144">Pre-requisites</span></span>

    * <span data-ttu-id="8c437-145">A [Visual studióhoz készült Quantum Development Kit](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="8c437-145">The [Quantum Development Kit for Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span></span>

1. <span data-ttu-id="8c437-146">Hozzon létre egy új Q#-alkalmazást</span><span class="sxs-lookup"><span data-stu-id="8c437-146">Create a new Q# application</span></span>

    * <span data-ttu-id="8c437-147">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="8c437-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="8c437-148">A keresőmezőbe írja be a következőt: `Q#`</span><span class="sxs-lookup"><span data-stu-id="8c437-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="8c437-149">Válassza a **Q#-alkalmazás** elemet</span><span class="sxs-lookup"><span data-stu-id="8c437-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="8c437-150">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="8c437-150">Select **Next**</span></span>
    * <span data-ttu-id="8c437-151">Válassza ki az alkalmazás nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="8c437-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="8c437-152">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="8c437-152">Select **Create**</span></span>

1. <span data-ttu-id="8c437-153">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="8c437-153">Inspect the project</span></span>

    <span data-ttu-id="8c437-154">Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.</span><span class="sxs-lookup"><span data-stu-id="8c437-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="8c437-155">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="8c437-155">Run the application</span></span>

    * <span data-ttu-id="8c437-156">Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="8c437-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="8c437-157">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="8c437-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="8c437-158">Most már folytathatja a kvantum-fejlesztést a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="8c437-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="8c437-159">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8c437-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="8c437-160">Projekt létrehozása C# a vs Code használatával</span><span class="sxs-lookup"><span data-stu-id="8c437-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="8c437-161">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8c437-161">Pre-requisites</span></span>

    * <span data-ttu-id="8c437-162">A [vs Code-hoz készült Quantum Development Kit](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span><span class="sxs-lookup"><span data-stu-id="8c437-162">The [Quantum Development Kit for VS Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span></span>

1. <span data-ttu-id="8c437-163">Hozzon létre egy új projektet:</span><span class="sxs-lookup"><span data-stu-id="8c437-163">Create a new project:</span></span>

    * <span data-ttu-id="8c437-164">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="8c437-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="8c437-165">Válassza a **Q #: új projekt létrehozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="8c437-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="8c437-166">Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást</span><span class="sxs-lookup"><span data-stu-id="8c437-166">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="8c437-167">A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra</span><span class="sxs-lookup"><span data-stu-id="8c437-167">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="8c437-168">Futtassa az alkalmazást:</span><span class="sxs-lookup"><span data-stu-id="8c437-168">Run the application:</span></span>

    * <span data-ttu-id="8c437-169">Lépjen a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="8c437-169">Go to **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="8c437-170">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8c437-170">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="8c437-171">Most már folytathatja a kvantum-fejlesztést a Visual Studio Code használatával.</span><span class="sxs-lookup"><span data-stu-id="8c437-171">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="8c437-172">A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="8c437-172">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="8c437-173">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8c437-173">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="8c437-174">C# Projekt létrehozása a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="8c437-174">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="8c437-175">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8c437-175">Pre-requisites</span></span>

    * <span data-ttu-id="8c437-176">A [parancssorhoz tartozó Quantum Development Kit](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span><span class="sxs-lookup"><span data-stu-id="8c437-176">The [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span></span>

1. <span data-ttu-id="8c437-177">Új alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c437-177">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="8c437-178">Lépjen az új alkalmazás könyvtárához</span><span class="sxs-lookup"><span data-stu-id="8c437-178">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="8c437-179">Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="8c437-179">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="8c437-180">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="8c437-180">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="8c437-181">A következő kimenetnek kell megjelennie: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8c437-181">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="8c437-182">Most folytassa a kvantum-fejlesztést a parancssori eszközök használatával.</span><span class="sxs-lookup"><span data-stu-id="8c437-182">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="8c437-183">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="8c437-183">What's next?</span></span>

<span data-ttu-id="8c437-184">Most, hogy létrehozott egy projektet az előnyben részesített környezetben, folytathatja a kvantum-fejlesztést.</span><span class="sxs-lookup"><span data-stu-id="8c437-184">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
