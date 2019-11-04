---
title: 'Q # technikák – tesztelés és hibakeresés | Microsoft Docs'
description: 'Q # technikák – tesztelés és hibakeresés'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183488"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="971f9-103">Tesztelés és hibakeresés</span><span class="sxs-lookup"><span data-stu-id="971f9-103">Testing and Debugging</span></span>

<span data-ttu-id="971f9-104">Csakúgy, mint a klasszikus programozás esetében, elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a kvantum programot, amely helytelen.</span><span class="sxs-lookup"><span data-stu-id="971f9-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="971f9-105">Ebben a szakaszban a Q # által nyújtott eszközöket fogjuk kiszolgálni a kvantum-programok teszteléséhez és hibakereséséhez.</span><span class="sxs-lookup"><span data-stu-id="971f9-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="971f9-106">Egység tesztek</span><span class="sxs-lookup"><span data-stu-id="971f9-106">Unit Tests</span></span>

<span data-ttu-id="971f9-107">A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat ír *, amelyekben* kód fut egy könyvtárban, és hasonlítsa össze a kimenetét a várt kimenettel.</span><span class="sxs-lookup"><span data-stu-id="971f9-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="971f9-108">Előfordulhat például, hogy azt szeretnénk, hogy a `Square(2)` visszaadja `4`ét, mert tudjuk, hogy *a priori* 2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="971f9-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="971f9-109">A Q # támogatja az egységnyi tesztek létrehozását a kvantum-programokhoz, amelyek a [xUnit](https://xunit.github.io/) egység tesztelési keretrendszerében tesztekként hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="971f9-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="971f9-110">Tesztelési projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="971f9-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="971f9-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="971f9-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="971f9-112">Nyissa meg a Visual Studio 2019 alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="971f9-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="971f9-113">Lépjen a `File` menüre, és válassza a `New` > `Project...`lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="971f9-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="971f9-114">A Project template Explorerben `Installed` > `Visual C#`alatt válassza ki a `Q# Test Project` sablont.</span><span class="sxs-lookup"><span data-stu-id="971f9-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="971f9-115">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="971f9-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="971f9-116">A kedvenc parancssorában futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="971f9-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="971f9-117">Mindkét esetben az új projekt két fájl megnyitását fogja megnyitni.</span><span class="sxs-lookup"><span data-stu-id="971f9-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="971f9-118">Az első fájl, `Tests.qs`, kényelmes helyet biztosít az új Q # egység tesztek definiálásához.</span><span class="sxs-lookup"><span data-stu-id="971f9-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="971f9-119">Kezdetben ez a fájl egy minta egység tesztelési `AllocateQubitTest` tartalmaz, amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket{0}$ állapotban van-e, és kinyomtat egy üzenetet:</span><span class="sxs-lookup"><span data-stu-id="971f9-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="971f9-120">Bármely Q # művelet, amely kompatibilis a `(Unit => Unit)` vagy az `(Unit -> Unit)`-kompatibilis funkcióval, egységként való tesztelésként hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="971f9-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="971f9-121">A második fájl `TestSuiteRunner.cs` olyan metódust tartalmaz, amely felfedi a Q # Unit teszteket, és futtatja őket.</span><span class="sxs-lookup"><span data-stu-id="971f9-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="971f9-122">Ezt a módszert `TestTarget` `OperationDriver` attribútummal kell megjegyzetni.</span><span class="sxs-lookup"><span data-stu-id="971f9-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="971f9-123">A `OperationDriver` attribútum a Microsoft. Quantum. szimulációs. xUnit xUnit bővítményének részét képezi.</span><span class="sxs-lookup"><span data-stu-id="971f9-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="971f9-124">Az Unit Testing Framework meghívja a `TestTarget` metódust minden Q # egység által észlelt teszthez.</span><span class="sxs-lookup"><span data-stu-id="971f9-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="971f9-125">A keretrendszer `op` argumentumon keresztül továbbítja az egység teszt leírását a metódusnak.</span><span class="sxs-lookup"><span data-stu-id="971f9-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="971f9-126">A következő kódrészlet:</span><span class="sxs-lookup"><span data-stu-id="971f9-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="971f9-127">végrehajtja az egység tesztjét `QuantumSimulator`on.</span><span class="sxs-lookup"><span data-stu-id="971f9-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="971f9-128">Alapértelmezés szerint az egység teszt-felderítési mechanizmusa az összes Q # függvényt vagy kompatibilis típusú műveletet keresi, amelyek megfelelnek a következő tulajdonságokkal:</span><span class="sxs-lookup"><span data-stu-id="971f9-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="971f9-129">Ugyanabban a szerelvényben található, mint a metódus `OperationDriver` attribútummal való megjegyzése.</span><span class="sxs-lookup"><span data-stu-id="971f9-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="971f9-130">Ugyanabban a névtérben található, mint az `OperationDriver` attribútummal jegyzett metódus.</span><span class="sxs-lookup"><span data-stu-id="971f9-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="971f9-131">`Test`végződésű névvel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="971f9-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="971f9-132">Az egység tesztelési funkcióinak és műveleteinek egy szerelvénye, egy névtere és egy utótagja a `OperationDriver` attribútum nem kötelező paramétereinek használatával állítható be:</span><span class="sxs-lookup"><span data-stu-id="971f9-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="971f9-133">`AssemblyName` paraméter beállítja annak a szerelvénynek a nevét, amelyet tesztek keres.</span><span class="sxs-lookup"><span data-stu-id="971f9-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="971f9-134">`TestNamespace` paraméter beállítja annak a névtérnek a nevét, amelyet tesztek keres.</span><span class="sxs-lookup"><span data-stu-id="971f9-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="971f9-135">`Suffix` beállítja a műveleti vagy a függvények neveinak az egység-tesztelésnek megfelelő utótagját.</span><span class="sxs-lookup"><span data-stu-id="971f9-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="971f9-136">Továbbá a `TestCasePrefix` opcionális paraméterrel megadhat egy előtagot a tesztelési eset nevéhez.</span><span class="sxs-lookup"><span data-stu-id="971f9-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="971f9-137">A művelet neve előtt megjelenő előtag megjelenik a tesztelési esetek listájában.</span><span class="sxs-lookup"><span data-stu-id="971f9-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="971f9-138">A `TestCasePrefix = "QSim:"` például a talált tesztek listájában `QSim:AllocateQubitTest`ként fog megjelenni `AllocateQubitTest`.</span><span class="sxs-lookup"><span data-stu-id="971f9-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="971f9-139">Ez akkor lehet hasznos, ha például azt szeretné, hogy a rendszer melyik szimulátort használja a tesztek futtatásához.</span><span class="sxs-lookup"><span data-stu-id="971f9-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="971f9-140">Q # egység tesztek futtatása</span><span class="sxs-lookup"><span data-stu-id="971f9-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="971f9-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="971f9-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="971f9-142">Egyszeri egyszeri megoldás beállítása esetén lépjen `Test` menüre, és válassza `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="971f9-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="971f9-143">A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások (`.suo`) fájljában tárolódik.</span><span class="sxs-lookup"><span data-stu-id="971f9-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="971f9-144">Ha törli ezt a fájlt, akkor újra ki kell választania `X64` a processzor architektúrájának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="971f9-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="971f9-145">Hozza létre a projektet, lépjen a `Test` menüre, és válassza a `Windows` > `Test Explorer`lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="971f9-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="971f9-146">a `AllocateQubitTest` megjelennek a `Not Run Tests` csoportban lévő tesztek listájában.</span><span class="sxs-lookup"><span data-stu-id="971f9-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="971f9-147">Válassza ki `Run All` vagy futtassa ezt az egyéni tesztet, és adja meg a következőt.</span><span class="sxs-lookup"><span data-stu-id="971f9-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="971f9-148">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="971f9-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="971f9-149">A tesztek futtatásához navigáljon a projekt mappájához (a `Tests.csproj`tartalmazó mappához), és hajtsa végre a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="971f9-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="971f9-150">A következőhöz hasonló kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="971f9-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="971f9-151">Naplózás és kijelentések</span><span class="sxs-lookup"><span data-stu-id="971f9-151">Logging and Assertions</span></span>

<span data-ttu-id="971f9-152">Az egyik fontos következménye annak, hogy a Q #-ban lévő függvények ne legyenek mellékhatásai az, hogy olyan függvényt hajtson végre, amelynek kimeneti típusa az üres rekord `()` a Q # programon belül soha nem figyelhető meg.</span><span class="sxs-lookup"><span data-stu-id="971f9-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="971f9-153">Vagyis a célszámítógép úgy is dönthet, hogy nem hajt végre olyan függvényt, amely `()`t ad vissza, és ezzel garantálja, hogy ez a mulasztás nem módosítja a következő Q # kód viselkedését.</span><span class="sxs-lookup"><span data-stu-id="971f9-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="971f9-154">Ez lehetővé teszi a függvények visszaadását `()` egy hasznos eszközként, amely az állításokat és a hibakeresési logikát a Q # programokba ágyazza be.</span><span class="sxs-lookup"><span data-stu-id="971f9-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="971f9-155">Naplózás</span><span class="sxs-lookup"><span data-stu-id="971f9-155">Logging</span></span>

<span data-ttu-id="971f9-156">A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)`, és lehetővé teszi a diagnosztikai üzenetek létrehozását.</span><span class="sxs-lookup"><span data-stu-id="971f9-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="971f9-157">A `QuantumSimulator` `onLog` művelettel határozható meg a Q # Code-hívások `Message`akor végrehajtott műveletek.</span><span class="sxs-lookup"><span data-stu-id="971f9-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="971f9-158">Alapértelmezés szerint a naplózott üzenetek standard kimenetre vannak kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="971f9-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="971f9-159">A Unit test Suite meghatározásakor a naplózott üzenetek a teszt kimenetére irányíthatók.</span><span class="sxs-lookup"><span data-stu-id="971f9-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="971f9-160">Ha egy projekt a Q # teszt Project sablonból jön létre, az átirányítás előre be van állítva a csomaghoz, és alapértelmezés szerint a következőképpen jön létre:</span><span class="sxs-lookup"><span data-stu-id="971f9-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="971f9-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="971f9-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="971f9-162">Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt végrehajtásával kapcsolatos információkat tartalmazza: az átadott/sikertelen állapot, az eltelt idő és a "kimenet" hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="971f9-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="971f9-163">Ha a kimenet hivatkozásra kattint, a teszt kimenete új ablakban fog megnyílni.</span><span class="sxs-lookup"><span data-stu-id="971f9-163">If you click the "Output" link, test output will open in a new window.</span></span>

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="971f9-165">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="971f9-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="971f9-166">Az egyes tesztek Pass/Fail állapotának kinyomtatását a konzolon `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="971f9-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="971f9-167">A sikertelen tesztek esetén a fenti `output.WriteLine(msg)` hívás eredményeként naplózott kimenetek is kinyomtathatók a konzolon a hiba diagnosztizálásához.</span><span class="sxs-lookup"><span data-stu-id="971f9-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="971f9-168">Állításokat</span><span class="sxs-lookup"><span data-stu-id="971f9-168">Assertions</span></span>

<span data-ttu-id="971f9-169">Ugyanezt a logikát alkalmazhatja az érvényesítések megvalósítására is.</span><span class="sxs-lookup"><span data-stu-id="971f9-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="971f9-170">Vegyünk egy egyszerű példát:</span><span class="sxs-lookup"><span data-stu-id="971f9-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="971f9-171">Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, kivételt kell kiemelni a Q # programot futtató célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="971f9-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="971f9-172">Definíció szerint az ilyen típusú hibák nem figyelhetők meg a Q #-on belül, mert egy `fail` utasítás elérésekor nem fut további Q # kód.</span><span class="sxs-lookup"><span data-stu-id="971f9-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="971f9-173">Így ha folytatjuk a `AssertPositive`meghívását, biztos lehet abban, hogy a bemenete pozitív volt.</span><span class="sxs-lookup"><span data-stu-id="971f9-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="971f9-174">Ezen ötletek kiépítésekor [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude) két különösen hasznos állítást kínál, <xref:microsoft.quantum.intrinsic.assert> és <xref:microsoft.quantum.intrinsic.assertprob> mind a modellként, mind a `()`.</span><span class="sxs-lookup"><span data-stu-id="971f9-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="971f9-175">Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy olyan kvantum-regisztrációt, amelyre a mérést végzi, valamint egy feltételezett eredményt.</span><span class="sxs-lookup"><span data-stu-id="971f9-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="971f9-176">A szimulációval működő célszámítógépeken nem köti [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem), és elvégezheti az ilyen méréseket anélkül, hogy megzavarja volna az ilyen állításokra adott regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="971f9-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="971f9-177">A szimulátor ezután a fenti `AssertPositive` függvényhez hasonlóan megszakítja a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:</span><span class="sxs-lookup"><span data-stu-id="971f9-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="971f9-178">Fizikai kvantum-hardveren, ahol a klónozás nélküli tétel megakadályozza a kvantum-állapot vizsgálatát, a `Assert` és a `AssertProb` műveletek egyszerűen visszatérhetnek a `()` más hatás nélkül.</span><span class="sxs-lookup"><span data-stu-id="971f9-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="971f9-179">A <xref:microsoft.quantum.diagnostics> névtér a `Assert` család számos további funkcióját biztosítja, amelyek lehetővé teszik a fejlettebb feltételek ellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="971f9-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="971f9-180">Memóriakép függvények</span><span class="sxs-lookup"><span data-stu-id="971f9-180">Dump Functions</span></span>

<span data-ttu-id="971f9-181">A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:microsoft.quantum.diagnostics> névtér két olyan függvényt kínál, amely a célszámítógép aktuális állapotával (<xref:microsoft.quantum.diagnostics.dumpmachine> és <xref:microsoft.quantum.diagnostics.dumpregister>) képes a fájlba való kiírásra.</span><span class="sxs-lookup"><span data-stu-id="971f9-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="971f9-182">A generált kimenet a célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="971f9-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="971f9-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="971f9-183">DumpMachine</span></span>

<span data-ttu-id="971f9-184">A Quantum Development Kit részeként elosztott teljes állapotú kvantum-szimulátor a teljes kvantumrendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja be, amely a komplex számok egydimenziós tömbje, amelyben az egyes elemek a a számítási alap állapotának kiszámítása valószínűsége $ \ket{n} $, ahol $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ a BITS $\{b_i\}$ esetében.</span><span class="sxs-lookup"><span data-stu-id="971f9-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="971f9-185">Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ hívó <xref:microsoft.quantum.diagnostics.dumpmachine> generálja ezt a kimenetet :</span><span class="sxs-lookup"><span data-stu-id="971f9-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="971f9-186">Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.</span><span class="sxs-lookup"><span data-stu-id="971f9-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="971f9-187">A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{n} $ és a poláris formátumban egyaránt.</span><span class="sxs-lookup"><span data-stu-id="971f9-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="971f9-188">Az első sorra vonatkozó részletek:</span><span class="sxs-lookup"><span data-stu-id="971f9-188">In detail for the first row:</span></span>

* <span data-ttu-id="971f9-189">**`∣0❭:`** ez a sor a `0` számítási alap állapotának felel meg</span><span class="sxs-lookup"><span data-stu-id="971f9-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="971f9-190">**`0.707107 +  0.000000 i`** : a valószínűségi amplitúdó a Descartes formátumban.</span><span class="sxs-lookup"><span data-stu-id="971f9-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="971f9-191">**` == `** : a `equal` aláírja a elválasztja mindkét egyenértékű ábrázolást.</span><span class="sxs-lookup"><span data-stu-id="971f9-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="971f9-192">**`**********  `** : a magnitúdó grafikus ábrázolása, a `*` száma arányos az állapot-vektor mérési valószínűségével.</span><span class="sxs-lookup"><span data-stu-id="971f9-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="971f9-193">**`[ 0.500000 ]`** : a magnitúdó numerikus értéke</span><span class="sxs-lookup"><span data-stu-id="971f9-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="971f9-194">**`    ---`** : az amplitúdó fázisának grafikus ábrázolása (lásd alább).</span><span class="sxs-lookup"><span data-stu-id="971f9-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="971f9-195">**`[ 0.0000 rad ]`** : a fázis numerikus értéke (radiánban).</span><span class="sxs-lookup"><span data-stu-id="971f9-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="971f9-196">A magnitúdó és a fázis is grafikus ábrázolással jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="971f9-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="971f9-197">A magnitúdó ábrázolása egyenesen előre látható: az `*`egy sávot mutat, annál nagyobb a valószínűsége annak, hogy a sáv nagyobb lesz.</span><span class="sxs-lookup"><span data-stu-id="971f9-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="971f9-198">A fázisban a következő szimbólumok jelennek meg, amelyek a tartományon alapuló szöget jelölik:</span><span class="sxs-lookup"><span data-stu-id="971f9-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="971f9-199">Az alábbi példák a gyakori állapotok `DumpMachine` mutatják be:</span><span class="sxs-lookup"><span data-stu-id="971f9-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="971f9-200">A qubit azonosítója futásidőben van hozzárendelve, és nem szükségszerűen igazodik azzal a sorrendtel, ahogy a qubit le lett foglalva, vagy a qubit-regisztráción belüli pozíciója.</span><span class="sxs-lookup"><span data-stu-id="971f9-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="971f9-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="971f9-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="971f9-202">Létrehozhat egy qubit-azonosítót a Visual Studióban, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:</span><span class="sxs-lookup"><span data-stu-id="971f9-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > <span data-ttu-id="971f9-204">a (z) `register2` indextel `0` qubit azonosító =`3`, az index `1` azonosítójú qubit azonosítója =`2`.</span><span class="sxs-lookup"><span data-stu-id="971f9-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="971f9-205">Parancssor / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="971f9-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="971f9-206">Qubit-azonosítót a <xref:microsoft.quantum.intrinsic.message> függvénnyel talál, és átadhatja a qubit változót az üzenetben, például:</span><span class="sxs-lookup"><span data-stu-id="971f9-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="971f9-207">amely a következő kimenetet eredményezheti:</span><span class="sxs-lookup"><span data-stu-id="971f9-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="971f9-208">Ez azt jelenti, hogy a `register2` qubit rendelkező `0` azonosítója =`3`, a qubit index `1` azonosítója =`2`.</span><span class="sxs-lookup"><span data-stu-id="971f9-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="971f9-209"><xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics> névtér része, ezért a használatához hozzá kell adnia egy `open` utasítást:</span><span class="sxs-lookup"><span data-stu-id="971f9-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="971f9-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="971f9-210">DumpRegister</span></span>

<span data-ttu-id="971f9-211"><xref:microsoft.quantum.diagnostics.dumpregister> úgy működik, mint <xref:microsoft.quantum.diagnostics.dumpmachine>, kivéve, ha a qubits egy tömbjét is végrehajtja, amely korlátozza az adatok mennyiségét, hogy csak a megfelelő qubits legyenek érvényesek.</span><span class="sxs-lookup"><span data-stu-id="971f9-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="971f9-212">A <xref:microsoft.quantum.diagnostics.dumpmachine>hoz hasonlóan a <xref:microsoft.quantum.diagnostics.dumpregister> által generált információk a célszámítógéptől függenek.</span><span class="sxs-lookup"><span data-stu-id="971f9-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="971f9-213">A teljes állapotú kvantum-szimulátor esetében a Wave függvény a megadott qubits által generált kvantum alrendszerek globális fázisára mutat, a <xref:microsoft.quantum.diagnostics.dumpmachine>formátumával megegyező formátumban.</span><span class="sxs-lookup"><span data-stu-id="971f9-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="971f9-214">Tegyük fel például, hogy egy gép csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[0]` hozza létre ezt a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="971f9-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="971f9-215">és a <xref:microsoft.quantum.diagnostics.dumpregister> meghívása `qubit[1]` a kimenetet hozza létre:</span><span class="sxs-lookup"><span data-stu-id="971f9-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="971f9-216">Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot.</span><span class="sxs-lookup"><span data-stu-id="971f9-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="971f9-217">Ebben az esetben a <xref:microsoft.quantum.diagnostics.dumpregister> a következő üzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="971f9-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="971f9-218">Az alábbi példa bemutatja, hogyan használhatja a Q # Code-ban <xref:microsoft.quantum.diagnostics.dumpregister> és <xref:microsoft.quantum.diagnostics.dumpmachine> is:</span><span class="sxs-lookup"><span data-stu-id="971f9-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="971f9-219">Hibakeresés</span><span class="sxs-lookup"><span data-stu-id="971f9-219">Debugging</span></span>

<span data-ttu-id="971f9-220">`Assert` és `Dump` függvények és műveletek mellett a Q # a standard Visual Studio hibakeresési képességeinek egy részhalmazát támogatja: [vonali töréspontok beállítása, kód átadása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)az [F10 használatával](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) és [a klasszikus változók értékeinek vizsgálata ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)a szimulátoron a kód végrehajtása során minden lehetséges.</span><span class="sxs-lookup"><span data-stu-id="971f9-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="971f9-221">A Visual Studio Code-ban való hibakeresés még nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="971f9-221">Debugging in Visual Studio Code is not yet supported.</span></span>

