---
title: Fejlesztés Q# Jupyter-notebookokkal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: bbd1f58ba7de205e452be7bac72b5fd78e7acd56
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871450"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="353b6-102">Fejlesztés Q# Jupyter-notebookokkal</span><span class="sxs-lookup"><span data-stu-id="353b6-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="353b6-103">Telepítse a QDK-t a Q#-műveletek Q# Jupyter-notebookokon történő fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="353b6-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="353b6-104">A Jupyter-notebookok helyszíni kódvégrehajtást tesznek lehetővé utasításokkal, megjegyzésekkel és egyéb tartalmakkal együtt.</span><span class="sxs-lookup"><span data-stu-id="353b6-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="353b6-105">Ez a környezet megfelelő a beágyazott magyarázatokkal ellátott Q#-kód írásához vagy kvantum-számítástechnikai interaktív oktatóanyagokhoz.</span><span class="sxs-lookup"><span data-stu-id="353b6-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="353b6-106">Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="353b6-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

> [!NOTE]
> * <span data-ttu-id="353b6-107">A Q# Jupyter-notebookokban csak Q#-kódot futtathat, és a műveletek nem hívhatók meg külső gazdaprogramokból (pl. Python- vagy C#-fájlokból).</span><span class="sxs-lookup"><span data-stu-id="353b6-107">In Q# Jupyter Notebooks, you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="353b6-108">Ez a környezet nem megfelelő, ha egy külső klasszikus gazdaprogrammal együtt szeretné használni a kvantumprogramot.</span><span class="sxs-lookup"><span data-stu-id="353b6-108">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

## <a name="install-the-iq-jupyter-kernel"></a><span data-ttu-id="353b6-109">Az IQ# Jupyter kernel telepítése</span><span class="sxs-lookup"><span data-stu-id="353b6-109">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="353b6-110">Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.</span><span class="sxs-lookup"><span data-stu-id="353b6-110">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="353b6-111">Telepítés a Conda használatával (ajánlott)</span><span class="sxs-lookup"><span data-stu-id="353b6-111">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="353b6-112">Telepítse a [Miniconda](https://docs.conda.io/en/latest/miniconda.html) vagy [Anaconda](https://www.anaconda.com/products/individual#Downloads) telepítőt.</span><span class="sxs-lookup"><span data-stu-id="353b6-112">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="353b6-113">**Megjegyzés:** 64 bites telepítés szükséges.</span><span class="sxs-lookup"><span data-stu-id="353b6-113">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="353b6-114">Nyisson meg egy Anaconda-parancssort.</span><span class="sxs-lookup"><span data-stu-id="353b6-114">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="353b6-115">Ha inkább a PowerShellt vagy a pwsh-t szeretné használni: nyisson meg egy rendszerhéjat, futtassa a `conda init powershell` parancsot, majd zárja be és nyissa meg újból a rendszerhéjat.</span><span class="sxs-lookup"><span data-stu-id="353b6-115">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="353b6-116">Az alábbi parancsok futtatásával hozzon létre és aktiváljon egy új Conda-környezetet `qsharp-env` néven a szükséges csomagokkal (beleértve a Jupyter Notebookot és az IQ#-ot):</span><span class="sxs-lookup"><span data-stu-id="353b6-116">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="353b6-117">A telepítés ellenőrzéséhez és a helyi csomaggyorsítótár valamennyi szükséges QDK-összetevővel való feltöltéséhez futtassa a `python -c "import qsharp"` parancsot ugyanarról a terminálról.</span><span class="sxs-lookup"><span data-stu-id="353b6-117">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="353b6-118">Telepítés a .NET CLI használatával (haladó)</span><span class="sxs-lookup"><span data-stu-id="353b6-118">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="353b6-119">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="353b6-119">Prerequisites:</span></span>

    - <span data-ttu-id="353b6-120">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="353b6-120">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="353b6-121">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="353b6-121">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="353b6-122">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="353b6-122">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="353b6-123">Telepítse az `Microsoft.Quantum.IQSharp` csomagot.</span><span class="sxs-lookup"><span data-stu-id="353b6-123">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="353b6-124">Ha hibaüzenetet kap a `dotnet iqsharp install` lépés során, nyisson meg egy új terminálablakot, és próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="353b6-124">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="353b6-125">Ha ez a lépés továbbra sem sikerül, keresse meg a telepített `dotnet-iqsharp` eszközt (Windows rendszeren: `dotnet-iqsharp.exe`), majd futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="353b6-125">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="353b6-126">ahol a `/path/to/dotnet-iqsharp` helyére a fájlrendszerben található `dotnet-iqsharp` eszközre mutató abszolút elérési útvonalat kell beírni.</span><span class="sxs-lookup"><span data-stu-id="353b6-126">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="353b6-127">Ez általában a `.dotnet/tools` területen található a felhasználó profil mappájában.</span><span class="sxs-lookup"><span data-stu-id="353b6-127">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="353b6-128">Ennyi az egész!</span><span class="sxs-lookup"><span data-stu-id="353b6-128">That's it!</span></span> <span data-ttu-id="353b6-129">Most már a Jupyterhez tartozó IQ# kernel is telepítve van, amely a Q#-műveletek Jupyter-notebookokból való fordításához és végrehajtásához szükséges fő funkciókat biztosítja.</span><span class="sxs-lookup"><span data-stu-id="353b6-129">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-q-notebook"></a><span data-ttu-id="353b6-130">Az első Q#-notebook létrehozása</span><span class="sxs-lookup"><span data-stu-id="353b6-130">Create your first Q# notebook</span></span>

<span data-ttu-id="353b6-131">Most már készen áll arra, hogy ellenőrizze a Q# Jupyter Notebook telepítését egy egyszerű Q#-művelet írásával és futtatásával.</span><span class="sxs-lookup"><span data-stu-id="353b6-131">Now you are ready to verify your Q# Jupyter Notebook installation by writing and executing a simple Q# operation.</span></span>

1. <span data-ttu-id="353b6-132">A Jupyter Notebook kiszolgáló indításához futtassa a következő programot a telepítés során létrehozott környezetből (azaz a létrehozott Conda-környezetből vagy a Python-környezetből, amelyben a Jupytert telepítette):</span><span class="sxs-lookup"><span data-stu-id="353b6-132">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="353b6-133">Ha a Jupyter Notebook nem nyílik meg automatikusan a böngészőben, a megnyitásához másolja és illessze be a böngészőbe a parancssor által megadott URL-címet.</span><span class="sxs-lookup"><span data-stu-id="353b6-133">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="353b6-134">Válassza a „New” (Új) → „Q#” lehetőséget egy Jupyter-notebook létrehozásához egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:</span><span class="sxs-lookup"><span data-stu-id="353b6-134">Choose "New" → "Q#" to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="353b6-135">Futtassa a notebook következő celláját:</span><span class="sxs-lookup"><span data-stu-id="353b6-135">Run this cell of the notebook:</span></span>

    ![Jupyter Notebook-cella Q#-kóddal](~/media/install-guide-jupyter.png)

    <span data-ttu-id="353b6-137">A cella kimenetében a következőnek kell megjelennie: `SampleQuantumRandomNumberGenerator`.</span><span class="sxs-lookup"><span data-stu-id="353b6-137">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="353b6-138">A Jupyter Notebookban való futtatáskor a Q#-kód le lesz fordítva, és a cella kiadja a talált műveletek nevét.</span><span class="sxs-lookup"><span data-stu-id="353b6-138">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="353b6-139">Egy új cellában, a `%simulate` paranccsal hajtsa végre az imént létrehozott műveletet (szimulátorban):</span><span class="sxs-lookup"><span data-stu-id="353b6-139">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Jupyter Notebook-cella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="353b6-141">Megjelenik a meghívott művelet eredménye.</span><span class="sxs-lookup"><span data-stu-id="353b6-141">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="353b6-142">Mivel a művelet egy véletlenszerű eredményt hoz létre, ezért ebben az esetben a képernyőn a `Zero` vagy `One` érték jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="353b6-142">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="353b6-143">Ha újra és újra futtatja a cellát, mindkét eredményt körülbelül az esetek felében fogja látni.</span><span class="sxs-lookup"><span data-stu-id="353b6-143">If you execute the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="353b6-144">További lépések</span><span class="sxs-lookup"><span data-stu-id="353b6-144">Next steps</span></span>

<span data-ttu-id="353b6-145">Most, hogy telepítette a Q# Jupyter-notebookokhoz készült QDK-t, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng). Ehhez a Q#-kódot közvetlenül a Jupyter-notebook környezetben írhatja.</span><span class="sxs-lookup"><span data-stu-id="353b6-145">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="353b6-146">Az alábbi oktatóanyagokban talál további példákat arra, hogy mire használhatja még a Q# Jupyter-notebookokat:</span><span class="sxs-lookup"><span data-stu-id="353b6-146">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="353b6-147">[A Q# és a Jupyter Notebook bemutatása](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="353b6-147">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="353b6-148">Itt egy Q# Jupyter-notebook példáján mutatjuk be, hogyan használható a Q# a Jupyter-környezetben.</span><span class="sxs-lookup"><span data-stu-id="353b6-148">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="353b6-149">A [Kvantum Katák](xref:microsoft.quantum.overview.katas) saját ütemben elvégezhető oktatóanyagok és programozási gyakorlatok nyílt forráskódú gyűjteményei, Q# Jupyter-notebookok formájában.</span><span class="sxs-lookup"><span data-stu-id="353b6-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="353b6-150">A [Kvantum Katák oktatóanyagban található notebookok](https://github.com/microsoft/QuantumKatas#tutorial-topics) jó kiindulási pontként szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="353b6-150">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="353b6-151">A Kvantum Katák célja a kvantum-számítástechnika elemeinek és a Q#-programozás egyidejű megismertetése.</span><span class="sxs-lookup"><span data-stu-id="353b6-151">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="353b6-152">Remek példái annak, hogy milyen tartalmak hozhatók létre Q# Jupyter-notebookokkal.</span><span class="sxs-lookup"><span data-stu-id="353b6-152">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
