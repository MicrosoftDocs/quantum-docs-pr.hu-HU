---
title: Ismerje meg, hogyan frissítheti a Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185851"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="75f20-102">A Microsoft Quantum Development Kit frissítése (QDK)</span><span class="sxs-lookup"><span data-stu-id="75f20-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="75f20-103">Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="75f20-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="75f20-104">Ez a cikk azt feltételezi, hogy már telepítette a QDK.</span><span class="sxs-lookup"><span data-stu-id="75f20-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="75f20-105">Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="75f20-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="75f20-106">A frissítési lépések a fejlesztési környezettől függenek.</span><span class="sxs-lookup"><span data-stu-id="75f20-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="75f20-107">A következő fejezetekben válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="75f20-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="75f20-108">Python</span><span class="sxs-lookup"><span data-stu-id="75f20-108">Python</span></span>

1. <span data-ttu-id="75f20-109">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="75f20-110">A `iqsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="75f20-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="75f20-111">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="75f20-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="75f20-112">A `qsharp` csomag frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="75f20-113">A `qsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="75f20-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="75f20-114">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="75f20-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="75f20-115">Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.</span><span class="sxs-lookup"><span data-stu-id="75f20-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="75f20-116">Jupyter-notebookok</span><span class="sxs-lookup"><span data-stu-id="75f20-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="75f20-117">A `iqsharp` kernel frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="75f20-118">A `iqsharp` verziójának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="75f20-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="75f20-119">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="75f20-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="75f20-120">Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.</span><span class="sxs-lookup"><span data-stu-id="75f20-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="75f20-121">C#Windows rendszeren a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="75f20-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="75f20-122">A Q # Visual Studio bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="75f20-123">A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit</span><span class="sxs-lookup"><span data-stu-id="75f20-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="75f20-124">A frissítés elfogadása</span><span class="sxs-lookup"><span data-stu-id="75f20-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="75f20-125">A Project-sablonokat a bővítménnyel együtt frissíti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="75f20-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="75f20-126">A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="75f20-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="75f20-127">A meglévő projektek kódja nem frissül a bővítmény frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="75f20-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="75f20-128">QDK-csomagok frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-128">Update the QDK packages</span></span>

    - <span data-ttu-id="75f20-129">Meglévő alkalmazás megnyitása</span><span class="sxs-lookup"><span data-stu-id="75f20-129">Open an existing application</span></span>
    - <span data-ttu-id="75f20-130">Válassza ki a **függőségeket** a megoldáskezelő</span><span class="sxs-lookup"><span data-stu-id="75f20-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="75f20-131">Válassza a **NuGet-csomagok kezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="75f20-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="75f20-132">A **Microsoft. Quantum** csomagok frissítése a legújabb verzióra</span><span class="sxs-lookup"><span data-stu-id="75f20-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="75f20-133">Most már futtathatja az alkalmazást a legújabb QDK.</span><span class="sxs-lookup"><span data-stu-id="75f20-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="75f20-134">C#, a VS Code használatával</span><span class="sxs-lookup"><span data-stu-id="75f20-134">C#, using VS Code</span></span>

1. <span data-ttu-id="75f20-135">A Quantum VS Code bővítmény frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="75f20-136">Újraindítás VS Code</span><span class="sxs-lookup"><span data-stu-id="75f20-136">Restart VS Code</span></span>
    - <span data-ttu-id="75f20-137">Navigáljon a **kiterjesztések** lapra</span><span class="sxs-lookup"><span data-stu-id="75f20-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="75f20-138">Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="75f20-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="75f20-139">A bővítmény újratöltése</span><span class="sxs-lookup"><span data-stu-id="75f20-139">Reload the extension</span></span>

1. <span data-ttu-id="75f20-140">A Quantum Project-sablonok frissítése:</span><span class="sxs-lookup"><span data-stu-id="75f20-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="75f20-141">Ugrás a -> **parancs-paletta** **megtekintése**</span><span class="sxs-lookup"><span data-stu-id="75f20-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="75f20-142">Válassza a **Q #: Project-sablonok telepítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="75f20-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="75f20-143">Meglévő alkalmazás megnyitása a VS Code-ban</span><span class="sxs-lookup"><span data-stu-id="75f20-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="75f20-144">A. csproj fájl szerkesztése az új csomag verzióinak hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="75f20-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="75f20-145">Ha más `Microsoft.Quantum` csomagokat használ, frissítse ezeket is.</span><span class="sxs-lookup"><span data-stu-id="75f20-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="75f20-146">Most már futtathatja az alkalmazást a frissített QDK</span><span class="sxs-lookup"><span data-stu-id="75f20-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="75f20-147">C#, a `dotnet` parancssori eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="75f20-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="75f20-148">A .NET-hez készült Quantum Project-sablonok frissítése</span><span class="sxs-lookup"><span data-stu-id="75f20-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="75f20-149">Meglévő alkalmazás frissítése és futtatása</span><span class="sxs-lookup"><span data-stu-id="75f20-149">Update and run an existing application</span></span>

    - <span data-ttu-id="75f20-150">A QDK-csomag verzióinak frissítése az alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="75f20-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="75f20-151">Ha az alkalmazás más `Microsoft.Quantum` csomagokat használ, frissítse ezeket is.</span><span class="sxs-lookup"><span data-stu-id="75f20-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="75f20-152">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="75f20-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="75f20-153">Az alkalmazás az új csomag verziójával fog futni</span><span class="sxs-lookup"><span data-stu-id="75f20-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="75f20-154">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="75f20-154">What's next?</span></span>

<span data-ttu-id="75f20-155">Most, hogy frissítette a Quantum Development Kit-t az előnyben részesített környezetben, továbbra is fejlesztheti és futtathatja a kvantum-programokat.</span><span class="sxs-lookup"><span data-stu-id="75f20-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="75f20-156">Ha még nem írt programot, megkezdheti [az első kvantum-program](xref:microsoft.quantum.write-program)megkezdését.</span><span class="sxs-lookup"><span data-stu-id="75f20-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
