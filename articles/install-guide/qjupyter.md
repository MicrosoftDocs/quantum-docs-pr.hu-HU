---
title: 'Fejlesztés Q # Jupyter notebookokkal'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831069"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="aa068-102">Fejlesztés Q # Jupyter notebookokkal</span><span class="sxs-lookup"><span data-stu-id="aa068-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="aa068-103">A q # Jupyter Jegyzetfüzeteken a Q # műveletek fejlesztéséhez telepítse a QDK.</span><span class="sxs-lookup"><span data-stu-id="aa068-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="aa068-104">A Jupyter-jegyzetfüzetek lehetővé teszik a kód futtatását az utasítások, megjegyzések és egyéb tartalmak mellett.</span><span class="sxs-lookup"><span data-stu-id="aa068-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="aa068-105">Ez a környezet ideális a Q # kód írására a beágyazott magyarázatokkal vagy a kvantum-számítástechnikai interaktív oktatóanyagokkal.</span><span class="sxs-lookup"><span data-stu-id="aa068-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="aa068-106">Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="aa068-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="aa068-107">Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.</span><span class="sxs-lookup"><span data-stu-id="aa068-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="aa068-108">A Q # Jupyter jegyzetfüzetek esetében csak a Q # kód futtatható, és a műveletek nem hívhatók meg külső gazdagép-programokból (például Pythonból vagy C# fájlokból).</span><span class="sxs-lookup"><span data-stu-id="aa068-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="aa068-109">Ez a környezet nem megfelelő, ha a cél egy külső klasszikus gazda program összevonása a kvantum-programmal.</span><span class="sxs-lookup"><span data-stu-id="aa068-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="aa068-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="aa068-110">Pre-requisites</span></span>

    - <span data-ttu-id="aa068-111">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="aa068-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="aa068-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="aa068-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="aa068-113">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="aa068-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="aa068-114">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="aa068-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="aa068-115">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="aa068-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="aa068-116">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="aa068-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="aa068-117">Nyissa meg a Jupyter jegyzetfüzetet, és illessze be a parancssorban megadott URL-címet a böngészőjébe.</span><span class="sxs-lookup"><span data-stu-id="aa068-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="aa068-118">Hozzon létre egy Jupyter-notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:</span><span class="sxs-lookup"><span data-stu-id="aa068-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="aa068-119">Futtassa a notebook következő celláját:</span><span class="sxs-lookup"><span data-stu-id="aa068-119">Run this cell of the notebook:</span></span>

        ![Jupyter-notebookcella Q#-kóddal](~/media/install-guide-jupyter.png)

        <span data-ttu-id="aa068-121">A cella kimenetében a következőnek kell megjelennie: `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="aa068-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="aa068-122">A Jupyter-notebookokban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.</span><span class="sxs-lookup"><span data-stu-id="aa068-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="aa068-123">Egy új cellában hajtsa végre az imént létrehozott műveletet (szimulátorban) a `%simulate` parancs használatával:</span><span class="sxs-lookup"><span data-stu-id="aa068-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter-notebookcella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="aa068-125">Ekkor meg kell jelennie a képernyőn kinyomtatott üzenetnek a meghívott művelet eredményével együtt (itt látható az üres rekord `()`, mert a művelet egyszerűen visszaadja a `Unit` típusát).</span><span class="sxs-lookup"><span data-stu-id="aa068-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="aa068-126">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="aa068-126">What's next?</span></span>

<span data-ttu-id="aa068-127">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="aa068-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
