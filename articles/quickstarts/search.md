---
title: A keresési Grover-algoritmus futtatása Q#-ban – Quantum Development Kit
description: Állítson össze egy Q#-projektet, amely bemutatja a Grover-algoritmus, a bevett kvantumalgoritmusok egyikének működését.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443936"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="a421b-103">Gyorsútmutató: A keresési Grover-algoritmus implementálása Q#-ban</span><span class="sxs-lookup"><span data-stu-id="a421b-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="a421b-104">Ebből a gyorsútmutatóból megismerheti, hogyan hozhat létre és futtathat Grover-keresést a strukturálatlan adatok keresésének felgyorsításához.</span><span class="sxs-lookup"><span data-stu-id="a421b-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="a421b-105">A Grover-keresés az egyik legnépszerűbb kvantum-számítástechnikai algoritmus, és ebből a viszonylag kicsi Q#-implementációból megtapasztalhatja, hogy milyen előnyökkel jár a kvantummegoldások magas szintű Q# kvantumprogramozási nyelven történő programozása a kvantumalgoritmusok kifejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="a421b-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="a421b-106">Az útmutató végén találja annak bemutatását, hogy a szimulációkimenet hogyan talál meg sikeresen egy sztringet egy rendezetlen bejegyzéslistában annak az időnek a töredéke alatt, amennyi a teljes lista klasszikus számítógépen történő áttekintéséhez kellene.</span><span class="sxs-lookup"><span data-stu-id="a421b-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="a421b-107">Grover algoritmusa egy strukturálatlan adatlistában keres bizonyos tételeket.</span><span class="sxs-lookup"><span data-stu-id="a421b-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="a421b-108">Választ adhat például a következő kérdésre: A kártyapakliból húzott kártya egy kőr ász?</span><span class="sxs-lookup"><span data-stu-id="a421b-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="a421b-109">Az adott tétel címkéjét _megjelölt bemenetnek_ hívják.</span><span class="sxs-lookup"><span data-stu-id="a421b-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="a421b-110">Grover keresési algoritmusát felhasználva egy kvantumszámítógép garantáltan kevesebb lépésből futtatja a keresést, mint ahány tételből áll a keresendő lista – erre egy átlagos algoritmus nem képes.</span><span class="sxs-lookup"><span data-stu-id="a421b-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="a421b-111">A sebességnövekedés elhanyagolható egy kártyapakli esetében; több millió vagy több milliárd tételt tartalmazó listák esetében azonban már számottevő.</span><span class="sxs-lookup"><span data-stu-id="a421b-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="a421b-112">Grover keresési algoritmusát néhány sornyi kóddal megírhatja.</span><span class="sxs-lookup"><span data-stu-id="a421b-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a421b-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a421b-113">Prerequisites</span></span>

- <span data-ttu-id="a421b-114">A Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="a421b-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="a421b-115">Mit csinál pontosan Grover keresési algoritmusa?</span><span class="sxs-lookup"><span data-stu-id="a421b-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="a421b-116">Grover algoritmusa rákérdez, hogy a lista egyik tétele az-e, amelyet keresünk.</span><span class="sxs-lookup"><span data-stu-id="a421b-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="a421b-117">Ezt a lista indexeinek minden együtthatójára vagy valószínűségi amplitúdójára vetített kvantum-szuperpozíciójának összeállításával teszi, ami annak a valószínűségét mutatja, hogy az adott indexet keressük-e.</span><span class="sxs-lookup"><span data-stu-id="a421b-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="a421b-118">Az algoritmus mozgatórugója az a két lépés, ami fokozatosan növeli a keresett index együtthatóját, amíg az együttható valószínűségi amplitúdója el nem éri az egyet.</span><span class="sxs-lookup"><span data-stu-id="a421b-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="a421b-119">A fokozatos növekedések száma kevesebb, mint a lista tételeinek száma.</span><span class="sxs-lookup"><span data-stu-id="a421b-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="a421b-120">Grover keresési algoritmusa ezért kevesebb lépésből hajtja végre a keresést, mint az átlagos algoritmusok.</span><span class="sxs-lookup"><span data-stu-id="a421b-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover keresési algoritmusának funkcionális diagramja](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="a421b-122">A kód írása</span><span class="sxs-lookup"><span data-stu-id="a421b-122">Write the code</span></span>

1. <span data-ttu-id="a421b-123">A Quantum Development Kit használatával [hozzon létre egy új Q#-projektet](xref:microsoft.quantum.howto.createproject) `Grover` néven az Ön által választott fejlesztői környezetben.</span><span class="sxs-lookup"><span data-stu-id="a421b-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="a421b-124">Az új projektjében adja a következő kódot az `Operations.qs` fájlhoz:</span><span class="sxs-lookup"><span data-stu-id="a421b-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="a421b-125">A keresendő lista meghatározásához hozzon létre egy új fájlt `Reflections.qs` néven, és illessze be a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="a421b-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="a421b-126">A `ReflectAboutMarked` művelet meghatározza az Ön által keresett megjelölt bemenetet, a nullák és egyek váltakozásából álló sztringet.</span><span class="sxs-lookup"><span data-stu-id="a421b-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="a421b-127">Ez a minta szoftveresen rögzíti a megjelölt bemenetet, amely kiterjeszthető más bemenetek keresésére, vagy általánosítható bármilyen bemenetre.</span><span class="sxs-lookup"><span data-stu-id="a421b-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="a421b-128">Ezután futtassa új Q#-programját a `ReflectAboutMarked` által jelölt tétel megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="a421b-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="a421b-129">Python a Visual Studio Code-dal vagy a parancssorból</span><span class="sxs-lookup"><span data-stu-id="a421b-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="a421b-130">Mentse `host.py`-ként a következő kódot az új Q#-program Pythonból történő futtatásához:</span><span class="sxs-lookup"><span data-stu-id="a421b-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="a421b-131">Ezután a parancssorból futtathatja a Python-gazdaprogramot:</span><span class="sxs-lookup"><span data-stu-id="a421b-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="a421b-132">C# a Visual Studio Code-dal vagy a parancssorból</span><span class="sxs-lookup"><span data-stu-id="a421b-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="a421b-133">Adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ből:</span><span class="sxs-lookup"><span data-stu-id="a421b-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="a421b-134">Ezután a parancssorból futtathatja a C#-gazdaprogramot:</span><span class="sxs-lookup"><span data-stu-id="a421b-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="a421b-135">C# a Visual Studio 2019-cel</span><span class="sxs-lookup"><span data-stu-id="a421b-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="a421b-136">A Visual Studióban adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ból:</span><span class="sxs-lookup"><span data-stu-id="a421b-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="a421b-137">Ezután nyomja le az F5 billentyűt, így a program elkezdi a végrehajtást, és megjelenik egy új előugró ablak a következő eredményekkel:</span><span class="sxs-lookup"><span data-stu-id="a421b-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="a421b-138">A `ReflectAboutMarked` műveletet csak négyszer kellett lehívni, és a Q#-program képes volt megtalálni a „01010” bemenetet $2^{5} = 32$ lehetséges bemenet közül!</span><span class="sxs-lookup"><span data-stu-id="a421b-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="a421b-139">További lépések</span><span class="sxs-lookup"><span data-stu-id="a421b-139">Next steps</span></span>

<span data-ttu-id="a421b-140">Ha hasznosnak találta ezt a gyorsútmutatót, tekintsen meg néhányat a lenti források közül, amelyek azzal foglalkoznak, hogyan írhat saját kvantumalkalmazásokat a Q# segítségével:</span><span class="sxs-lookup"><span data-stu-id="a421b-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="a421b-141">Vissza a QDK-val való ismerkedésről szóló útmutatóhoz</span><span class="sxs-lookup"><span data-stu-id="a421b-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="a421b-142">Egy általánosabb [példa](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) a keresési Grover-algoritmusra</span><span class="sxs-lookup"><span data-stu-id="a421b-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="a421b-143">A Grover-kereséssel és a Kvantum Katákkal kapcsolatos további információk</span><span class="sxs-lookup"><span data-stu-id="a421b-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="a421b-144">További információk a Grover keresési algoritmusa mögött álló kvantum-számítástechnikai technikával, az [amplitúdó-erősítéssel](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification) kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="a421b-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="a421b-145">Kvantum-számítástechnikai fogalmak</span><span class="sxs-lookup"><span data-stu-id="a421b-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="a421b-146">Példák a Quantum Development Kit használatára</span><span class="sxs-lookup"><span data-stu-id="a421b-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
