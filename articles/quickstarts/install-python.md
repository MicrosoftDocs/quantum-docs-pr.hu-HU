---
title: Fejlesztés Q#-pal és Pythonnal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: ec5e66e0c85d89888a8ff1e7d6bf18bf89ff44ac
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871586"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="d8af1-102">Fejlesztés Q#-pal és Pythonnal</span><span class="sxs-lookup"><span data-stu-id="d8af1-102">Develop with Q# and Python</span></span>

<span data-ttu-id="d8af1-103">Telepítse a QDK-t a Python-gazdaprogramok fejlesztéséhez Q#-műveletek meghívása céljával.</span><span class="sxs-lookup"><span data-stu-id="d8af1-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="d8af1-104">A(z) `qsharp` Python-csomag telepítése</span><span class="sxs-lookup"><span data-stu-id="d8af1-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="d8af1-105">Telepítés a Conda használatával (ajánlott)</span><span class="sxs-lookup"><span data-stu-id="d8af1-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="d8af1-106">Telepítse a [Miniconda](https://docs.conda.io/en/latest/miniconda.html) vagy [Anaconda](https://www.anaconda.com/products/individual#Downloads) telepítőt.</span><span class="sxs-lookup"><span data-stu-id="d8af1-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="d8af1-107">**Megjegyzés:** 64 bites telepítés szükséges.</span><span class="sxs-lookup"><span data-stu-id="d8af1-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="d8af1-108">Nyisson meg egy Anaconda-parancssort.</span><span class="sxs-lookup"><span data-stu-id="d8af1-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="d8af1-109">Ha inkább a PowerShellt vagy a pwsh-t szeretné használni: nyisson meg egy rendszerhéjat, futtassa a `conda init powershell` parancsot, majd zárja be és nyissa meg újból a rendszerhéjat.</span><span class="sxs-lookup"><span data-stu-id="d8af1-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="d8af1-110">Az alábbi parancsok futtatásával hozzon létre és aktiváljon egy új Conda-környezetet `qsharp-env` néven a szükséges csomagokkal (beleértve a Jupyter Notebookot és az IQ#-ot):</span><span class="sxs-lookup"><span data-stu-id="d8af1-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="d8af1-111">A telepítés ellenőrzéséhez és a helyi csomaggyorsítótár valamennyi szükséges QDK-összetevővel való feltöltéséhez futtassa a `python -c "import qsharp"` parancsot ugyanarról a terminálról.</span><span class="sxs-lookup"><span data-stu-id="d8af1-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="d8af1-112">Telepítés a .NET CLI és pip használatával (haladó)</span><span class="sxs-lookup"><span data-stu-id="d8af1-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="d8af1-113">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="d8af1-113">Prerequisites:</span></span>

    - <span data-ttu-id="d8af1-114">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="d8af1-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="d8af1-115">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="d8af1-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="d8af1-116">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="d8af1-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="d8af1-117">Telepítse a `qsharp` Python-csomagot, amely lehetővé teszi a Q# és a Python közötti együttműködést.</span><span class="sxs-lookup"><span data-stu-id="d8af1-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="d8af1-118">Telepítse az IQ#-ot, amely a Jupyter és a Python által használt kernel, és a Q#-műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.</span><span class="sxs-lookup"><span data-stu-id="d8af1-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="d8af1-119">Ha hibaüzenetet kap a `dotnet iqsharp install` lépés során, nyisson meg egy új terminálablakot, és próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="d8af1-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="d8af1-120">Ha ez a lépés továbbra sem sikerül, keresse meg a telepített `dotnet-iqsharp` eszközt (Windows rendszeren: `dotnet-iqsharp.exe`), majd futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="d8af1-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="d8af1-121">ahol a `/path/to/dotnet-iqsharp` helyére a fájlrendszerben található `dotnet-iqsharp` eszközre mutató abszolút elérési útvonalat kell beírni.</span><span class="sxs-lookup"><span data-stu-id="d8af1-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="d8af1-122">Ez általában a `.dotnet/tools` területen található a felhasználó profil mappájában.</span><span class="sxs-lookup"><span data-stu-id="d8af1-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="d8af1-123">Ennyi az egész!</span><span class="sxs-lookup"><span data-stu-id="d8af1-123">That's it!</span></span> <span data-ttu-id="d8af1-124">Most már a `qsharp` Python-csomag és a Jupyterhez tartozó IQ# kernel is telepítve van, amelyek a Q#-műveletek Pythonból való fordításához és végrehajtásához szükséges fő funkciókat biztosítják, és lehetővé teszik a Q# Jupyter-notebookok használatát.</span><span class="sxs-lookup"><span data-stu-id="d8af1-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="d8af1-125">Az IDE kiválasztása</span><span class="sxs-lookup"><span data-stu-id="d8af1-125">Choose your IDE</span></span>

<span data-ttu-id="d8af1-126">Bár a Q#-ot bármilyen IDE-ben használhatja a Pythonnal, határozottan javasoljuk, hogy Q#- és Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t.</span><span class="sxs-lookup"><span data-stu-id="d8af1-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="d8af1-127">A QDK Visual Studio Code-bővítmény használatával olyan további funkciókhoz férhet hozzá, mint a figyelmeztetések, a szintaxiselemek kiemelése, a projektsablonok és egyebek.</span><span class="sxs-lookup"><span data-stu-id="d8af1-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="d8af1-128">Ha a VS Code-ot szeretné használni:</span><span class="sxs-lookup"><span data-stu-id="d8af1-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="d8af1-129">A [VS Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="d8af1-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="d8af1-130">Telepítse a [VS Code-hoz készült QDK-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="d8af1-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="d8af1-131">Ha másik szerkesztőt szeretne használni, a fenti utasítások minden tudnivalót tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="d8af1-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="d8af1-132">Az első Q#-program megírása</span><span class="sxs-lookup"><span data-stu-id="d8af1-132">Write your first Q# program</span></span>

<span data-ttu-id="d8af1-133">Most már készen áll arra, hogy ellenőrizze a `qsharp` Python-csomag telepítését egy egyszerű Q#-program írásával és futtatásával.</span><span class="sxs-lookup"><span data-stu-id="d8af1-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="d8af1-134">Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="d8af1-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="d8af1-135">Az `Operation.qs` fájlt is tartalmazó mappában hozzon létre egy `host.py` nevű Python-programot a Q# `SampleQuantumRandomNumberGenerator()` műveletének szimulálásához:</span><span class="sxs-lookup"><span data-stu-id="d8af1-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. <span data-ttu-id="d8af1-136">Futtassa a következő programot a telepítés során létrehozott környezetből (azaz a Conda vagy Python-környezetből, ahova a `qsharp`-ot telepítette):</span><span class="sxs-lookup"><span data-stu-id="d8af1-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="d8af1-137">Megjelenik a meghívott művelet eredménye.</span><span class="sxs-lookup"><span data-stu-id="d8af1-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="d8af1-138">Mivel a művelet egy véletlenszerű eredményt hoz létre, ezért ebben az esetben a képernyőn a `Zero` vagy `One` érték jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d8af1-138">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="d8af1-139">Ha újra és újra futtatja a programot, mindkét eredményt körülbelül az esetek felében fogja látni.</span><span class="sxs-lookup"><span data-stu-id="d8af1-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="d8af1-140">A Python-kód csak egy szokásos Python-program.</span><span class="sxs-lookup"><span data-stu-id="d8af1-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="d8af1-141">Python Jupyter-környezeteket, beleértve Python-alapú Jupyter-notebookokat is használhat klasszikus Python-programok írásához és Q#-műveletek meghívásához.</span><span class="sxs-lookup"><span data-stu-id="d8af1-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="d8af1-142">A Python-program képes Q#-műveleteket importálni bármilyen olyan .qs fájlból, amely ugyanabban a mappában található, mint maga a Python-kód.</span><span class="sxs-lookup"><span data-stu-id="d8af1-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8af1-143">További lépések</span><span class="sxs-lookup"><span data-stu-id="d8af1-143">Next steps</span></span>

<span data-ttu-id="d8af1-144">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, ezen oktatóanyag segítségével megírhatja és futtathatja [első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="d8af1-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
