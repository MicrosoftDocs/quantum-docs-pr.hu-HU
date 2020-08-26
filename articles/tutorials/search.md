---
title: A saját keresési algoritmusának futtatása a Q# Quantum Development Kit-ben
description: Hozzon létre egy Q# projektet, amely bemutatja a a "a" és a "a" típusú, kanonikus algoritmusok egyikét.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: f2ae56bdca893e8a317c16d0a993da15b9f021b5
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863119"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="e6c7b-103">Oktatóanyag: A keresési Grover-algoritmus implementálása Q#-ban\#</span><span class="sxs-lookup"><span data-stu-id="e6c7b-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="e6c7b-104">Ebből az oktatóanyagból megtudhatja, hogyan hozhat létre és futtathat Grover-keresést a strukturálatlan adatok keresésének felgyorsításához.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="e6c7b-105">A a a legelterjedtebb kvantummechanika-algoritmusok egyike, és ez a viszonylag kis megvalósítás számos előnyt jelent a kvantum Q# -megoldások magas szintű kvantum-programozási nyelvvel való programozásának számos előnye, Q# hogy kifejezze a kvantum-algoritmusokat.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="e6c7b-106">Az útmutató végén találja annak bemutatását, hogy a szimulációkimenet hogyan talál meg sikeresen egy sztringet egy rendezetlen bejegyzéslistában annak az időnek a töredéke alatt, amennyi a teljes lista klasszikus számítógépen történő áttekintéséhez kellene.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="e6c7b-107">Grover algoritmusa egy strukturálatlan adatlistában keres bizonyos tételeket.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="e6c7b-108">Választ adhat például a következő kérdésre: A kártyapakliból húzott kártya egy kőr ász?</span><span class="sxs-lookup"><span data-stu-id="e6c7b-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="e6c7b-109">Az adott tétel címkéjét _megjelölt bemenetnek_ hívják.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="e6c7b-110">Grover keresési algoritmusát felhasználva egy kvantumszámítógép garantáltan kevesebb lépésből futtatja a keresést, mint ahány tételből áll a keresendő lista – erre egy átlagos algoritmus nem képes.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="e6c7b-111">A sebességnövekedés elhanyagolható egy kártyapakli esetében; több millió vagy több milliárd tételt tartalmazó listák esetében azonban már számottevő.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="e6c7b-112">Grover keresési algoritmusát néhány sornyi kóddal megírhatja.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6c7b-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e6c7b-113">Prerequisites</span></span>

- <span data-ttu-id="e6c7b-114">A Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="e6c7b-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="e6c7b-115">Mit csinál pontosan Grover keresési algoritmusa?</span><span class="sxs-lookup"><span data-stu-id="e6c7b-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="e6c7b-116">Grover algoritmusa rákérdez, hogy a lista egyik tétele az-e, amelyet keresünk.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="e6c7b-117">Ezt a lista indexeinek minden együtthatójára vagy valószínűségi amplitúdójára vetített kvantum-szuperpozíciójának összeállításával teszi, ami annak a valószínűségét mutatja, hogy az adott indexet keressük-e.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="e6c7b-118">Az algoritmus mozgatórugója az a két lépés, ami fokozatosan növeli a keresett index együtthatóját, amíg az együttható valószínűségi amplitúdója el nem éri az egyet.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="e6c7b-119">A fokozatos növekedések száma kevesebb, mint a lista tételeinek száma.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="e6c7b-120">Grover keresési algoritmusa ezért kevesebb lépésből hajtja végre a keresést, mint az átlagos algoritmusok.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover keresési algoritmusának funkcionális diagramja](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="e6c7b-122">A kód írása</span><span class="sxs-lookup"><span data-stu-id="e6c7b-122">Write the code</span></span>

1. <span data-ttu-id="e6c7b-123">A Quantum Development Kit használatával [hozzon létre egy új Q# projektet az alkalmazáshoz](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="e6c7b-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="e6c7b-124">A projektnek adja a következő címet: `Grover`.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="e6c7b-125">Az új projektjében adja a következő kódot az `Program.qs` fájlhoz:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="e6c7b-126">A keresendő lista meghatározásához hozzon létre egy új fájlt `Reflections.qs` néven, és illessze be a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="e6c7b-127">A `ReflectAboutMarked` művelet meghatározza az Ön által keresett megjelölt bemenetet, a nullák és egyek váltakozásából álló sztringet.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="e6c7b-128">Ez a minta szoftveresen rögzíti a megjelölt bemenetet, amely kiterjeszthető más bemenetek keresésére, vagy általánosítható bármilyen bemenetre.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="e6c7b-129">Ezután futtassa az új Q# programot, és keresse meg a által megjelölt elemet `ReflectAboutMarked` .</span><span class="sxs-lookup"><span data-stu-id="e6c7b-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="e6c7b-130">Q# alkalmazások Visual Studióval vagy Visual Studio Code-ban</span><span class="sxs-lookup"><span data-stu-id="e6c7b-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="e6c7b-131">A végrehajtható fájl a projekt konfigurációja és a parancssori lehetőségek függvényében egy szimulátoron vagy egy erőforrásbecslőn futtatja az `@EntryPoint()` attribútummal jelölt műveletet vagy függvényt.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="e6c7b-132">A szkript végrehajtásához egyszerűen nyomja le a Ctrl + F5 billentyűkombinációt a Visual Studióban.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="e6c7b-133">A VS Code-ban a `Program.qs` első alkalommal való összeállításához írja be az alábbiakat a terminálban:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="e6c7b-134">A későbbi futtatásokhoz az összeállítást nem kell megismételni.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="e6c7b-135">Futtatáshoz írja be a következő parancsot, majd nyomja le az Enter billentyűt:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="e6c7b-136">Ekkor a következő üzenetnek kell megjelennie a terminálon:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="e6c7b-137">Ennek az az oka, hogy nem adta meg a használni kívánt qubitek számát, így a terminál kínálja fel a végrehajtható fájlhoz elérhető parancsokat.</span><span class="sxs-lookup"><span data-stu-id="e6c7b-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="e6c7b-138">Ha 5 qubitet szeretnénk használni, a következőt írjuk be:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="e6c7b-139">Az Enter lenyomásakor a következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="e6c7b-140">További lépések</span><span class="sxs-lookup"><span data-stu-id="e6c7b-140">Next steps</span></span>

<span data-ttu-id="e6c7b-141">Ha ezt az oktatóanyagot élvezte, tekintse meg az alábbi források némelyikét, ha többet szeretne megtudni arról, hogyan használható a Q# saját kvantum-alkalmazások írására:</span><span class="sxs-lookup"><span data-stu-id="e6c7b-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="e6c7b-142">Vissza a QDK-val való ismerkedésről szóló útmutatóhoz</span><span class="sxs-lookup"><span data-stu-id="e6c7b-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="e6c7b-143">Egy általánosabb [példa](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) a keresési Grover-algoritmusra</span><span class="sxs-lookup"><span data-stu-id="e6c7b-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="e6c7b-144">A Grover-kereséssel és a Kvantum Katákkal kapcsolatos további információk</span><span class="sxs-lookup"><span data-stu-id="e6c7b-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="e6c7b-145">További információk a Grover keresési algoritmusa mögött álló kvantum-számítástechnikai technikával, az [amplitúdó-erősítéssel][amplitude-amplification] kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="e6c7b-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="e6c7b-146">Kvantum-számítástechnikai fogalmak</span><span class="sxs-lookup"><span data-stu-id="e6c7b-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="e6c7b-147">Példák a Quantum Development Kit használatára</span><span class="sxs-lookup"><span data-stu-id="e6c7b-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
