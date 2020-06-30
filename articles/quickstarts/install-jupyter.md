---
title: Fejlesztés Q# Jupyter-notebookokkal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274095"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="f0b98-102">Fejlesztés Q# Jupyter-notebookokkal</span><span class="sxs-lookup"><span data-stu-id="f0b98-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="f0b98-103">Telepítse a QDK-t a Q#-műveletek Q# Jupyter-notebookokon történő fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="f0b98-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="f0b98-104">A Jupyter-notebookok helyszíni kódvégrehajtást tesznek lehetővé utasításokkal, megjegyzésekkel és egyéb tartalmakkal együtt.</span><span class="sxs-lookup"><span data-stu-id="f0b98-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="f0b98-105">Ez a környezet megfelelő a beágyazott magyarázatokkal ellátott Q#-kód írásához vagy kvantum-számítástechnikai interaktív oktatóanyagokhoz.</span><span class="sxs-lookup"><span data-stu-id="f0b98-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="f0b98-106">Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="f0b98-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="f0b98-107">Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.</span><span class="sxs-lookup"><span data-stu-id="f0b98-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="f0b98-108">A Q# Jupyter-notebookokban csak Q#-kódot futtathat, és a műveletek nem hívhatók meg külső gazdaprogramokból (pl. Python- vagy C#-fájlokból).</span><span class="sxs-lookup"><span data-stu-id="f0b98-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="f0b98-109">Ez a környezet nem megfelelő, ha egy külső klasszikus gazdaprogrammal együtt szeretné használni a kvantumprogramot.</span><span class="sxs-lookup"><span data-stu-id="f0b98-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="f0b98-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="f0b98-110">Prerequisites</span></span>

    - <span data-ttu-id="f0b98-111">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="f0b98-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="f0b98-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="f0b98-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="f0b98-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="f0b98-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="f0b98-114">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="f0b98-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="f0b98-115">Ha hibaüzenetet kap a `dotnet iqsharp install` lépés során, nyisson meg egy új terminálablakot, és próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="f0b98-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="f0b98-116">Ha ez a lépés továbbra sem sikerül, keresse meg a telepített `dotnet-iqsharp` eszközt (Windows rendszeren: `dotnet-iqsharp.exe`), majd futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="f0b98-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="f0b98-117">ahol a `/path/to/dotnet-iqsharp` helyére a fájlrendszerben található `dotnet-iqsharp` eszközre mutató abszolút elérési útvonalat kell beírni.</span><span class="sxs-lookup"><span data-stu-id="f0b98-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="f0b98-118">Ez általában a `.dotnet/tools` területen található a felhasználó profil mappájában.</span><span class="sxs-lookup"><span data-stu-id="f0b98-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="f0b98-119">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="f0b98-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f0b98-120">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="f0b98-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="f0b98-121">A Jupyter Notebook megnyitásához másolja és illessze be a böngészőbe a parancssor által megadott URL-címet.</span><span class="sxs-lookup"><span data-stu-id="f0b98-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="f0b98-122">Hozzon létre egy Jupyter Notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:</span><span class="sxs-lookup"><span data-stu-id="f0b98-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="f0b98-123">Futtassa a notebook következő celláját:</span><span class="sxs-lookup"><span data-stu-id="f0b98-123">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook-cella Q#-kóddal](~/media/install-guide-jupyter.png)

        <span data-ttu-id="f0b98-125">A cella kimenetében a következőnek kell megjelennie: `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="f0b98-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="f0b98-126">A Jupyter Notebookban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.</span><span class="sxs-lookup"><span data-stu-id="f0b98-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="f0b98-127">Egy új cellában, a `%simulate` paranccsal hajtsa végre az imént létrehozott műveletet (szimulátorban):</span><span class="sxs-lookup"><span data-stu-id="f0b98-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook-cella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="f0b98-129">A képernyőn megjelenik az üzenet a meghívott művelet eredményével együtt (ebben az esetben a `()` rekord üres, mert a művelet egyszerűen a `Unit` típust adja vissza).</span><span class="sxs-lookup"><span data-stu-id="f0b98-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0b98-130">További lépések</span><span class="sxs-lookup"><span data-stu-id="f0b98-130">Next steps</span></span>

<span data-ttu-id="f0b98-131">Most, hogy telepítette a Q# Jupyter-notebookokhoz készült QDK-t, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng). Ehhez a Q#-kódot közvetlenül a Jupyter Notebook környezetben írhatja.</span><span class="sxs-lookup"><span data-stu-id="f0b98-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="f0b98-132">Az alábbi oktatóanyagokban talál további példákat arra, hogy mire használhatja még a Q# Jupyter-notebookokat:</span><span class="sxs-lookup"><span data-stu-id="f0b98-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="f0b98-133">[A Q# és a Jupyter Notebook bemutatása](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="f0b98-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="f0b98-134">Itt egy Q# Jupyter Notebook példáján mutatjuk be, hogyan használható a Q# ebben a környezetben.</span><span class="sxs-lookup"><span data-stu-id="f0b98-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="f0b98-135">A [Kvantum Katák](xref:microsoft.quantum.overview.katas) saját ütemben elvégezhető oktatóanyagok és programozási gyakorlatok nyílt forráskódú gyűjteményei, Q# Jupyter-notebookok formájában.</span><span class="sxs-lookup"><span data-stu-id="f0b98-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="f0b98-136">A [Kvantum Katák oktatóanyagban található notebookok](https://github.com/microsoft/QuantumKatas#tutorial-topics) jó kiindulási pontként szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="f0b98-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="f0b98-137">A Kvantum Katák célja a kvantum-számítástechnika elemeinek és a Q#-programozás egyidejű megismertetése.</span><span class="sxs-lookup"><span data-stu-id="f0b98-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="f0b98-138">Remek példái annak, hogy milyen tartalmak hozhatók létre Q# Jupyter-notebookokkal.</span><span class="sxs-lookup"><span data-stu-id="f0b98-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
