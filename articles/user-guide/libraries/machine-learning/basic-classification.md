---
title: Alapszintű besorolás a Quantum Machine Learning könyvtárral
description: Megtudhatja, hogyan hajtható végre a Q# Microsoft QDK quantum Machine learning könyvtára használatával írt Quantum szekvenciális osztályozó.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: f9c3e7ab85c0f0d1a6063e593607d35c5cb76936
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868967"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="4af8b-103">Alapszintű besorolás: adatok osztályozása a QDK</span><span class="sxs-lookup"><span data-stu-id="4af8b-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="4af8b-104">Ebből a rövid útmutatóból megtudhatja, hogyan hajtható végre a Q# QDK quantum Machine learning könyvtárának használatával írt Quantum szekvenciális osztályozó.</span><span class="sxs-lookup"><span data-stu-id="4af8b-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="4af8b-105">Ebben az útmutatóban a Half-moon adatkészletet fogjuk használni a ben definiált osztályozó szerkezet használatával Q# .</span><span class="sxs-lookup"><span data-stu-id="4af8b-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4af8b-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="4af8b-106">Prerequisites</span></span>

- <span data-ttu-id="4af8b-107">A Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="4af8b-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="4af8b-108">Hozzon létre egy Q# projektet egy [Python-gazda programhoz](xref:microsoft.quantum.install.python) vagy egy [C#-gazdagéphez](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="4af8b-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="4af8b-109">Gazda program</span><span class="sxs-lookup"><span data-stu-id="4af8b-109">Host program</span></span>

<span data-ttu-id="4af8b-110">A gazda program három részből áll:</span><span class="sxs-lookup"><span data-stu-id="4af8b-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="4af8b-111">Töltse be az adatkészletet, és válassza ki a modell kezdő paramétereinek készletét.</span><span class="sxs-lookup"><span data-stu-id="4af8b-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="4af8b-112">Képzés végrehajtása a modell paramétereinek és torzításának meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="4af8b-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="4af8b-113">A modell ellenőrzése a pontosság megállapításához</span><span class="sxs-lookup"><span data-stu-id="4af8b-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="4af8b-114">Python a Visual Studio Code-dal vagy a parancssorból</span><span class="sxs-lookup"><span data-stu-id="4af8b-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="4af8b-115">A Q# Python-beli osztályozó futtatásához mentse a következő kódot `host.py` .</span><span class="sxs-lookup"><span data-stu-id="4af8b-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="4af8b-116">Ne feledje, hogy az Q# `Training.qs` oktatóanyag későbbi részében ismertetett fájlra is szüksége lesz.</span><span class="sxs-lookup"><span data-stu-id="4af8b-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="4af8b-117">Ezután a parancssorból futtathatja a Python-gazdaprogramot:</span><span class="sxs-lookup"><span data-stu-id="4af8b-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="4af8b-118">C# a Visual Studio Code-dal vagy a parancssorból</span><span class="sxs-lookup"><span data-stu-id="4af8b-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="4af8b-119">A Q# C#-beli osztályozó futtatásához mentse a következő kódot `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="4af8b-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="4af8b-120">Ne feledje, hogy az Q# `Training.qs` oktatóanyag későbbi részében ismertetett fájlra is szüksége lesz.</span><span class="sxs-lookup"><span data-stu-id="4af8b-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="4af8b-121">Ezután a parancssorból futtathatja a C#-gazdaprogramot:</span><span class="sxs-lookup"><span data-stu-id="4af8b-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="4af8b-122">C# a Visual Studio 2019-cel</span><span class="sxs-lookup"><span data-stu-id="4af8b-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="4af8b-123">Ha az új programot a C# használatával szeretné futtatni a Q# Visual Studióban, módosítsa `Host.cs` a következő C#-kód befoglalásával.</span><span class="sxs-lookup"><span data-stu-id="4af8b-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="4af8b-124">Ne feledje, hogy az Q# `Training.qs` oktatóanyag későbbi részében ismertetett fájlra is szüksége lesz.</span><span class="sxs-lookup"><span data-stu-id="4af8b-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="4af8b-125">Ezután nyomja le az F5 billentyűt, így a program elkezdi a végrehajtást, és megjelenik egy új előugró ablak a következő eredményekkel:</span><span class="sxs-lookup"><span data-stu-id="4af8b-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="4af8b-126">Q \# besorolási kód</span><span class="sxs-lookup"><span data-stu-id="4af8b-126">Q\# classifier code</span></span>

<span data-ttu-id="4af8b-127">Most nézzük meg, hogyan vannak meghatározva a gazda program által meghívott műveletek a következőben: Q# .</span><span class="sxs-lookup"><span data-stu-id="4af8b-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="4af8b-128">A következő kódot menti egy nevű fájlba `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="4af8b-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="4af8b-129">A fenti kódban meghatározott legfontosabb funkciók és műveletek a következők:</span><span class="sxs-lookup"><span data-stu-id="4af8b-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="4af8b-130">`ClassifierStructure() : ControlledRotation[]`: ebben a függvényben az áramköri modell felépítését úgy állítjuk be, hogy hozzáadja az ellenőrzött kapuk rétegeit.</span><span class="sxs-lookup"><span data-stu-id="4af8b-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="4af8b-131">Ez a lépés egy szekvenciális, mélyebb tanulási modellben található neuronok rétegeinek deklarációját hasonlítja.</span><span class="sxs-lookup"><span data-stu-id="4af8b-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="4af8b-132">`TrainHalfMoonModel() : (Double[], Double)`: Ez a művelet a kód legfontosabb része, és meghatározza a képzést.</span><span class="sxs-lookup"><span data-stu-id="4af8b-132">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="4af8b-133">Itt betöltjük a mintákat a könyvtárban található adatkészletből, beállítjuk a Hyper-paramétereket és a betanítás kezdeti paramétereit, és elindítjuk a képzést a könyvtárban található művelet meghívásával `TrainSequentialClassifier` .</span><span class="sxs-lookup"><span data-stu-id="4af8b-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="4af8b-134">Megjeleníti a paramétereket és a torzítást, amely meghatározza az osztályozó.</span><span class="sxs-lookup"><span data-stu-id="4af8b-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="4af8b-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Ez a művelet meghatározza a modell kiértékelésének ellenőrzési folyamatát.</span><span class="sxs-lookup"><span data-stu-id="4af8b-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="4af8b-136">Itt betöltjük a mintákat az ellenőrzéshez, a mintavételezések számát és a tűréshatárt.</span><span class="sxs-lookup"><span data-stu-id="4af8b-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="4af8b-137">Az érvényesítéshez a kiválasztott kötegben a téves besorolások számát adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="4af8b-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4af8b-138">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="4af8b-138">Next steps</span></span>

<span data-ttu-id="4af8b-139">Először is játszhat a kóddal, és megpróbálhat módosítani néhány paramétert, hogy megtudja, hogyan befolyásolja a képzést.</span><span class="sxs-lookup"><span data-stu-id="4af8b-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="4af8b-140">Ezután a következő oktatóanyagban [tervezze meg saját besorolását](xref:microsoft.quantum.libraries.machine-learning.design), és Ismerje meg, hogyan határozhatja meg az osztályozó szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="4af8b-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
