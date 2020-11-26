---
title: Tesztelés és hibakeresés
description: Megtudhatja, hogyan használhatók az egységes tesztek, a tények és a kijelentések, valamint a kvantum-programok tesztelésére és hibakeresésére szolgáló függvények.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 17a67f0a6fa7ffb9436828178acd93e1cb87a8cd
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233991"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="c9f20-103">Tesztelés és hibakeresés</span><span class="sxs-lookup"><span data-stu-id="c9f20-103">Testing and debugging</span></span>

<span data-ttu-id="c9f20-104">A klasszikus programozáshoz hasonlóan elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a helytelen viselkedést.</span><span class="sxs-lookup"><span data-stu-id="c9f20-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="c9f20-105">Ebben a szakaszban a Q# kvantum-programok tesztelésére és hibakeresésére szolgáló eszközöket ismertetjük.</span><span class="sxs-lookup"><span data-stu-id="c9f20-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="c9f20-106">Egység tesztek</span><span class="sxs-lookup"><span data-stu-id="c9f20-106">Unit Tests</span></span>

<span data-ttu-id="c9f20-107">A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat *ír,* amelyekben a kód egy könyvtárban fut, és a kimenetét egy bizonyos várt kimenethez hasonlítja össze.</span><span class="sxs-lookup"><span data-stu-id="c9f20-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="c9f20-108">Például gondoskodhat arról, hogy a visszaadott érték a következőt jeleníti meg: `Square(2)` `4` 1 – 2 ^ 2 = $4. *a priori*</span><span class="sxs-lookup"><span data-stu-id="c9f20-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="c9f20-109">Q# támogatja az egységek tesztelését a kvantum-programokhoz, és amelyek a [xUnit](https://xunit.github.io/) -egység tesztelési keretrendszerén belül is futtathatnak teszteket.</span><span class="sxs-lookup"><span data-stu-id="c9f20-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="c9f20-110">Tesztelési projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9f20-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9f20-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9f20-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c9f20-112">Nyissa meg a Visual Studio 2019 alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="c9f20-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="c9f20-113">Lépjen a **fájl** menüre, és válassza az **új > projekt...** lehetőséget. A jobb felső sarokban keresse meg a `Q#` elemet, és válassza ki a **Q# teszt projekt** sablonját.</span><span class="sxs-lookup"><span data-stu-id="c9f20-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9f20-114">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9f20-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c9f20-115">A kedvenc parancssorában futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="c9f20-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="c9f20-116">Az új projekt egyetlen fájllal rendelkezik `Tests.qs` , amely kényelmes helyet biztosít az új egység-tesztek definiálásához Q# .</span><span class="sxs-lookup"><span data-stu-id="c9f20-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="c9f20-117">Kezdetben ez a fájl egy minta egység tesztet tartalmaz, `AllocateQubit` amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket $ állapotban van-e, {0} és kinyomtat egy üzenetet:</span><span class="sxs-lookup"><span data-stu-id="c9f20-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="c9f20-118">Q#A Type és Returns argumentumot használó műveletek vagy függvények `Unit` `Unit` az attribútumon keresztül is megjelölhetik egységként `@Test("...")` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="c9f20-119">Az előző példában az attribútum argumentuma `"QuantumSimulator"` meghatározza azt a célt, amelyen a teszt fut.</span><span class="sxs-lookup"><span data-stu-id="c9f20-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="c9f20-120">Egyetlen teszt több célponton is futhat.</span><span class="sxs-lookup"><span data-stu-id="c9f20-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="c9f20-121">Adjon meg például egy attribútumot a `@Test("ResourcesEstimator")` előtt `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="c9f20-122">Mentse a fájlt, és futtassa az összes tesztet.</span><span class="sxs-lookup"><span data-stu-id="c9f20-122">Save the file and run all tests.</span></span> <span data-ttu-id="c9f20-123">Ekkor két egységre vonatkozó tesztnek kell lennie, amelyek közül az egyik, a pedig az `AllocateQubit` `QuantumSimulator` , ahol a fut `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="c9f20-124">A Q# fordító felismeri a beépített célokat `"QuantumSimulator"` , `"ToffoliSimulator"` és `"ResourcesEstimator"` érvényes futtatási célokat az egység-tesztekhez.</span><span class="sxs-lookup"><span data-stu-id="c9f20-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="c9f20-125">A teljes nevet is megadhatja egy egyéni futtatási cél definiálásához.</span><span class="sxs-lookup"><span data-stu-id="c9f20-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="c9f20-126">Futó Q# egység tesztek</span><span class="sxs-lookup"><span data-stu-id="c9f20-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9f20-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9f20-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c9f20-128">Egyszeri egyszeri megoldás beállítása esetén lépjen a **teszt** menüre, és válassza a **tesztelési beállítások > az alapértelmezett processzor-architektúra > x64** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9f20-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="c9f20-129">A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások ( `.suo` ) fájljában tárolódik.</span><span class="sxs-lookup"><span data-stu-id="c9f20-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="c9f20-130">Ha törli ezt a fájlt, akkor a processzor architektúrája előtt ki kell választania az **x64** -et.</span><span class="sxs-lookup"><span data-stu-id="c9f20-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="c9f20-131">Hozza létre a projektet, nyissa meg a **teszt** menüt, és válassza a **Windows > test Explorer** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9f20-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="c9f20-132">A **AllocateQubit** megjeleníti a tesztek listáját a **nem futtatott tesztek** csoportban.</span><span class="sxs-lookup"><span data-stu-id="c9f20-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="c9f20-133">Válassza **az összes futtatása** lehetőséget, vagy futtassa ezt az egyéni tesztet.</span><span class="sxs-lookup"><span data-stu-id="c9f20-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9f20-134">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9f20-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c9f20-135">A tesztek futtatásához navigáljon a projekt mappájához (a mappát tartalmazó mappához `Tests.csproj` ), és futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="c9f20-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="c9f20-136">A következőhöz hasonló kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="c9f20-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="c9f20-137">Az egységbeli tesztek a nevük vagy a futtatási cél szerint szűrhetők:</span><span class="sxs-lookup"><span data-stu-id="c9f20-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="c9f20-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c9f20-138">\*\*_</span></span>

<span data-ttu-id="c9f20-139">A belső függvény <xref:Microsoft.Quantum.Intrinsic.Message> típusa `(String -> Unit)` és engedélyezése lehetővé teszi a diagnosztikai üzenetek létrehozását.</span><span class="sxs-lookup"><span data-stu-id="c9f20-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9f20-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9f20-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c9f20-141">Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt futtatásával kapcsolatos információkat jeleníti meg: a Pass/Fail állapot, az eltelt idő és a kimenetre mutató hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="c9f20-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="c9f20-142">Kattintson az _ output \* (\*kimenet\*\*) elemre a tesztelési kimenet új ablakban való megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c9f20-142">Click _ *Output*\* to open the test output in a new window.</span></span>

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9f20-144">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9f20-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c9f20-145">Az egyes tesztek esetén a Pass/Fail állapotot a konzolon kell kinyomtatni `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="c9f20-146">A sikertelen tesztek esetén a kimenetek a konzolon is kinyomtathatók a hiba diagnosztizálásához.</span><span class="sxs-lookup"><span data-stu-id="c9f20-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="c9f20-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c9f20-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="c9f20-148">Tények és kijelentések</span><span class="sxs-lookup"><span data-stu-id="c9f20-148">Facts and Assertions</span></span>

<span data-ttu-id="c9f20-149">Mivel a függvények Q# nem rendelkeznek _logikai_ mellékhatásokkal, a programon belül soha nem figyelheti meg, hogy egy adott Q# alkalmazásból más típusú effektusok is futnak, amelyek kimeneti típusa az üres rekord `()` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-149">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="c9f20-150">Vagyis a célszámítógép dönthet úgy, hogy nem futtat olyan függvényt, amely visszaadja `()` azt a garanciát, hogy ez a mulasztás nem módosítja a következő Q# kódok viselkedését.</span><span class="sxs-lookup"><span data-stu-id="c9f20-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="c9f20-151">Ez a viselkedés lehetővé teszi, hogy a függvény visszaadja `()` (például `Unit` ) egy hasznos eszközt a bejelentésekhez és a hibakeresési logikához a Q# programokba.</span><span class="sxs-lookup"><span data-stu-id="c9f20-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="c9f20-152">Vegyünk egy egyszerű példát:</span><span class="sxs-lookup"><span data-stu-id="c9f20-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="c9f20-153">Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, és kivételt vet fel a programot futtató célszámítógépen Q# .</span><span class="sxs-lookup"><span data-stu-id="c9f20-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="c9f20-154">Definíció szerint az ilyen típusú hibák nem figyelhetők meg a belülről Q# , mert a célszámítógép már nem futtatja a Q# kódot egy utasítás elérése után `fail` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-154">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="c9f20-155">Így ha folytatunk egy hívást a szolgáltatásba `PositivityFact` , biztos lehet abban, hogy a bemenete pozitív volt.</span><span class="sxs-lookup"><span data-stu-id="c9f20-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="c9f20-156">Vegye figyelembe, hogy ugyanaz a viselkedés valósítható meg, mint a `PositivityFact` [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) névtérből származó függvény használatával <xref:Microsoft.Quantum.Diagnostics> :</span><span class="sxs-lookup"><span data-stu-id="c9f20-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="c9f20-157">A _Assertions \* másrészt a tényekhez hasonlóan használják, de a célszámítógép állapotától függően változhatnak.</span><span class="sxs-lookup"><span data-stu-id="c9f20-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="c9f20-158">Ennek megfelelően a műveletekként vannak definiálva, míg a tények függvényekként vannak definiálva (ahogy az előző példában is látható).</span><span class="sxs-lookup"><span data-stu-id="c9f20-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="c9f20-159">A különbségtétel megértéséhez vegye figyelembe, hogy a következők valamelyikét kell használnia egy állításon belül:</span><span class="sxs-lookup"><span data-stu-id="c9f20-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="c9f20-160">Itt a műveletet használjuk a <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> rendelkezésre álló qubits számának visszaküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="c9f20-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="c9f20-161">Mivel ez a program globális állapotától és a futtatási környezettől függ, a definíciójának is `AssertQubitsAreAvailable` egy műveletnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c9f20-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="c9f20-162">Ezt a globális állapotot azonban használhatja arra, hogy egy egyszerű `Bool` értéket adjon meg bemenetként a `Fact` függvénynek.</span><span class="sxs-lookup"><span data-stu-id="c9f20-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="c9f20-163">Ezen ötletek alapján [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude)két, különösen hasznos állítást kínál, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> és <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> mindkét modell a műveletekre épül `()` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="c9f20-164">Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy kvantum-regisztrációt és egy feltételezett eredményt mutat be.</span><span class="sxs-lookup"><span data-stu-id="c9f20-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="c9f20-165">A szimuláció által végzett működést [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem)nem köti, és ezeket a méréseket anélkül hajthatja végre, hogy megzavarja a regisztrációt, amely megfelel az ilyen állításoknak.</span><span class="sxs-lookup"><span data-stu-id="c9f20-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="c9f20-166">A szimulátor ezután az `PositivityFact` előző függvényhez hasonló módon állíthatja le a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:</span><span class="sxs-lookup"><span data-stu-id="c9f20-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="c9f20-167">Fizikai kvantum-hardveren, ahol a nem klónozási tétel megakadályozza a kvantum-állapot vizsgálatát, a `AssertMeasurement` és a `AssertMeasurementProbability` műveletek egyszerűen visszatérhetnek `()` más hatás nélkül.</span><span class="sxs-lookup"><span data-stu-id="c9f20-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="c9f20-168">A <xref:Microsoft.Quantum.Diagnostics> névtér több funkciót is biztosít a `Assert` család számára, amellyel további speciális feltételeket is megtudhat.</span><span class="sxs-lookup"><span data-stu-id="c9f20-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="c9f20-169">Memóriakép függvények</span><span class="sxs-lookup"><span data-stu-id="c9f20-169">Dump Functions</span></span>

<span data-ttu-id="c9f20-170">A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:Microsoft.Quantum.Diagnostics> névtér két olyan függvényt biztosít, amelyek a célszámítógép aktuális állapotát a következő fájlba tudják bemutatni: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> és <xref:Microsoft.Quantum.Diagnostics.DumpRegister> .</span><span class="sxs-lookup"><span data-stu-id="c9f20-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="c9f20-171">A generált kimenet a célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="c9f20-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="c9f20-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="c9f20-172">DumpMachine</span></span>

<span data-ttu-id="c9f20-173">A Quantum Development Kit részeként terjesztett teljes állapotú kvantum-szimulátor a teljes kvantum-rendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja a komplex számok egydimenziós tömbje, amelyben az egyes elemek a számítás alapjául szolgáló "\ket{n} $" számítási valószínűségének amplitúdóját jelölik, ahol a $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ a BITS $ \{ b_i \} $ esetében.</span><span class="sxs-lookup"><span data-stu-id="c9f20-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="c9f20-174">Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , a \end{align} $ $ hívás <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generálja ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="c9f20-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c9f20-175">Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.</span><span class="sxs-lookup"><span data-stu-id="c9f20-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="c9f20-176">A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{n} $ és a poláris formátumban egyaránt.</span><span class="sxs-lookup"><span data-stu-id="c9f20-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="c9f20-177">Az első sorra vonatkozó részletek:</span><span class="sxs-lookup"><span data-stu-id="c9f20-177">In detail for the first row:</span></span>

* <span data-ttu-id="c9f20-178">**`∣0❭:`** Ez a sor a `0` számítási alap állapotnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="c9f20-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="c9f20-179">**`0.707107 +  0.000000 i`**: a valószínűségi amplitúdója Descartes formátumban.</span><span class="sxs-lookup"><span data-stu-id="c9f20-179">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="c9f20-180">**` == `**: a `equal` jel elválasztja mindkét egyenértékű ábrázolást.</span><span class="sxs-lookup"><span data-stu-id="c9f20-180">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="c9f20-181">**`**********  `**: A magnitúdó grafikus ábrázolása, amelynek száma arányos az `*` állapot-vektor mérésének valószínűségével.</span><span class="sxs-lookup"><span data-stu-id="c9f20-181">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="c9f20-182">**`[ 0.500000 ]`**: a magnitúdó numerikus értéke</span><span class="sxs-lookup"><span data-stu-id="c9f20-182">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="c9f20-183">**`    ---`**: Az amplitúdó fázisának grafikus ábrázolása (lásd a következő kimenetet).</span><span class="sxs-lookup"><span data-stu-id="c9f20-183">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="c9f20-184">**`[ 0.0000 rad ]`**: a fázis numerikus értéke (radiánban).</span><span class="sxs-lookup"><span data-stu-id="c9f20-184">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="c9f20-185">A magnitúdó és a fázis is grafikus ábrázolással jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c9f20-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="c9f20-186">A magnitúdó ábrázolása egyenesen előre látható: egy sáv `*` , annál nagyobb a valószínűsége annak, hogy a sáv nagyobb lesz.</span><span class="sxs-lookup"><span data-stu-id="c9f20-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="c9f20-187">A fázisban a következő szimbólumok jelennek meg, amelyek a tartományon alapuló szöget jelölik:</span><span class="sxs-lookup"><span data-stu-id="c9f20-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="c9f20-188">Az alábbi példák `DumpMachine` néhány gyakori állapotot mutatnak be:</span><span class="sxs-lookup"><span data-stu-id="c9f20-188">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="c9f20-189">A qubit azonosítója futásidőben van hozzárendelve, és nem feltétlenül igazodik azzal a sorrendtel, ahogy a qubit le lett foglalva, vagy a qubit-regisztráción belüli pozíciója.</span><span class="sxs-lookup"><span data-stu-id="c9f20-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9f20-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9f20-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="c9f20-191">A Visual Studióban egy qubit-azonosítót is megtalálhat, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:</span><span class="sxs-lookup"><span data-stu-id="c9f20-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > <span data-ttu-id="c9f20-193">az indextel rendelkező `0` qubit `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9f20-194">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9f20-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="c9f20-195">A qubit megkeresheti a függvény használatával, és átadhatja <xref:Microsoft.Quantum.Intrinsic.Message> a qubit változót az üzenetben, például:</span><span class="sxs-lookup"><span data-stu-id="c9f20-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="c9f20-196">amely a következő kimenetet eredményezheti:</span><span class="sxs-lookup"><span data-stu-id="c9f20-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="c9f20-197">Ez azt jelenti, hogy az indextel rendelkező qubit `0` `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .</span><span class="sxs-lookup"><span data-stu-id="c9f20-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="c9f20-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c9f20-198">\*\*_</span></span>

<span data-ttu-id="c9f20-199">Mivel <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a a névtér része  <xref:Microsoft.Quantum.Diagnostics> , hozzá kell adnia egy `open` utasítást az eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="c9f20-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="c9f20-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="c9f20-200">DumpRegister</span></span>

<span data-ttu-id="c9f20-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> ugyanúgy működik <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , mint az, hogy a qubits egy tömbjét is végrehajtja, amely az adatok mennyiségét csak a megfelelő qubits vonatkozó információkra korlátozza.</span><span class="sxs-lookup"><span data-stu-id="c9f20-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="c9f20-202">A szolgáltatáshoz hasonlóan <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a által generált információk is a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> célszámítógéptől függenek.</span><span class="sxs-lookup"><span data-stu-id="c9f20-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="c9f20-203">Ahhoz, hogy a teljes állapotú kvantum-szimulátor a fájlba írja a Wave funkciót, a megadott qubits által generált kvantum alrendszer globális szakaszába kerül, amely ugyanabban a formátumban van <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .</span><span class="sxs-lookup"><span data-stu-id="c9f20-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="c9f20-204">Például: ismételje meg a gépet, amely csak két qubits foglal le, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt} \ket {2} {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ hívás <xref:Microsoft.Quantum.Diagnostics.DumpRegister> a következő kimenet előállítására `qubit[0]` :</span><span class="sxs-lookup"><span data-stu-id="c9f20-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c9f20-205">ezt a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> kimenetet a következőre hívja `qubit[1]` elő:</span><span class="sxs-lookup"><span data-stu-id="c9f20-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="c9f20-206">Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot.</span><span class="sxs-lookup"><span data-stu-id="c9f20-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="c9f20-207">Ebben az esetben <xref:Microsoft.Quantum.Diagnostics.DumpRegister> a következő üzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="c9f20-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="c9f20-208">Az alábbi példa bemutatja, hogyan használható a kód a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> és <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a Q# kódban:</span><span class="sxs-lookup"><span data-stu-id="c9f20-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="c9f20-209">Hibakeresés</span><span class="sxs-lookup"><span data-stu-id="c9f20-209">Debugging</span></span>

<span data-ttu-id="c9f20-210">A (z `Assert` ) és a `Dump` functions és az Operations (funkciók és műveletek) esetében a Q# Visual Studio szabványos hibakeresési képességeinek egy részhalmazát támogatja: a [vonali töréspontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), az [F10 használatával történő léptetés](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), valamint a [klasszikus változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) mind lehetséges, ha a kódot a szimulátoron futtatják.</span><span class="sxs-lookup"><span data-stu-id="c9f20-210">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="c9f20-211">A Visual Studio Code-ban a hibakeresés a C# által a OmniSharp által működtetett Visual Studio Code-bővítmény által biztosított hibakeresési képességeket használja, és a [legújabb verziót](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)kell telepítenie.</span><span class="sxs-lookup"><span data-stu-id="c9f20-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
