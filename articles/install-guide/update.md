---
title: Ismerje meg, hogyan frissítheti a Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036310"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a642a-102">A Microsoft Quantum Development Kit frissítése (QDK)</span><span class="sxs-lookup"><span data-stu-id="a642a-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a642a-103">Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="a642a-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="a642a-104">Ez a cikk azt feltételezi, hogy már telepítette a QDK.</span><span class="sxs-lookup"><span data-stu-id="a642a-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="a642a-105">Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="a642a-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="a642a-106">Javasoljuk, hogy naprakészen tartson a legújabb QDK-kiadással.</span><span class="sxs-lookup"><span data-stu-id="a642a-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="a642a-107">Ezt a frissítési útmutatót követve frissíthet a legújabb QDK-verzióra.</span><span class="sxs-lookup"><span data-stu-id="a642a-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="a642a-108">A folyamat két részből áll:</span><span class="sxs-lookup"><span data-stu-id="a642a-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="a642a-109">meglévő Q # fájlok és projektek frissítése a kód a frissített szintaxissal való igazításához</span><span class="sxs-lookup"><span data-stu-id="a642a-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="a642a-110">saját maga frissítése a választott fejlesztési környezet QDK</span><span class="sxs-lookup"><span data-stu-id="a642a-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="a642a-111">Q # projektek frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-111">Updating Q# Projects</span></span> 

<span data-ttu-id="a642a-112">Függetlenül attól, hogy a (z C# ) vagy a Python használatával üzemelteti a q # műveleteit, kövesse ezeket az utasításokat a q # projektjeinek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a642a-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="a642a-113">Először is győződjön meg arról, hogy rendelkezik a [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)legújabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="a642a-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="a642a-114">Futtassa a következő parancsot a parancssorban:</span><span class="sxs-lookup"><span data-stu-id="a642a-114">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="a642a-115">Ellenőrizze, hogy a kimenet `3.1.100` vagy magasabb-e.</span><span class="sxs-lookup"><span data-stu-id="a642a-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="a642a-116">Ha nem, telepítse a [legújabb verziót](https://dotnet.microsoft.com/download) , és ellenőrizze újra.</span><span class="sxs-lookup"><span data-stu-id="a642a-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="a642a-117">Ezután kövesse az alábbi utasításokat a beállítástól függően (Visual Studio, Visual Studio Code vagy közvetlenül a parancssorból).</span><span class="sxs-lookup"><span data-stu-id="a642a-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="a642a-118">Q # projektek frissítése a Visual Studióban</span><span class="sxs-lookup"><span data-stu-id="a642a-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="a642a-119">A Visual Studio 2019 legújabb verziójának frissítése [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="a642a-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="a642a-120">A megoldás megnyitása a Visual Studióban</span><span class="sxs-lookup"><span data-stu-id="a642a-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="a642a-121">A menüben válassza a **Build** -> **tiszta megoldás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a642a-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="a642a-122">A. csproj-fájlok mindegyikében frissítse a célként megadott keretrendszert, hogy `netcoreapp3.0` (vagy `netstandard2.1`, ha a könyvtári projekt).</span><span class="sxs-lookup"><span data-stu-id="a642a-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="a642a-123">Az űrlap sorainak szerkesztése:</span><span class="sxs-lookup"><span data-stu-id="a642a-123">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="a642a-124">A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.</span><span class="sxs-lookup"><span data-stu-id="a642a-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="a642a-125">A megoldásban lévő összes fájl mentése és lezárása</span><span class="sxs-lookup"><span data-stu-id="a642a-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="a642a-126">Válassza az **eszközök** -> **parancssori** -> **fejlesztői parancssor** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a642a-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="a642a-127">A megoldás minden egyes projektje esetében futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="a642a-127">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="a642a-128">Ha a projektek más Microsoft. Quantum csomagokat használnak (például Microsoft. Quantum. Numerikusok), futtassa a parancsot ezekre is.</span><span class="sxs-lookup"><span data-stu-id="a642a-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="a642a-129">A parancssor bezárásához és a **build** -> **Build megoldás** *kiválasztásához (ne válassza az* Újraépítés megoldás lehetőséget)</span><span class="sxs-lookup"><span data-stu-id="a642a-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="a642a-130">Most már kihagyhatja a [Visual Studio QDK bővítmény frissítését](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="a642a-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="a642a-131">Q # projektek frissítése a Visual Studio Code-ban</span><span class="sxs-lookup"><span data-stu-id="a642a-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="a642a-132">A Visual Studio Code-ban nyissa meg a frissíteni kívánt projektet tartalmazó mappát.</span><span class="sxs-lookup"><span data-stu-id="a642a-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="a642a-133">Válassza ki a **terminal** -> **új terminált**</span><span class="sxs-lookup"><span data-stu-id="a642a-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="a642a-134">Kövesse a parancssor használatával történő frissítéshez szükséges utasításokat (közvetlenül alább)</span><span class="sxs-lookup"><span data-stu-id="a642a-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="a642a-135">Q # projektek frissítése a parancssor használatával</span><span class="sxs-lookup"><span data-stu-id="a642a-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="a642a-136">Navigáljon a projektfájlt tartalmazó mappára.</span><span class="sxs-lookup"><span data-stu-id="a642a-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="a642a-137">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="a642a-137">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="a642a-138">A. csproj-fájlok mindegyikében frissítse a célként megadott keretrendszert, hogy `netcoreapp3.0` (vagy `netstandard2.1`, ha a könyvtári projekt).</span><span class="sxs-lookup"><span data-stu-id="a642a-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="a642a-139">Az űrlap sorainak szerkesztése:</span><span class="sxs-lookup"><span data-stu-id="a642a-139">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="a642a-140">A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.</span><span class="sxs-lookup"><span data-stu-id="a642a-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="a642a-141">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="a642a-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="a642a-142">Ha a projekt más Microsoft. Quantum csomagokat (például Microsoft. Quantum. numerikus értékeket) használ, futtassa a parancsot ezekre is.</span><span class="sxs-lookup"><span data-stu-id="a642a-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="a642a-143">Mentse és zárjunk be minden fájlt.</span><span class="sxs-lookup"><span data-stu-id="a642a-143">Save and close all files.</span></span>
6. <span data-ttu-id="a642a-144">Ismételje meg a 1-4-et minden egyes projekt-függőség esetében, majd térjen vissza a fő projektet tartalmazó mappára, és futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="a642a-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="a642a-145">Ha már frissítette a Q #-projektjeit, kövesse az alábbi utasításokat a QDK frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a642a-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="a642a-146">A QDK frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-146">Updating the QDK</span></span>

<span data-ttu-id="a642a-147">A QDK frissítésének folyamata a fejlesztési nyelvtől és környezettől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="a642a-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="a642a-148">Válassza ki az alábbi fejlesztési környezetet.</span><span class="sxs-lookup"><span data-stu-id="a642a-148">Select your development environment below.</span></span>

* [<span data-ttu-id="a642a-149">Python: az IQ # bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="a642a-150">Jupyter jegyzetfüzetek: az IQ # bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="a642a-151">Visual Studio: a QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="a642a-152">VS code: a QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="a642a-153">Parancssor és C#: Project-sablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="a642a-154">A Pythonhoz készült IQ # frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="a642a-155">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-155">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="a642a-156">A `iqsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="a642a-156">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a642a-157">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="a642a-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="a642a-158">Ne aggódjon, ha a `iqsharp` verziója magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="a642a-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="a642a-159">A `qsharp` csomag frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="a642a-160">A `qsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="a642a-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="a642a-161">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="a642a-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="a642a-162">Futtassa a következő parancsot a `.qs` fájlok helyéről</span><span class="sxs-lookup"><span data-stu-id="a642a-162">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="a642a-163">Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.</span><span class="sxs-lookup"><span data-stu-id="a642a-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="a642a-164">Az IQ # frissítése Jupyter-jegyzetfüzetekhez</span><span class="sxs-lookup"><span data-stu-id="a642a-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="a642a-165">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-165">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="a642a-166">A `iqsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="a642a-166">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a642a-167">A kimenetnek az alábbihoz hasonlónak kell lennie:</span><span class="sxs-lookup"><span data-stu-id="a642a-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="a642a-168">Ne aggódjon, ha a `iqsharp` verziója magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="a642a-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="a642a-169">Futtassa a következő parancsot a Jupyter Notebook egyik cellájából:</span><span class="sxs-lookup"><span data-stu-id="a642a-169">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="a642a-170">Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.</span><span class="sxs-lookup"><span data-stu-id="a642a-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="a642a-171">A Visual Studio QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="a642a-172">A Q # Visual Studio bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="a642a-173">A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit</span><span class="sxs-lookup"><span data-stu-id="a642a-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="a642a-174">A frissítés elfogadása</span><span class="sxs-lookup"><span data-stu-id="a642a-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="a642a-175">A Project-sablonokat a bővítménnyel együtt frissíti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a642a-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="a642a-176">A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="a642a-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="a642a-177">A meglévő projektek kódja nem frissül a bővítmény frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="a642a-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="a642a-178">A VS Code QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="a642a-179">A Quantum VS Code bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="a642a-180">Újraindítás VS Code</span><span class="sxs-lookup"><span data-stu-id="a642a-180">Restart VS Code</span></span>
    - <span data-ttu-id="a642a-181">Navigáljon a **kiterjesztések** lapra</span><span class="sxs-lookup"><span data-stu-id="a642a-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="a642a-182">Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="a642a-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="a642a-183">A bővítmény újratöltése</span><span class="sxs-lookup"><span data-stu-id="a642a-183">Reload the extension</span></span>

2. <span data-ttu-id="a642a-184">A Quantum Project-sablonok frissítése:</span><span class="sxs-lookup"><span data-stu-id="a642a-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="a642a-185">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="a642a-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="a642a-186">Válassza a **Q #: Project-sablonok telepítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a642a-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="a642a-187">Néhány másodperc elteltével be kell szereznie egy felugró ablakban, hogy a "Project templates telepítése sikeresen megtörtént"</span><span class="sxs-lookup"><span data-stu-id="a642a-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="a642a-188">C#, a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="a642a-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="a642a-189">A .NET-hez készült Quantum Project-sablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="a642a-189">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="a642a-190">A következő lépések</span><span class="sxs-lookup"><span data-stu-id="a642a-190">What's next?</span></span>

<span data-ttu-id="a642a-191">Most, hogy frissítette a Quantum Development Kit-t az előnyben részesített környezetben, továbbra is fejlesztheti és futtathatja a kvantum-programokat.</span><span class="sxs-lookup"><span data-stu-id="a642a-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="a642a-192">Ha még nem írt programot, megkezdheti [az első kvantum-program](xref:microsoft.quantum.write-program)megkezdését.</span><span class="sxs-lookup"><span data-stu-id="a642a-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
