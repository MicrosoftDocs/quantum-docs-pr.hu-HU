---
title: Ismerje meg, hogyan frissítheti a Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463277"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ec99a-102">A Microsoft Quantum Development Kit frissítése (QDK)</span><span class="sxs-lookup"><span data-stu-id="ec99a-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ec99a-103">Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="ec99a-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="ec99a-104">Ez a cikk azt feltételezi, hogy már telepítette a QDK.</span><span class="sxs-lookup"><span data-stu-id="ec99a-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="ec99a-105">Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="ec99a-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="ec99a-106">Q # projektek frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="ec99a-107">Először telepítse a [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) legújabb verzióját, és futtassa a következő parancsot a parancssorban:</span><span class="sxs-lookup"><span data-stu-id="ec99a-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="ec99a-108">Ellenőrizze, hogy a kimenet 3.0.100-e vagy magasabb-e, majd kövesse az alábbi utasításokat a beállítástól függően.</span><span class="sxs-lookup"><span data-stu-id="ec99a-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="ec99a-109">Visual Studióban</span><span class="sxs-lookup"><span data-stu-id="ec99a-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="ec99a-110">A Visual Studio 2019 legújabb verziójának frissítése [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="ec99a-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="ec99a-111">A megoldás megnyitása a Visual Studióban</span><span class="sxs-lookup"><span data-stu-id="ec99a-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="ec99a-112">A menüben válassza a Build > tiszta megoldás elemet.</span><span class="sxs-lookup"><span data-stu-id="ec99a-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="ec99a-113">[Frissítse a cél keretrendszert](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) minden. csproj-fájlból a netcoreapp 3.0-ra (vagy netstandard 2.1-re, ha az egy könyvtáros projekt)</span><span class="sxs-lookup"><span data-stu-id="ec99a-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="ec99a-114">A megoldásban lévő összes fájl mentése és lezárása</span><span class="sxs-lookup"><span data-stu-id="ec99a-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="ec99a-115">Válassza az eszközök > parancssori > fejlesztői parancssor lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec99a-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="ec99a-116">A megoldás minden egyes projektje esetében futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="ec99a-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="ec99a-117">Ha a projektek más Microsoft. Quantum csomagokat használnak, ezeket is futtassa a parancs futtatásával.</span><span class="sxs-lookup"><span data-stu-id="ec99a-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="ec99a-118">Zárjuk be a parancssort, és válassza a Build > Build megoldás ( *ne válassza a* megoldás újraépítése lehetőséget, mivel az Újraépítés kezdetben sikertelen lesz)</span><span class="sxs-lookup"><span data-stu-id="ec99a-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="ec99a-119">A Visual Studio Code-ban</span><span class="sxs-lookup"><span data-stu-id="ec99a-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="ec99a-120">A Visual Studio Code-ban nyissa meg a frissíteni kívánt projektet tartalmazó mappát.</span><span class="sxs-lookup"><span data-stu-id="ec99a-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="ec99a-121">Válassza ki a Terminal > új terminált</span><span class="sxs-lookup"><span data-stu-id="ec99a-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="ec99a-122">Kövesse a parancssor használatával történő frissítésre vonatkozó utasításokat.</span><span class="sxs-lookup"><span data-stu-id="ec99a-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="ec99a-123">A parancssor használata</span><span class="sxs-lookup"><span data-stu-id="ec99a-123">Using the command line</span></span>

1. <span data-ttu-id="ec99a-124">Navigáljon a projektfájlt tartalmazó mappára.</span><span class="sxs-lookup"><span data-stu-id="ec99a-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="ec99a-125">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="ec99a-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="ec99a-126">[Frissítse a cél keretrendszert](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) minden. csproj-fájlból a netcoreapp 3.0-ra (vagy netstandard 2.1-re, ha az egy könyvtáros projekt)</span><span class="sxs-lookup"><span data-stu-id="ec99a-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="ec99a-127">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="ec99a-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="ec99a-128">Ha a projekt más Microsoft. Quantum csomagokat használ, ezeket is futtassa a parancs futtatásával.</span><span class="sxs-lookup"><span data-stu-id="ec99a-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="ec99a-129">Az összes fájl mentése és lezárása</span><span class="sxs-lookup"><span data-stu-id="ec99a-129">Save and close all files</span></span>
6. <span data-ttu-id="ec99a-130">Ismételje meg a 1-4-et minden egyes projekt-függőség esetében, majd térjen vissza a fő projektet tartalmazó mappára, és futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="ec99a-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="ec99a-131">A Pythonhoz készült IQ # frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="ec99a-132">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ec99a-133">A `iqsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="ec99a-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ec99a-134">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="ec99a-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="ec99a-135">A `qsharp` csomag frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="ec99a-136">A `qsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="ec99a-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="ec99a-137">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="ec99a-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="ec99a-138">Futtassa a következő parancsot a `.qs` fájlok helyéről</span><span class="sxs-lookup"><span data-stu-id="ec99a-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="ec99a-139">Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.</span><span class="sxs-lookup"><span data-stu-id="ec99a-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="ec99a-140">Az IQ # frissítése Jupyter-jegyzetfüzetekhez</span><span class="sxs-lookup"><span data-stu-id="ec99a-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="ec99a-141">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ec99a-142">A `iqsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="ec99a-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ec99a-143">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="ec99a-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="ec99a-144">Futtassa a következő parancsot a Jupyter Notebook egyik cellájából:</span><span class="sxs-lookup"><span data-stu-id="ec99a-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="ec99a-145">Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.</span><span class="sxs-lookup"><span data-stu-id="ec99a-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="ec99a-146">A Visual Studio QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="ec99a-147">A Q # Visual Studio bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ec99a-148">A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit</span><span class="sxs-lookup"><span data-stu-id="ec99a-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="ec99a-149">A frissítés elfogadása</span><span class="sxs-lookup"><span data-stu-id="ec99a-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec99a-150">A Project-sablonokat a bővítménnyel együtt frissíti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="ec99a-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="ec99a-151">A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="ec99a-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="ec99a-152">A meglévő projektek kódja nem frissül a bővítmény frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="ec99a-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="ec99a-153">A VS Code QDK bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="ec99a-154">A Quantum VS Code bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ec99a-155">Újraindítás VS Code</span><span class="sxs-lookup"><span data-stu-id="ec99a-155">Restart VS Code</span></span>
    - <span data-ttu-id="ec99a-156">Navigáljon a **kiterjesztések** lapra</span><span class="sxs-lookup"><span data-stu-id="ec99a-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="ec99a-157">Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="ec99a-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="ec99a-158">A bővítmény újratöltése</span><span class="sxs-lookup"><span data-stu-id="ec99a-158">Reload the extension</span></span>

1. <span data-ttu-id="ec99a-159">A Quantum Project-sablonok frissítése:</span><span class="sxs-lookup"><span data-stu-id="ec99a-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="ec99a-160">Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="ec99a-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ec99a-161">Válassza a **Q #: Project-sablonok telepítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="ec99a-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="ec99a-162">C#, a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="ec99a-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="ec99a-163">A .NET-hez készült Quantum Project-sablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="ec99a-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="ec99a-164">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="ec99a-164">What's next?</span></span>

<span data-ttu-id="ec99a-165">Most, hogy frissítette a Quantum Development Kit-t az előnyben részesített környezetben, továbbra is fejlesztheti és futtathatja a kvantum-programokat.</span><span class="sxs-lookup"><span data-stu-id="ec99a-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="ec99a-166">Ha még nem írt programot, megkezdheti [az első kvantum-program](xref:microsoft.quantum.write-program)megkezdését.</span><span class="sxs-lookup"><span data-stu-id="ec99a-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
