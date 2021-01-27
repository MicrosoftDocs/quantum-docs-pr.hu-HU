---
title: A Quantum Development Kit (QDK) frissítése
description: Ismerteti, hogyan frissítheti Q#-projektjeit és a Microsoft Quantum Development Kitet az aktuális verzióra.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: quickstart
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1b5def3226bd073c878f8573aaddd757d733ec48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858063"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="05d80-103">A Microsoft Quantum Development Kit (QDK) frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="05d80-104">Ismerje meg, hogy frissítheti a Microsoft Quantum Development Kitet (QDK) a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="05d80-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="05d80-105">A cikk feltételezi, hogy már telepítette a QDK-t.</span><span class="sxs-lookup"><span data-stu-id="05d80-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="05d80-106">Ha most telepíti először, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="05d80-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="05d80-107">Azt javasoljuk, hogy mindig a QDK legújabb kiadását használja.</span><span class="sxs-lookup"><span data-stu-id="05d80-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="05d80-108">A QDK legújabb verziójára való frissítéshez kövesse ezt a frissítési útmutatót.</span><span class="sxs-lookup"><span data-stu-id="05d80-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="05d80-109">A folyamat két részből áll:</span><span class="sxs-lookup"><span data-stu-id="05d80-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="05d80-110">A meglévő Q#-fájlok és -projektek frissítéséből, hogy a kód az összes frissített szintaxisnak megfeleljen.</span><span class="sxs-lookup"><span data-stu-id="05d80-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="05d80-111">A QDK a kiválasztott fejlesztési környezethez történő frissítéséből.</span><span class="sxs-lookup"><span data-stu-id="05d80-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="05d80-112">Q#-projektek frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-112">Updating Q# Projects</span></span> 

<span data-ttu-id="05d80-113">Függetlenül attól, hogy a C#-ot vagy Pythont használ a Q#-műveleteihez, kövesse ezeket az utasításokat a Q#-projektek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="05d80-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="05d80-114">Először is ellenőrizze, hogy a [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) legújabb verzióját használja-e.</span><span class="sxs-lookup"><span data-stu-id="05d80-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="05d80-115">Futtassa az alábbi parancsot a parancssorban:</span><span class="sxs-lookup"><span data-stu-id="05d80-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="05d80-116">Győződjön meg arról, hogy a kimenet `3.1.100` vagy nagyobb.</span><span class="sxs-lookup"><span data-stu-id="05d80-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="05d80-117">Ha nem, telepítse a [legújabb verziót](https://dotnet.microsoft.com/download), és ellenőrizze még egyszer.</span><span class="sxs-lookup"><span data-stu-id="05d80-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="05d80-118">Ezután a környezetétől (Visual Studio, Visual Studio Code vagy közvetlenül a parancssor) függően kövesse az alábbi utasításokat.</span><span class="sxs-lookup"><span data-stu-id="05d80-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="05d80-119">Q#-projektek frissítése a Visual Studióban</span><span class="sxs-lookup"><span data-stu-id="05d80-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="05d80-120">Frissítés a Visual Studio 2019 legújabb verziójára – a kapcsolódó utasításokat [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio) találja.</span><span class="sxs-lookup"><span data-stu-id="05d80-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio) for instructions.</span></span>
2. <span data-ttu-id="05d80-121">Nyissa meg a megoldást a Visual Studióban.</span><span class="sxs-lookup"><span data-stu-id="05d80-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="05d80-122">A menüben válassza a **Build (Létrehozás)**  -> **Clean Solution (Megoldás eltávolítása)** elemet.</span><span class="sxs-lookup"><span data-stu-id="05d80-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="05d80-123">A .csproj-fájlok mindegyikében frissítse a célkeretrendszert a következőre: `netcoreapp3.1` (kódtárprojekt esetén a következőre: `netstandard2.1`).</span><span class="sxs-lookup"><span data-stu-id="05d80-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="05d80-124">Szerkessze az űrlap sorait:</span><span class="sxs-lookup"><span data-stu-id="05d80-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="05d80-125">A célkeretrendszer megadásáról további információt [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) talál.</span><span class="sxs-lookup"><span data-stu-id="05d80-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="05d80-126">A .csproj-fájlok mindegyikében, az alábbi sorban látható módon állítsa be az SDK-t a következőre: `Microsoft.Quantum.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="05d80-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="05d80-127">Vegye figyelembe, hogy a verziószámnak a legfrissebb elérhető verziónak kell lennie, amelyet a [kibocsátási megjegyzések](https://docs.microsoft.com/quantum/relnotes/) áttekintésével állapíthat meg.</span><span class="sxs-lookup"><span data-stu-id="05d80-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="05d80-128">Mentsen, majd zárja be a megoldás összes fájlját.</span><span class="sxs-lookup"><span data-stu-id="05d80-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="05d80-129">Válassza a **Tools (Eszközök)**  -> **Command Line (Parancssor)**  -> **Developer Command Prompt (Fejlesztői parancssor)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05d80-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="05d80-130">Használhatja a Visual Studio csomagkezelési konzolját is.</span><span class="sxs-lookup"><span data-stu-id="05d80-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="05d80-131">A megoldásban található összes projekt esetében az alábbi parancs futtatásával **távolítsa el** ezt a csomagot:</span><span class="sxs-lookup"><span data-stu-id="05d80-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="05d80-132">Ha a projektek más Microsoft.Quantum- vagy Microsoft.Azure.Quantum-csomagot is használnak (pl. Microsoft.Quantum.Numerics), futtassa az **add** parancsot az általuk használt verzió frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="05d80-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="05d80-133">Zárja be a parancssort, és válassza a **Build (Létrehozás)**  -> **Build Solution (Megoldás létrehozása)** lehetőséget (*ne* a Rebuild Solution (Megoldás újrafordítása) lehetőséget válassza).</span><span class="sxs-lookup"><span data-stu-id="05d80-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="05d80-134">Most már továbbléphet a [Visual Studio QDK-bővítmény frissítéséhez](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="05d80-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="05d80-135">Q#-projektek frissítése a Visual Studio Code-ban</span><span class="sxs-lookup"><span data-stu-id="05d80-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="05d80-136">Nyissa meg a frissíteni kívánt projektet tartalmazó mappát a Visual Studio Code-ban.</span><span class="sxs-lookup"><span data-stu-id="05d80-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="05d80-137">Válassza a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05d80-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="05d80-138">Kövesse a parancssorral történő frissítésre vonatkozó utasításokat (közvetlenül ez alatt látható).</span><span class="sxs-lookup"><span data-stu-id="05d80-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="05d80-139">Q#-projektek frissítése a parancssor használatával</span><span class="sxs-lookup"><span data-stu-id="05d80-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="05d80-140">Nyissa meg a fő projektfájlt tartalmazó mappát.</span><span class="sxs-lookup"><span data-stu-id="05d80-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="05d80-141">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="05d80-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="05d80-142">Állapítsa meg a QDK aktuális verzióját.</span><span class="sxs-lookup"><span data-stu-id="05d80-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="05d80-143">Ehhez tekintse meg a [kibocsátási megjegyzéseket](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="05d80-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="05d80-144">A verzió formátuma a következőhöz hasonló: `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="05d80-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="05d80-145">Minden `.csproj`-fájl esetében hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="05d80-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="05d80-146">Frissítse célkeretrendszert a következőre: `netcoreapp3.1` (kódtárprojekt esetén a következőre: `netstandard2.1`).</span><span class="sxs-lookup"><span data-stu-id="05d80-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="05d80-147">Szerkessze az űrlap sorait:</span><span class="sxs-lookup"><span data-stu-id="05d80-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="05d80-148">A célkeretrendszer megadásáról további információt [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) talál.</span><span class="sxs-lookup"><span data-stu-id="05d80-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="05d80-149">Cserélje le az SDK hivatkozását a projekt definíciójában.</span><span class="sxs-lookup"><span data-stu-id="05d80-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="05d80-150">Ellenőrizze, hogy a verziószám megfelel-e a **3. lépésben** megadott értéknek.</span><span class="sxs-lookup"><span data-stu-id="05d80-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="05d80-151">Távolítsa el a `Microsoft.Quantum.Development.Kit` csomagra mutató hivatkozást (ha van ilyen), amely a következő bejegyzésben található:</span><span class="sxs-lookup"><span data-stu-id="05d80-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="05d80-152">Frissítse az összes Microsoft Quantum-csomag verzióját a QDK legfrissebb kiadott verziójára (amelyet a **3. lépésben** állapított meg).</span><span class="sxs-lookup"><span data-stu-id="05d80-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="05d80-153">Ezen csomagok elnevezése a következő mintát követi:</span><span class="sxs-lookup"><span data-stu-id="05d80-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="05d80-154">A csomaghivatkozások formátuma:</span><span class="sxs-lookup"><span data-stu-id="05d80-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="05d80-155">Mentse a módosított fájlt.</span><span class="sxs-lookup"><span data-stu-id="05d80-155">Save the updated file.</span></span>

    - <span data-ttu-id="05d80-156">Az alábbiak elvégzésével állítsa vissza a projekt függőségeit:</span><span class="sxs-lookup"><span data-stu-id="05d80-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="05d80-157">Lépjen vissza a fő projektfájlt tartalmazó mappához, majd futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="05d80-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="05d80-158">A Q#-projektek frissítése után kövesse az alábbi utasításokat a QDK frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="05d80-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="05d80-159">A QDK frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-159">Updating the QDK</span></span>

<span data-ttu-id="05d80-160">A QDK frissítési folyamata a fejlesztési nyelvtől és a környezettől függ.</span><span class="sxs-lookup"><span data-stu-id="05d80-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="05d80-161">A lenti listából válassza ki a fejlesztőkörnyezetet.</span><span class="sxs-lookup"><span data-stu-id="05d80-161">Select your development environment below.</span></span>

* [<span data-ttu-id="05d80-162">Python: frissítse a(z) `qsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="05d80-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="05d80-163">Jupyter-notebookok: frissítse az IQ#-kernelt</span><span class="sxs-lookup"><span data-stu-id="05d80-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="05d80-164">Visual Studio: a QDK-bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="05d80-165">VS Code: a QDK-bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="05d80-166">Parancssor és C#: projektsablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="05d80-167">A(z) `qsharp` Python-csomag frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="05d80-168">A frissítési eljárás attól függ, hogy a telepítést eredetileg a Conda vagy a .NET CLI és a pip használatával végezte.</span><span class="sxs-lookup"><span data-stu-id="05d80-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="05d80-169">Frissítés a Conda használatával (ajánlott)</span><span class="sxs-lookup"><span data-stu-id="05d80-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="05d80-170">Aktiválja azt a Conda-környezetet, amelyben a(z) `qsharp` csomagot telepítette, majd futtassa a következő parancsot a frissítéséhez:</span><span class="sxs-lookup"><span data-stu-id="05d80-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="05d80-171">Futtassa az alábbi parancsot a(z) `.qs`-fájlok helyéről:</span><span class="sxs-lookup"><span data-stu-id="05d80-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="05d80-172">Frissítés a .NET CLI és a pip használatával (haladó)</span><span class="sxs-lookup"><span data-stu-id="05d80-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="05d80-173">Frissítse az `iqsharp` kernelt</span><span class="sxs-lookup"><span data-stu-id="05d80-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="05d80-174">Ellenőrizze az `iqsharp` verzióját</span><span class="sxs-lookup"><span data-stu-id="05d80-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="05d80-175">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="05d80-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="05d80-176">Ne aggódjon, ha a(z) `iqsharp` verziószáma nagyobb.</span><span class="sxs-lookup"><span data-stu-id="05d80-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="05d80-177">Annak meg kell egyeznie a(z) [legújabb kiadással](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="05d80-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="05d80-178">Frissítse a(z) `qsharp` csomagot:</span><span class="sxs-lookup"><span data-stu-id="05d80-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="05d80-179">Ellenőrizze a(z) `qsharp` verzióját:</span><span class="sxs-lookup"><span data-stu-id="05d80-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="05d80-180">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="05d80-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="05d80-181">Futtassa az alábbi parancsot a(z) `.qs`-fájlok helyéről:</span><span class="sxs-lookup"><span data-stu-id="05d80-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="05d80-182">Most már használhatja a frissített `qsharp` Python-csomagot a meglévő kvantumprogramok futtatásához.</span><span class="sxs-lookup"><span data-stu-id="05d80-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="05d80-183">Az IQ# Jupyter kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="05d80-184">A frissítési eljárás attól függ, hogy a telepítést eredetileg a Conda vagy a .NET CLI és a pip használatával végezte.</span><span class="sxs-lookup"><span data-stu-id="05d80-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="05d80-185">Frissítés a Conda használatával (ajánlott)</span><span class="sxs-lookup"><span data-stu-id="05d80-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="05d80-186">Aktiválja azt a Conda-környezetet, amelyben a(z) `qsharp` csomagot telepítette, majd futtassa a következő parancsot a frissítéséhez:</span><span class="sxs-lookup"><span data-stu-id="05d80-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="05d80-187">Futtassa az alábbi parancsot valamennyi meglévő Q# Jupyter-notebook egy-egy cellájából:</span><span class="sxs-lookup"><span data-stu-id="05d80-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="05d80-188">Frissítés a .NET CLI és a pip használatával (haladó)</span><span class="sxs-lookup"><span data-stu-id="05d80-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="05d80-189">Frissítse a(z) `Microsoft.Quantum.IQSharp` csomagot:</span><span class="sxs-lookup"><span data-stu-id="05d80-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="05d80-190">Ellenőrizze a(z) `iqsharp` verzióját:</span><span class="sxs-lookup"><span data-stu-id="05d80-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="05d80-191">A kimenet az alábbihoz hasonló lesz:</span><span class="sxs-lookup"><span data-stu-id="05d80-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="05d80-192">Ne aggódjon, ha a(z) `iqsharp` verziószáma nagyobb.</span><span class="sxs-lookup"><span data-stu-id="05d80-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="05d80-193">Annak meg kell egyeznie a(z) [legújabb kiadással](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="05d80-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="05d80-194">Futtassa az alábbi parancsot valamennyi meglévő Q# Jupyter-notebook egy-egy cellájából:</span><span class="sxs-lookup"><span data-stu-id="05d80-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

<span data-ttu-id="05d80-195">\*\*_</span><span class="sxs-lookup"><span data-stu-id="05d80-195">\*\*_</span></span>

<span data-ttu-id="05d80-196">Most már használhatja a frissített IQ# kernelt a meglévő Q# Jupyter-notebookok futtatásához.</span><span class="sxs-lookup"><span data-stu-id="05d80-196">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="05d80-197">A Visual Studio QDK-bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-197">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="05d80-198">A Q# Visual Studio-bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-198">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="05d80-199">A Visual Studio arra kéri, hogy fogadja a [Quantum Visual Studio-bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit</span><span class="sxs-lookup"><span data-stu-id="05d80-199">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="05d80-200">Fogadja el a frissítést</span><span class="sxs-lookup"><span data-stu-id="05d80-200">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="05d80-201">A rendszer frissíti a projektsablonokat a bővítménnyel.</span><span class="sxs-lookup"><span data-stu-id="05d80-201">The project templates are updated with the extension.</span></span> <span data-ttu-id="05d80-202">A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="05d80-202">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="05d80-203">A meglévő projektek kódja nem frissül a bővítmény frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="05d80-203">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="05d80-204">A VS Code QDK-bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-204">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="05d80-205">Frissítse a Quantum VS Code-bővítményt</span><span class="sxs-lookup"><span data-stu-id="05d80-205">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="05d80-206">Indítsa újra a VS Code-ot</span><span class="sxs-lookup"><span data-stu-id="05d80-206">Restart VS Code</span></span>
    - <span data-ttu-id="05d80-207">Navigáljon a _ *Extensions*\* lapra</span><span class="sxs-lookup"><span data-stu-id="05d80-207">Navigate to the _ *Extensions*\* tab</span></span>
    - <span data-ttu-id="05d80-208">Válassza a **Visual Studio Code-hoz készült Microsoft Quantum Development Kit** bővítményt</span><span class="sxs-lookup"><span data-stu-id="05d80-208">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="05d80-209">Töltse be újból a bővítményt</span><span class="sxs-lookup"><span data-stu-id="05d80-209">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="05d80-210">C#, a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="05d80-210">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="05d80-211">Frissítse a .NET-hez tartozó Quantum-projektsablonokat</span><span class="sxs-lookup"><span data-stu-id="05d80-211">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="05d80-212">A parancssorból:</span><span class="sxs-lookup"><span data-stu-id="05d80-212">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="05d80-213">Ha a parancssori sablonokat is használni szeretné, és már telepítve van a VS Code QDK-bővítmény, a projektsablonokat magából a bővítményből is frissítheti:</span><span class="sxs-lookup"><span data-stu-id="05d80-213">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="05d80-214">A QDK-bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="05d80-214">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="05d80-215">A VS Code-ban lépjen a **View** -> **Command Palette** (Nézet > Parancskatalógus) lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="05d80-215">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="05d80-216">Válassza a következőt **Q#: Install command line project templates** (Q#: Parancssori projektsablonok telepítése)</span><span class="sxs-lookup"><span data-stu-id="05d80-216">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="05d80-217">Néhány másodperc elteltével megjelenik a projektsablonok sikeres telepítésének megerősítését tartalmazó felugró ablak</span><span class="sxs-lookup"><span data-stu-id="05d80-217">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
