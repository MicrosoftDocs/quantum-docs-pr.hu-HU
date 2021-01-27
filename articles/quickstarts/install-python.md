---
title: Fejlesztés Q#-pal és Pythonnal
description: Megtudhatja, hogyan hozhat létre Q#-alkalmazásokat a Python használatával.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ec40b6f1b7a8d9144860e3b8cfd554eb51bae81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844273"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="7740a-103">Fejlesztés Q#-pal és Pythonnal</span><span class="sxs-lookup"><span data-stu-id="7740a-103">Develop with Q# and Python</span></span>

<span data-ttu-id="7740a-104">Telepítse a QDK-t a Python-gazdaprogramok fejlesztéséhez Q#-műveletek meghívása céljával.</span><span class="sxs-lookup"><span data-stu-id="7740a-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="7740a-105">A(z) `qsharp` Python-csomag telepítése</span><span class="sxs-lookup"><span data-stu-id="7740a-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="7740a-106">Telepítés a Conda használatával (ajánlott)</span><span class="sxs-lookup"><span data-stu-id="7740a-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="7740a-107">Telepítse a [Miniconda](https://docs.conda.io/en/latest/miniconda.html) vagy [Anaconda](https://www.anaconda.com/products/individual#Downloads) telepítőt.</span><span class="sxs-lookup"><span data-stu-id="7740a-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="7740a-108">**Megjegyzés:** 64 bites telepítés szükséges.</span><span class="sxs-lookup"><span data-stu-id="7740a-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="7740a-109">Nyisson meg egy Anaconda-parancssort.</span><span class="sxs-lookup"><span data-stu-id="7740a-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="7740a-110">Ha inkább a PowerShellt vagy a pwsh-t szeretné használni: nyisson meg egy rendszerhéjat, futtassa a `conda init powershell` parancsot, majd zárja be és nyissa meg újból a rendszerhéjat.</span><span class="sxs-lookup"><span data-stu-id="7740a-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="7740a-111">Az alábbi parancsok futtatásával hozzon létre és aktiváljon egy új Conda-környezetet `qsharp-env` néven a szükséges csomagokkal (beleértve a Jupyter Notebookot és az IQ#-ot):</span><span class="sxs-lookup"><span data-stu-id="7740a-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="7740a-112">A telepítés ellenőrzéséhez és a helyi csomaggyorsítótár valamennyi szükséges QDK-összetevővel való feltöltéséhez futtassa a `python -c "import qsharp"` parancsot ugyanarról a terminálról.</span><span class="sxs-lookup"><span data-stu-id="7740a-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="7740a-113">Telepítés a .NET CLI és pip használatával (haladó)</span><span class="sxs-lookup"><span data-stu-id="7740a-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="7740a-114">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="7740a-114">Prerequisites:</span></span>

    - <span data-ttu-id="7740a-115">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="7740a-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="7740a-116">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="7740a-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="7740a-117">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="7740a-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="7740a-118">Telepítse a `qsharp` Python-csomagot, amely lehetővé teszi a Q# és a Python közötti együttműködést.</span><span class="sxs-lookup"><span data-stu-id="7740a-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="7740a-119">Telepítse az IQ#-ot, amely a Jupyter és a Python által használt kernel, és a Q#-műveletek fordításának és futtatásának alapvető funkcióit biztosítja.</span><span class="sxs-lookup"><span data-stu-id="7740a-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="7740a-120">Ha hibaüzenetet kap a `dotnet iqsharp install` lépés során, nyisson meg egy új terminálablakot, és próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="7740a-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="7740a-121">Ha ez a lépés továbbra sem sikerül, keresse meg a telepített `dotnet-iqsharp` eszközt (Windows rendszeren: `dotnet-iqsharp.exe`), majd futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="7740a-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="7740a-122">ahol a `/path/to/dotnet-iqsharp` helyére a fájlrendszerben található `dotnet-iqsharp` eszközre mutató abszolút elérési útvonalat kell beírni.</span><span class="sxs-lookup"><span data-stu-id="7740a-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="7740a-123">Ez általában a `.dotnet/tools` területen található a felhasználó profil mappájában.</span><span class="sxs-lookup"><span data-stu-id="7740a-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="7740a-124">\*\*_</span><span class="sxs-lookup"><span data-stu-id="7740a-124">\*\*_</span></span>

<span data-ttu-id="7740a-125">Ennyi az egész!</span><span class="sxs-lookup"><span data-stu-id="7740a-125">That's it!</span></span> <span data-ttu-id="7740a-126">Most már a `qsharp` Python-csomag és a Jupyterhez tartozó IQ# kernel is telepítve van, amelyek a Q#-műveletek Pythonból való fordításához és futtatásához szükséges fő funkciókat biztosítják, és lehetővé teszik a Q# Jupyter-notebookok használatát.</span><span class="sxs-lookup"><span data-stu-id="7740a-126">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="7740a-127">Az IDE kiválasztása</span><span class="sxs-lookup"><span data-stu-id="7740a-127">Choose your IDE</span></span>

<span data-ttu-id="7740a-128">Bár a Q#-t bármilyen IDE-ben használhatja a Pythonnal, határozottan javasoljuk, hogy Q#- és Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t.</span><span class="sxs-lookup"><span data-stu-id="7740a-128">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="7740a-129">A QDK Visual Studio Code-bővítmény használatával olyan további funkciókhoz férhet hozzá, mint a figyelmeztetések, a szintaxiselemek kiemelése, a projektsablonok és egyebek.</span><span class="sxs-lookup"><span data-stu-id="7740a-129">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="7740a-130">Ha a VS Code-ot szeretné használni:</span><span class="sxs-lookup"><span data-stu-id="7740a-130">If you would like to use VS Code:</span></span>

- <span data-ttu-id="7740a-131">A [VS Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac).</span><span class="sxs-lookup"><span data-stu-id="7740a-131">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="7740a-132">Telepítse a [VS Code-hoz készült QDK-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="7740a-132">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="7740a-133">Ha másik szerkesztőt szeretne használni, a fenti utasítások minden tudnivalót tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="7740a-133">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="7740a-134">Az első Q#-program megírása</span><span class="sxs-lookup"><span data-stu-id="7740a-134">Write your first Q# program</span></span>

<span data-ttu-id="7740a-135">Most már készen áll arra, hogy ellenőrizze a `qsharp` Python-csomag telepítését egy egyszerű Q#-program írásával és futtatásával.</span><span class="sxs-lookup"><span data-stu-id="7740a-135">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="7740a-136">Hozzon létre egy minimális Q# műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="7740a-136">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="7740a-137">Az `Operation.qs` fájlt is tartalmazó mappában hozzon létre egy `host.py` nevű Python-programot a Q# `SampleQuantumRandomNumberGenerator()` műveletének szimulálásához:</span><span class="sxs-lookup"><span data-stu-id="7740a-137">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="7740a-138">Futtassa a következő programot a telepítés során létrehozott környezetből (azaz a Conda vagy Python-környezetből, ahova a `qsharp`-ot telepítette):</span><span class="sxs-lookup"><span data-stu-id="7740a-138">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="7740a-139">Megjelenik a meghívott művelet eredménye.</span><span class="sxs-lookup"><span data-stu-id="7740a-139">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="7740a-140">Mivel a művelet egy véletlenszerű eredményt hoz létre, ezért ebben az esetben a képernyőn a `0` vagy `1` érték jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7740a-140">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="7740a-141">Ha újra és újra futtatja a programot, mindkét eredményt körülbelül az esetek felében fogja látni.</span><span class="sxs-lookup"><span data-stu-id="7740a-141">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> <span data-ttu-id="7740a-142">_ A Python-kód csak egy normál Python-program.</span><span class="sxs-lookup"><span data-stu-id="7740a-142">_ The Python code is just a normal Python program.</span></span> <span data-ttu-id="7740a-143">Python Jupyter-környezeteket, beleértve Python-alapú Jupyter-notebookokat is használhat klasszikus Python-programok írásához és Q#-műveletek meghívásához.</span><span class="sxs-lookup"><span data-stu-id="7740a-143">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="7740a-144">A Python-program képes Q#-műveleteket importálni bármilyen olyan .qs fájlból, amely ugyanabban a mappában található, mint maga a Python-kód.</span><span class="sxs-lookup"><span data-stu-id="7740a-144">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7740a-145">További lépések</span><span class="sxs-lookup"><span data-stu-id="7740a-145">Next steps</span></span>

<span data-ttu-id="7740a-146">Most, hogy a választott környezetben tesztelte a Quantum Development Kitet, ezen oktatóanyag segítségével megírhatja és futtathatja [első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="7740a-146">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
