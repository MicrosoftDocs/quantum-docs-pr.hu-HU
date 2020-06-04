---
title: A Quantum Development Kit (QDK) frissítése
description: 'Ismerteti, hogyan lehet frissíteni a Q #-projekteket és a Microsoft Quantum Development Kitt a jelenlegi verzióra.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327568"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="18ec5-103">A Microsoft Quantum Development Kit frissítése (QDK)</span><span class="sxs-lookup"><span data-stu-id="18ec5-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="18ec5-104">Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="18ec5-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="18ec5-105">Ez a cikk azt feltételezi, hogy már telepítette a QDK.</span><span class="sxs-lookup"><span data-stu-id="18ec5-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="18ec5-106">Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="18ec5-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="18ec5-107">Javasoljuk, hogy naprakészen tartson a legújabb QDK-kiadással.</span><span class="sxs-lookup"><span data-stu-id="18ec5-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="18ec5-108">Ezt a frissítési útmutatót követve frissíthet a legújabb QDK-verzióra.</span><span class="sxs-lookup"><span data-stu-id="18ec5-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="18ec5-109">A folyamat két részből áll:</span><span class="sxs-lookup"><span data-stu-id="18ec5-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="18ec5-110">Meglévő Q # fájlok és projektek frissítése a kód a frissített szintaxissal való igazításához.</span><span class="sxs-lookup"><span data-stu-id="18ec5-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="18ec5-111">A kiválasztott fejlesztési környezethez tartozó QDK frissítése.</span><span class="sxs-lookup"><span data-stu-id="18ec5-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="18ec5-112">Q # projektek frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-112">Updating Q# Projects</span></span> 

<span data-ttu-id="18ec5-113">Függetlenül attól, hogy C# vagy Python használatával üzemelteti a Q # műveleteit, kövesse ezeket az utasításokat a Q # projektjeinek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="18ec5-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="18ec5-114">Először is győződjön meg arról, hogy rendelkezik a [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)legújabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="18ec5-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="18ec5-115">Futtassa a következő parancsot a parancssorban:</span><span class="sxs-lookup"><span data-stu-id="18ec5-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="18ec5-116">Ellenőrizze a kimenetet `3.1.100` vagy a magasabbat.</span><span class="sxs-lookup"><span data-stu-id="18ec5-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="18ec5-117">Ha nem, telepítse a [legújabb verziót](https://dotnet.microsoft.com/download) , és ellenőrizze újra.</span><span class="sxs-lookup"><span data-stu-id="18ec5-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="18ec5-118">Ezután kövesse az alábbi utasításokat a beállítástól függően (Visual Studio, Visual Studio Code vagy közvetlenül a parancssorból).</span><span class="sxs-lookup"><span data-stu-id="18ec5-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="18ec5-119">Q # projektek frissítése a Visual Studióban</span><span class="sxs-lookup"><span data-stu-id="18ec5-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="18ec5-120">Frissítsen a Visual Studio 2019 legújabb verziójára, [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="18ec5-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="18ec5-121">Nyissa meg a megoldást a Visual Studióban.</span><span class="sxs-lookup"><span data-stu-id="18ec5-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="18ec5-122">Válassza a menü **Build**  ->  **tiszta megoldás**létrehozása elemét.</span><span class="sxs-lookup"><span data-stu-id="18ec5-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="18ec5-123">Az egyes. csproj-fájlokban frissítse a célként megadott keretrendszert `netcoreapp3.1` (vagy `netstandard2.1` Ha ez egy függvénytár-projekt).</span><span class="sxs-lookup"><span data-stu-id="18ec5-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="18ec5-124">Az űrlap sorainak szerkesztése:</span><span class="sxs-lookup"><span data-stu-id="18ec5-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="18ec5-125">A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.</span><span class="sxs-lookup"><span data-stu-id="18ec5-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="18ec5-126">Az összes. csproj fájlban állítsa be az SDK-t az `Microsoft.Quantum.Sdk` alábbi sorban látható módon.</span><span class="sxs-lookup"><span data-stu-id="18ec5-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="18ec5-127">Figyelje meg, hogy a verziószámnak a legújabb elérhetőnek kell lennie, és megtekintheti a [kibocsátási megjegyzések](https://docs.microsoft.com/quantum/relnotes/)áttekintésével.</span><span class="sxs-lookup"><span data-stu-id="18ec5-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="18ec5-128">Mentse és zárjunk be minden fájlt a megoldásban.</span><span class="sxs-lookup"><span data-stu-id="18ec5-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="18ec5-129">Válassza az **eszközök**  ->  **parancssori**  ->  **fejlesztői parancssor**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18ec5-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="18ec5-130">Másik lehetőségként használhatja a csomagkezelő konzolt a Visual Studióban is.</span><span class="sxs-lookup"><span data-stu-id="18ec5-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="18ec5-131">A megoldás minden egyes projektje esetében futtassa a következő parancsot a csomag **eltávolításához** :</span><span class="sxs-lookup"><span data-stu-id="18ec5-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="18ec5-132">Ha a projektek más Microsoft. Quantum vagy Microsoft. Azure. Quantum csomagokat használnak (pl. microsoft. Quantum. Numerikusok), futtassa az **Add** parancsot a következőhöz a használt verzió frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="18ec5-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="18ec5-133">Zárjuk be a parancssort, és válassza a **Build**  ->  **Build Solution** ( *ne* válassza az Újraépítés megoldást) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18ec5-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="18ec5-134">Most már kihagyhatja a [Visual Studio QDK bővítmény frissítését](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="18ec5-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="18ec5-135">Q # projektek frissítése a Visual Studio Code-ban</span><span class="sxs-lookup"><span data-stu-id="18ec5-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="18ec5-136">A Visual Studio Code-ban nyissa meg a frissíteni kívánt projektet tartalmazó mappát.</span><span class="sxs-lookup"><span data-stu-id="18ec5-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="18ec5-137">Válassza a **terminál**  ->  **új terminál**elemet.</span><span class="sxs-lookup"><span data-stu-id="18ec5-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="18ec5-138">Kövesse a parancssor használatával történő frissítéshez szükséges utasításokat (közvetlenül alább).</span><span class="sxs-lookup"><span data-stu-id="18ec5-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="18ec5-139">Q # projektek frissítése a parancssor használatával</span><span class="sxs-lookup"><span data-stu-id="18ec5-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="18ec5-140">Navigáljon a fő projektfájlt tartalmazó mappához.</span><span class="sxs-lookup"><span data-stu-id="18ec5-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="18ec5-141">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="18ec5-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="18ec5-142">Határozza meg a QDK aktuális verzióját.</span><span class="sxs-lookup"><span data-stu-id="18ec5-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="18ec5-143">A megkereséséhez tekintse át a [kibocsátási megjegyzéseket](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="18ec5-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="18ec5-144">A verzió formátuma a következőhöz hasonló lesz: `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="18ec5-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="18ec5-145">Az egyes `.csproj` fájlokban végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="18ec5-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="18ec5-146">Frissítse a célként megadott keretrendszert a `netcoreapp3.1` következőre: (vagy `netstandard2.1` Ha ez egy függvénytár-projekt).</span><span class="sxs-lookup"><span data-stu-id="18ec5-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="18ec5-147">Az űrlap sorainak szerkesztése:</span><span class="sxs-lookup"><span data-stu-id="18ec5-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="18ec5-148">A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.</span><span class="sxs-lookup"><span data-stu-id="18ec5-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="18ec5-149">Cserélje le az SDK-ra mutató hivatkozást a projekt definíciójában.</span><span class="sxs-lookup"><span data-stu-id="18ec5-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="18ec5-150">Győződjön meg arról, hogy a verziószám a **3. lépésben**meghatározott értéknek felel meg.</span><span class="sxs-lookup"><span data-stu-id="18ec5-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="18ec5-151">Ha van, távolítsa el a csomagra mutató hivatkozást `Microsoft.Quantum.Development.Kit` , amely a következő bejegyzésben lesz meghatározva:</span><span class="sxs-lookup"><span data-stu-id="18ec5-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="18ec5-152">Frissítse az összes Microsoft Quantum-csomag verzióját a QDK legutóbb kiadott verziójára (a **3. lépésben**meghatározva).</span><span class="sxs-lookup"><span data-stu-id="18ec5-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="18ec5-153">A csomagok neve a következő mintákkal történik:</span><span class="sxs-lookup"><span data-stu-id="18ec5-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="18ec5-154">A csomagokra mutató hivatkozások formátuma a következő:</span><span class="sxs-lookup"><span data-stu-id="18ec5-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="18ec5-155">Mentse a módosított fájlt.</span><span class="sxs-lookup"><span data-stu-id="18ec5-155">Save the updated file.</span></span>

    - <span data-ttu-id="18ec5-156">Állítsa vissza a projekt függőségeit a következő módon:</span><span class="sxs-lookup"><span data-stu-id="18ec5-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="18ec5-157">Váltson vissza a fő projektet tartalmazó mappára, és futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="18ec5-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="18ec5-158">Ha már frissítette a Q #-projektjeit, kövesse az alábbi utasításokat a QDK frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="18ec5-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="18ec5-159">A QDK frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-159">Updating the QDK</span></span>

<span data-ttu-id="18ec5-160">A QDK frissítésének folyamata a fejlesztési nyelvtől és környezettől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="18ec5-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="18ec5-161">Válassza ki az alábbi fejlesztési környezetet.</span><span class="sxs-lookup"><span data-stu-id="18ec5-161">Select your development environment below.</span></span>

* [<span data-ttu-id="18ec5-162">Python: az IQ # bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="18ec5-163">Jupyter jegyzetfüzetek: az IQ # bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="18ec5-164">Visual Studio: a QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="18ec5-165">VS code: a QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="18ec5-166">Parancssor és C#: Project-sablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="18ec5-167">A Pythonhoz készült IQ # frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="18ec5-168">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="18ec5-169">A `iqsharp` verzió ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="18ec5-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="18ec5-170">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="18ec5-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="18ec5-171">Ne aggódjon, ha a `iqsharp` verzió magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="18ec5-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="18ec5-172">A `qsharp` csomag frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="18ec5-173">A `qsharp` verzió ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="18ec5-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="18ec5-174">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="18ec5-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="18ec5-175">Futtassa a következő parancsot a fájlok helyéről `.qs`</span><span class="sxs-lookup"><span data-stu-id="18ec5-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="18ec5-176">Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.</span><span class="sxs-lookup"><span data-stu-id="18ec5-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="18ec5-177">Az IQ # frissítése Jupyter-jegyzetfüzetekhez</span><span class="sxs-lookup"><span data-stu-id="18ec5-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="18ec5-178">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="18ec5-179">A `iqsharp` verzió ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="18ec5-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="18ec5-180">A kimenetnek az alábbihoz hasonlónak kell lennie:</span><span class="sxs-lookup"><span data-stu-id="18ec5-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="18ec5-181">Ne aggódjon, ha a `iqsharp` verzió magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="18ec5-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="18ec5-182">Futtassa a következő parancsot a Jupyter Notebook egyik cellájából:</span><span class="sxs-lookup"><span data-stu-id="18ec5-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="18ec5-183">Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.</span><span class="sxs-lookup"><span data-stu-id="18ec5-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="18ec5-184">A Visual Studio QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="18ec5-185">A Q # Visual Studio bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="18ec5-186">A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit</span><span class="sxs-lookup"><span data-stu-id="18ec5-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="18ec5-187">A frissítés elfogadása</span><span class="sxs-lookup"><span data-stu-id="18ec5-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="18ec5-188">A Project-sablonokat a bővítménnyel együtt frissíti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="18ec5-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="18ec5-189">A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="18ec5-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="18ec5-190">A meglévő projektek kódja nem frissül a bővítmény frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="18ec5-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="18ec5-191">A VS Code QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="18ec5-192">A Quantum VS Code bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="18ec5-193">Újraindítás VS Code</span><span class="sxs-lookup"><span data-stu-id="18ec5-193">Restart VS Code</span></span>
    - <span data-ttu-id="18ec5-194">Navigáljon a **kiterjesztések** lapra</span><span class="sxs-lookup"><span data-stu-id="18ec5-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="18ec5-195">Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="18ec5-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="18ec5-196">A bővítmény újratöltése</span><span class="sxs-lookup"><span data-stu-id="18ec5-196">Reload the extension</span></span>

2. <span data-ttu-id="18ec5-197">A Quantum Project-sablonok frissítése:</span><span class="sxs-lookup"><span data-stu-id="18ec5-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="18ec5-198">Ugrás a **View**  ->  **parancs-paletta** megtekintéséhez</span><span class="sxs-lookup"><span data-stu-id="18ec5-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="18ec5-199">Válassza a **Q #: Project-sablonok telepítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="18ec5-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="18ec5-200">Néhány másodperc elteltével be kell szereznie egy felugró ablakban, hogy a "Project templates telepítése sikeresen megtörtént"</span><span class="sxs-lookup"><span data-stu-id="18ec5-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="18ec5-201">C# a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="18ec5-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="18ec5-202">A .NET-hez készült Quantum Project-sablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="18ec5-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
