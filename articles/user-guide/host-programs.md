---
title: Programok futtatásának módjai Q#
description: A programok futtatásának különböző módjai – áttekintés Q# . A parancssorból, a Q# Jupyter-jegyzetfüzetből és a klasszikus gazdagép-programokból Python vagy .net nyelven.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231689"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="58073-104">Programok futtatásának módjai Q#</span><span class="sxs-lookup"><span data-stu-id="58073-104">Ways to run a Q# program</span></span>

<span data-ttu-id="58073-105">A Quantum Development Kit egyik legnagyobb erőssége a platformok és a fejlesztői környezetek rugalmassága.</span><span class="sxs-lookup"><span data-stu-id="58073-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="58073-106">Ez azonban azt is jelenti, hogy az új Q# felhasználók a [telepítési útmutatóban](xref:microsoft.quantum.install)található számos lehetőség alapján megzavarják vagy elárasztják magukat.</span><span class="sxs-lookup"><span data-stu-id="58073-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="58073-107">Ezen az oldalon elmagyarázza, hogy mi történik a Q# program futtatásakor, és hasonlítsa össze a felhasználók által megtehető különböző módokat.</span><span class="sxs-lookup"><span data-stu-id="58073-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="58073-108">Az elsődleges különbség az, hogy a Q# következőket lehet futtatni:</span><span class="sxs-lookup"><span data-stu-id="58073-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="58073-109">önálló alkalmazásként, ahol az az Q# egyetlen érintett nyelv, és a program közvetlenül hívja meg a programot.</span><span class="sxs-lookup"><span data-stu-id="58073-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="58073-110">Két metódus valójában a következő kategóriába tartozik:</span><span class="sxs-lookup"><span data-stu-id="58073-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="58073-111">a parancssori felület</span><span class="sxs-lookup"><span data-stu-id="58073-111">the command-line interface</span></span>
  - <span data-ttu-id="58073-112">Q# Jupyter notebookok</span><span class="sxs-lookup"><span data-stu-id="58073-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="58073-113">egy Python-vagy .NET-nyelven írt további *gazdagép-programmal*(például C# vagy F #), amely ezt követően meghívja a programot, és folytatja a visszaadott eredmények feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="58073-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="58073-114">Ha szeretné jobban megérteni ezeket a folyamatokat és azok különbségeit, tekintse meg Q# az egyszerű programot, és hasonlítsa össze a futtatási módszereit.</span><span class="sxs-lookup"><span data-stu-id="58073-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="58073-115">Alapszintű Q# program</span><span class="sxs-lookup"><span data-stu-id="58073-115">Basic Q# program</span></span>

<span data-ttu-id="58073-116">Egy alapszintű kvantum-program a qubit előállítását is magában foglalhatja az államok $ \ket $ és a $ \ket $ értékkel egyenlő arányban {0} {1} , a mérést és az eredményt visszaadva, amely a két, azonos valószínűséggel rendelkező állapot közül véletlenszerűen fog állni.</span><span class="sxs-lookup"><span data-stu-id="58073-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="58073-117">Ennek a folyamatnak a lényege a [Quantum Random Number Generator](xref:microsoft.quantum.quickstarts.qrng) rövid útmutatója.</span><span class="sxs-lookup"><span data-stu-id="58073-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="58073-118">A-ben Q# ezt a következő kód hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="58073-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="58073-119">Ez a kód azonban önmagában nem futtatható Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="58073-120">Ehhez egy [művelet](xref:microsoft.quantum.qsharp.operationsandfunctions)törzsét kell kiállítania, amely akkor fut le, amikor a---vagy közvetlenül, vagy egy másik művelet hívja meg.</span><span class="sxs-lookup"><span data-stu-id="58073-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="58073-121">Ezért a következő űrlapon is írhat egy műveletet:</span><span class="sxs-lookup"><span data-stu-id="58073-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="58073-122">Definiált egy műveletet, `MeasureSuperposition` amely nem vesz fel bemeneteket, és eredmény típusú értéket ad [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types)vissza.</span><span class="sxs-lookup"><span data-stu-id="58073-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="58073-123">A műveletek mellett a Q# determinisztikus számításait is lehetővé teszi a functions szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="58073-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="58073-124">Az olyan megkötési garancián kívül, amely azt jelenti, hogy az qubits-n alapuló számításokat a függvények helyett a műveletekhez kell ágyazni, kevés a különbség a műveletek és a függvények között.</span><span class="sxs-lookup"><span data-stu-id="58073-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="58073-125">Ezeket együttesen *callables* nevezzük.</span><span class="sxs-lookup"><span data-stu-id="58073-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="58073-126">Meghívható definiálva egy Q# fájlban</span><span class="sxs-lookup"><span data-stu-id="58073-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="58073-127">A hívható pontosan az, amit a meghívott és futtat Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="58073-128">Azonban ehhez több kiegészítésre van szükség, amely egy teljes fájlt tartalmaz `*.qs` Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="58073-129">Az összes Q# típus-és callables (az Ön által definiált és a nyelvhez tartozók is) a *névterekben* vannak definiálva, amelyek minden olyan teljes nevet megadnak, amelyre hivatkozni lehet.</span><span class="sxs-lookup"><span data-stu-id="58073-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="58073-130">Például a és a [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) műveletek a és a [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) névterekben találhatók (a [ Q# standard könyvtárak](xref:microsoft.quantum.libraries.standard.intro)része).</span><span class="sxs-lookup"><span data-stu-id="58073-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="58073-131">Így mindig meghívhatják a *teljes* nevüket, de mindig megtehetik, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` hogy ez nagyon zsúfolt programkódot eredményez.</span><span class="sxs-lookup"><span data-stu-id="58073-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="58073-132">Ehelyett `open` az utasítások lehetővé teszik, hogy a callables tömör gyorsírással legyenek hivatkozva, ahogy a fenti műveleti törzsben tettük.</span><span class="sxs-lookup"><span data-stu-id="58073-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="58073-133">A Q# műveletet tartalmazó teljes fájl ezért a saját névterek definiálását, a callables, a művelet által használt névterek megnyitását, majd a műveletet:</span><span class="sxs-lookup"><span data-stu-id="58073-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="58073-134">A névterek a megnyitásakor is *aliasként* használhatók, ami akkor lehet hasznos, ha a hívható/Type nevek két névtérben ütköznek.</span><span class="sxs-lookup"><span data-stu-id="58073-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="58073-135">Tegyük fel például, hogy a `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` fentieket fogjuk használni, majd meghívjuk a- `H` on keresztül `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="58073-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="58073-136">Ennek egyetlen kivétele a [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) névtér, amely mindig automatikusan megnyílik.</span><span class="sxs-lookup"><span data-stu-id="58073-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="58073-137">Ezért a callables, mint a [`Length`](xref:Microsoft.Quantum.Core.Length) mindig közvetlenül használhatók.</span><span class="sxs-lookup"><span data-stu-id="58073-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="58073-138">Futtatás a célszámítógépen</span><span class="sxs-lookup"><span data-stu-id="58073-138">Running on target machines</span></span>

<span data-ttu-id="58073-139">Mostantól a program általános futtatási modellje is Q# világossá válik.</span><span class="sxs-lookup"><span data-stu-id="58073-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="58073-140">Először is az adott futtatáshoz megadott meghívónak hozzá kell férnie az ugyanabban a névtérben definiált összes más callables és típushoz.</span><span class="sxs-lookup"><span data-stu-id="58073-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="58073-141">Emellett a [ Q# könyvtárak](xref:microsoft.quantum.libraries)bármelyikének hozzáférését is elérheti, de ezeket a teljes névvel vagy a fent ismertetett utasítások használatával kell hivatkozni `open` .</span><span class="sxs-lookup"><span data-stu-id="58073-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="58073-142">A meghívót ezután futtathatja a *[célszámítógépen](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="58073-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="58073-143">Ilyen célszámítógépek lehetnek a tényleges kvantum-hardverek vagy a QDK részeként elérhető több szimulátorok.</span><span class="sxs-lookup"><span data-stu-id="58073-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="58073-144">Erre a célra a leghasznosabb célszámítógép a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)egy példánya, `QuantumSimulator` amely úgy számítja ki a program viselkedését, mintha egy zaj nélküli kvantum-számítógépen futna.</span><span class="sxs-lookup"><span data-stu-id="58073-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="58073-145">Eddig azt ismertetjük, hogy mi történik, ha egy adott Q# hívás fut.</span><span class="sxs-lookup"><span data-stu-id="58073-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="58073-146">Függetlenül attól, hogy Q# egy önálló alkalmazásban vagy egy gazdagép programban használ-e, ez az általános folyamat több vagy kevesebb, mint a QDK rugalmassága---.</span><span class="sxs-lookup"><span data-stu-id="58073-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="58073-147">A Quantum Development Kit Meghívási módjai közötti különbségek tehát azt mutatják be, hogy *how* a Q# hívható hívása hogyan fut, és milyen módon adja vissza az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="58073-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="58073-148">Pontosabban a különbségek a következő körben forognak:</span><span class="sxs-lookup"><span data-stu-id="58073-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="58073-149">Annak jelzése, Q# hogy melyik meghívót kell futtatni</span><span class="sxs-lookup"><span data-stu-id="58073-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="58073-150">A lehetséges hívható argumentumok megadása</span><span class="sxs-lookup"><span data-stu-id="58073-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="58073-151">Azon célszámítógép meghatározása, amelyen futtatni szeretné</span><span class="sxs-lookup"><span data-stu-id="58073-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="58073-152">A visszaadott eredmények</span><span class="sxs-lookup"><span data-stu-id="58073-152">How any results are returned</span></span>

<span data-ttu-id="58073-153">Először is megbeszéljük, hogy ez hogyan történik az Q# önálló alkalmazás parancssorból való használatával, majd folytassa a Python és a C# gazdagép-programok használatát.</span><span class="sxs-lookup"><span data-stu-id="58073-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="58073-154">Fenntartjuk a Jupyter-jegyzetfüzetek önálló alkalmazását az Q# utolsó számára, mivel az első háromtól eltérően az elsődleges funkció nem a helyi fájlok körébe kerül Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="58073-155">Habár nem mutatjuk be ezeket a példákat, a futtatási módszerek közötti egyetlen egység az, hogy a programon belülről kinyomtatott összes üzenet Q# ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) például: vagy [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ) általában mindig a megfelelő konzolra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="58073-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="58073-156">Q# a parancssorból</span><span class="sxs-lookup"><span data-stu-id="58073-156">Q# from the command prompt</span></span>
<span data-ttu-id="58073-157">A programok írásához legkönnyebben elsajátíthatja az első lépéseket, Q# hogy elkerülje a különálló fájlok és a második nyelv használatának elkerülését.</span><span class="sxs-lookup"><span data-stu-id="58073-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="58073-158">A Visual Studio Code vagy a Visual Studio és a QDK bővítmény lehetővé teszi a zökkenőmentes munkafolyamatot, amelyben a Q# callables-t csak egyetlen Q# fájlból futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="58073-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="58073-159">Ehhez a következő lépéssel fogjuk futtatni a programot:</span><span class="sxs-lookup"><span data-stu-id="58073-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="58073-160">parancsot a parancssorban.</span><span class="sxs-lookup"><span data-stu-id="58073-160">at the command prompt.</span></span>
<span data-ttu-id="58073-161">A legegyszerűbb munkafolyamat az, amikor a terminál címtárának helye megegyezik a fájl nevével Q# , amely könnyen kezelhető a Q# fájl szerkesztésével együtt a vs Code integrált termináljának használatával, például:.</span><span class="sxs-lookup"><span data-stu-id="58073-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="58073-162">A [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) azonban számos lehetőséget is elfogad, és a program más helyről is futtatható, ha egyszerűen megadja a `--project <PATH>` Q# fájl helyét.</span><span class="sxs-lookup"><span data-stu-id="58073-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="58073-163">Belépési pont hozzáadása a Q# fájlhoz</span><span class="sxs-lookup"><span data-stu-id="58073-163">Add entry point to Q# file</span></span>

<span data-ttu-id="58073-164">A legtöbb Q# fájl egynél több meghívót tartalmaz, ezért a fordítónak természetesen azt is tudnia kell, hogy *melyik* meghívásos futtatásra van szükség a parancs megadásakor `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="58073-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="58073-165">Ez a fájl egyszerű módosításával történik Q# :</span><span class="sxs-lookup"><span data-stu-id="58073-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="58073-166">Adjon hozzá egy sort, amely `@EntryPoint()` közvetlenül megelőzi a meghívót.</span><span class="sxs-lookup"><span data-stu-id="58073-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="58073-167">Ezért a fenti fájl a következő lesz:</span><span class="sxs-lookup"><span data-stu-id="58073-167">Our file from above would therefore become</span></span>
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

<span data-ttu-id="58073-168">Most a `dotnet run` parancssorból érkező hívás a `MeasureSuperposition` futtatáshoz vezet, és a visszaadott érték közvetlenül a terminálra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="58073-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="58073-169">Így a rendszer `One` vagy kinyomtatja a következőt: `Zero` .</span><span class="sxs-lookup"><span data-stu-id="58073-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="58073-170">Vegye figyelembe, hogy nem számít, hogy ha több callables van definiálva, csak a `MeasureSuperposition` futtatásra kerül.</span><span class="sxs-lookup"><span data-stu-id="58073-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="58073-171">Emellett nem jelent problémát, ha a meghívó a nyilatkozata előtt is tartalmaz [dokumentációs megjegyzéseket](xref:microsoft.quantum.qsharp.comments#documentation-comments) , az `@EntryPoint()` attribútum egyszerűen elhelyezhető.</span><span class="sxs-lookup"><span data-stu-id="58073-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="58073-172">Hívható argumentumok</span><span class="sxs-lookup"><span data-stu-id="58073-172">Callable arguments</span></span>

<span data-ttu-id="58073-173">Eddig csak olyan műveletet vettünk figyelembe, amely nem vesz fel bemeneteket.</span><span class="sxs-lookup"><span data-stu-id="58073-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="58073-174">Tegyük fel, hogy hasonló műveletet hajtottunk végre, de több qubits---az argumentumként megadott számú értéket.</span><span class="sxs-lookup"><span data-stu-id="58073-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="58073-175">Egy ilyen művelet a következőképpen írható</span><span class="sxs-lookup"><span data-stu-id="58073-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="58073-176">ahol a visszaadott érték a mérési eredmények tömbje.</span><span class="sxs-lookup"><span data-stu-id="58073-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="58073-177">Vegye figyelembe, hogy [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) a és [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) a [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) névterek esetében további `open` utasításokra van szükség mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="58073-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="58073-178">Ha az `@EntryPoint()` attribútumot az új művelet előtt helyezi át (vegye figyelembe, hogy egy fájlban csak egy ilyen sor lehet), és a futtatására tett kísérlet egyszerűen `dotnet run` olyan hibaüzenetet eredményez, amely azt jelzi, hogy milyen további parancssori kapcsolók szükségesek, és hogyan fejezheti ki őket.</span><span class="sxs-lookup"><span data-stu-id="58073-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="58073-179">A parancssor általános formátuma ténylegesen `dotnet run [options]` , a hívható argumentumok pedig itt vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="58073-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="58073-180">Ebben az esetben az argumentum `n` hiányzik, és azt mutatja, hogy meg kell adnia a beállítást `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="58073-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="58073-181">A qubits való futtatáshoz `MeasureSuperpositionArray` ezért használjuk a következőt: `n=4`</span><span class="sxs-lookup"><span data-stu-id="58073-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="58073-182">a következőhöz hasonló kimenetet eredményez</span><span class="sxs-lookup"><span data-stu-id="58073-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="58073-183">Ez a tanfolyam több argumentumra is kiterjed.</span><span class="sxs-lookup"><span data-stu-id="58073-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="58073-184">A ben definiált argumentumok nevét `camelCase` a fordító csak kis mértékben módosítja Q# bemenetként.</span><span class="sxs-lookup"><span data-stu-id="58073-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="58073-185">Például, ha `n` a helyett a fenti nevet használtuk `numQubits` , akkor ez a bemenet a parancssoron keresztül lesz megadva a `--num-qubits 4` helyett `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="58073-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="58073-186">A hibaüzenet más lehetőségeket is tartalmaz, amelyek használhatók, beleértve a célszámítógép módosításának módját is.</span><span class="sxs-lookup"><span data-stu-id="58073-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="58073-187">Különböző célszámítógépek</span><span class="sxs-lookup"><span data-stu-id="58073-187">Different target machines</span></span>

<span data-ttu-id="58073-188">Mivel a műveleteik eredményei a tényleges qubits a várt eredmények voltak, egyértelmű, hogy a parancssorból az alapértelmezett célszámítógép a teljes állapotú kvantum-szimulátor `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="58073-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="58073-189">Azonban arra is utasíthatja a callables, hogy egy adott célszámítógépen fusson a `--simulator` (vagy a gyorsírással) lehetőséggel `-s` .</span><span class="sxs-lookup"><span data-stu-id="58073-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="58073-190">Futtathatja például a következőt [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="58073-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="58073-191">Ekkor a kinyomtatott kimenet</span><span class="sxs-lookup"><span data-stu-id="58073-191">The printed output is then</span></span>

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

<span data-ttu-id="58073-192">Az ezekkel a mérőszámokkal kapcsolatos részletekért lásd [: erőforrás-kalkulátor: a jelentett mérőszámok](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="58073-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="58073-193">Parancssori Futtatás összegzése</span><span class="sxs-lookup"><span data-stu-id="58073-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="58073-194">Nem Q# `dotnet run` Beállítások</span><span class="sxs-lookup"><span data-stu-id="58073-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="58073-195">Ahogy azt röviden említettük a `--project` kapcsolóval, a [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) a Q# meghívásos argumentumokhoz nem kapcsolódó beállításokat is elfogadja.</span><span class="sxs-lookup"><span data-stu-id="58073-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="58073-196">Ha mindkét típusú beállítást megadja, a `dotnet` -specifikus beállításokat elsőként kell megadni, majd egy elválasztó karakter `--` , majd a Q# -specifikus beállításokat.</span><span class="sxs-lookup"><span data-stu-id="58073-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="58073-197">Például megadhat egy elérési utat, valamint a fenti művelethez tartozó qubits `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="58073-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="58073-198">Q# gazdagép-programokkal</span><span class="sxs-lookup"><span data-stu-id="58073-198">Q# with host programs</span></span>

<span data-ttu-id="58073-199">Ha a Q# fájl a kezünkben van, a művelet vagy a függvény közvetlenül a parancssorból való meghívására szolgáló alternatíva egy másik klasszikus nyelven üzemelő *gazda program* használata.</span><span class="sxs-lookup"><span data-stu-id="58073-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="58073-200">Pontosabban megteheti a Python vagy a .NET nyelv, például a C# vagy az F # kombinációját (a rövidség kedvéért csak a C# adatokat fogjuk részletezni).</span><span class="sxs-lookup"><span data-stu-id="58073-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="58073-201">Az együttműködési képesség engedélyezéséhez valamivel több beállítás szükséges, de ezek a részletek a [telepítési útmutatókban](xref:microsoft.quantum.install)találhatók.</span><span class="sxs-lookup"><span data-stu-id="58073-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="58073-202">Dióhéjban a helyzet most már tartalmaz egy gazda programfájlt (például `*.py` vagy `*.cs` ) a fájllal megegyező helyen Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="58073-203">Most már a futtatott *gazda* program fut, és a futása közben Q# a fájl adott műveleteit és funkcióit is meghívhatja Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="58073-204">Az együttműködési képesség lényege, hogy a Q# fordító a Q# fájl tartalmát elérhetővé teszi a gazda program számára, hogy azok meghívhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="58073-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="58073-205">A gazda program használatának egyik legfőbb előnye, hogy a program által visszaadott klasszikus adatmennyiséget a Q# gazdagép nyelvén lehet tovább feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="58073-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="58073-206">Ez állhat néhány speciális adatfeldolgozásból (például egy olyanra, amely nem hajtható végre belsőleg Q# ), majd az Q# eredmények alapján további műveleteket hívhat meg, vagy az eredmények ábrázolására is alkalmas Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="58073-207">Az általános séma itt látható, és megbeszéljük a Python és a C# adott implementációit alább.</span><span class="sxs-lookup"><span data-stu-id="58073-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="58073-208">Az F # gazda programot használó minta a .net-es [együttműködési mintákon](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)érhető el.</span><span class="sxs-lookup"><span data-stu-id="58073-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="58073-209">Az `@EntryPoint()` Q# alkalmazásokhoz használt attribútum nem használható a gazdagép-programokkal.</span><span class="sxs-lookup"><span data-stu-id="58073-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="58073-210">A rendszer hibát jelez, ha az Q# egy gazdagép által hívott fájlban szerepel.</span><span class="sxs-lookup"><span data-stu-id="58073-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="58073-211">A különböző gazdagépekkel való munkavégzéshez nincs szükség módosításra a `*.qs` Q# fájlokhoz.</span><span class="sxs-lookup"><span data-stu-id="58073-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="58073-212">A következő gazda program-implementációk mindegyike ugyanazzal a Q# fájllal működik:</span><span class="sxs-lookup"><span data-stu-id="58073-212">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="58073-213">Válassza ki a megfelelő gazdagép-nyelvhez tartozó fület.</span><span class="sxs-lookup"><span data-stu-id="58073-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="58073-214">Python</span><span class="sxs-lookup"><span data-stu-id="58073-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="58073-215">A Python-gazda program a következőképpen épül fel:</span><span class="sxs-lookup"><span data-stu-id="58073-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="58073-216">Importálja a modult `qsharp` , amely regisztrálja a modul-betöltőt az Q# együttműködési képességhez.</span><span class="sxs-lookup"><span data-stu-id="58073-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="58073-217">Ez lehetővé teszi Q# , hogy a névterek Python-modulokként jelenjenek meg, amelyekről "importálhatók" Q# callables.</span><span class="sxs-lookup"><span data-stu-id="58073-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="58073-218">Ne feledje, hogy a callables nem Q# maga az importált, hanem a Python-Csonkok, amelyek lehetővé teszik a hívását.</span><span class="sxs-lookup"><span data-stu-id="58073-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="58073-219">Ezek a Python-osztályok objektumaiként viselkednek.</span><span class="sxs-lookup"><span data-stu-id="58073-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="58073-220">Ezen objektumok módszereit használva megadjuk azokat a célszámítógépeken, amelyeken a műveletet a program futtatásakor küldi el a rendszer.</span><span class="sxs-lookup"><span data-stu-id="58073-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="58073-221">Importálja azokat a Q# callables, amelyeket a rendszer közvetlenül meghív---ebben az esetben, `MeasureSuperposition` és `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="58073-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="58073-222">Ha a `qsharp` modult importálta, a callables közvetlenül a Q# könyvtár névteréről is importálhatja.</span><span class="sxs-lookup"><span data-stu-id="58073-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="58073-223">A többi Python-kód között mostantól meghívhatja ezeket a callables az adott célszámítógépeken, és hozzárendelheti azok változóhoz való visszatérését (ha értéket adnak vissza) a további használatra.</span><span class="sxs-lookup"><span data-stu-id="58073-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="58073-224">Megcélzott gépek meghatározása</span><span class="sxs-lookup"><span data-stu-id="58073-224">Specifying target machines</span></span>
<span data-ttu-id="58073-225">Egy adott célszámítógépen futtatandó művelet meghívása az importált objektumon különböző Python-módszerekkel történik.</span><span class="sxs-lookup"><span data-stu-id="58073-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="58073-226">A (z `.simulate(<args>)` ) például a használatával `QuantumSimulator` futtatja a műveletet, míg `.estimate_resources(<args>)` a (z `ResourcesEstimator` ).</span><span class="sxs-lookup"><span data-stu-id="58073-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="58073-227">Bemenetek továbbítása a Q-ba\#</span><span class="sxs-lookup"><span data-stu-id="58073-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="58073-228">A Q# meghívható argumentumokat kulcsszó típusú argumentum formájában kell megadni, ahol a kulcsszó az argumentum neve a Q# meghívásos definícióban.</span><span class="sxs-lookup"><span data-stu-id="58073-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="58073-229">Ez `MeasureSuperpositionArray.simulate(n=4)` érvényes, míg `MeasureSuperpositionArray.simulate(4)` hiba történt.</span><span class="sxs-lookup"><span data-stu-id="58073-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="58073-230">Ezért a Python-gazda program</span><span class="sxs-lookup"><span data-stu-id="58073-230">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="58073-231">a következőhöz hasonló kimenetet eredményez:</span><span class="sxs-lookup"><span data-stu-id="58073-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="58073-232">Q#Kód használata más projektekről vagy csomagokból</span><span class="sxs-lookup"><span data-stu-id="58073-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="58073-233">Alapértelmezés szerint a `import qsharp` parancs betölti az `.qs` aktuális mappában található összes fájlt, és a Q# műveleteit és funkcióit elérhetővé teszi a Python-szkripten belülről való használatra.</span><span class="sxs-lookup"><span data-stu-id="58073-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="58073-234">Q#A kód egy másik mappából való betöltéséhez az [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) -val egy projektre mutató hivatkozást adhat hozzá `.csproj` Q# (azaz egy projekt, amely hivatkozik `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="58073-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="58073-235">Ez a parancs lefordítja a `.qs` mappában található összes fájlt, amely tartalmazza a `.csproj` és almappáit.</span><span class="sxs-lookup"><span data-stu-id="58073-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="58073-236">Emellett rekurzív módon betölti az `PackageReference` adott fájlban hivatkozott vagy projekteken keresztül hivatkozott csomagokat is Q# `ProjectReference` `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="58073-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="58073-237">A következő Python-kód például egy külső projektet importál, amely az aktuális mappához viszonyított elérési útra hivatkozik, és meghívja az egyik Q# műveletét:</span><span class="sxs-lookup"><span data-stu-id="58073-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="58073-238">Ez a következőhöz hasonló kimenetet eredményez:</span><span class="sxs-lookup"><span data-stu-id="58073-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="58073-239">A kódot tartalmazó külső csomagok betöltéséhez Q# használja az [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)-t.</span><span class="sxs-lookup"><span data-stu-id="58073-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="58073-240">Ha az Q# aktuális mappában található kód külső projekttől vagy csomagtól függ, a futtatásakor hibák jelenhetnek meg `import qsharp` , mivel a függőségek még nincsenek betöltve.</span><span class="sxs-lookup"><span data-stu-id="58073-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="58073-241">A szükséges külső csomagok vagy projektek a parancsban való betöltéséhez győződjön meg arról, Q# `import qsharp` hogy a Python-szkripttel rendelkező mappa tartalmaz egy `.csproj` hivatkozást tartalmazó fájlt `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="58073-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="58073-242">A ben `.csproj` adja hozzá a tulajdonságot a következőhöz: `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="58073-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="58073-243">Ez Q# a művelet arra utasítja, hogy rekurzív módon töltse be `ProjectReference` `PackageReference` `.csproj` a parancsban található összes vagy elemet `import qsharp` .</span><span class="sxs-lookup"><span data-stu-id="58073-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="58073-244">Íme például egy egyszerű `.csproj` fájl, amely a Q# csomag automatikus betöltését okozza `Microsoft.Quantum.Chemistry` :</span><span class="sxs-lookup"><span data-stu-id="58073-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="58073-245">Jelenleg ezt az egyéni `<IQSharpLoadAutomatically>` tulajdonságot a Python-gazdagépek igénylik, de a jövőben ez a `.csproj` Python-szkripttel megegyező mappában található fájl alapértelmezett viselkedése lehet.</span><span class="sxs-lookup"><span data-stu-id="58073-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="58073-246">A rendszer jelenleg a `<QsharpCompile>` `.csproj` következő beállítást veszi figyelembe a Python-gazdagépek esetében, és a mappában található összes `.qs` fájl `.csproj` (beleértve az almappákat is) be van töltve és le van fordítva.</span><span class="sxs-lookup"><span data-stu-id="58073-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="58073-247">`.csproj`A beállítások támogatása a jövőben is javulni fog (további részletekért lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="58073-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="58073-248">C#</span><span class="sxs-lookup"><span data-stu-id="58073-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="58073-249">A C# gazda program több összetevővel rendelkezik, és nagyon szorosan együttműködik a QDK egyes összetevőivel, például a szimulátorokkal, amelyek a C# nyelvre épülnek.</span><span class="sxs-lookup"><span data-stu-id="58073-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="58073-250">A Q# fordító itt működik, ha egy egyenértékű névvel ellátott C#-névteret hoz létre a Q# fájl névterében Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="58073-251">Ezzel egyenértékű névvel ellátott C# osztályt hoz létre minden egyes Q# definiált callables vagy típushoz.</span><span class="sxs-lookup"><span data-stu-id="58073-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="58073-252">Első lépésként a gazda programunkban használt osztályokat tesszük elérhetővé a következő `using` utasításokkal, amelyek nagyjából analagous a `open` fájl utasításait Q# :</span><span class="sxs-lookup"><span data-stu-id="58073-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="58073-253">Ezután deklaráljuk a C#-névteret, néhány más bitet és darabot (lásd az alábbi teljes kódrészletet), majd a klasszikus programozást (például a callables számítási argumentumait Q# ).</span><span class="sxs-lookup"><span data-stu-id="58073-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="58073-254">Az utóbbi nem szükséges az esetünkben, de az ilyen jellegű használatról a .net-es  [együttműködési minta](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)tartalmaz példát.</span><span class="sxs-lookup"><span data-stu-id="58073-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="58073-255">Célgépek</span><span class="sxs-lookup"><span data-stu-id="58073-255">Target machines</span></span>

<span data-ttu-id="58073-256">A szolgáltatásba való visszatéréshez Q# létre kell hoznia a célszámítógép egy példányát.</span><span class="sxs-lookup"><span data-stu-id="58073-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="58073-257">Más célszámítógépek használata olyan egyszerű, mint egy másik példány létrehozása, bár ennek a módja, és a visszatérések feldolgozása némileg eltérő lehet.</span><span class="sxs-lookup"><span data-stu-id="58073-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="58073-258">A rövidség kedvéért most ragaszkodunk a [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) szolgáltatáshoz, és belefoglaljuk az [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [alábbiakat](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="58073-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="58073-259">A műveletekben létrehozott minden C# osztálynak Q# van egy `Run` metódusa, amely az első argumentum, amelynek a célszámítógép-példánynak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="58073-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="58073-260">Tehát a futtatásához `MeasureSuperposition` használjuk a következőt: `QuantumSimulator` `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="58073-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="58073-261">A visszaadott eredmények ezután a C#-változókhoz rendelhetők:</span><span class="sxs-lookup"><span data-stu-id="58073-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="58073-262">A `Run` metódus aszinkron módon fut, mert ez a valódi kvantum-hardver esetében ez a helyzet, ezért a `await` kulcsszó blokkolja a további feldolgozást, amíg a feladat be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="58073-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="58073-263">Ha a Q# hívható nem rendelkezik visszaadott értékkel (például visszatérési típussal rendelkezik `Unit` ), akkor a Futtatás továbbra is ugyanúgy végezhető el, ha nem rendel hozzá egy változóhoz.</span><span class="sxs-lookup"><span data-stu-id="58073-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="58073-264">Ebben az esetben a teljes sor csupán a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="58073-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="58073-265">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="58073-265">Arguments</span></span>

<span data-ttu-id="58073-266">A Q# meghívóhoz tartozó bármely argumentum egyszerűen a célszámítógép után további argumentumként lesz átadva.</span><span class="sxs-lookup"><span data-stu-id="58073-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="58073-267">Így a qubits eredményei `MeasureSuperpositionArray` a `n=4` következőn keresztül lettek beolvasva</span><span class="sxs-lookup"><span data-stu-id="58073-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="58073-268">A teljes C# gazda program így néz ki:</span><span class="sxs-lookup"><span data-stu-id="58073-268">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="58073-269">A C#-fájl helyén a gazda program a parancssorból is futtatható. Ehhez írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="58073-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="58073-270">Ebben az esetben a-konzolra írt kimenetet a következőhöz hasonló módon fogja látni:</span><span class="sxs-lookup"><span data-stu-id="58073-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="58073-271">A fordítóprogram névterekkel való együttműködése miatt előfordulhat, hogy a Q# callables az utasítás nélkül elérhetővé tesszük `using NamespaceName;` , és egyszerűen csak a C# névtér címére kell illeszkedni.</span><span class="sxs-lookup"><span data-stu-id="58073-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="58073-272">Ez azt helyettesíti, hogy `namespace host` `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="58073-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="58073-273">Beleértve a források becslését</span><span class="sxs-lookup"><span data-stu-id="58073-273">Including the resources estimator</span></span>

<span data-ttu-id="58073-274">A [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) kimenet beolvasásához némileg eltérő implementáció szükséges.</span><span class="sxs-lookup"><span data-stu-id="58073-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="58073-275">Először is, ahelyett, hogy egy `using` utasítással (például a következővel) változóként kívánja létrehozni őket `QuantumSimulator` , az osztály objektumainak közvetlen létrehozását</span><span class="sxs-lookup"><span data-stu-id="58073-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="58073-276">Figyelje meg, hogy a több művelet által használt egyetlen cél szimulátor helyett Q# mindegyikhez létrehozunk egyet.</span><span class="sxs-lookup"><span data-stu-id="58073-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="58073-277">Ennek az az oka, hogy maga az objektum is módosul, ha célként használt gépekként használják őket, és ezek eredményeit később a Class metódussal lehet lekérni `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="58073-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="58073-278">A műveleteknek az erőforrás-becslések való futtatásához használjuk a következőt</span><span class="sxs-lookup"><span data-stu-id="58073-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="58073-279">majd az eredményeket tabulátorral elválasztott értékként (TSV) a és a karakterrel kell beolvasni `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="58073-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="58073-280">Tehát a teljes C# gazda program mind a, mind a `QuantumSimulator` formáját a `ResourcesEstimator` következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="58073-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="58073-281">amely a következőhöz hasonló kimenetet eredményezhet</span><span class="sxs-lookup"><span data-stu-id="58073-281">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="58073-282">Q# Jupyter notebookok</span><span class="sxs-lookup"><span data-stu-id="58073-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="58073-283">Q# A Jupyter notebookok az I Q# kernelt használják, amely lehetővé teszi az callables egyetlen jegyzetfüzetben való definiálását, fordítását és futtatását Q# ---az összes útmutató, Megjegyzés és egyéb tartalom mellett.</span><span class="sxs-lookup"><span data-stu-id="58073-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="58073-284">Ez azt jelenti, hogy habár lehetséges a fájlok importálása és használata `*.qs` Q# , nem szükségesek a futtatási modellben.</span><span class="sxs-lookup"><span data-stu-id="58073-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="58073-285">Itt részletesen ismertetjük, hogyan futtatjuk a Q# fent meghatározott műveleteket, de a Jupyter notebookok használatának szélesebb körű bemutatása a Q# [notebookok bevezetője Q# és Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="58073-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="58073-286">Műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="58073-286">Defining operations</span></span>

<span data-ttu-id="58073-287">Egy Q# Jupyter notebook a kódot ugyanúgy kell megadnia, Q# mint egy fájl névterében Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="58073-288">Így lehetővé tehetjük a callables való hozzáférést a [ Q# szabványos könyvtárakból](xref:microsoft.quantum.libraries.standard.intro) a `open` megfelelő névterekhez tartozó utasításokkal.</span><span class="sxs-lookup"><span data-stu-id="58073-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="58073-289">Ha egy cellát egy ilyen utasítással futtat, a névterek definíciói a munkaterület teljes területén elérhetők.</span><span class="sxs-lookup"><span data-stu-id="58073-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="58073-290">A [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic) és a [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (például [`H`](xref:Microsoft.Quantum.Intrinsic.H) és) Callables [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) automatikusan elérhetők a Jupyter-jegyzetfüzetekben lévő cellákban definiált műveletekhez Q# .</span><span class="sxs-lookup"><span data-stu-id="58073-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="58073-291">Ez azonban nem igaz a külső forrásfájlok által bevitt kód esetében Q# (a [jegyzetfüzetek bevezetője Q# és Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)között látható folyamat).</span><span class="sxs-lookup"><span data-stu-id="58073-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="58073-292">Hasonlóképpen, a definiált műveletekhez csak a Q# kód írása és a cella futtatása szükséges.</span><span class="sxs-lookup"><span data-stu-id="58073-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="58073-293">A kimenet ezután felsorolja ezeket a műveleteket, amelyek ezután meghívhatók a jövőbeli cellákból.</span><span class="sxs-lookup"><span data-stu-id="58073-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="58073-294">Célgépek</span><span class="sxs-lookup"><span data-stu-id="58073-294">Target machines</span></span>

<span data-ttu-id="58073-295">Az adott célszámítógépeken futó műveletek futtatásának funkciói az [I Q# Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp)segítségével érhetők el.</span><span class="sxs-lookup"><span data-stu-id="58073-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="58073-296">Például a a (z) `%simulate` `QuantumSimulator` és a következőt `%estimate` használja `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="58073-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="58073-297">Bemenetek átadása a függvényeknek és műveleteknek</span><span class="sxs-lookup"><span data-stu-id="58073-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="58073-298">Ha át szeretné adni a bemeneteket a Q# műveletekhez, az argumentumok a `key=value` Run Magic parancsba párokként adhatók át.</span><span class="sxs-lookup"><span data-stu-id="58073-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="58073-299">Tehát a következő `MeasureSuperpositionArray` négy qubits futtatható `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="58073-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="58073-300">Ez a minta hasonlóan használható a `%estimate` és más futtatási parancsokhoz is.</span><span class="sxs-lookup"><span data-stu-id="58073-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="58073-301">Q#Kód használata más projektekről vagy csomagokból</span><span class="sxs-lookup"><span data-stu-id="58073-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="58073-302">Alapértelmezés szerint a Q# Jupyter notebook betölti az `.qs` aktuális mappában található összes fájlt, és a Q# műveleteit és funkcióit elérhetővé teszi a notebookon belülről való használatra.</span><span class="sxs-lookup"><span data-stu-id="58073-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="58073-303">A [ `%who` Magic parancs](xref:microsoft.quantum.iqsharp.magic-ref.who) felsorolja az összes jelenleg elérhető Q# műveletet és funkciót.</span><span class="sxs-lookup"><span data-stu-id="58073-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="58073-304">Q#A kód egy másik mappából való betöltéséhez használhatja a [ `%project` Magic parancsot](xref:microsoft.quantum.iqsharp.magic-ref.project) a `.csproj` projekthez tartozó fájlra mutató hivatkozás hozzáadásához Q# (azaz a projekt, amely hivatkozik `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="58073-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="58073-305">Ez a parancs lefordítja a `.qs` `.csproj` (és almappákat) tartalmazó mappában található összes fájlt.</span><span class="sxs-lookup"><span data-stu-id="58073-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="58073-306">Emellett rekurzív módon betölti az `PackageReference` adott fájlban hivatkozott vagy projekteken keresztül hivatkozott csomagokat is Q# `ProjectReference` `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="58073-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="58073-307">A következő cellák például egy Q# külső projektből származó műveletet szimulálnak, ahol a projekt elérési útja az aktuális mappához képest hivatkozik:</span><span class="sxs-lookup"><span data-stu-id="58073-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="58073-308">A kódot tartalmazó külső csomagok betöltéséhez Q# használja a [ `%package` Magic parancsot](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="58073-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="58073-309">A csomagok betöltése a csomag részét képező szerelvényekben található bármely egyéni mágikus parancsot vagy kódolókat is elérhetővé tesz.</span><span class="sxs-lookup"><span data-stu-id="58073-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="58073-310">Ha külső csomagokat vagy projekteket szeretne betölteni a Q# Jegyzetfüzet intialization, győződjön meg arról, hogy a notebook mappa tartalmaz egy `.csproj` hivatkozást tartalmazó fájlt `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="58073-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="58073-311">A ben `.csproj` adja hozzá a tulajdonságot a következőhöz: `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="58073-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="58073-312">Ez Q# arra utasítja a rendszer, hogy rekurzív módon töltse be a `ProjectReference` `PackageReference` `.csproj` Jegyzetfüzet betöltési idején található bármely vagy elemeket.</span><span class="sxs-lookup"><span data-stu-id="58073-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="58073-313">Íme például egy egyszerű `.csproj` fájl, amely a Q# csomag automatikus betöltését okozza `Microsoft.Quantum.Chemistry` :</span><span class="sxs-lookup"><span data-stu-id="58073-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="58073-314">Jelenleg ezt az egyéni `<IQSharpLoadAutomatically>` tulajdonságot Q# Jupyter notebook gazdagépek igénylik, de a jövőben ez lehet egy, a `.csproj` Jegyzetfüzet-fájllal azonos mappában található fájl alapértelmezett viselkedése.</span><span class="sxs-lookup"><span data-stu-id="58073-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="58073-315">Jelenleg a `<QsharpCompile>` `.csproj` Jupyter notebook gazdagépek figyelmen kívül hagyják a beállítást Q# , és a `.qs` mappában található összes fájl `.csproj` (beleértve az almappákat is) be van töltve és le van fordítva.</span><span class="sxs-lookup"><span data-stu-id="58073-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="58073-316">`.csproj`A beállítások támogatása a jövőben is javulni fog (további részletekért lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="58073-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
