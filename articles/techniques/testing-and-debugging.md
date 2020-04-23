---
title: Q# programok tesztelése és hibakeresése
description: Ismerje meg, hogyan használhatja az egységteszteket, tényeket és állításokat, valamint a memóriaképi függvényeket a kvantumprogramok teszteléséhez és hibakereséséhez.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030582"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="6ed5b-103">Tesztelés és hibakeresés</span><span class="sxs-lookup"><span data-stu-id="6ed5b-103">Testing and Debugging</span></span>

<span data-ttu-id="6ed5b-104">Csakúgy, mint a klasszikus programozás, elengedhetetlen, hogy képes legyen ellenőrizni, hogy a kvantum programok járnak elhivatott, és hogy képes diagnosztizálni a kvantum program, amely helytelen.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="6ed5b-105">Ebben a részben a Q# által a kvantumprogramok tesztelésére és hibakeresésére szolgáló eszközöket fedjük le.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="6ed5b-106">Egységvizsgálatok</span><span class="sxs-lookup"><span data-stu-id="6ed5b-106">Unit Tests</span></span>

<span data-ttu-id="6ed5b-107">A klasszikus programok tesztelésének egyik gyakori megközelítése az egységteszteknek nevezett kis programok *írása,* amelyek kódot futtatnak egy könyvtárban, és összehasonlítják a kimenetet néhány várható kimenettel.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="6ed5b-108">Például, mi május akar `Square(2)` `4`-hoz biztosít amit visszatér , óta tudjuk *a priori* amit $2^2 = 4$.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="6ed5b-109">A Q# támogatja a kvantumprogramok egységtesztjeinek létrehozását, és az [xUnit](https://xunit.github.io/) egységtesztelési keretrendszeren belül tesztként hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="6ed5b-110">Tesztprojekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="6ed5b-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6ed5b-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6ed5b-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="6ed5b-112">Nyissa meg a Visual Studio 2019-et.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="6ed5b-113">Lépjen a `File` menübe, és válassza a lehetőséget. `New`  >  `Project...`</span><span class="sxs-lookup"><span data-stu-id="6ed5b-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="6ed5b-114">A jobb felső sarokban `Q#`keresse meg `Q# Test Project` a t, és jelölje ki a sablont.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6ed5b-115">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6ed5b-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="6ed5b-116">A kedvenc parancssorból futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="6ed5b-117">Az új projekt egyetlen `Tests.qs`fájllal fog rendelkezni, amely kényelmes helyet biztosít az új Q# egységtesztek meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="6ed5b-118">Kezdetben ez a fájl `AllocateQubit` tartalmaz egy minta egység teszt, amely{0}ellenőrzi, hogy egy újonnan lefoglalt qubit van a $\ket $ állapotban, és kinyomtatja az üzenetet:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: <span data-ttu-id="6ed5b-119">Minden Q# művelet vagy függvény, `Unit` amely `Unit` egy típusú argumentumot `@Test("...")` vesz fel, és visszatér, egységtesztként jelölhető meg az attribútumon keresztül.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="6ed5b-120">Az attribútum `"QuantumSimulator"` fenti argumentuma azt a célt határozza meg, amelyen a tesztet végrehajtják.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="6ed5b-121">Egyetlen teszt több célon is végrehajtható.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="6ed5b-122">Például adjon hozzá `@Test("ResourcesEstimator")` egy `AllocateQubit`fenti attribútumot.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="6ed5b-123">Mentse a fájlt, és hajtsa végre az összes tesztet.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-123">Save the file and execute all tests.</span></span> <span data-ttu-id="6ed5b-124">Most már két egységtesztnek kell lennie, az egyiken az AllocateQubit végrehajtása a QuantumSimulatoron, a másik pedig a ResourceEstimator ban.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="6ed5b-125">A Q# fordító a "QuantumSimulator", "ToffoliSimulator" és "ResourcesEstimator" beépített célokat az egységtesztek érvényes végrehajtási célként ismeri fel.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="6ed5b-126">Az egyéni végrehajtási cél definiálásához bármilyen teljesen minősített nevet is meg adhat.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="6ed5b-127">Q# egységtesztek futtatása</span><span class="sxs-lookup"><span data-stu-id="6ed5b-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6ed5b-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6ed5b-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="6ed5b-129">Megoldásonként egyszer ként nyissa meg `Test` a menüt, és válassza a lehetőséget. `Test Settings`  >  `Default Processor Architecture`  >  `X64`</span><span class="sxs-lookup"><span data-stu-id="6ed5b-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="6ed5b-130">A Visual Studio alapértelmezett processzorarchitektúrás beállítása`.suo`az egyes megoldások megoldásbeállításaiban ( ) tárolódik.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="6ed5b-131">Ha törli ezt a fájlt, akkor `X64` újra ki kell választania processzorarchitektúrának.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="6ed5b-132">Készítse el a `Test` projektet, `Windows`  >  `Test Explorer`lépjen a menübe, és válassza a lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="6ed5b-133">`AllocateQubit`megjelenik a `Not Run Tests` csoportteszteinek listájában.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="6ed5b-134">Válassza `Run All` ki vagy futtassa ezt az egyedi tesztet, és át kell mennie!</span><span class="sxs-lookup"><span data-stu-id="6ed5b-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6ed5b-135">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6ed5b-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="6ed5b-136">A tesztek futtatásához keresse meg a projekt `Tests.csproj`mappáját (a tartalmazó mappát), és hajtsa végre a parancsot:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="6ed5b-137">A kimenetnek a következőhöz hasonlónak kell lennie:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-137">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="6ed5b-138">Az egységtesztek a nevük és/vagy a végrehajtási cél szerint szűrhetők:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="6ed5b-139">A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)` van, és lehetővé teszi a diagnosztikai üzenetek létrehozását.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6ed5b-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6ed5b-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="6ed5b-141">Miután végrehajtott egy tesztet a Test Explorerben, és rákattintott a tesztre, egy panel jelenik meg a tesztvégrehajtással kapcsolatos információkkal: Átadott/sikertelen állapot, eltelt idő és "Kimenet" hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="6ed5b-142">Ha a "Kimenet" hivatkozásra kattint, a tesztkimenet egy új ablakban nyílik meg.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-142">If you click the "Output" link, test output will open in a new window.</span></span>

![vizsgálati kimenet](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6ed5b-144">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6ed5b-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="6ed5b-145">Az egyes tesztek áthaladási/sikertelenségi `dotnet test`állapotát a rendszer kinyomtatja a konzolra.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="6ed5b-146">Sikertelen tesztek esetén a kimenetek is kivannak nyomtatva a konzolra, hogy segítsenek diagnosztizálni a hibát.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="6ed5b-147">Tények és állítások</span><span class="sxs-lookup"><span data-stu-id="6ed5b-147">Facts and Assertions</span></span>

<span data-ttu-id="6ed5b-148">Mivel a Q# függvényeknek _nincsenek logikai_ mellékhatásai, a Q# programon belül `()` nem figyelhető meg olyan függvény végrehajtásának _bármely más,_ amelynek kimeneti típusa az üres tuple.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="6ed5b-149">Ez azt jelenti, hogy a célgép dönthet `()` úgy, hogy nem hajt végre olyan függvényt, amely azzal a garanciával tér vissza, hogy ez a mulasztás nem módosítja a következő Q# kód viselkedését.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="6ed5b-150">Ez a `()` függvények visszaadását (azaz `Unit`) hasznos eszközzé teszi az állítások beágyazásához és a logika Q# programokba való beágyazásához.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="6ed5b-151">Vegyünk egy egyszerű példát:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="6ed5b-152">Itt a `fail` kulcsszó azt jelzi, hogy a számítás nem folytatódhat, ami kivételt jelent a Q# programot futtató célgépben.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="6ed5b-153">Definíció szerint egy ilyen hiba nem figyelhető meg a Q#-on belül, `fail` mivel a utasítás elérése után nem fut további Q# kód.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="6ed5b-154">Így, ha haladunk tovább `PositivityFact`a hívást , akkor biztos lehet benne, hogy a bemenet pozitív volt.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="6ed5b-155">Ne feledje, hogy ugyanazt a viselkedést valósíthatjuk meg, mint `PositivityFact` a függvény használata a [`Fact`](xref:microsoft.quantum.diagnostics.fact) <xref:microsoft.quantum.diagnostics> névtérből:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="6ed5b-156">*Az állításokat*viszont a tényekhez hasonlóan használják, de függhetnek a célgép állapotától.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="6ed5b-157">Ennek megfelelően ezek műveletekként vannak meghatározva, míg a tények függvényként vannak meghatározva (a fentiek szerint).</span><span class="sxs-lookup"><span data-stu-id="6ed5b-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="6ed5b-158">A különbségtétel megértéséhez vegye figyelembe egy tény következő használatát egy állításon belül:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="6ed5b-159">Itt a műveletet <xref:microsoft.quantum.environment.getqubitsavailabletouse> arra használjuk, hogy visszaadjuk a használható qubitek számát.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="6ed5b-160">Mivel ez egyértelműen függ a globális állapotát a program `AssertQubitsAreAvailable` és a végrehajtási környezet, a mi meghatározása kell egy művelet is.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="6ed5b-161">Azonban használhatja, hogy a globális `Bool` állapot hozamegy `Fact` egyszerű értéket, mint bemenet a függvény.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="6ed5b-162">Ezekre az ötletekre építve [az előjáték](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assert> két <xref:microsoft.quantum.intrinsic.assertprob> különösen hasznos állítást kínál, és mindkettő tikulizált műveletként. `()`</span><span class="sxs-lookup"><span data-stu-id="6ed5b-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="6ed5b-163">Ezek az állítások mindegyike egy Pauli operátort vesz igénybe, amely leírja egy adott érdeklődési tételmérést, egy kvantumregisztert, amelyen a mérést el kell végezni, és egy hipotetikus eredményt.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="6ed5b-164">A szimulációval működő célgépeken nem köt [minket a klónozás nélküli tétel,](https://en.wikipedia.org/wiki/No-cloning_theorem)és az ilyen méréseket anélkül tudjuk elvégezni, hogy megzavarnánk az ilyen állításoknak átadott nyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="6ed5b-165">A szimulátor a fenti `PositivityFact` függvényhez hasonlóan megszakíthatja a számítást, ha a gyakorlatban nem figyelhető meg a hipotetikus eredmény:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="6ed5b-166">A fizikai kvantum hardver, ahol a nem-klónozó tétel megakadályozza vizsgálata kvantum állapot, a `Assert` és `AssertProb` a műveletek egyszerűen vissza `()` más hatása nélkül.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="6ed5b-167">A <xref:microsoft.quantum.diagnostics> névtér számos további `Assert` funkciót biztosít a családnak, amelyek lehetővé teszik számunkra, hogy ellenőrizzük a fejlettebb feltételeket.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="6ed5b-168">Kiírási függvények</span><span class="sxs-lookup"><span data-stu-id="6ed5b-168">Dump Functions</span></span>

<span data-ttu-id="6ed5b-169">A kvantumprogramok hibaelhárításának <xref:microsoft.quantum.diagnostics> elősegítése érdekében a névtér két olyan funkciót <xref:microsoft.quantum.diagnostics.dumpmachine> kínál, amelyek a célgép aktuális állapotát egy fájlba képesek kiönteni: és <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="6ed5b-170">Az egyes létrehozott kimenet a célgéptől függ.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="6ed5b-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="6ed5b-171">DumpMachine</span></span>

<span data-ttu-id="6ed5b-172">A Quantum Development Kit részeként elosztott teljes állapotú kvantumszimulátor a teljes kvantumrendszer [hullámfunkcióját](https://en.wikipedia.org/wiki/Wave_function) írja be a fájlba, mint egy dimenziós komplex számokat tartalmazó tömb, amelyben minden elem a számítási alapállapot ($\ket{n}$) mérésének valószínűségét jelöli, ahol $\ket{n} = \ket{b_{n-1}... b_1b_0}$ bitek\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="6ed5b-173">Például egy olyan gépen, amelyen csak két qubit van lefoglalva, és kvantumállapotban $${1}\begin{align}{2}\ket{\psi} = \frac {\sqrt }{00} \ket - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ hívás <xref:microsoft.quantum.diagnostics.dumpmachine> generálja ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="6ed5b-174">Az első sor a megfelelő qubitek azonosítóival a diszatematikusok jelentős sorrendjében tartalmaz megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="6ed5b-175">A többi sor a $\ket{n}$ alapállapot-vektor mérésének valószínűségi amplitúdóját írja le descartes-i és poláris formátumban egyaránt.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="6ed5b-176">Részletesen az első sorban:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-176">In detail for the first row:</span></span>

* <span data-ttu-id="6ed5b-177">**`∣0❭:`** ez a sor `0` megfelel a számítási alap állapotának</span><span class="sxs-lookup"><span data-stu-id="6ed5b-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="6ed5b-178">**`0.707107 +  0.000000 i`**: a valószínűségi amplitúdó descartes-i formátumban.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="6ed5b-179">**` == `**: `equal` a megjelölés mindkét egyenértékű ábrázolást elhatogatja.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="6ed5b-180">**`**********  `**: A grafikus ábrázolása nagysága, `*` a szám arányos a valószínűsége, hogy ezt az állapotot vektor.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="6ed5b-181">**`[ 0.500000 ]`**: a magnitúdó számértéke</span><span class="sxs-lookup"><span data-stu-id="6ed5b-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="6ed5b-182">**`    ---`**: Az amplitúdó fázisának grafikus ábrázolása (lásd alább).</span><span class="sxs-lookup"><span data-stu-id="6ed5b-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="6ed5b-183">**`[ 0.0000 rad ]`**: a fázis numerikus értéke (radiánban).</span><span class="sxs-lookup"><span data-stu-id="6ed5b-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="6ed5b-184">Mind a magnitúdó, mind a fázis grafikus ábrázolással jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="6ed5b-185">A magnitúdó ábrázolása egyenesen `*`előre: ez azt mutatja, egy bár, annál nagyobb a valószínűsége, annál nagyobb a sáv lesz.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="6ed5b-186">A fázishoz a következő szimbólumokat jelenítjük meg, amelyek a szöget jelölik a tartományok alapján:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="6ed5b-187">A következő `DumpMachine` példák néhány gyakori állapotot mutatnak be:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-187">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="6ed5b-188">A qubit azonosítója futásidőben van hozzárendelve, és nem feltétlenül igazodik a qubit kiosztási sorrendjéhez vagy a qubit regiszterben elfoglalt pozíciójához.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="6ed5b-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6ed5b-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="6ed5b-190">A Visual Studio-ban úgy találhat ki qubit id azonosítót, hogy egy töréspontot helyez el a kódban, és megvizsgálja egy qubit változó értékét, például:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![show qubit id a Visual Studio-ban](~/media/qubit_id.png)
  >
  > <span data-ttu-id="6ed5b-192">a qubit `0` index `register2` be van`3`kapcsolva = `1` , az`2`indexes qubit id= .</span><span class="sxs-lookup"><span data-stu-id="6ed5b-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="6ed5b-193">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6ed5b-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="6ed5b-194">A qubit id-t a <xref:microsoft.quantum.intrinsic.message> függvény használatával és az üzenetben lévő qubit változó átadásával lehet kitalálni, például:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="6ed5b-195">amely ezt a kimenetet generálhatja:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="6ed5b-196">ami azt jelenti, hogy `0` `register2` a be-`3`és az indexes qubit id= , az indexes `1` qubit id=`2`.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="6ed5b-197"><xref:microsoft.quantum.diagnostics.dumpmachine>a névtér <xref:microsoft.quantum.diagnostics> része, ezért a használatához hozzá kell `open` adnia egy utasítást:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="6ed5b-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="6ed5b-198">DumpRegister</span></span>

<span data-ttu-id="6ed5b-199"><xref:microsoft.quantum.diagnostics.dumpregister>működik, <xref:microsoft.quantum.diagnostics.dumpmachine>kivéve azt is tart egy sor qubits korlátozni az információ mennyisége, hogy csak a vonatkozó, hogy a megfelelő qubits.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="6ed5b-200">A <xref:microsoft.quantum.diagnostics.dumpmachine>rendszerhez is a <xref:microsoft.quantum.diagnostics.dumpregister> rendszer által generált információ a célgéptől függ.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="6ed5b-201">A teljes állapotú kvantum szimulátor azt írja a fájlba a hullám funkció akár egy globális fázisa a kvantum al-rendszer által generált megadott qubits ugyanabban a formátumban, mint <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="6ed5b-202">Például, hogy újra egy gép csak két qubitkiosztott és a kvantum állapot $$ \begin{align}{1}\ket{\psi} ={2}\frac {\sqrt } \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket `qubit[0]` {1} \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ), \end{align} $$ hívás <xref:microsoft.quantum.diagnostics.dumpregister> generálja ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="6ed5b-203">és <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[1]` felhívás generálja ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="6ed5b-204">Általában egy másik regiszterbe gabalyodott regiszter állapota vegyes állapot, nem pedig tiszta állapot.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="6ed5b-205">Ebben az <xref:microsoft.quantum.diagnostics.dumpregister> esetben a következő üzenetet adja ki:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="6ed5b-206">A következő példa bemutatja, <xref:microsoft.quantum.diagnostics.dumpregister> hogyan <xref:microsoft.quantum.diagnostics.dumpmachine> használhatja mindkettőt és a Q# kódot:</span><span class="sxs-lookup"><span data-stu-id="6ed5b-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="6ed5b-207">Hibakeresés</span><span class="sxs-lookup"><span data-stu-id="6ed5b-207">Debugging</span></span>

<span data-ttu-id="6ed5b-208">`Assert` A `Dump` q# a szabványos Visual Studio hibakeresési képességek egy részét támogatja: [sortörési pontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [kódváltás f10 használatával történő léptetése](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) és a klasszikus [változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) a szimulátoron történő kódfuttatássorán lehetséges.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="6ed5b-209">A Visual Studio Code hibakeresési funkciói a C# for Visual Studio Code bővítmény Által biztosított hibakeresési lehetőségeket használják, amelyeket az OmniSharp hajt, és a [legújabb verzió](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)telepítését igényli.</span><span class="sxs-lookup"><span data-stu-id="6ed5b-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
