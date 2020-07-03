---
title: 'Q # program futtatásának módjai'
description: 'A Q # programok futtatásának különböző módjai – áttekintés. A parancssorból, a Q # Jupyter notebookok és a klasszikus gazda programok Python vagy .NET nyelven.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887682"
---
# <a name="ways-to-run-a-q-program"></a><span data-ttu-id="c660f-104">Q # program futtatásának módjai</span><span class="sxs-lookup"><span data-stu-id="c660f-104">Ways to run a Q# program</span></span>

<span data-ttu-id="c660f-105">A Quantum Development Kit egyik legnagyobb erőssége a platformok és a fejlesztői környezetek rugalmassága.</span><span class="sxs-lookup"><span data-stu-id="c660f-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="c660f-106">Ez azonban azt is jelenti, hogy az új Q #-felhasználók a [telepítési útmutatóban](xref:microsoft.quantum.install)található számos lehetőség alapján megzavarják vagy elárasztják magukat.</span><span class="sxs-lookup"><span data-stu-id="c660f-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="c660f-107">Ezen az oldalon elmagyarázza, hogy mi történik a Q # program futtatásakor, és hasonlítsa össze a felhasználók által megtehető különböző módokat.</span><span class="sxs-lookup"><span data-stu-id="c660f-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="c660f-108">Az elsődleges különbség az, hogy a Q # futtatható:</span><span class="sxs-lookup"><span data-stu-id="c660f-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="c660f-109">önálló alkalmazásként, ahol a Q # az egyetlen érintett nyelv, és a program közvetlenül hívja meg a programot.</span><span class="sxs-lookup"><span data-stu-id="c660f-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="c660f-110">Két metódus valójában a következő kategóriába tartozik:</span><span class="sxs-lookup"><span data-stu-id="c660f-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="c660f-111">a parancssori felület</span><span class="sxs-lookup"><span data-stu-id="c660f-111">the command line interface</span></span>
  - <span data-ttu-id="c660f-112">Q# nyelvű Jupyter-notebookok</span><span class="sxs-lookup"><span data-stu-id="c660f-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="c660f-113">egy további, Pythonban vagy .NET nyelven írt (pl. C# vagy F #) *befogadó programmal*, amely ezután meghívja a programot, és folytatja a visszaadott eredmények feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="c660f-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="c660f-114">Ha szeretné jobban megérteni ezeket a folyamatokat és azok különbségeit, tekintse meg az egyszerű Q # programot, és hasonlítsa össze a végrehajtható módszereket.</span><span class="sxs-lookup"><span data-stu-id="c660f-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-q-program"></a><span data-ttu-id="c660f-115">Alapszintű Q # program</span><span class="sxs-lookup"><span data-stu-id="c660f-115">Basic Q# program</span></span>

<span data-ttu-id="c660f-116">Egy alapszintű kvantum-program a qubit előállítását is magában foglalhatja az államok $ \ket $ és a $ \ket $ értékkel egyenlő arányban {0} {1} , a mérést és az eredményt visszaadva, amely a két, azonos valószínűséggel rendelkező állapot közül véletlenszerűen fog állni.</span><span class="sxs-lookup"><span data-stu-id="c660f-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="c660f-117">Ennek a folyamatnak a lényege a [Quantum Random Number Generator](xref:microsoft.quantum.quickstarts.qrng) rövid útmutatója.</span><span class="sxs-lookup"><span data-stu-id="c660f-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="c660f-118">A Q # esetében ezt a következő kód hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="c660f-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="c660f-119">Ez a kód azonban önmagában nem hajtható végre a Q # használatával.</span><span class="sxs-lookup"><span data-stu-id="c660f-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="c660f-120">Ehhez egy [művelet](xref:microsoft.quantum.guide.basics#q-operations-and-functions)törzsét kell kiállítania, amely akkor kerül végrehajtásra, amikor a---vagy közvetlenül, vagy egy másik művelet hívja meg.</span><span class="sxs-lookup"><span data-stu-id="c660f-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="c660f-121">Ezért a következő űrlapon is írhat egy műveletet:</span><span class="sxs-lookup"><span data-stu-id="c660f-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="c660f-122">Definiált egy műveletet, `MeasureSuperposition` amely nem vesz fel bemeneteket, és eredmény típusú értéket ad [Result](xref:microsoft.quantum.guide.types)vissza.</span><span class="sxs-lookup"><span data-stu-id="c660f-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="c660f-123">Habár az ezen a lapon szereplő példák csak a Q #- *műveletekből*állhatnak, az összes, a q # *függvényre*vonatkozó fogalmat is tárgyaljuk, ezért ezek együttesen *callables*.</span><span class="sxs-lookup"><span data-stu-id="c660f-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="c660f-124">A különbségeket a [Q # alapjai: Operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions)(műveletek és függvények) ismertetik, és az ezek meghatározásával kapcsolatos további részleteket a [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions)szolgáltatásban találja.</span><span class="sxs-lookup"><span data-stu-id="c660f-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-q-file"></a><span data-ttu-id="c660f-125">Meghívható definiálva egy Q # fájlban</span><span class="sxs-lookup"><span data-stu-id="c660f-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="c660f-126">A meghívásos pontosan a meghívott és a Q # által futtatott.</span><span class="sxs-lookup"><span data-stu-id="c660f-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="c660f-127">Azonban ehhez több kiegészítésre van szükség, amely egy teljes `*.qs` Q # fájlból áll.</span><span class="sxs-lookup"><span data-stu-id="c660f-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="c660f-128">Az összes Q # típus és callables (az Ön által definiált és a nyelvhez tartozók) a *névterekben*vannak definiálva, amelyek minden olyan teljes nevet megadnak, amelyre hivatkozni lehet.</span><span class="sxs-lookup"><span data-stu-id="c660f-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="c660f-129">Például a és a [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) műveletek a és a [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) névterekben találhatók (a [Q # standard kódtárak](xref:microsoft.quantum.qsharplibintro)része).</span><span class="sxs-lookup"><span data-stu-id="c660f-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="c660f-130">Így mindig meghívhatják a *teljes* nevüket, de mindig megtehetik, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` hogy ez nagyon zsúfolt programkódot eredményez.</span><span class="sxs-lookup"><span data-stu-id="c660f-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="c660f-131">Ehelyett `open` az utasítások lehetővé teszik, hogy a callables tömör gyorsírással legyenek hivatkozva, ahogy a fenti műveleti törzsben tettük.</span><span class="sxs-lookup"><span data-stu-id="c660f-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="c660f-132">A művelethez tartozó teljes Q # fájl ezért a saját névtér definiálását jelenti, a callables a művelet által használt névterek megnyitásával, majd a művelettel:</span><span class="sxs-lookup"><span data-stu-id="c660f-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="c660f-133">A névterek a megnyitásakor is *aliasként* használhatók, ami akkor lehet hasznos, ha a hívható/Type nevek két névtérben ütköznek.</span><span class="sxs-lookup"><span data-stu-id="c660f-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="c660f-134">Tegyük fel például, hogy a `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` fentieket fogjuk használni, majd meghívjuk a- `H` on keresztül `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="c660f-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="c660f-135">Ennek egyetlen kivétele a [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) névtér, amely mindig automatikusan megnyílik.</span><span class="sxs-lookup"><span data-stu-id="c660f-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="c660f-136">Ezért a callables, mint a [`Length`](xref:microsoft.quantum.core.length) mindig közvetlenül használhatók.</span><span class="sxs-lookup"><span data-stu-id="c660f-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="c660f-137">Végrehajtás a célszámítógépen</span><span class="sxs-lookup"><span data-stu-id="c660f-137">Execution on target machines</span></span>

<span data-ttu-id="c660f-138">Most a Q # program általános végrehajtási modellje világossá válik.</span><span class="sxs-lookup"><span data-stu-id="c660f-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="c660f-139">Először is a végrehajtáshoz megadott meghívásos hozzáférés minden más, ugyanabban a névtérben definiált callables és típushoz elérhető.</span><span class="sxs-lookup"><span data-stu-id="c660f-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="c660f-140">Emellett a [Q #-tárak](xref:microsoft.quantum.libraries)bármelyikéhez hozzáfér, de a teljes névvel vagy a `open` fent ismertetett utasítások használatával kell hivatkozni rájuk.</span><span class="sxs-lookup"><span data-stu-id="c660f-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="c660f-141">A meghívót a rendszer ezután a *[célszámítógépen](xref:microsoft.quantum.machines)* hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="c660f-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="c660f-142">Ilyen célszámítógépek lehetnek a tényleges kvantum-hardverek vagy a QDK részeként elérhető több szimulátorok.</span><span class="sxs-lookup"><span data-stu-id="c660f-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="c660f-143">Erre a célra a leghasznosabb célszámítógép a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)egy példánya, `QuantumSimulator` amely úgy számítja ki a program viselkedését, mintha egy zaj nélküli kvantum-számítógépen hajtották végre.</span><span class="sxs-lookup"><span data-stu-id="c660f-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="c660f-144">Eddig azt is ismertetjük, hogy mi történik, ha egy adott Q # meghívót hajt végre.</span><span class="sxs-lookup"><span data-stu-id="c660f-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="c660f-145">Függetlenül attól, hogy a Q # egy önálló alkalmazásban vagy egy gazda programban van használatban, ez az általános folyamat több vagy kevesebb, mint a QDK rugalmassága---.</span><span class="sxs-lookup"><span data-stu-id="c660f-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="c660f-146">A kvantum-fejlesztési készletbe való hívás különböző módjai közötti különbségek így felfedik a Q # hívható hívásának *módját* , és hogy milyen módon adja vissza az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="c660f-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="c660f-147">Pontosabban a különbségek körül forog</span><span class="sxs-lookup"><span data-stu-id="c660f-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="c660f-148">annak jelzése, hogy melyik Q # hívható legyen végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="c660f-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="c660f-149">a lehetséges hívható argumentumok megadása</span><span class="sxs-lookup"><span data-stu-id="c660f-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="c660f-150">annak a célszámítógépnek a meghatározása, amelyre a szolgáltatást végre szeretné hajtani, és</span><span class="sxs-lookup"><span data-stu-id="c660f-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="c660f-151">az eredmények visszaadása.</span><span class="sxs-lookup"><span data-stu-id="c660f-151">how any results are returned.</span></span>

<span data-ttu-id="c660f-152">Először is megbeszéljük, hogy ez hogyan történik a Q # önálló alkalmazás parancssorból való használatával, majd folytassa a Python és a C# gazdagép-programok használatát.</span><span class="sxs-lookup"><span data-stu-id="c660f-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="c660f-153">Fenntartjuk a Q # Jupyter-jegyzetfüzetek önálló alkalmazását, mert az első háromtól eltérően az elsődleges funkció nem a helyi Q # fájl körébe kerül.</span><span class="sxs-lookup"><span data-stu-id="c660f-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="c660f-154">Habár nem mutatjuk be ezeket a példákat, a végrehajtási módszerek egyike az, hogy a Q # programon belülről kinyomtatott összes üzenet (például: [`Message`](xref:microsoft.quantum.intrinsic.message) vagy [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ) általában mindig a megfelelő konzolra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="c660f-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="q-from-the-command-line"></a><span data-ttu-id="c660f-155">Q # a parancssorból</span><span class="sxs-lookup"><span data-stu-id="c660f-155">Q# from the command line</span></span>
<span data-ttu-id="c660f-156">A Q # programok írásához legkönnyebben elsajátíthatja az első lépéseket, hogy elkerülje a különálló fájlok és a második nyelv összetételét.</span><span class="sxs-lookup"><span data-stu-id="c660f-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="c660f-157">A Visual Studio Code vagy a Visual Studio és a QDK bővítmény használatával zökkenőmentes munkafolyamatot használhat, amelyben a Q # callables csak egyetlen Q # fájlból fut.</span><span class="sxs-lookup"><span data-stu-id="c660f-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="c660f-158">Ebben az esetben végső soron a program végrehajtásának meghívása a következővel:</span><span class="sxs-lookup"><span data-stu-id="c660f-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="c660f-159">a parancssorban.</span><span class="sxs-lookup"><span data-stu-id="c660f-159">in the command line.</span></span>
<span data-ttu-id="c660f-160">A legegyszerűbb munkafolyamat az, amikor a terminál címtárának helye megegyezik a Q # fájllal, amely könnyen kezelhető a Q # fájl szerkesztése mellett az integrált terminál használatával a VS Code-ban, például:.</span><span class="sxs-lookup"><span data-stu-id="c660f-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="c660f-161">A [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) azonban számos lehetőséget is elfogad, és a program más helyről is futtatható, ha egyszerűen megadja a `--project <PATH>` Q # fájl helyét.</span><span class="sxs-lookup"><span data-stu-id="c660f-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-q-file"></a><span data-ttu-id="c660f-162">Belépési pont hozzáadása a Q # fájlhoz</span><span class="sxs-lookup"><span data-stu-id="c660f-162">Add entry point to Q# file</span></span>

<span data-ttu-id="c660f-163">A legtöbb Q # fájl egynél több meghívót tartalmaz, ezért természetesen a fordítónak tudnia kell, hogy *melyik* meghívásos végrehajtásra van szükség a `dotnet run` parancs megadásakor.</span><span class="sxs-lookup"><span data-stu-id="c660f-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="c660f-164">Ez a Q # fájl egyszerű módosításával történik:</span><span class="sxs-lookup"><span data-stu-id="c660f-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="c660f-165">Adjon hozzá egy sort, amely `@EntryPoint()` közvetlenül megelőzi a meghívót.</span><span class="sxs-lookup"><span data-stu-id="c660f-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="c660f-166">Ezért a fenti fájl a következő lesz:</span><span class="sxs-lookup"><span data-stu-id="c660f-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="c660f-167">Most pedig a `dotnet run` parancssorból érkező hívás `MeasureSuperposition` fut, és a visszaadott érték közvetlenül a terminálra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="c660f-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="c660f-168">Így a rendszer `One` vagy kinyomtatja a következőt: `Zero` .</span><span class="sxs-lookup"><span data-stu-id="c660f-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="c660f-169">Vegye figyelembe, hogy nem számít, hogy ha több callables van definiálva, csak a `MeasureSuperposition` futtatásra kerül.</span><span class="sxs-lookup"><span data-stu-id="c660f-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="c660f-170">Emellett nem jelent problémát, ha a meghívó a nyilatkozata előtt is tartalmaz [dokumentációs megjegyzéseket](xref:microsoft.quantum.guide.filestructure#documentation-comments) , az `@EntryPoint()` attribútum egyszerűen elhelyezhető.</span><span class="sxs-lookup"><span data-stu-id="c660f-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="c660f-171">Hívható argumentumok</span><span class="sxs-lookup"><span data-stu-id="c660f-171">Callable arguments</span></span>

<span data-ttu-id="c660f-172">Eddig csak olyan műveletet vettünk figyelembe, amely nem vesz fel bemeneteket.</span><span class="sxs-lookup"><span data-stu-id="c660f-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="c660f-173">Tegyük fel, hogy hasonló műveletet hajtottunk végre, de több qubits---az argumentumként megadott számú értéket.</span><span class="sxs-lookup"><span data-stu-id="c660f-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="c660f-174">Egy ilyen művelet a következőképpen írható</span><span class="sxs-lookup"><span data-stu-id="c660f-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="c660f-175">ahol a visszaadott érték a mérési eredmények tömbje.</span><span class="sxs-lookup"><span data-stu-id="c660f-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="c660f-176">Vegye figyelembe, hogy [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) [`ForEach`](xref:microsoft.quantum.arrays.foreach) a és [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) a [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) névterek esetében további `open` utasításokra van szükség mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="c660f-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="c660f-177">Ha az `@EntryPoint()` attribútumot az új művelet előtt helyezi át (vegye figyelembe, hogy egy fájlban csak egy ilyen sor lehet), és a futtatásának megkísérlése egyszerűen `dotnet run` olyan hibaüzenetet eredményez, amely azt jelzi, hogy milyen további parancssori kapcsolók szükségesek, és hogyan fejezheti ki őket.</span><span class="sxs-lookup"><span data-stu-id="c660f-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="c660f-178">A parancssor általános formátuma ténylegesen `dotnet run [options]` , a hívható argumentumok pedig itt vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="c660f-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="c660f-179">Ebben az esetben az argumentum `n` hiányzik, és azt mutatja, hogy meg kell adnia a beállítást `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="c660f-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="c660f-180">A qubits való futtatáshoz `MeasureSuperpositionArray` ezért használjuk a következőt: `n=4`</span><span class="sxs-lookup"><span data-stu-id="c660f-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="c660f-181">a következőhöz hasonló kimenetet eredményez</span><span class="sxs-lookup"><span data-stu-id="c660f-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="c660f-182">Ez a tanfolyam több argumentumra is kiterjed.</span><span class="sxs-lookup"><span data-stu-id="c660f-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="c660f-183">A ben definiált argumentumok nevét `camelCase` a fordító a Q # bemenetként fogadja el kis mértékben.</span><span class="sxs-lookup"><span data-stu-id="c660f-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="c660f-184">Például, ha `n` a helyett a fenti nevet használtuk `numQubits` , akkor ez a bemenet a parancssoron keresztül lesz megadva a `--num-qubits 4` helyett `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="c660f-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="c660f-185">A hibaüzenet más lehetőségeket is tartalmaz, amelyek használhatók, beleértve a célszámítógép módosításának módját is.</span><span class="sxs-lookup"><span data-stu-id="c660f-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="c660f-186">Különböző célszámítógépek</span><span class="sxs-lookup"><span data-stu-id="c660f-186">Different target machines</span></span>

<span data-ttu-id="c660f-187">Mivel a műveleteik eredményei a tényleges qubits a várt eredmények voltak, egyértelmű, hogy a parancssorból az alapértelmezett célszámítógép a teljes állapotú quauntum szimulátor `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="c660f-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="c660f-188">Azonban arra is utasíthatja a callables, hogy egy adott célszámítógépen fusson a `--simulator` (vagy a gyorsírással) lehetőséggel `-s` .</span><span class="sxs-lookup"><span data-stu-id="c660f-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="c660f-189">Futtathatja például a következőt [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="c660f-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="c660f-190">Ekkor a kinyomtatott kimenet</span><span class="sxs-lookup"><span data-stu-id="c660f-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="c660f-191">Az ezekkel a mérőszámokkal kapcsolatos részletekért lásd [: erőforrás-kalkulátor: a jelentett mérőszámok](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="c660f-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="c660f-192">Parancssori végrehajtás összegzése</span><span class="sxs-lookup"><span data-stu-id="c660f-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a><span data-ttu-id="c660f-193">Nem Q # `dotnet run` kapcsolók</span><span class="sxs-lookup"><span data-stu-id="c660f-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="c660f-194">Ahogy a fentiekben röviden említettük `--project` , a [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) a Q # hívható argumentumokhoz nem kapcsolódó beállításokat is elfogadja.</span><span class="sxs-lookup"><span data-stu-id="c660f-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="c660f-195">Ha mindkét típusú beállítást megadja, a `dotnet` -specifikus beállításokat elsőként kell megadni, majd egy elválasztó karakter `--` , majd a Q #-specifikus beállításokat.</span><span class="sxs-lookup"><span data-stu-id="c660f-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="c660f-196">Például a specifiying egy elérési utat a fenti művelethez tartozó qubits együtt hajthat végre `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="c660f-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="q-with-host-programs"></a><span data-ttu-id="c660f-197">Q # gazdagép-programokkal</span><span class="sxs-lookup"><span data-stu-id="c660f-197">Q# with host programs</span></span>

<span data-ttu-id="c660f-198">A Q # fájllal együtt a művelet vagy a függvény közvetlenül a parancssorból való meghívására szolgáló alternatíva egy másik klasszikus nyelven *futtatott gazda program* használata.</span><span class="sxs-lookup"><span data-stu-id="c660f-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="c660f-199">Pontosabban megteheti a Python vagy a .NET nyelv, például a C# vagy az F # kombinációját (a rövidség kedvéért csak a C# adatokat fogjuk részletezni).</span><span class="sxs-lookup"><span data-stu-id="c660f-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="c660f-200">Az együttműködési képesség engedélyezéséhez valamivel több beállítás szükséges, de ezek a részletek a [telepítési útmutatókban](xref:microsoft.quantum.install)találhatók.</span><span class="sxs-lookup"><span data-stu-id="c660f-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c660f-201">Dióhéjban a helyzet most már tartalmaz egy gazda programfájlt (például `*.py` vagy `*.cs` ) a Q # fájllal megegyező helyen.</span><span class="sxs-lookup"><span data-stu-id="c660f-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="c660f-202">Most már a futtatott *gazda* program, a végrehajtásuk során pedig a q # fájl adott q # műveleteit és funkcióit hívhatja meg.</span><span class="sxs-lookup"><span data-stu-id="c660f-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="c660f-203">Az együttműködési képesség lényege a Q # fordítóprogramon alapul, amely a Q # fájl tartalmát elérhetővé teszi a gazda program számára, hogy azok meghívhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="c660f-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="c660f-204">A gazda program használatának egyik legfőbb előnye, hogy a Q # program által visszaadott klasszikus adatmennyiséget a gazdagép nyelvén lehet tovább feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="c660f-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="c660f-205">Ez néhány speciális adatfeldolgozásból állhat (például a Q #-ban belsőleg nem hajtható végre), majd az eredmények alapján további Q # műveletek is meghívhatók, vagy a Q # találatok ábrázolásával.</span><span class="sxs-lookup"><span data-stu-id="c660f-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="c660f-206">Az általános séma itt látható, és megbeszéljük a Python és a C# adott implementációit alább.</span><span class="sxs-lookup"><span data-stu-id="c660f-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="c660f-207">Az F # gazda programot használó minta a .net-es [együttműködési mintákon](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)érhető el.</span><span class="sxs-lookup"><span data-stu-id="c660f-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="c660f-208">A `@EntryPoint()` Q # parancssori alkalmazásokhoz használt attribútum nem használható gazda programokkal.</span><span class="sxs-lookup"><span data-stu-id="c660f-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="c660f-209">Egy hiba akkor jelenik meg, ha a Q # fájlban szerepel a gazdagép által meghívva.</span><span class="sxs-lookup"><span data-stu-id="c660f-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="c660f-210">A különböző gazdagép-programokkal való együttműködéshez nem szükséges módosítani a `*.qs` Q #-fájl módosításait.</span><span class="sxs-lookup"><span data-stu-id="c660f-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="c660f-211">A következő gazda program-implementációk mindegyike ugyanazzal a Q # fájllal működik:</span><span class="sxs-lookup"><span data-stu-id="c660f-211">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="c660f-212">Válassza ki a megfelelő gazdagép-nyelvhez tartozó fület.</span><span class="sxs-lookup"><span data-stu-id="c660f-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="c660f-213">Python</span><span class="sxs-lookup"><span data-stu-id="c660f-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="c660f-214">A Python-gazda program a következőképpen épül fel:</span><span class="sxs-lookup"><span data-stu-id="c660f-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="c660f-215">Importálja a modult `qsharp` , amely a Q # együttműködési képességhez regisztrálja a modul betöltőjét.</span><span class="sxs-lookup"><span data-stu-id="c660f-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="c660f-216">Ez lehetővé teszi, hogy a Q # névterek Python-modulokként jelenjenek meg, amelyekről "import" Q # callables lehet.</span><span class="sxs-lookup"><span data-stu-id="c660f-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="c660f-217">Vegye figyelembe, hogy a Q # callables nem az importált, hanem a Python-Csonkok, amelyek lehetővé teszik a hívását.</span><span class="sxs-lookup"><span data-stu-id="c660f-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="c660f-218">Ezek a Python-osztályok objektumaiként viselkednek, és a metódusok segítségével határozzák meg, hogy a rendszer hogyan küldje el a műveletet a művelet végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="c660f-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="c660f-219">Importálja a Q # callables, melyeket a rendszer közvetlenül meghív---ebben az esetben, `MeasureSuperposition` és `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="c660f-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="c660f-220">Az `qsharp` importált modullal közvetlenül a Q # Library-névterekről is importálhatja a callables.</span><span class="sxs-lookup"><span data-stu-id="c660f-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="c660f-221">A többi Python-kód között mostantól meghívhatja ezeket a callables az adott célszámítógépeken, és hozzárendelheti azok változóhoz való visszatérését (ha értéket adnak vissza) a további használatra.</span><span class="sxs-lookup"><span data-stu-id="c660f-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="c660f-222">Megcélzott gépek meghatározása</span><span class="sxs-lookup"><span data-stu-id="c660f-222">Specifying target machines</span></span>
<span data-ttu-id="c660f-223">Egy adott célszámítógépen futtatandó művelet meghívása az importált objektumon különböző Python-módszerekkel történik.</span><span class="sxs-lookup"><span data-stu-id="c660f-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="c660f-224">A (z `.simulate(<args>)` ) például a használatával `QuantumSimulator` futtatja a műveletet, míg `.estimate_resources(<args>)` a (z `ResourcesEstimator` ).</span><span class="sxs-lookup"><span data-stu-id="c660f-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="c660f-225">Bemenetek továbbítása a Q-ba\#</span><span class="sxs-lookup"><span data-stu-id="c660f-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="c660f-226">A Q # meghívható argumentumait kulcsszó típusú argumentum formájában kell megadni, ahol a kulcsszó az argumentum neve a Q # meghívható definíciójában.</span><span class="sxs-lookup"><span data-stu-id="c660f-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="c660f-227">Ez `MeasureSuperpositionArray.simulate(n=4)` érvényes, míg `MeasureSuperpositionArray.simulate(4)` hiba történt.</span><span class="sxs-lookup"><span data-stu-id="c660f-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="c660f-228">Ezért a Python-gazda program</span><span class="sxs-lookup"><span data-stu-id="c660f-228">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="c660f-229">a következőhöz hasonló kimenetet eredményez:</span><span class="sxs-lookup"><span data-stu-id="c660f-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="c660f-230">C#</span><span class="sxs-lookup"><span data-stu-id="c660f-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="c660f-231">A C# gazda program több összetevővel rendelkezik, és nagyon szorosan együttműködik a QDK egyes összetevőivel, például a szimulátorokkal, amelyek a C# nyelvre épülnek.</span><span class="sxs-lookup"><span data-stu-id="c660f-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="c660f-232">A Q # fordítóprogram egy egyenértékű, C# névtér létrehozásával működik a q # névtérben a q # fájlban.</span><span class="sxs-lookup"><span data-stu-id="c660f-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="c660f-233">Ezzel egyenértékű névvel ellátott C# osztályt hoz létre minden olyan Q # callables vagy típushoz, amelyet itt definiáltak.</span><span class="sxs-lookup"><span data-stu-id="c660f-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="c660f-234">Első lépésként a gazda programunkban használt osztályokat tesszük elérhetővé az `using` utasításokkal, amelyek nagyjából analagous a `open` Q # fájl utasításait:</span><span class="sxs-lookup"><span data-stu-id="c660f-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="c660f-235">Ezután deklaráljuk a C#-névteret, néhány más bitet és darabot (lásd az alábbi teljes kódrészletet), majd a klasszikus programozást (például a Q # callables tartozó számítási argumentumokat).</span><span class="sxs-lookup"><span data-stu-id="c660f-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="c660f-236">Az utóbbi nem szükséges az esetünkben, de az ilyen jellegű használatról a .net-es [együttműködési minta](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)tartalmaz példát.</span><span class="sxs-lookup"><span data-stu-id="c660f-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="c660f-237">Célgépek</span><span class="sxs-lookup"><span data-stu-id="c660f-237">Target machines</span></span>

<span data-ttu-id="c660f-238">A Q #-ra való visszalépéshez létre kell hoznia egy példányt a célszámítógépen, amelyről végrehajtjuk a műveletet.</span><span class="sxs-lookup"><span data-stu-id="c660f-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="c660f-239">Más célszámítógépek használata olyan egyszerű, mint egy másik példány létrehozása, bár ennek a módja, és a visszatérések feldolgozása némileg eltérő lehet.</span><span class="sxs-lookup"><span data-stu-id="c660f-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="c660f-240">A rövidség kedvéért most ragaszkodunk a [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) szolgáltatáshoz, és belefoglaljuk az [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [alábbiakat](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="c660f-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="c660f-241">A Q # műveletekben létrehozott minden C# osztálynak van egy `Run` metódusa, amely az első argumentum, amelynek a célszámítógép-példánynak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c660f-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="c660f-242">Tehát a futtatásához `MeasureSuperposition` használjuk a következőt: `QuantumSimulator` `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="c660f-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="c660f-243">A visszaadott eredmények ezután a C#-változókhoz rendelhetők:</span><span class="sxs-lookup"><span data-stu-id="c660f-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="c660f-244">A `Run` metódus aszinkron módon van végrehajtva, mert ez a valódi kvantum-hardver esetében ez lesz, ezért a `await` kulcsszó a feladat befejezéséig blokkolja a további végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="c660f-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="c660f-245">Ha a Q # hívható nem rendelkezik visszaadott értékkel (azaz visszatérési típussal `Unit` ), a végrehajtás továbbra is ugyanúgy végezhető el, amíg hozzá nem rendel egy változóhoz.</span><span class="sxs-lookup"><span data-stu-id="c660f-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="c660f-246">Ebben az esetben a teljes sor csupán a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="c660f-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="c660f-247">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c660f-247">Arguments</span></span>

<span data-ttu-id="c660f-248">A Q # meghívható összes argumentuma egyszerűen átadja a afer további argumentumként.</span><span class="sxs-lookup"><span data-stu-id="c660f-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="c660f-249">Így a qubits eredményei `MeasureSuperpositionArray` a `n=4` következőn keresztül lettek beolvasva</span><span class="sxs-lookup"><span data-stu-id="c660f-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="c660f-250">A teljes C# gazda program így néz ki:</span><span class="sxs-lookup"><span data-stu-id="c660f-250">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="c660f-251">A C#-fájl helyén a gazda program a parancssorból is futtatható. Ehhez írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="c660f-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="c660f-252">Ebben az esetben a-konzolra írt kimenetet a következőhöz hasonló módon fogja látni:</span><span class="sxs-lookup"><span data-stu-id="c660f-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="c660f-253">A fordítók névterekkel való együttműködése miatt előfordulhat, hogy a Q # callables az utasítás nélkül elérhetővé válik `using NamespaceName;` , és egyszerűen csak a C# névtér címére lesz kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="c660f-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="c660f-254">Ez azt helyettesíti, hogy `namespace host` `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="c660f-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="c660f-255">Beleértve a források becslését</span><span class="sxs-lookup"><span data-stu-id="c660f-255">Including the resources estimator</span></span>

<span data-ttu-id="c660f-256">A [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) kimenet beolvasásához némileg eltérő implementáció szükséges.</span><span class="sxs-lookup"><span data-stu-id="c660f-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="c660f-257">Először is, ahelyett, hogy egy `using` utasítással (például a következővel) változóként kívánja létrehozni őket `QuantumSimulator` , az osztály objektumainak közvetlen létrehozását</span><span class="sxs-lookup"><span data-stu-id="c660f-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="c660f-258">Figyelje meg, hogy egy cél-szimulátor helyett több Q # művelet is használható, mindegyikhez létrehozunk egyet.</span><span class="sxs-lookup"><span data-stu-id="c660f-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="c660f-259">Ennek az az oka, hogy maga az objektum is módosul, ha célként használt gépekként használják őket, és ezek eredményeit később a Class metódussal lehet lekérni `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="c660f-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="c660f-260">A műveleteknek az erőforrás-becslések való futtatásához használjuk a következőt</span><span class="sxs-lookup"><span data-stu-id="c660f-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="c660f-261">majd az eredményeket tabulátorral elválasztott értékként (TSV) a és a karakterrel kell beolvasni `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="c660f-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="c660f-262">Tehát a teljes C# gazda program mind a, mind a `QuantumSimulator` formáját a `ResourcesEstimator` következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="c660f-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="c660f-263">amely a következőhöz hasonló kimenetet eredményezhet</span><span class="sxs-lookup"><span data-stu-id="c660f-263">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a><span data-ttu-id="c660f-264">Q# nyelvű Jupyter-notebookok</span><span class="sxs-lookup"><span data-stu-id="c660f-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="c660f-265">A q # Jupyter notebookok használják az IQ # kernelt, amely lehetővé teszi a Q # callables egyetlen jegyzetfüzetben való definiálását, fordítását és futtatását---az összes útmutatást, megjegyzést és egyéb tartalmat.</span><span class="sxs-lookup"><span data-stu-id="c660f-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="c660f-266">Ez azt jelenti, hogy habár lehetséges a Q # fájlok importálása és használata `*.qs` , nem szükségesek a végrehajtási modellben.</span><span class="sxs-lookup"><span data-stu-id="c660f-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="c660f-267">Itt részletesen ismertetjük, hogyan futtathatja a fentebb definiált Q #-műveleteket, de a Q # Jupyter jegyzetfüzetek használatának szélesebb körű bemutatása a q [# és a Jupyter jegyzetfüzetek](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)esetében érhető el.</span><span class="sxs-lookup"><span data-stu-id="c660f-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="c660f-268">Műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="c660f-268">Defining operations</span></span>

<span data-ttu-id="c660f-269">A Q # Jupyter Notebookban a q # kódot kell megadnia, ugyanúgy, mint a Q # fájl névterében.</span><span class="sxs-lookup"><span data-stu-id="c660f-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="c660f-270">Így engedélyezhető a [Q # standard könyvtár](xref:microsoft.quantum.qsharplibintro) callables való hozzáférés a `open` megfelelő névterekhez tartozó utasításokkal.</span><span class="sxs-lookup"><span data-stu-id="c660f-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="c660f-271">Ha egy cellát egy ilyen utasítással futtat, a névterek definíciói a munkaterület teljes területén elérhetők.</span><span class="sxs-lookup"><span data-stu-id="c660f-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="c660f-272">A [Microsoft. Quantum. belső](xref:microsoft.quantum.intrinsic) és a [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (például [`H`](xref:microsoft.quantum.intrinsic.h) és) Callables [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) automatikusan elérhetők a Q # Jupyter jegyzetfüzetekben található cellákban definiált műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="c660f-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="c660f-273">Ez azonban nem igaz a külső Q # forrásfájlok esetében beérkező kód esetén (a [q # és a Jupyter notebookok bevezetőjét bemutató](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)folyamat).</span><span class="sxs-lookup"><span data-stu-id="c660f-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="c660f-274">Hasonlóképpen, a definiált műveletekhez csak a Q # kód írása és a cella futtatása szükséges.</span><span class="sxs-lookup"><span data-stu-id="c660f-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="c660f-275">A kimenet ezután felsorolja ezeket a műveleteket, amelyek ezután meghívhatók a jövőbeli cellákból.</span><span class="sxs-lookup"><span data-stu-id="c660f-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="c660f-276">Célgépek</span><span class="sxs-lookup"><span data-stu-id="c660f-276">Target machines</span></span>

<span data-ttu-id="c660f-277">Az adott célszámítógépeken futó műveletek futtatásának funkciói az [IQ # Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp)használatával érhetők el.</span><span class="sxs-lookup"><span data-stu-id="c660f-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="c660f-278">Például a a (z) `%simulate` `QuantumSimulator` és a következőt `%estimate` használja `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="c660f-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="c660f-279">Bemenetek átadása a függvényeknek és műveleteknek</span><span class="sxs-lookup"><span data-stu-id="c660f-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="c660f-280">Jelenleg a végrehajtási mágikus parancsok csak olyan műveletekkel használhatók, amelyek nem rendelkeznek argumentumokkal.</span><span class="sxs-lookup"><span data-stu-id="c660f-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="c660f-281">Tehát a futtatáshoz `MeasureSuperpositionArray` definiálnia kell egy "burkoló" műveletet, amely ezután meghívja a műveletet a következő argumentumokkal:</span><span class="sxs-lookup"><span data-stu-id="c660f-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="c660f-282">Ez a művelet természetesen a `%estimate` és más végrehajtási parancsokkal is használható.</span><span class="sxs-lookup"><span data-stu-id="c660f-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
