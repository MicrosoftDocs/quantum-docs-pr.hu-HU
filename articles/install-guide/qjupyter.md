---
title: Fejlesztés Q# Jupyter-notebookokkal
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660773"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="06123-102">Fejlesztés Q# Jupyter-notebookokkal</span><span class="sxs-lookup"><span data-stu-id="06123-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="06123-103">A q # Jupyter Jegyzetfüzeteken a Q # műveletek fejlesztéséhez telepítse a QDK.</span><span class="sxs-lookup"><span data-stu-id="06123-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="06123-104">A Jupyter-jegyzetfüzetek lehetővé teszik a kód futtatását az utasítások, megjegyzések és egyéb tartalmak mellett.</span><span class="sxs-lookup"><span data-stu-id="06123-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="06123-105">Ez a környezet ideális a Q # kód írására a beágyazott magyarázatokkal vagy a kvantum-számítástechnikai interaktív oktatóanyagokkal.</span><span class="sxs-lookup"><span data-stu-id="06123-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="06123-106">Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="06123-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="06123-107">Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.</span><span class="sxs-lookup"><span data-stu-id="06123-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="06123-108">A Q # Jupyter jegyzetfüzetek esetében csak a Q # kód futtatható, és a műveletek nem hívhatók meg külső gazdagép-programokból (például Python vagy C# fájlokból).</span><span class="sxs-lookup"><span data-stu-id="06123-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="06123-109">Ez a környezet nem megfelelő, ha a cél egy külső klasszikus gazda program összevonása a kvantum-programmal.</span><span class="sxs-lookup"><span data-stu-id="06123-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="06123-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="06123-110">Pre-requisites</span></span>

    - <span data-ttu-id="06123-111">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="06123-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="06123-112">Jupyter notebook</span><span class="sxs-lookup"><span data-stu-id="06123-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="06123-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="06123-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="06123-114">Telepítse a(z) `iqsharp` csomagot</span><span class="sxs-lookup"><span data-stu-id="06123-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="06123-115">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="06123-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="06123-116">Futtassa a következő parancsot a notebook-kiszolgáló elindításához:</span><span class="sxs-lookup"><span data-stu-id="06123-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="06123-117">A Jupyter Notebook megnyitásához másolja és illessze be a parancssorban megadott URL-címet a böngészőjébe.</span><span class="sxs-lookup"><span data-stu-id="06123-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="06123-118">Hozzon létre egy Jupyter Notebook Q # kernelrel, és adja hozzá a következő kódot az első jegyzetfüzet-cellához:</span><span class="sxs-lookup"><span data-stu-id="06123-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="06123-119">Futtassa a notebook következő celláját:</span><span class="sxs-lookup"><span data-stu-id="06123-119">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook cella Q # kóddal](~/media/install-guide-jupyter.png)

        <span data-ttu-id="06123-121">A cella kimenetében a következőnek kell megjelennie: `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="06123-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="06123-122">Ha Jupyter Notebook fut, a Q # kód le lesz fordítva, és a jegyzetfüzet a megtalált művelet (ek) nevét adja meg.</span><span class="sxs-lookup"><span data-stu-id="06123-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="06123-123">Egy új cellában hajtsa végre az imént létrehozott műveletet (szimulátorban) a következő `%simulate` paranccsal:</span><span class="sxs-lookup"><span data-stu-id="06123-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook cella% szimulálása mágia](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="06123-125">A képernyőn megjelenő üzenetnek a meghívott művelet eredményével együtt kell megjelennie (itt látható az üres rekord, mert a `()` műveletünk egyszerűen egy `Unit` típust ad vissza).</span><span class="sxs-lookup"><span data-stu-id="06123-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="06123-126">További lépések</span><span class="sxs-lookup"><span data-stu-id="06123-126">Next steps</span></span>

<span data-ttu-id="06123-127">Most, hogy telepítette a QDK a Q # Jupyter-jegyzetfüzetekhez, megírhatja és futtathatja [első Quantum programját](xref:microsoft.quantum.quickstarts.qrng) úgy, hogy a q # kódját közvetlenül a Jupyter notebook-környezetbe írja.</span><span class="sxs-lookup"><span data-stu-id="06123-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="06123-128">A Q # Jupyter notebookokkal kapcsolatos további példákért tekintse meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="06123-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="06123-129">[Bevezetés a Q # és a Jupyter notebookba](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="06123-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="06123-130">Itt egy Q # Jupyter Notebook jelenik meg, amely bemutatja, hogyan használható a Q # ebben a környezetben.</span><span class="sxs-lookup"><span data-stu-id="06123-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="06123-131">[Quantum katas](xref:microsoft.quantum.overview.katas), a saját ütemben elsajátított oktatóanyagok és a Q # Jupyter jegyzetfüzetek formájában elérhető programozási gyakorlatok gyűjteménye.</span><span class="sxs-lookup"><span data-stu-id="06123-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="06123-132">A [Quantum katas oktatóanyagának notebookja](https://github.com/microsoft/QuantumKatas#tutorial-topics) jó kiindulási pont.</span><span class="sxs-lookup"><span data-stu-id="06123-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="06123-133">A Quantum katas célja, hogy egy időben megtanítsa a Quantum Computing és a Q # programozási elemeit.</span><span class="sxs-lookup"><span data-stu-id="06123-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="06123-134">Kiváló példa arra, hogy milyen típusú tartalmat hozhat létre a Q # Jupyter notebookokkal.</span><span class="sxs-lookup"><span data-stu-id="06123-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
