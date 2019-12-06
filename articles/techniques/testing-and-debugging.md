---
title: 'Q # technikák – tesztelés és hibakeresés | Microsoft Docs'
description: 'Q # technikák – tesztelés és hibakeresés'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: d352ffa315b654cfcf8991fa116465d3dad49f0a
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864270"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="4e7dd-103">Tesztelés és hibakeresés</span><span class="sxs-lookup"><span data-stu-id="4e7dd-103">Testing and Debugging</span></span>

<span data-ttu-id="4e7dd-104">Csakúgy, mint a klasszikus programozás esetében, elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a kvantum programot, amely helytelen.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="4e7dd-105">Ebben a szakaszban a Q # által nyújtott eszközöket fogjuk kiszolgálni a kvantum-programok teszteléséhez és hibakereséséhez.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="4e7dd-106">Egység tesztek</span><span class="sxs-lookup"><span data-stu-id="4e7dd-106">Unit Tests</span></span>

<span data-ttu-id="4e7dd-107">A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat ír *, amelyekben* kód fut egy könyvtárban, és hasonlítsa össze a kimenetét a várt kimenettel.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="4e7dd-108">Előfordulhat például, hogy azt szeretnénk, hogy a `Square(2)` visszaadja `4`ét, mert tudjuk, hogy *a priori* 2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="4e7dd-109">A Q # támogatja az egységnyi tesztek létrehozását a kvantum-programokhoz, amelyek a [xUnit](https://xunit.github.io/) egység tesztelési keretrendszerében tesztekként hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="4e7dd-110">Tesztelési projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="4e7dd-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4e7dd-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4e7dd-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4e7dd-112">Nyissa meg a Visual Studio 2019 alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="4e7dd-113">Lépjen a `File` menüre, és válassza a `New` > `Project...`lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="4e7dd-114">A jobb felső sarokban keresse meg a `Q#`, majd válassza ki a `Q# Test Project` sablont.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4e7dd-115">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4e7dd-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4e7dd-116">A kedvenc parancssorában futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="4e7dd-117">Az új projektben egyetlen fájl `Tests.qs`lesz, amely kényelmes helyet biztosít az új Q # egység tesztek definiálásához.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="4e7dd-118">Kezdetben ez a fájl egy minta egység tesztelési `AllocateQubit` tartalmaz, amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket{0}$ állapotban van-e, és kinyomtat egy üzenetet:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="4e7dd-119">: új: minden olyan Q # művelet vagy függvény, amely `Unit` típusú argumentumot fogad, és az `Unit` a `@Test("...")` attribútumon keresztüli egység-tesztként jelölhető meg.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="4e7dd-120">A fent `"QuantumSimulator"` attribútum argumentuma meghatározza a teszt végrehajtásának célját.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="4e7dd-121">Egyetlen tesztet több célponton is végrehajthat.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="4e7dd-122">Adjon hozzá például egy `@Test("ResourcesEstimator")` `AllocateQubit`fenti attribútumot.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="4e7dd-123">Mentse a fájlt, és hajtsa végre az összes tesztet.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-123">Save the file and execute all tests.</span></span> <span data-ttu-id="4e7dd-124">Ebben az esetben két egységes tesztnek kell lennie, amelyek közül a AllocateQubit a QuantumSimulator hajtja végre, és a ResourceEstimator hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="4e7dd-125">A Q # Compiler a "QuantumSimulator", a "ToffoliSimulator" és a "ResourcesEstimator" beépített célokat ismeri fel érvényes végrehajtási célokként az egység tesztek számára.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="4e7dd-126">A teljes nevet is megadhatja egy egyéni végrehajtási cél definiálásához.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="4e7dd-127">Q # egység tesztek futtatása</span><span class="sxs-lookup"><span data-stu-id="4e7dd-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4e7dd-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4e7dd-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4e7dd-129">Egyszeri egyszeri megoldás beállítása esetén lépjen `Test` menüre, és válassza `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="4e7dd-130">A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások (`.suo`) fájljában tárolódik.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="4e7dd-131">Ha törli ezt a fájlt, akkor újra ki kell választania `X64` a processzor architektúrájának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="4e7dd-132">Hozza létre a projektet, lépjen a `Test` menüre, és válassza a `Windows` > `Test Explorer`lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="4e7dd-133">a `AllocateQubit` megjelennek a `Not Run Tests` csoportban lévő tesztek listájában.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="4e7dd-134">Válassza ki `Run All` vagy futtassa ezt az egyéni tesztet, és adja meg a következőt.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4e7dd-135">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4e7dd-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4e7dd-136">A tesztek futtatásához navigáljon a projekt mappájához (a `Tests.csproj`tartalmazó mappához), és hajtsa végre a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="4e7dd-137">A következőhöz hasonló kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="4e7dd-138">Az egységbeli tesztek a nevük és/vagy a végrehajtási cél alapján szűrhetők:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="4e7dd-139">A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)`, és lehetővé teszi a diagnosztikai üzenetek létrehozását.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4e7dd-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4e7dd-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4e7dd-141">Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt végrehajtásával kapcsolatos információkat tartalmazza: az átadott/sikertelen állapot, az eltelt idő és a "kimenet" hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="4e7dd-142">Ha a kimenet hivatkozásra kattint, a teszt kimenete új ablakban fog megnyílni.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-142">If you click the "Output" link, test output will open in a new window.</span></span>

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4e7dd-144">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4e7dd-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4e7dd-145">Az egyes tesztek Pass/Fail állapotának kinyomtatását a konzolon `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="4e7dd-146">A sikertelen tesztek esetén a kimenetek a konzolon is kinyomtathatók a hiba diagnosztizálásához.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="assertions"></a><span data-ttu-id="4e7dd-147">Állításokat</span><span class="sxs-lookup"><span data-stu-id="4e7dd-147">Assertions</span></span>

<span data-ttu-id="4e7dd-148">Mivel a Q # függvények nem rendelkeznek _logikai_ mellékhatással, az olyan függvények végrehajtásának _egyéb_ következményei, amelyek kimeneti típusa az üres rekord `()` a q # programon belül soha nem figyelhető meg.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="4e7dd-149">Vagyis a célszámítógép úgy is dönthet, hogy nem hajt végre olyan függvényt, amely `()`t ad vissza, és ezzel garantálja, hogy ez a mulasztás nem módosítja a következő Q # kód viselkedését.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="4e7dd-150">Ez lehetővé teszi a függvények visszaadását `()` egy hasznos eszközként, amely az állításokat és a hibakeresési logikát a Q # programokba ágyazza be.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-150">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="4e7dd-151">Ugyanezt a logikát alkalmazhatja az érvényesítések megvalósítására is.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-151">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="4e7dd-152">Vegyünk egy egyszerű példát:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-152">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="4e7dd-153">Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, kivételt kell kiemelni a Q # programot futtató célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-153">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="4e7dd-154">Definíció szerint az ilyen típusú hibák nem figyelhetők meg a Q #-on belül, mert egy `fail` utasítás elérésekor nem fut további Q # kód.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-154">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="4e7dd-155">Így ha folytatjuk a `AssertPositive`meghívását, biztos lehet abban, hogy a bemenete pozitív volt.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-155">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="4e7dd-156">Ezen ötletek kiépítésekor [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude) két különösen hasznos állítást kínál, <xref:microsoft.quantum.intrinsic.assert> és <xref:microsoft.quantum.intrinsic.assertprob> mind a modellként, mind a `()`.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-156">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="4e7dd-157">Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy olyan kvantum-regisztrációt, amelyre a mérést végzi, valamint egy feltételezett eredményt.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-157">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="4e7dd-158">A szimulációval működő célszámítógépeken nem köti [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem), és elvégezheti az ilyen méréseket anélkül, hogy megzavarja volna az ilyen állításokra adott regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-158">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="4e7dd-159">A szimulátor ezután a fenti `AssertPositive` függvényhez hasonlóan megszakítja a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-159">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="4e7dd-160">Fizikai kvantum-hardveren, ahol a klónozás nélküli tétel megakadályozza a kvantum-állapot vizsgálatát, a `Assert` és a `AssertProb` műveletek egyszerűen visszatérhetnek a `()` más hatás nélkül.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-160">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="4e7dd-161">A <xref:microsoft.quantum.diagnostics> névtér a `Assert` család számos további funkcióját biztosítja, amelyek lehetővé teszik a fejlettebb feltételek ellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-161">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="4e7dd-162">Memóriakép függvények</span><span class="sxs-lookup"><span data-stu-id="4e7dd-162">Dump Functions</span></span>

<span data-ttu-id="4e7dd-163">A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:microsoft.quantum.diagnostics> névtér két olyan függvényt kínál, amely a célszámítógép aktuális állapotával (<xref:microsoft.quantum.diagnostics.dumpmachine> és <xref:microsoft.quantum.diagnostics.dumpregister>) képes a fájlba való kiírásra.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-163">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="4e7dd-164">A generált kimenet a célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-164">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="4e7dd-165">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="4e7dd-165">DumpMachine</span></span>

<span data-ttu-id="4e7dd-166">A Quantum Development Kit részeként terjesztett teljes állapotú kvantum-szimulátor a teljes kvantum-rendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja a komplex számok egydimenziós tömbje, amelyben az egyes elemek a számítás alapjául szolgáló "\ket{n} $" számítási valószínűségének amplitúdóját jelölik, ahol a $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ a BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-166">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="4e7dd-167">Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ hívó <xref:microsoft.quantum.diagnostics.dumpmachine> létrehozza ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-167">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4e7dd-168">Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-168">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="4e7dd-169">A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{n} $ és a poláris formátumban egyaránt.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-169">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="4e7dd-170">Az első sorra vonatkozó részletek:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-170">In detail for the first row:</span></span>

* <span data-ttu-id="4e7dd-171">**`∣0❭:`** ez a sor a `0` számítási alap állapotának felel meg</span><span class="sxs-lookup"><span data-stu-id="4e7dd-171">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="4e7dd-172">**`0.707107 +  0.000000 i`** : a valószínűségi amplitúdó a Descartes formátumban.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-172">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="4e7dd-173">**` == `** : a `equal` aláírja a elválasztja mindkét egyenértékű ábrázolást.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-173">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="4e7dd-174">**`**********  `** : a magnitúdó grafikus ábrázolása, a `*` száma arányos az állapot-vektor mérési valószínűségével.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-174">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="4e7dd-175">**`[ 0.500000 ]`** : a magnitúdó numerikus értéke</span><span class="sxs-lookup"><span data-stu-id="4e7dd-175">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="4e7dd-176">**`    ---`** : az amplitúdó fázisának grafikus ábrázolása (lásd alább).</span><span class="sxs-lookup"><span data-stu-id="4e7dd-176">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="4e7dd-177">**`[ 0.0000 rad ]`** : a fázis numerikus értéke (radiánban).</span><span class="sxs-lookup"><span data-stu-id="4e7dd-177">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="4e7dd-178">A magnitúdó és a fázis is grafikus ábrázolással jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-178">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="4e7dd-179">A magnitúdó ábrázolása egyenesen előre látható: az `*`egy sávot mutat, annál nagyobb a valószínűsége annak, hogy a sáv nagyobb lesz.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-179">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="4e7dd-180">A fázisban a következő szimbólumok jelennek meg, amelyek a tartományon alapuló szöget jelölik:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-180">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="4e7dd-181">Az alábbi példák a gyakori állapotok `DumpMachine` mutatják be:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-181">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="4e7dd-182">A qubit azonosítója futásidőben van hozzárendelve, és nem szükségszerűen igazodik azzal a sorrendtel, ahogy a qubit le lett foglalva, vagy a qubit-regisztráción belüli pozíciója.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-182">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4e7dd-183">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4e7dd-183">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="4e7dd-184">Létrehozhat egy qubit-azonosítót a Visual Studióban, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-184">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > <span data-ttu-id="4e7dd-186">a (z) `register2` indextel `0` qubit azonosító =`3`, az index `1` azonosítójú qubit azonosítója =`2`.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-186">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4e7dd-187">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4e7dd-187">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="4e7dd-188">Qubit-azonosítót a <xref:microsoft.quantum.intrinsic.message> függvénnyel talál, és átadhatja a qubit változót az üzenetben, például:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-188">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="4e7dd-189">amely a következő kimenetet eredményezheti:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-189">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="4e7dd-190">Ez azt jelenti, hogy a `register2` qubit rendelkező `0` azonosítója =`3`, a qubit index `1` azonosítója =`2`.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-190">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="4e7dd-191"><xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics> névtér része, ezért a használatához hozzá kell adnia egy `open` utasítást:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-191"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="4e7dd-192">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="4e7dd-192">DumpRegister</span></span>

<span data-ttu-id="4e7dd-193"><xref:microsoft.quantum.diagnostics.dumpregister> úgy működik, mint <xref:microsoft.quantum.diagnostics.dumpmachine>, kivéve, ha a qubits egy tömbjét is végrehajtja, amely korlátozza az adatok mennyiségét, hogy csak a megfelelő qubits legyenek érvényesek.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-193"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="4e7dd-194">A <xref:microsoft.quantum.diagnostics.dumpmachine>hoz hasonlóan a <xref:microsoft.quantum.diagnostics.dumpregister> által generált információk a célszámítógéptől függenek.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-194">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="4e7dd-195">A teljes állapotú kvantum-szimulátor esetében a Wave függvény a megadott qubits által generált kvantum alrendszerek globális fázisára mutat, a <xref:microsoft.quantum.diagnostics.dumpmachine>formátumával megegyező formátumban.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-195">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="4e7dd-196">Tegyük fel például, hogy egy gép csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generálja ezt a kimenetet :</span><span class="sxs-lookup"><span data-stu-id="4e7dd-196">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4e7dd-197">és a <xref:microsoft.quantum.diagnostics.dumpregister> meghívása `qubit[1]` a kimenetet hozza létre:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-197">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="4e7dd-198">Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-198">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="4e7dd-199">Ebben az esetben a <xref:microsoft.quantum.diagnostics.dumpregister> a következő üzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-199">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="4e7dd-200">Az alábbi példa bemutatja, hogyan használhatja a Q # Code-ban <xref:microsoft.quantum.diagnostics.dumpregister> és <xref:microsoft.quantum.diagnostics.dumpmachine> is:</span><span class="sxs-lookup"><span data-stu-id="4e7dd-200">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="4e7dd-201">Hibakeresés</span><span class="sxs-lookup"><span data-stu-id="4e7dd-201">Debugging</span></span>

<span data-ttu-id="4e7dd-202">A `Assert` és `Dump` függvények és műveletek mellett a Q # a standard Visual Studio hibakeresési képességeinek egy részhalmazát támogatja: a [vonali töréspontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), a [kód az F10 használatával](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) történő [megvizsgálása és a klasszikus változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) mind lehetséges a szimulátoron végzett kód végrehajtása során.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-202">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="4e7dd-203">A Visual Studio Code-ban végzett hibakeresés a OmniSharp által működtetett C# Visual Studio Code-bővítmény által biztosított hibakeresési képességeket használja, és a [legújabb verzió](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)telepítését igényli.</span><span class="sxs-lookup"><span data-stu-id="4e7dd-203">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
