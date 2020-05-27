---
title: Összefonódások megismerése Q# nyelven
description: Ismerje meg, hogyan írhat kvantumprogramot Q# nyelven. Bell-állapotot jelző alkalmazás fejlesztése a Quantum Development Kit (QDK) használatával
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 7836e39227fa2282c6e2faa039f6e625103d5403
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426848"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="74985-104">Oktatóanyag: Összefonódások megismerése Q\# nyelven</span><span class="sxs-lookup"><span data-stu-id="74985-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="74985-105">Ebben az oktatóanyagban bemutatjuk, hogyan írhat olyan Q# nyelvű programot, amely qubiteket manipulál és mér meg, valamint szemlélteti a szuperpozíció és az összefonódás hatásait.</span><span class="sxs-lookup"><span data-stu-id="74985-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="74985-106">Az útmutató végigvezet a QDK telepítésén, a program létrehozásán, majd a program kvantumszimulátoron való végrehajtásán.</span><span class="sxs-lookup"><span data-stu-id="74985-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="74985-107">Írni fog egy Bell nevű alkalmazást a kvantum-összefonódás szemléltetése céljából.</span><span class="sxs-lookup"><span data-stu-id="74985-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="74985-108">A Bell név a Bell-állapotokra utal. Ezek két qubit konkrét kvantumállapotát jelentik, amelyekkel szemléltethetők a szuperpozíció és a kvantum-összefonódás legegyszerűbb példái.</span><span class="sxs-lookup"><span data-stu-id="74985-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="74985-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="74985-109">Pre-requisites</span></span>

<span data-ttu-id="74985-110">Ha készen áll a kódolásra, először végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="74985-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="74985-111">[Telepítse](xref:microsoft.quantum.install) a Quantum Development Kitet a választott nyelven és fejlesztési környezetben.</span><span class="sxs-lookup"><span data-stu-id="74985-111">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment</span></span>
* <span data-ttu-id="74985-112">Ha a QDK már telepítve van, győződjön meg arról, hogy a legújabb verzióra van [frissítve](xref:microsoft.quantum.update).</span><span class="sxs-lookup"><span data-stu-id="74985-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="74985-113">A leírást a QDK telepítése nélkül is követheti, hogy áttekintést kapjon a Q# programozási nyelvről és a kvantum-számítástechnika alapvető koncepcióiról.</span><span class="sxs-lookup"><span data-stu-id="74985-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="74985-114">A qubitek viselkedésének szemléltetése a Q# segítségével</span><span class="sxs-lookup"><span data-stu-id="74985-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="74985-115">Emlékezzen vissza a [qubit egyszerű definíciójára](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="74985-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="74985-116">Míg a hagyományos bit egyetlen bináris értéket hordoz, ami 0 vagy 1 lehet, a qubit állapota egyszerre lehet a 0 és az 1 érték közötti **szuperpozícióban**.</span><span class="sxs-lookup"><span data-stu-id="74985-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  <span data-ttu-id="74985-117">Alapjában véve a qubit úgy képzelhető el, mint egy térbeli irány (más néven vektor).</span><span class="sxs-lookup"><span data-stu-id="74985-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="74985-118">A qubitek bármilyen lehetséges irányba mutathatnak.</span><span class="sxs-lookup"><span data-stu-id="74985-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="74985-119">A két **klasszikus állapot** az a két irány, amelyek a 0 érték mérésének 100%-os esélyét és az 1 érték mérésének 100%-os esélyét jelentik.</span><span class="sxs-lookup"><span data-stu-id="74985-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="74985-120">Ennek a megjelenítésnek a formálisabb vizualizációja a [Bloch-gömb](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="74985-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>


<span data-ttu-id="74985-121">A mérés ténye egy bináris eredményt ad, és megváltoztatja a qubit állapotát.</span><span class="sxs-lookup"><span data-stu-id="74985-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="74985-122">A mérés egy bináris eredményt ad, amely 0 vagy 1 lehet.</span><span class="sxs-lookup"><span data-stu-id="74985-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="74985-123">A qubit a szuperpozícióból (amely bármilyen irányú lehet) az egyik klasszikus állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="74985-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="74985-124">Ezt követően ugyanannak a mérésnek a megismétlése – ha időközben nem végeztünk el semmilyen más műveletet – ugyanazt a bináris eredményt adja.</span><span class="sxs-lookup"><span data-stu-id="74985-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="74985-125">Több qubit **össze is fonható**.</span><span class="sxs-lookup"><span data-stu-id="74985-125">Multiple qubits can be **entangled**.</span></span> <span data-ttu-id="74985-126">Ha az összefonódott qubitek egyikéről mérést készítünk, a másik/többi állapotáról is információt kapunk.</span><span class="sxs-lookup"><span data-stu-id="74985-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="74985-127">Most már készen állunk annak szemléltetésére, hogy a Q# hogyan fejezi ki ezt a viselkedést.</span><span class="sxs-lookup"><span data-stu-id="74985-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="74985-128">A lehető legegyszerűbb programmal kezd, és azt építi fel a kvantum-szuperpozíció és a kvantum-összefonódás bemutatásához.</span><span class="sxs-lookup"><span data-stu-id="74985-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="74985-129">Telepítés</span><span class="sxs-lookup"><span data-stu-id="74985-129">Setup</span></span>

<span data-ttu-id="74985-130">A Microsoft Quantum Development Kittel fejlesztett alkalmazások két részből állnak:</span><span class="sxs-lookup"><span data-stu-id="74985-130">Applications developed with Microsoft's Quantum Development Kit consist of two parts:</span></span>

1. <span data-ttu-id="74985-131">Egy vagy több kvantumalgoritmusból, amelyek a Q# kvantumprogramozási nyelvvel lettek implementálva.</span><span class="sxs-lookup"><span data-stu-id="74985-131">One or more quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="74985-132">Egy gazdaprogramból, amely a Pythonhoz vagy C#-hoz hasonló programozási nyelven van implementálva, és amely a fő belépési pontként szolgál, valamint Q#-műveleteket hív meg egy kvantumalgoritmus végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="74985-132">A host program, implemented in a programming language like Python or C# that serves as the main entry point and invokes Q# operations to execute a quantum algorithm.</span></span>

#### <a name="python"></a>[<span data-ttu-id="74985-133">Python</span><span class="sxs-lookup"><span data-stu-id="74985-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="74985-134">Válasszon egy helyet az alkalmazásnak</span><span class="sxs-lookup"><span data-stu-id="74985-134">Choose a location for your application</span></span>

1. <span data-ttu-id="74985-135">Hozzon létre egy `Bell.qs` nevű fájlt.</span><span class="sxs-lookup"><span data-stu-id="74985-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="74985-136">Ez a fájl fogja tartalmazni a Q#-kódot.</span><span class="sxs-lookup"><span data-stu-id="74985-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="74985-137">Hozzon létre egy `host.py` nevű fájlt.</span><span class="sxs-lookup"><span data-stu-id="74985-137">Create a file called `host.py`.</span></span> <span data-ttu-id="74985-138">Ez a fájl fogja tartalmazni a Python-gazdakódot.</span><span class="sxs-lookup"><span data-stu-id="74985-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="74985-139">C#-parancssor</span><span class="sxs-lookup"><span data-stu-id="74985-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="74985-140">Új Q#-projekt létrehozása:</span><span class="sxs-lookup"><span data-stu-id="74985-140">Create a new Q# project:</span></span>

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="74985-141">Látható egy `.csproj` fájl, egy `Operations.qs` nevű Q#-fájl és egy `Driver.cs` nevű gazdaprogramot</span><span class="sxs-lookup"><span data-stu-id="74985-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="74985-142">A Q#-fájl átnevezése</span><span class="sxs-lookup"><span data-stu-id="74985-142">Rename the Q# file</span></span>

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="74985-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74985-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="74985-144">Új projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="74985-144">Create a new project</span></span>

   * <span data-ttu-id="74985-145">A Visual Studio megnyitása</span><span class="sxs-lookup"><span data-stu-id="74985-145">Open Visual Studio</span></span>
   * <span data-ttu-id="74985-146">Lépjen a **Fájl** menübe, és válassza az **Új** -> **Projekt...** elemet.</span><span class="sxs-lookup"><span data-stu-id="74985-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="74985-147">A projektsablon intézőjében írja be a keresőmezőbe a(z) `Q#` kifejezést, majd válassza ki a(z) `Q# Application` sablont</span><span class="sxs-lookup"><span data-stu-id="74985-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="74985-148">Adja a projektnek a `Bell` nevet</span><span class="sxs-lookup"><span data-stu-id="74985-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="74985-149">A Q#-fájl átnevezése</span><span class="sxs-lookup"><span data-stu-id="74985-149">Rename the Q# file</span></span>

   * <span data-ttu-id="74985-150">Lépjen a **Megoldáskezelőbe**</span><span class="sxs-lookup"><span data-stu-id="74985-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="74985-151">Kattintson a jobb gombbal az `Operations.qs` fájlra</span><span class="sxs-lookup"><span data-stu-id="74985-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="74985-152">Nevezze át `Bell.qs` névre</span><span class="sxs-lookup"><span data-stu-id="74985-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="74985-153">Q#-művelet írása</span><span class="sxs-lookup"><span data-stu-id="74985-153">Write a Q# operation</span></span>

<span data-ttu-id="74985-154">A célunk, hogy előkészítsünk két adott kvantumállapotú qubitet, és ezzel bemutassuk, hogyan módosítható a Q# használatával a qubitek állapota, és hogyan szemléltethetők a szuperpozíció és az összefonódás hatásai.</span><span class="sxs-lookup"><span data-stu-id="74985-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="74985-155">Ezt darabonként fogjuk felépíteni a qubitek állapotának, műveleteinek és méréseinek bemutatása érdekében.</span><span class="sxs-lookup"><span data-stu-id="74985-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="74985-156">**Áttekintés:**  Az alább látható első kódban bemutatjuk, hogyan használható a Q# a qubitekhez.</span><span class="sxs-lookup"><span data-stu-id="74985-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="74985-157">Bemutatunk két műveletet – `M` és `X` –, amelyek átalakítják a qubitek állapotát.</span><span class="sxs-lookup"><span data-stu-id="74985-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="74985-158">Ebben a kódrészletben meghatározunk egy `Set` műveletet, amelynek egyik paramétere egy qubit, a másik pedig a `desired`, amely a qubit kívánt állapotát jelöli.</span><span class="sxs-lookup"><span data-stu-id="74985-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="74985-159">A `Set` művelet elvégez egy mérést a qubiten az `M` művelet használatával.</span><span class="sxs-lookup"><span data-stu-id="74985-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="74985-160">A Q# használatakor a qubitek mérése mindig vagy `Zero` vagy `One` értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="74985-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="74985-161">Ha a mérés által visszaadott érték nem egyenlő semelyik kívánt értékkel, a Set „megfordítja” a qubitet. Ez azt jelenti, hogy végrehajt egy `X` műveletet, amely módosítja a qubit állapotát, és az új állapotban megfordul annak a valószínűsége, hogy a mérés `Zero` vagy `One` értéket adjon vissza.</span><span class="sxs-lookup"><span data-stu-id="74985-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="74985-162">Ezután a `Set` művelet hatásának szemléltetésére a rendszer hozzáad egy `TestBellState` műveletet.</span><span class="sxs-lookup"><span data-stu-id="74985-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="74985-163">Ennek a műveletnek a bemenete egy `Zero` vagy `One`. A művelet néhányszor meghívja a `Set` műveletet ezzel a bemenettel, és megszámolja, hogy a qubit mérése hányszor adott `Zero`, és hányszor `One` eredményt.</span><span class="sxs-lookup"><span data-stu-id="74985-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="74985-164">Természetesen a `TestBellState` művelet első szimulációjától egy olyan kimenetet várunk, amely azt mutatja, hogy minden `Zero` bemeneti paraméterrel rendelkező qubit a `Zero` eredményt adja vissza, és minden `One` bemeneti paraméterrel rendelkező qubit az `One` eredményt.</span><span class="sxs-lookup"><span data-stu-id="74985-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="74985-165">Később az `TestBellState` művelethez további kódot adunk hozzá a szuperpozíció és az összefonódás szemléltetése céljából.</span><span class="sxs-lookup"><span data-stu-id="74985-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="74985-166">Q#-műveletkód</span><span class="sxs-lookup"><span data-stu-id="74985-166">Q# operation code</span></span>

1. <span data-ttu-id="74985-167">Cserélje le a Bell.qs fájl tartalmát a következő kódra:</span><span class="sxs-lookup"><span data-stu-id="74985-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="74985-168">Most már meghívható ez a művelet, hogy egy qubitet egy klasszikus állapotba állítson, és az esetek 100%-ában kizárólag `Zero` vagy `One` eredményt adjon vissza.</span><span class="sxs-lookup"><span data-stu-id="74985-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="74985-169">A `Zero` és az `One` állandók, amelyek a qubit mérésének két lehetséges eredményét jelölik.</span><span class="sxs-lookup"><span data-stu-id="74985-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="74985-170">A `Set` művelet elvégzi a qubit mérését.</span><span class="sxs-lookup"><span data-stu-id="74985-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="74985-171">Ha a qubit a kívánt állapotban van, a `Set` művelet békén hagyja. Ha nem, akkor pedig végrehajtja az `X` műveletet, amely a kívánt állapotba állítja a qubitet.</span><span class="sxs-lookup"><span data-stu-id="74985-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="74985-172">A Q#-műveletek bemutatása</span><span class="sxs-lookup"><span data-stu-id="74985-172">About Q# operations</span></span>

<span data-ttu-id="74985-173">A Q#-műveletek kvantum-alrutinok.</span><span class="sxs-lookup"><span data-stu-id="74985-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="74985-174">Vagyis meghívható rutinok, amelyek kvantumműveleteket tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="74985-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="74985-175">A műveletek argumentumai rekordként vannak meghatározva, zárójelek között.</span><span class="sxs-lookup"><span data-stu-id="74985-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="74985-176">A művelet visszatérési típusa a kettőspont után van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="74985-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="74985-177">Ebben az esetben a `Set` művelet nem ad vissza semmit, ezért a jelölése a következőt adja vissza: `Unit`.</span><span class="sxs-lookup"><span data-stu-id="74985-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="74985-178">Ez a Q# nyelvű megfelelője az F# `unit` elemének, amely nagyjából hasonló a C# `void` és eleméhez a Python üres rekordjaihoz (`Tuple[()]`).</span><span class="sxs-lookup"><span data-stu-id="74985-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="74985-179">Az első Q#-műveletben két kvantumműveletet használt:</span><span class="sxs-lookup"><span data-stu-id="74985-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="74985-180">Az [M](xref:microsoft.quantum.intrinsic.m) műveletet, amely megméri a qubit állapotát</span><span class="sxs-lookup"><span data-stu-id="74985-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="74985-181">Az [X](xref:microsoft.quantum.intrinsic.x) műveletet, amely átállítja a qubit állapotát</span><span class="sxs-lookup"><span data-stu-id="74985-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="74985-182">A kvantumműveletek átalakítják a qubitek állapotát.</span><span class="sxs-lookup"><span data-stu-id="74985-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="74985-183">Bizonyos esetekben a hagyományos logikai kapuk mintájára szokás kvantumkapukat emlegetni műveletek helyett.</span><span class="sxs-lookup"><span data-stu-id="74985-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="74985-184">Ez a szokás a kvantum-számítástechnika korai időszakából ered, amikor az algoritmusok még csupán elméleti fogalmak voltak, és diagramként vizualizálták őket, hasonlóan a klasszikus számítástechnikában használt kapcsolási rajzokhoz.</span><span class="sxs-lookup"><span data-stu-id="74985-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="74985-185">Q#-tesztkód hozzáadása</span><span class="sxs-lookup"><span data-stu-id="74985-185">Add Q# test code</span></span>

1. <span data-ttu-id="74985-186">Adja hozzá az alábbi műveletet a `Set` fájlhoz, a névtéren belül, a `Bell.qs` művelet végén:</span><span class="sxs-lookup"><span data-stu-id="74985-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="74985-187">Ennek a műveletnek (`TestBellState`) `count` iterációja ismétlődik, beállít egy megadott `initial` értéket egy qubiten, majd megméri (`M`) az eredményt.</span><span class="sxs-lookup"><span data-stu-id="74985-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="74985-188">Statisztikát gyűjt arról, hogy hány nulla és egy értéket mért, és visszaküldi őket a hívónak.</span><span class="sxs-lookup"><span data-stu-id="74985-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="74985-189">Még egy szükséges műveletet végrehajt.</span><span class="sxs-lookup"><span data-stu-id="74985-189">It performs one other necessary operation.</span></span> <span data-ttu-id="74985-190">Visszaállítja a qubitet egy ismert állapotra (`Zero`), mielőtt visszaadja, hogy mások is lefoglalhassák ezt a qubitet egy ismert állapotban.</span><span class="sxs-lookup"><span data-stu-id="74985-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="74985-191">Ez a `using` utasítás miatt szükséges.</span><span class="sxs-lookup"><span data-stu-id="74985-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="74985-192">A Q# nyelvű változók bemutatása</span><span class="sxs-lookup"><span data-stu-id="74985-192">About variables in Q#</span></span>

<span data-ttu-id="74985-193">A Q# változói alapértelmezés szerint nem módosíthatók; a kötésük után nem változtatható az értékük.</span><span class="sxs-lookup"><span data-stu-id="74985-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="74985-194">A nem módosítható változók kötése a `let` kulcsszóval jelölhető.</span><span class="sxs-lookup"><span data-stu-id="74985-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="74985-195">A műveleti argumentumok soha nem módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="74985-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="74985-196">Ha olyan változóra van szüksége, amelynek értéke módosítható (mint a `numOnes` a fenti példában), a `mutable` kulcsszóval deklarálhatja a változót.</span><span class="sxs-lookup"><span data-stu-id="74985-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="74985-197">A módosítható változók értéke a `set` utasítással módosítható.</span><span class="sxs-lookup"><span data-stu-id="74985-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="74985-198">A változó típusát mindkét esetben a fordító következteti ki.</span><span class="sxs-lookup"><span data-stu-id="74985-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="74985-199">A Q#-ban nincs szükség a változók jegyzetekkel való ellátására.</span><span class="sxs-lookup"><span data-stu-id="74985-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="74985-200">A Q# nyelvű `using` utasítások bemutatása</span><span class="sxs-lookup"><span data-stu-id="74985-200">About `using` statements in Q#</span></span>

<span data-ttu-id="74985-201">A `using` utasítás szintén a Q# nyelvre jellemző.</span><span class="sxs-lookup"><span data-stu-id="74985-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="74985-202">Ezzel foglalhatók le qubitek a kódblokkokhoz.</span><span class="sxs-lookup"><span data-stu-id="74985-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="74985-203">A Q#-ban az összes qubit lefoglalása és felszabadítása dinamikusan történik, tehát nem rögzített erőforrások, amelyek az összetett algoritmusok teljes élettartamára érvényesek.</span><span class="sxs-lookup"><span data-stu-id="74985-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="74985-204">A `using` utasítás a blokk elején foglal le qubiteket, és a blokk végén felszabadítja őket.</span><span class="sxs-lookup"><span data-stu-id="74985-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="74985-205">A gazdaalkalmazás kódjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="74985-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="74985-206">Python</span><span class="sxs-lookup"><span data-stu-id="74985-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="74985-207">Nyissa meg a `host.py` fájlt, és adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="74985-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="74985-208">C#</span><span class="sxs-lookup"><span data-stu-id="74985-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="74985-209">Cserélje le a `Driver.cs` fájl tartalmát a következő kódra:</span><span class="sxs-lookup"><span data-stu-id="74985-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="74985-210">A gazdaalkalmazás kódjának ismertetése</span><span class="sxs-lookup"><span data-stu-id="74985-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="74985-211">Python</span><span class="sxs-lookup"><span data-stu-id="74985-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="74985-212">A Python-gazdaalkalmazás három részből áll:</span><span class="sxs-lookup"><span data-stu-id="74985-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="74985-213">A kvantumalgoritmushoz szükséges összes argumentum kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="74985-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="74985-214">A példában a `count` 1000 értéken van rögzítve, és az `initial` a qubit kezdeti értéke.</span><span class="sxs-lookup"><span data-stu-id="74985-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="74985-215">A kvantumalgoritmus futtatása az importált Q#-művelet `simulate()` metódusának meghívásával.</span><span class="sxs-lookup"><span data-stu-id="74985-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="74985-216">A művelet eredményének feldolgozása.</span><span class="sxs-lookup"><span data-stu-id="74985-216">Process the result of the operation.</span></span> <span data-ttu-id="74985-217">A példában a `res` kapja a művelet eredményét.</span><span class="sxs-lookup"><span data-stu-id="74985-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="74985-218">Itt az eredmény a nullák (`num_zeros`) és egyesek (`num_ones`) szimulátor által mért számának a rekordja.</span><span class="sxs-lookup"><span data-stu-id="74985-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="74985-219">A rekordot két mezőre bontjuk, és kiíratjuk az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="74985-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="74985-220">C#</span><span class="sxs-lookup"><span data-stu-id="74985-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="74985-221">A C#-gazdaalkalmazás négy részből áll:</span><span class="sxs-lookup"><span data-stu-id="74985-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="74985-222">Kvantumszimulátor létrehozása.</span><span class="sxs-lookup"><span data-stu-id="74985-222">Construct a quantum simulator.</span></span> <span data-ttu-id="74985-223">A példában a `qsim` a szimulátor.</span><span class="sxs-lookup"><span data-stu-id="74985-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="74985-224">A kvantumalgoritmushoz szükséges összes argumentum kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="74985-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="74985-225">A példában a `count` 1000 értéken van rögzítve, és az `initial` a qubit kezdeti értéke.</span><span class="sxs-lookup"><span data-stu-id="74985-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="74985-226">A kvantumalgoritmus futtatása.</span><span class="sxs-lookup"><span data-stu-id="74985-226">Run the quantum algorithm.</span></span> <span data-ttu-id="74985-227">Mindegyik Q#-művelet létrehoz egy azonos nevű C#-osztályt.</span><span class="sxs-lookup"><span data-stu-id="74985-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="74985-228">Ez az osztály olyan `Run` metódussal rendelkezik, amely **aszinkron módon** hajtja végre a műveletet.</span><span class="sxs-lookup"><span data-stu-id="74985-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="74985-229">A végrehajtás azért aszinkron módú, mert a tényleges hardveren végzett végrehajtás aszinkron módon fog történni.</span><span class="sxs-lookup"><span data-stu-id="74985-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="74985-230">Mivel a `Run` metódus aszinkron módú, lekérjük a `Result` tulajdonságot; ez a feladat befejezéséig blokkolja a végrehajtást, és az eredményt szinkron módon adja vissza.</span><span class="sxs-lookup"><span data-stu-id="74985-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="74985-231">A művelet eredményének feldolgozása.</span><span class="sxs-lookup"><span data-stu-id="74985-231">Process the result of the operation.</span></span> <span data-ttu-id="74985-232">A példában a `res` kapja a művelet eredményét.</span><span class="sxs-lookup"><span data-stu-id="74985-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="74985-233">Itt az eredmény a nullák (`numZeros`) és egyesek (`numOnes`) szimulátor által mért számának a rekordja.</span><span class="sxs-lookup"><span data-stu-id="74985-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="74985-234">A rendszer ezt értékrekordként adja vissza C# nyelven.</span><span class="sxs-lookup"><span data-stu-id="74985-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="74985-235">A rekordot két mezőre bontjuk, kiíratjuk az eredményeket, és megvárunk egy billentyűlenyomást.</span><span class="sxs-lookup"><span data-stu-id="74985-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="74985-236">Buildelés és futtatás</span><span class="sxs-lookup"><span data-stu-id="74985-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="74985-237">Python</span><span class="sxs-lookup"><span data-stu-id="74985-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="74985-238">A terminálon futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="74985-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="74985-239">Ez a parancs futtatja a gazdaalkalmazást, amely a Q#-műveletet szimulálja.</span><span class="sxs-lookup"><span data-stu-id="74985-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="74985-240">A következő eredmények jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="74985-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="74985-241">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="74985-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="74985-242">A terminálon futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="74985-242">Run the following at your terminal:</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="74985-243">Ez a parancs automatikusan letölti az összes szükséges csomagot, buildeli az alkalmazást, majd futtatja a parancssorban.</span><span class="sxs-lookup"><span data-stu-id="74985-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="74985-244">Vagy nyomja le az **F1** billentyűt a Parancspaletta megnyitásához, és válassza a **Hibakeresés: Indítás hibakeresés nélkül** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74985-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="74985-245">A rendszer kérheti egy új ``launch.json`` fájl létrehozását, amely leírja a program indításának módját.</span><span class="sxs-lookup"><span data-stu-id="74985-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="74985-246">Az alapértelmezett ``launch.json`` fájl a legtöbb alkalmazással megfelelően működik.</span><span class="sxs-lookup"><span data-stu-id="74985-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="74985-247">A következő eredmények jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="74985-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="74985-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74985-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="74985-249">Csak nyomja le az `F5` billentyűt, és a program létrejön és fut!</span><span class="sxs-lookup"><span data-stu-id="74985-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="74985-250">A következő eredmények jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="74985-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="74985-251">Egy billentyű lenyomása után a program bezárul.</span><span class="sxs-lookup"><span data-stu-id="74985-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="74985-252">Szuperpozíció előkészítése</span><span class="sxs-lookup"><span data-stu-id="74985-252">Prepare superposition</span></span>

<span data-ttu-id="74985-253">**Áttekintés** Most nézzük meg, hogyan fejezi ki a Q# a qubitek szuperpozícióba helyezésének különböző módjait.</span><span class="sxs-lookup"><span data-stu-id="74985-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="74985-254">Emlékezzünk arra, hogy a qubitek állapota a 0 és az 1 értéket egyszerre lefedő szuperpozícióban is lehet.</span><span class="sxs-lookup"><span data-stu-id="74985-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="74985-255">Ennek eléréséhez a `Hadamard` műveletet használjuk.</span><span class="sxs-lookup"><span data-stu-id="74985-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="74985-256">Ha a qubit valamelyik klasszikus állapotban van (amikor a mérések mindig `Zero` vagy mindig `One` értéket adnak vissza), akkor a `Hadamard` vagy `H` művelet olyan állapotba helyezi a qubitet, amelyben a mérések 50%-ban `Zero` és 50%-ban `One` eredményt adnak.</span><span class="sxs-lookup"><span data-stu-id="74985-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="74985-257">Alapjában véve a qubit úgy képzelhető el, hogy félúton van a `Zero` és az `One` között.</span><span class="sxs-lookup"><span data-stu-id="74985-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="74985-258">Ilyenkor a `TestBellState` művelet szimulálása esetén azt fogjuk látni, hogy a mérések nagyjából azonos alkalommal adják ki a `Zero` és az `One` értéket.</span><span class="sxs-lookup"><span data-stu-id="74985-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="74985-259">Először csak megpróbáljuk átállítani a qubitet (tehát ha `Zero` állapotban van, `One` állapotba állítjuk, és fordítva).</span><span class="sxs-lookup"><span data-stu-id="74985-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="74985-260">Ezt úgy érhetjük el, ha végrehajtunk egy `X` műveletet, mielőtt megmérnénk az `TestBellState`-ben:</span><span class="sxs-lookup"><span data-stu-id="74985-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="74985-261">Most (az `F5` lenyomása után) megfordulnak az eredmények:</span><span class="sxs-lookup"><span data-stu-id="74985-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="74985-262">Azonban minden, amit eddig láttunk, klasszikus.</span><span class="sxs-lookup"><span data-stu-id="74985-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="74985-263">Kérjünk le egy kvantumeredményt.</span><span class="sxs-lookup"><span data-stu-id="74985-263">Let's get a quantum result.</span></span> <span data-ttu-id="74985-264">Mindössze le kell cserélnünk az előző futtatás `X` műveletét egy `H` vagy egy Hadamard-műveletre.</span><span class="sxs-lookup"><span data-stu-id="74985-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="74985-265">Ahelyett, hogy 0-ról 1-re teljesen átállítani a qubitet, csak félig fordítjuk át.</span><span class="sxs-lookup"><span data-stu-id="74985-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="74985-266">A `TestBellState`-ben most így néznek ki a lecserélt sorok:</span><span class="sxs-lookup"><span data-stu-id="74985-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="74985-267">Az eredmények most még érdekesebbek:</span><span class="sxs-lookup"><span data-stu-id="74985-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="74985-268">Minden méréskor egy klasszikus értéket kérünk, de a qubit félúton van 0 és 1 között, így (statisztikailag) az esetek felében 0, a másik felében 1 értéket kapunk.</span><span class="sxs-lookup"><span data-stu-id="74985-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="74985-269">Ez az úgynevezett __szuperpozíció__, és az első valódi betekintést nyújtja a kvantumállapotba.</span><span class="sxs-lookup"><span data-stu-id="74985-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="74985-270">Az összefonódás előkészítése</span><span class="sxs-lookup"><span data-stu-id="74985-270">Prepare entanglement</span></span>

<span data-ttu-id="74985-271">**Áttekintés:**  Most nézzek meg, hogyan fejezi ki a Q# a qubitek összefonódásának különböző módjait.</span><span class="sxs-lookup"><span data-stu-id="74985-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="74985-272">Először is az első qubitet a kezdeti állapotba, majd a `H` művelettel szuperpozícióba kell állítanunk.</span><span class="sxs-lookup"><span data-stu-id="74985-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="74985-273">Ezután, még mielőtt megmérnénk az első qubitet, végre kell hajtanunk egy új műveletet (`CNOT`), amelynek jelentése Controlled-Not (Nem szabályozott).</span><span class="sxs-lookup"><span data-stu-id="74985-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="74985-274">Ha ezt a műveletet végrehajtjuk két qubiten, akkor a második qubit át lesz állítva, ha az első qubit `One` volt.</span><span class="sxs-lookup"><span data-stu-id="74985-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="74985-275">Ekkor a két qubit összefonódik.</span><span class="sxs-lookup"><span data-stu-id="74985-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="74985-276">Az első qubit statisztikái nem változnak (mérés esetén 50%-os eséllyel lesz `Zero` vagy `One`), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk.</span><span class="sxs-lookup"><span data-stu-id="74985-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="74985-277">A `CNOT` összekapcsolta a két qubitet, így bármi is történik az egyikkel, ugyanaz történik a másikkal is.</span><span class="sxs-lookup"><span data-stu-id="74985-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="74985-278">Ha felcseréli a méréseket (a második qubitet mérve az első előtt), akkor is ugyanez történik.</span><span class="sxs-lookup"><span data-stu-id="74985-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="74985-279">Az első mérés eredménye véletlenszerű lesz, a második pedig mindig ugyanaz, mint amit az elsőnél kaptunk.</span><span class="sxs-lookup"><span data-stu-id="74985-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="74985-280">Az első lépés, hogy 2 qubitet foglalunk le egy helyett a `TestBellState`-ben:</span><span class="sxs-lookup"><span data-stu-id="74985-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="74985-281">Így új műveletet (`CNOT`) adhatunk hozzá a mérés (`M`) előtt a `TestBellState`-ben:</span><span class="sxs-lookup"><span data-stu-id="74985-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="74985-282">Hozzáadtunk egy másik `Set` műveletet az első qubit inicializálásához, hogy biztosan mindig `Zero` állapotban legyen indításkor.</span><span class="sxs-lookup"><span data-stu-id="74985-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="74985-283">A felszabadítása előtt alaphelyzetbe is kell állítanunk a második qubitet.</span><span class="sxs-lookup"><span data-stu-id="74985-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="74985-284">A teljes folyamatnak most így kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="74985-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="74985-285">Ha ezt lefuttatjuk, akkor pontosan ugyanazt a fifti-fifti eredményt fogjuk kapni, amit korábban is.</span><span class="sxs-lookup"><span data-stu-id="74985-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="74985-286">Minket azonban az érdekel, hogy a második qubit hogyan reagál az első mérésére.</span><span class="sxs-lookup"><span data-stu-id="74985-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="74985-287">Ez a statisztikát hozzáadjuk a `TestBellState` művelet új verziójához:</span><span class="sxs-lookup"><span data-stu-id="74985-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="74985-288">Az új visszaadott érték (`agree`) minden olyan alkalmat nyomon követ, amikor az első qubit mérési eredménye megegyezik a második kvantumbitével.</span><span class="sxs-lookup"><span data-stu-id="74985-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="74985-289">A gazdaalkalmazást is ennek megfelelően kell frissíteni:</span><span class="sxs-lookup"><span data-stu-id="74985-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="74985-290">Python</span><span class="sxs-lookup"><span data-stu-id="74985-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="74985-291">C#</span><span class="sxs-lookup"><span data-stu-id="74985-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="74985-292">Most a parancs futtatásakor valami egészen különleges eredményt kapunk:</span><span class="sxs-lookup"><span data-stu-id="74985-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="74985-293">Ahogy az áttekintésben is említettük, az első qubit statisztikái nem változnak (50%-os eséllyel lesz 0 vagy 1), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk, mivel a két qubit össze van fonódva!</span><span class="sxs-lookup"><span data-stu-id="74985-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="74985-294">Gratulálunk, megírta az első kvantumprogramját!</span><span class="sxs-lookup"><span data-stu-id="74985-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="whats-next"></a><span data-ttu-id="74985-295">A következő lépések</span><span class="sxs-lookup"><span data-stu-id="74985-295">What's next?</span></span>

<span data-ttu-id="74985-296">A [Grover-keresés](xref:microsoft.quantum.quickstarts.search) című oktatóanyag ismerteti, hogyan lehet létrehozni és futtatni egy Grover-keresést, amely az egyik legnépszerűbb kvantum-számítástechnikai algoritmus, és remekül példázza, hogyan oldhatók meg valós problémák egy Q#-programmal és a kvantum-számítástechnika segítségével.</span><span class="sxs-lookup"><span data-stu-id="74985-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="74985-297">A [Bevezetés a Quantum Development Kit használatába](xref:microsoft.quantum.welcome) című cikkben további módszereket is talál a Q# és a kvantumprogramozás elsajátítására.</span><span class="sxs-lookup"><span data-stu-id="74985-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>

