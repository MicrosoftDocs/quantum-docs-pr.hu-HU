---
title: Kvantum-véletlenszámgenerátor létrehozása
description: Elkészíthet egy Q#-projektet, amely bemutatja az alapvető kvantumfogalmakat, például a kvantum-véletlenszámgenerátor létrehozása általi szuperpozíciót.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 3e109553adc4d724733834e3660bfe7789052bcf
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426819"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="1b36a-103">Oktatóanyag: Kvantum-véletlenszámgenerátor implementálása a Q#-ban\#</span><span class="sxs-lookup"><span data-stu-id="1b36a-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="1b36a-104">A Q#-ban írt kvantumalgoritmusok egyik egyszerű példája egy kvantum-véletlenszámgenerátor.</span><span class="sxs-lookup"><span data-stu-id="1b36a-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="1b36a-105">Ez az algoritmus a kvantummechanika természetét használja ki egy véletlen szám előállításához.</span><span class="sxs-lookup"><span data-stu-id="1b36a-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b36a-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="1b36a-106">Prerequisites</span></span>

- <span data-ttu-id="1b36a-107">A Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="1b36a-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="1b36a-108">Q#-projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b36a-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)

## <a name="write-a-q-operation"></a><span data-ttu-id="1b36a-109">Q#-művelet írása</span><span class="sxs-lookup"><span data-stu-id="1b36a-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="1b36a-110">Q#-műveletkód</span><span class="sxs-lookup"><span data-stu-id="1b36a-110">Q# operation code</span></span>

1. <span data-ttu-id="1b36a-111">Cserélje le a Program.qs fájl tartalmát a következő kódra:</span><span class="sxs-lookup"><span data-stu-id="1b36a-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="1b36a-112">Ahogy azt [A kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding) című cikkben említettük, a qubit a kvantuminformáció egysége, amely szuperpozícióban lehet.</span><span class="sxs-lookup"><span data-stu-id="1b36a-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="1b36a-113">Ha megmérjük, a qubit értéke csak 0 vagy 1 lehet.</span><span class="sxs-lookup"><span data-stu-id="1b36a-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="1b36a-114">Végrehajtás során azonban a qubit állapota a 0 vagy 1 érték méréssel történő leolvasásának valószínűségét jelzi.</span><span class="sxs-lookup"><span data-stu-id="1b36a-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="1b36a-115">Ezt a valószínűségi állapotot nevezzük szuperpozíciónak.</span><span class="sxs-lookup"><span data-stu-id="1b36a-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="1b36a-116">E valószínűség segítségével generálhatunk véletlen számokat.</span><span class="sxs-lookup"><span data-stu-id="1b36a-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="1b36a-117">A Q#-műveletben bevezetjük a Q#-ban natív `Qubit` adattípust.</span><span class="sxs-lookup"><span data-stu-id="1b36a-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="1b36a-118">Egy `Qubit` csak a `using` utasítással foglalható le.</span><span class="sxs-lookup"><span data-stu-id="1b36a-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="1b36a-119">Lefoglalás esetén a qubit mindig `Zero` állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="1b36a-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="1b36a-120">A `H` művelet használatával a `Qubit` szuperpozícióba helyezhető.</span><span class="sxs-lookup"><span data-stu-id="1b36a-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="1b36a-121">A qubit megméréséhez és értékének leolvasásához használja az `M` belső műveletet.</span><span class="sxs-lookup"><span data-stu-id="1b36a-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="1b36a-122">A `Qubit` szuperpozícióba történő helyezésekor és megmérésekor az eredmény más érték lesz a kód meghívásának minden alkalmával.</span><span class="sxs-lookup"><span data-stu-id="1b36a-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="1b36a-123">A `Qubit` lefoglalásának feloldásakor kifejezetten vissza kell állítani a `Zero` állapotba, máskülönben a szimulátor futásidejű hibát fog jelenteni.</span><span class="sxs-lookup"><span data-stu-id="1b36a-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="1b36a-124">Ennek elérésére az egyik legegyszerűbb módszer a `Reset` meghívása.</span><span class="sxs-lookup"><span data-stu-id="1b36a-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="1b36a-125">A kód vizualizálása a Bloch-gömbbel</span><span class="sxs-lookup"><span data-stu-id="1b36a-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="1b36a-126">A Bloch-gömbön az északi pólus a **0** klasszikus értéket jelöli, a déli pólus pedig az **1** klasszikus értéket.</span><span class="sxs-lookup"><span data-stu-id="1b36a-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="1b36a-127">Minden szuperpozíció megadható a gömb egyik pontjaként (ezt a nyíl jelzi).</span><span class="sxs-lookup"><span data-stu-id="1b36a-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="1b36a-128">Minél közelebb van a nyíl hegye a pólushoz, annál nagyobb a valószínűsége, hogy a qubit a mérésekor a pólushoz hozzárendelt klasszikus értékkel esik egybe.</span><span class="sxs-lookup"><span data-stu-id="1b36a-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="1b36a-129">Az alábbi ábrán például a piros nyíllal jelölt qubitállapot esetében nagyobb a valószínűsége a **0** értéknek, ha megmérjük.</span><span class="sxs-lookup"><span data-stu-id="1b36a-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="1b36a-130">Ennek az ábrának a segítségével vizualizálhatjuk a kód működését:</span><span class="sxs-lookup"><span data-stu-id="1b36a-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="1b36a-131">Először is egy **0** állapotban inicializált qubittel kezdünk, és a `H` alkalmazásával létrehozunk egy szuperpozíciót, amelyben a **0** és az **1** valószínűsége egyenlő.</span><span class="sxs-lookup"><span data-stu-id="1b36a-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="1b36a-132">Ezután megmérjük a qubitet, és mentjük a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="1b36a-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="1b36a-133">A mérés eredménye teljesen véletlen, tehát egy véletlen bitből kaptuk meg.</span><span class="sxs-lookup"><span data-stu-id="1b36a-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="1b36a-134">Ezt a műveletet többször is meghívhatjuk egész számok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1b36a-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="1b36a-135">Ha például háromszor hívjuk meg a műveletet, hogy három véletlen bitet kapjunk, véletlen hárombites számokat hozhatunk létre (tehát egy 0 és 7 közötti véletlen számot).</span><span class="sxs-lookup"><span data-stu-id="1b36a-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="1b36a-136">Teljes körű véletlenszám-generátor létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b36a-136">Creating a complete random number generator</span></span>

<span data-ttu-id="1b36a-137">Most, hogy rendelkezünk egy olyan Q#-művelettel, amely véletlenszerű biteket hoz létre, felhasználhatjuk egy teljes kvantum-véletlenszámgenerátor összeállítására.</span><span class="sxs-lookup"><span data-stu-id="1b36a-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="1b36a-138">Használhatjuk a Q# nyelvű parancssori alkalmazásokat vagy egy gazdaprogramot.</span><span class="sxs-lookup"><span data-stu-id="1b36a-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="1b36a-139">Q# nyelvű parancssori alkalmazások a Visual Studióval vagy a Visual Studio Code-dal</span><span class="sxs-lookup"><span data-stu-id="1b36a-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="1b36a-140">A teljes Q# nyelvű parancssori alkalmazás létrehozásához vegye fel a következő belépési pontot a Q# nyelvű programba:</span><span class="sxs-lookup"><span data-stu-id="1b36a-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="1b36a-141">A végrehajtható fájl a projekt konfigurációja és a parancssori lehetőségek függvényében egy szimulátoron vagy egy erőforrásbecslőn futtatja az `@EntryPoint()` attribútummal jelölt műveletet vagy függvényt.</span><span class="sxs-lookup"><span data-stu-id="1b36a-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="1b36a-142">A szkript végrehajtásához egyszerűen nyomja le a Ctrl + F5 billentyűkombinációt a Visual Studióban.</span><span class="sxs-lookup"><span data-stu-id="1b36a-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="1b36a-143">A VS Code-ban a Program.qs első alkalommal való összeállításához írja be az alábbiakat a terminálban:</span><span class="sxs-lookup"><span data-stu-id="1b36a-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="1b36a-144">A későbbi futtatásokhoz az összeállítást nem kell megismételni.</span><span class="sxs-lookup"><span data-stu-id="1b36a-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="1b36a-145">Futtatáshoz írja be a következő parancsot, majd nyomja le az Enter billentyűt:</span><span class="sxs-lookup"><span data-stu-id="1b36a-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="1b36a-146">Python a Visual Studio Code-dal vagy a parancssorból</span><span class="sxs-lookup"><span data-stu-id="1b36a-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="1b36a-147">Mentse `host.py`-ként a következő kódot az új Q#-program Pythonból történő futtatásához:</span><span class="sxs-lookup"><span data-stu-id="1b36a-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="1b36a-148">Ezután a parancssorból futtathatja a Python-gazdaprogramot:</span><span class="sxs-lookup"><span data-stu-id="1b36a-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="1b36a-149">C# Visual Studióval vagy Visual Studio Code-dal</span><span class="sxs-lookup"><span data-stu-id="1b36a-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="1b36a-150">Adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ből:</span><span class="sxs-lookup"><span data-stu-id="1b36a-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="1b36a-151">Ezután a parancssorból futtathatja a C#-gazdaprogramot (Visual Studióban nyomja le az F5 billentyűt):</span><span class="sxs-lookup"><span data-stu-id="1b36a-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
