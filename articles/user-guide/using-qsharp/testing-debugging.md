---
title: Tesztelés és hibakeresés
description: Megtudhatja, hogyan használhatók az egységes tesztek, a tények és a kijelentések, valamint a kvantum-programok tesztelésére és hibakeresésére szolgáló függvények.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630031"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="4bf93-103">Tesztelés és hibakeresés</span><span class="sxs-lookup"><span data-stu-id="4bf93-103">Testing and debugging</span></span>

<span data-ttu-id="4bf93-104">Csakúgy, mint a klasszikus programozás esetében, elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a kvantum programot, amely helytelen.</span><span class="sxs-lookup"><span data-stu-id="4bf93-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="4bf93-105">Ebben a szakaszban a Q # által nyújtott eszközöket fogjuk kiszolgálni a kvantum-programok teszteléséhez és hibakereséséhez.</span><span class="sxs-lookup"><span data-stu-id="4bf93-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="4bf93-106">Egység tesztek</span><span class="sxs-lookup"><span data-stu-id="4bf93-106">Unit Tests</span></span>

<span data-ttu-id="4bf93-107">A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat ír *, amelyekben* kód fut egy könyvtárban, és hasonlítsa össze a kimenetét a várt kimenettel.</span><span class="sxs-lookup"><span data-stu-id="4bf93-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="4bf93-108">Előfordulhat például, hogy vissza kívánja állítani a visszaadott `Square(2)` értéket `4` , mivel tudjuk, hogy *a priori a* következő: 2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="4bf93-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="4bf93-109">A Q # támogatja az egységnyi tesztek létrehozását a kvantum-programokhoz, amelyek a [xUnit](https://xunit.github.io/) egység tesztelési keretrendszerében tesztekként hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="4bf93-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="4bf93-110">Tesztelési projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="4bf93-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4bf93-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4bf93-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4bf93-112">Nyissa meg a Visual Studio 2019 alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="4bf93-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="4bf93-113">Lépjen a `File` menüre, és válassza a elemet `New`  >  `Project...` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="4bf93-114">A jobb felső sarokban keresse meg a `Q#` elemet, és válassza ki a `Q# Test Project` sablont.</span><span class="sxs-lookup"><span data-stu-id="4bf93-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4bf93-115">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4bf93-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4bf93-116">A kedvenc parancssorában futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="4bf93-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="4bf93-117">Az új projekt egyetlen fájllal fog rendelkezni `Tests.qs` , amely kényelmes helyet biztosít az új Q # egység tesztek definiálásához.</span><span class="sxs-lookup"><span data-stu-id="4bf93-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="4bf93-118">Kezdetben ez a fájl egy minta egység tesztet tartalmaz, `AllocateQubit` amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket $ állapotban van-e, {0} és kinyomtat egy üzenetet:</span><span class="sxs-lookup"><span data-stu-id="4bf93-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="4bf93-119">: új: minden olyan Q # művelet vagy függvény, amely `Unit` a Type és Returns argumentumot `Unit` fogadja, az attribútumon keresztül lehet kijelölni egység tesztként `@Test("...")` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="4bf93-120">A fenti attribútumhoz megadott argumentum `"QuantumSimulator"` meghatározza a teszt végrehajtásának célját.</span><span class="sxs-lookup"><span data-stu-id="4bf93-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="4bf93-121">Egyetlen tesztet több célponton is végrehajthat.</span><span class="sxs-lookup"><span data-stu-id="4bf93-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="4bf93-122">Adja meg például a `@Test("ResourcesEstimator")` fenti attribútumot `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="4bf93-123">Mentse a fájlt, és hajtsa végre az összes tesztet.</span><span class="sxs-lookup"><span data-stu-id="4bf93-123">Save the file and execute all tests.</span></span> <span data-ttu-id="4bf93-124">Ebben az esetben két egységes tesztnek kell lennie, amelyek közül a AllocateQubit a QuantumSimulator hajtja végre, és a ResourceEstimator hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="4bf93-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="4bf93-125">A Q # Compiler a "QuantumSimulator", a "ToffoliSimulator" és a "ResourcesEstimator" beépített célokat ismeri fel érvényes végrehajtási célokként az egység tesztek számára.</span><span class="sxs-lookup"><span data-stu-id="4bf93-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="4bf93-126">A teljes nevet is megadhatja egy egyéni végrehajtási cél definiálásához.</span><span class="sxs-lookup"><span data-stu-id="4bf93-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="4bf93-127">Q # egység tesztek futtatása</span><span class="sxs-lookup"><span data-stu-id="4bf93-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4bf93-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4bf93-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4bf93-129">Egyszeri egyszeri megoldás beállítása esetén válassza a menü lehetőséget, majd a `Test` elemet `Test Settings`  >  `Default Processor Architecture`  >  `X64` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="4bf93-130">A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások ( `.suo` ) fájljában tárolódik.</span><span class="sxs-lookup"><span data-stu-id="4bf93-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="4bf93-131">Ha törli ezt a fájlt, akkor újra ki kell választania `X64` a processzor architektúráját.</span><span class="sxs-lookup"><span data-stu-id="4bf93-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="4bf93-132">Hozza létre a projektet, lépjen a `Test` menüre, és válassza a elemet `Windows`  >  `Test Explorer` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="4bf93-133">`AllocateQubit`megjelenik a csoportban lévő tesztek listájában `Not Run Tests` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="4bf93-134">Válassza ki `Run All` vagy futtassa ezt az egyéni tesztet, és adja meg a következőt.</span><span class="sxs-lookup"><span data-stu-id="4bf93-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4bf93-135">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4bf93-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4bf93-136">A tesztek futtatásához navigáljon a projekt mappájához (a mappát tartalmazó mappához `Tests.csproj` ), és hajtsa végre a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="4bf93-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="4bf93-137">A következőhöz hasonló kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="4bf93-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="4bf93-138">Az egységbeli tesztek a nevük és/vagy a végrehajtási cél alapján szűrhetők:</span><span class="sxs-lookup"><span data-stu-id="4bf93-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="4bf93-139">A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)` és engedélyezése lehetővé teszi a diagnosztikai üzenetek létrehozását.</span><span class="sxs-lookup"><span data-stu-id="4bf93-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4bf93-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4bf93-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4bf93-141">Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt végrehajtásával kapcsolatos információkat tartalmazza: az átadott/sikertelen állapot, az eltelt idő és a "kimenet" hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="4bf93-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="4bf93-142">Ha a kimenet hivatkozásra kattint, a teszt kimenete új ablakban fog megnyílni.</span><span class="sxs-lookup"><span data-stu-id="4bf93-142">If you click the "Output" link, test output will open in a new window.</span></span>

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4bf93-144">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4bf93-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4bf93-145">Az egyes tesztek esetén a Pass/Fail állapotot a konzolon kell kinyomtatni `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="4bf93-146">A sikertelen tesztek esetén a kimenetek a konzolon is kinyomtathatók a hiba diagnosztizálásához.</span><span class="sxs-lookup"><span data-stu-id="4bf93-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="4bf93-147">Tények és kijelentések</span><span class="sxs-lookup"><span data-stu-id="4bf93-147">Facts and Assertions</span></span>

<span data-ttu-id="4bf93-148">Mivel a Q # függvények nem rendelkeznek _logikai_ mellékhatással, az olyan függvények végrehajtásának bármilyen _egyéb_ hatása, amelynek kimeneti típusa az üres rekord, `()` soha nem figyelhető meg a q # programon belülről.</span><span class="sxs-lookup"><span data-stu-id="4bf93-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="4bf93-149">Vagyis a célszámítógép dönthet úgy, hogy nem hajt végre olyan függvényt, amely visszaadja `()` azt a garanciát, hogy ez a mulasztás nem módosítja a következő Q # kód viselkedését.</span><span class="sxs-lookup"><span data-stu-id="4bf93-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="4bf93-150">Ez `()` `Unit` a függvény egy hasznos eszközt ad vissza, amely az állításokat és a hibakeresési logikát a Q # programokba ágyazza be.</span><span class="sxs-lookup"><span data-stu-id="4bf93-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="4bf93-151">Vegyünk egy egyszerű példát:</span><span class="sxs-lookup"><span data-stu-id="4bf93-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="4bf93-152">Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, kivételt kell kiemelni a Q # programot futtató célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="4bf93-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="4bf93-153">Definíció szerint az ilyen típusú hibák nem figyelhetők meg a Q #-on belül, mert a rendszer nem futtat további Q # kódot egy `fail` utasítás elérésekor.</span><span class="sxs-lookup"><span data-stu-id="4bf93-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="4bf93-154">Így ha folytatunk egy hívást a `PositivityFact` szolgáltatásba, biztos lehet benne, hogy a bemenete pozitív volt.</span><span class="sxs-lookup"><span data-stu-id="4bf93-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="4bf93-155">Vegye figyelembe, hogy ugyanaz a viselkedés valósítható meg, mint a `PositivityFact` [`Fact`](xref:microsoft.quantum.diagnostics.fact) névtérből származó függvény használatával <xref:microsoft.quantum.diagnostics> :</span><span class="sxs-lookup"><span data-stu-id="4bf93-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="4bf93-156">Az egyéb *kijelentéseket*a tényekhez hasonlóan használják, de a célszámítógép állapotától függően változhatnak.</span><span class="sxs-lookup"><span data-stu-id="4bf93-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="4bf93-157">Ennek megfelelően a műveletekként vannak definiálva, míg a tények függvényekként vannak definiálva (mint fent).</span><span class="sxs-lookup"><span data-stu-id="4bf93-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="4bf93-158">A különbségtétel megértéséhez vegye figyelembe, hogy a következők valamelyikét kell használnia egy állításon belül:</span><span class="sxs-lookup"><span data-stu-id="4bf93-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="4bf93-159">Itt a műveletet használjuk a <xref:microsoft.quantum.environment.getqubitsavailabletouse> rendelkezésre álló qubits számának visszaküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="4bf93-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="4bf93-160">Mivel ez egyértelműen a program globális állapotától és a végrehajtási környezettől függ, a definíciójának is `AssertQubitsAreAvailable` egy műveletnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4bf93-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="4bf93-161">Ezt a globális állapotot azonban használhatja arra, hogy egy egyszerű `Bool` értéket adjon meg bemenetként a `Fact` függvénynek.</span><span class="sxs-lookup"><span data-stu-id="4bf93-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="4bf93-162">Ezen ötletek kiépítésekor [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude) két, különösen hasznos állítást kínál, <xref:microsoft.quantum.intrinsic.assert> és <xref:microsoft.quantum.intrinsic.assertprob> mindkét modell a műveletre van kifejlesztve `()` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="4bf93-163">Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy olyan kvantum-regisztrációt, amelyre a mérést végzi, valamint egy feltételezett eredményt.</span><span class="sxs-lookup"><span data-stu-id="4bf93-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="4bf93-164">A szimulációval működő célszámítógépeken nem köti [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem), és elvégezheti az ilyen méréseket anélkül, hogy megzavarja volna az ilyen állításokra adott regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="4bf93-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="4bf93-165">A szimulátor ezután a `PositivityFact` fenti függvényhez hasonlóan megszakítja a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:</span><span class="sxs-lookup"><span data-stu-id="4bf93-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="4bf93-166">Fizikai kvantummechanika esetén, ahol a nem klónozási tétel megakadályozza a kvantum állapot vizsgálatát, a `Assert` és a `AssertProb` műveletek egyszerűen visszatérhetnek `()` más hatás nélkül.</span><span class="sxs-lookup"><span data-stu-id="4bf93-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="4bf93-167">A <xref:microsoft.quantum.diagnostics> névtér a család számos további funkcióját biztosítja, `Assert` amelyek lehetővé teszik a speciális feltételek ellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="4bf93-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="4bf93-168">Memóriakép függvények</span><span class="sxs-lookup"><span data-stu-id="4bf93-168">Dump Functions</span></span>

<span data-ttu-id="4bf93-169">A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:microsoft.quantum.diagnostics> névtér két olyan függvényt biztosít, amelyek a célszámítógép aktuális állapotát a következő fájlba tudják bemutatni: <xref:microsoft.quantum.diagnostics.dumpmachine> és <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="4bf93-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="4bf93-170">A generált kimenet a célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="4bf93-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="4bf93-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="4bf93-171">DumpMachine</span></span>

<span data-ttu-id="4bf93-172">A Quantum Development Kit részeként terjesztett teljes állapotú kvantum-szimulátor a teljes kvantum-rendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja a komplex számok egydimenziós tömbje, amelyben az egyes elemek a számítás alapjául szolgáló "\ket{n} $" számítási valószínűségének amplitúdóját jelölik, ahol a $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ a BITS $ \{ b_i \} $ esetében.</span><span class="sxs-lookup"><span data-stu-id="4bf93-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="4bf93-173">Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , a \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpmachine> generálja ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="4bf93-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4bf93-174">Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.</span><span class="sxs-lookup"><span data-stu-id="4bf93-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="4bf93-175">A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{n} $ és a poláris formátumban egyaránt.</span><span class="sxs-lookup"><span data-stu-id="4bf93-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="4bf93-176">Az első sorra vonatkozó részletek:</span><span class="sxs-lookup"><span data-stu-id="4bf93-176">In detail for the first row:</span></span>

* <span data-ttu-id="4bf93-177">**`∣0❭:`** Ez a sor a `0` számítási alap állapotnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="4bf93-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="4bf93-178">**`0.707107 +  0.000000 i`**: a valószínűségi amplitúdója Descartes formátumban.</span><span class="sxs-lookup"><span data-stu-id="4bf93-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="4bf93-179">**` == `**: a `equal` jel elválasztja mindkét egyenértékű ábrázolást.</span><span class="sxs-lookup"><span data-stu-id="4bf93-179">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="4bf93-180">**`**********  `**: A magnitúdó grafikus ábrázolása, amelynek száma arányos az `*` állapot-vektor mérésének valószínűségével.</span><span class="sxs-lookup"><span data-stu-id="4bf93-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="4bf93-181">**`[ 0.500000 ]`**: a magnitúdó numerikus értéke</span><span class="sxs-lookup"><span data-stu-id="4bf93-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="4bf93-182">**`    ---`**: Az amplitúdó fázisának grafikus ábrázolása (lásd alább).</span><span class="sxs-lookup"><span data-stu-id="4bf93-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="4bf93-183">**`[ 0.0000 rad ]`**: a fázis numerikus értéke (radiánban).</span><span class="sxs-lookup"><span data-stu-id="4bf93-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="4bf93-184">A magnitúdó és a fázis is grafikus ábrázolással jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4bf93-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="4bf93-185">A magnitúdó ábrázolása egyenesen előre látható: egy sáv `*` , annál nagyobb a valószínűsége annak, hogy a sáv nagyobb lesz.</span><span class="sxs-lookup"><span data-stu-id="4bf93-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="4bf93-186">A fázisban a következő szimbólumok jelennek meg, amelyek a tartományon alapuló szöget jelölik:</span><span class="sxs-lookup"><span data-stu-id="4bf93-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="4bf93-187">Az alábbi példák `DumpMachine` néhány gyakori állapotot mutatnak be:</span><span class="sxs-lookup"><span data-stu-id="4bf93-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="4bf93-188">A qubit azonosítója futásidőben van hozzárendelve, és nem szükségszerűen igazodik azzal a sorrendtel, ahogy a qubit le lett foglalva, vagy a qubit-regisztráción belüli pozíciója.</span><span class="sxs-lookup"><span data-stu-id="4bf93-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4bf93-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4bf93-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="4bf93-190">Létrehozhat egy qubit-azonosítót a Visual Studióban, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:</span><span class="sxs-lookup"><span data-stu-id="4bf93-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > <span data-ttu-id="4bf93-192">az indextel rendelkező `0` qubit `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4bf93-193">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4bf93-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="4bf93-194">Az üzenetben megtalálhatja a qubit azonosítóját <xref:microsoft.quantum.intrinsic.message> , és átadhatja a qubit változót, például:</span><span class="sxs-lookup"><span data-stu-id="4bf93-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="4bf93-195">amely a következő kimenetet eredményezheti:</span><span class="sxs-lookup"><span data-stu-id="4bf93-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="4bf93-196">Ez azt jelenti, hogy az indextel rendelkező qubit `0` `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .</span><span class="sxs-lookup"><span data-stu-id="4bf93-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="4bf93-197"><xref:microsoft.quantum.diagnostics.dumpmachine>a <xref:microsoft.quantum.diagnostics> névtér része, ezért a használatához hozzá kell adnia egy `open` utasítást:</span><span class="sxs-lookup"><span data-stu-id="4bf93-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="4bf93-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="4bf93-198">DumpRegister</span></span>

<span data-ttu-id="4bf93-199"><xref:microsoft.quantum.diagnostics.dumpregister>ugyanúgy működik <xref:microsoft.quantum.diagnostics.dumpmachine> , mint például a qubits egy tömbjét is, amely korlátozza az információk mennyiségét, hogy csak a megfelelő qubits legyenek érvényesek.</span><span class="sxs-lookup"><span data-stu-id="4bf93-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="4bf93-200">A szolgáltatáshoz hasonlóan <xref:microsoft.quantum.diagnostics.dumpmachine> a által generált információk is a <xref:microsoft.quantum.diagnostics.dumpregister> célszámítógéptől függenek.</span><span class="sxs-lookup"><span data-stu-id="4bf93-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="4bf93-201">Ahhoz, hogy a teljes állapotú kvantum-szimulátor a fájlba írja a Wave funkciót, a megadott qubits által generált kvantum alrendszer globális szakaszába kerül, amely ugyanabban a formátumban van <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="4bf93-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="4bf93-202">Például: ismételje meg a gépet, amely csak két qubits foglal le, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt} \ket {2} {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpregister> a következő kimenet előállítására `qubit[0]` :</span><span class="sxs-lookup"><span data-stu-id="4bf93-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4bf93-203">ezt a <xref:microsoft.quantum.diagnostics.dumpregister> kimenetet a következőre hívja `qubit[1]` elő:</span><span class="sxs-lookup"><span data-stu-id="4bf93-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="4bf93-204">Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot.</span><span class="sxs-lookup"><span data-stu-id="4bf93-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="4bf93-205">Ebben az esetben <xref:microsoft.quantum.diagnostics.dumpregister> a következő üzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="4bf93-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="4bf93-206">Az alábbi példa bemutatja, hogyan használhatja a <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> Q # kódját:</span><span class="sxs-lookup"><span data-stu-id="4bf93-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="4bf93-207">Hibakeresés</span><span class="sxs-lookup"><span data-stu-id="4bf93-207">Debugging</span></span>

<span data-ttu-id="4bf93-208">A (z `Assert` ) és a `Dump` functions és az Operations (feladatok és műveletek) esetében a Q # a szabványos Visual Studio hibakeresési képességeinek egy részhalmazát támogatja: a [vonali töréspontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), a [kód az F10 használatával](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) történő [megvizsgálása és a klasszikus változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) mind lehetséges a szimulátorban.</span><span class="sxs-lookup"><span data-stu-id="4bf93-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="4bf93-209">A Visual Studio Code-ban a hibakeresés a C# által a OmniSharp által működtetett Visual Studio Code-bővítmény által biztosított hibakeresési képességeket használja, és a [legújabb verziót](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)kell telepítenie.</span><span class="sxs-lookup"><span data-stu-id="4bf93-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
