---
title: 'Programok futtatásának módjai :::no-loc(Q#):::'
description: 'A programok futtatásának különböző módjai – áttekintés :::no-loc(Q#)::: . A parancssorból, a :::no-loc(Q#)::: Jupyter-jegyzetfüzetből és a klasszikus gazdagép-programokból Python vagy .net nyelven.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691705"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="18b2d-104">Programok futtatásának módjai :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="18b2d-104">Ways to run a :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="18b2d-105">A Quantum Development Kit egyik legnagyobb erőssége a platformok és a fejlesztői környezetek rugalmassága.</span><span class="sxs-lookup"><span data-stu-id="18b2d-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="18b2d-106">Ez azonban azt is jelenti, hogy az új :::no-loc(Q#)::: felhasználók a [telepítési útmutatóban](xref:microsoft.quantum.install)található számos lehetőség alapján megzavarják vagy elárasztják magukat.</span><span class="sxs-lookup"><span data-stu-id="18b2d-106">However, this also means that new :::no-loc(Q#)::: users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="18b2d-107">Ezen az oldalon elmagyarázza, hogy mi történik a :::no-loc(Q#)::: program futtatásakor, és hasonlítsa össze a felhasználók által megtehető különböző módokat.</span><span class="sxs-lookup"><span data-stu-id="18b2d-107">On this page, we explain what happens when a :::no-loc(Q#)::: program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="18b2d-108">Az elsődleges különbség az, hogy a :::no-loc(Q#)::: következőket lehet futtatni:</span><span class="sxs-lookup"><span data-stu-id="18b2d-108">A primary distinction is that :::no-loc(Q#)::: can be run:</span></span>
- <span data-ttu-id="18b2d-109">önálló alkalmazásként, ahol az az :::no-loc(Q#)::: egyetlen érintett nyelv, és a program közvetlenül hívja meg a programot.</span><span class="sxs-lookup"><span data-stu-id="18b2d-109">as a standalone application, where :::no-loc(Q#)::: is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="18b2d-110">Két metódus valójában a következő kategóriába tartozik:</span><span class="sxs-lookup"><span data-stu-id="18b2d-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="18b2d-111">a parancssori felület</span><span class="sxs-lookup"><span data-stu-id="18b2d-111">the command-line interface</span></span>
  - <span data-ttu-id="18b2d-112">:::no-loc(Q#)::: Jupyter notebookok</span><span class="sxs-lookup"><span data-stu-id="18b2d-112">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
- <span data-ttu-id="18b2d-113">egy Python-vagy .NET-nyelven írt további *gazdagép-programmal* (például C# vagy F #), amely ezt követően meghívja a programot, és folytatja a visszaadott eredmények feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="18b2d-113">with an additional *host program* , written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="18b2d-114">Ha szeretné jobban megérteni ezeket a folyamatokat és azok különbségeit, tekintse meg :::no-loc(Q#)::: az egyszerű programot, és hasonlítsa össze a futtatási módszereit.</span><span class="sxs-lookup"><span data-stu-id="18b2d-114">To best understand these processes and their differences, we consider a simple :::no-loc(Q#)::: program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="18b2d-115">Alapszintű :::no-loc(Q#)::: program</span><span class="sxs-lookup"><span data-stu-id="18b2d-115">Basic :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="18b2d-116">Egy alapszintű kvantum-program a qubit előállítását is magában foglalhatja az államok $ \ket $ és a $ \ket $ értékkel egyenlő arányban {0} {1} , a mérést és az eredményt visszaadva, amely a két, azonos valószínűséggel rendelkező állapot közül véletlenszerűen fog állni.</span><span class="sxs-lookup"><span data-stu-id="18b2d-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="18b2d-117">Ennek a folyamatnak a lényege a [Quantum Random Number Generator](xref:microsoft.quantum.quickstarts.qrng) rövid útmutatója.</span><span class="sxs-lookup"><span data-stu-id="18b2d-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="18b2d-118">A-ben :::no-loc(Q#)::: ezt a következő kód hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="18b2d-118">In :::no-loc(Q#):::, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="18b2d-119">Ez a kód azonban önmagában nem futtatható :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-119">However, this code alone can't be run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="18b2d-120">Ehhez egy [művelet](xref:microsoft.quantum.guide.basics#q-operations-and-functions)törzsét kell kiállítania, amely akkor fut le, amikor a---vagy közvetlenül, vagy egy másik művelet hívja meg.</span><span class="sxs-lookup"><span data-stu-id="18b2d-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="18b2d-121">Ezért a következő űrlapon is írhat egy műveletet:</span><span class="sxs-lookup"><span data-stu-id="18b2d-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="18b2d-122">Definiált egy műveletet, `MeasureSuperposition` amely nem vesz fel bemeneteket, és eredmény típusú értéket ad [Result](xref:microsoft.quantum.guide.types)vissza.</span><span class="sxs-lookup"><span data-stu-id="18b2d-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="18b2d-123">Habár az ezen a lapon szereplő példák csak a :::no-loc(Q#)::: *műveletekből* állnak, az összes olyan fogalmat, amelyet a függvények is érintenek, :::no-loc(Q#)::: *functions* és ezért a *callables* együttesen hivatkozunk rájuk.</span><span class="sxs-lookup"><span data-stu-id="18b2d-123">While the examples on this page only consist of :::no-loc(Q#)::: *operations* , all of the concepts we will discuss pertain equally to :::no-loc(Q#)::: *functions* , and therefore we refer to them collectively as *callables* .</span></span> <span data-ttu-id="18b2d-124">A különbségeket az [ :::no-loc(Q#)::: alapjai: Operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), valamint az azok definiálásával kapcsolatos további információk a [Operations and functions (műveletek és függvények](xref:microsoft.quantum.guide.operationsfunctions)) című cikkben találhatók.</span><span class="sxs-lookup"><span data-stu-id="18b2d-124">Their differences are discussed at [:::no-loc(Q#)::: basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="18b2d-125">Meghívható definiálva egy :::no-loc(Q#)::: fájlban</span><span class="sxs-lookup"><span data-stu-id="18b2d-125">Callable defined in a :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="18b2d-126">A hívható pontosan az, amit a meghívott és futtat :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-126">The callable is precisely what's called and run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="18b2d-127">Azonban ehhez több kiegészítésre van szükség, amely egy teljes fájlt tartalmaz `*.qs` :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-127">However, it requires a few more additions to comprise a full `*.qs` :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="18b2d-128">Az összes :::no-loc(Q#)::: típus-és callables (az Ön által definiált és a nyelvhez tartozók is) a *névterekben* vannak definiálva, amelyek minden olyan teljes nevet megadnak, amelyre hivatkozni lehet.</span><span class="sxs-lookup"><span data-stu-id="18b2d-128">All :::no-loc(Q#)::: types and callables (both those you define and those intrinsic to the language) are defined within *namespaces* , which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="18b2d-129">Például a és a [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) műveletek a és a [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) névterekben találhatók (a [ :::no-loc(Q#)::: standard könyvtárak](xref:microsoft.quantum.qsharplibintro)része).</span><span class="sxs-lookup"><span data-stu-id="18b2d-129">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [:::no-loc(Q#)::: Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="18b2d-130">Így mindig meghívhatják a *teljes* nevüket, de mindig megtehetik, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` hogy ez nagyon zsúfolt programkódot eredményez.</span><span class="sxs-lookup"><span data-stu-id="18b2d-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="18b2d-131">Ehelyett `open` az utasítások lehetővé teszik, hogy a callables tömör gyorsírással legyenek hivatkozva, ahogy a fenti műveleti törzsben tettük.</span><span class="sxs-lookup"><span data-stu-id="18b2d-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="18b2d-132">A :::no-loc(Q#)::: műveletet tartalmazó teljes fájl ezért a saját névterek definiálását, a callables, a művelet által használt névterek megnyitását, majd a műveletet:</span><span class="sxs-lookup"><span data-stu-id="18b2d-132">The full :::no-loc(Q#)::: file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="18b2d-133">A névterek a megnyitásakor is *aliasként* használhatók, ami akkor lehet hasznos, ha a hívható/Type nevek két névtérben ütköznek.</span><span class="sxs-lookup"><span data-stu-id="18b2d-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="18b2d-134">Tegyük fel például, hogy a `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` fentieket fogjuk használni, majd meghívjuk a- `H` on keresztül `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="18b2d-135">Ennek egyetlen kivétele a [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) névtér, amely mindig automatikusan megnyílik.</span><span class="sxs-lookup"><span data-stu-id="18b2d-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="18b2d-136">Ezért a callables, mint a [`Length`](xref:Microsoft.Quantum.Core.Length) mindig közvetlenül használhatók.</span><span class="sxs-lookup"><span data-stu-id="18b2d-136">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="18b2d-137">Futtatás a célszámítógépen</span><span class="sxs-lookup"><span data-stu-id="18b2d-137">Running on target machines</span></span>

<span data-ttu-id="18b2d-138">Mostantól a program általános futtatási modellje is :::no-loc(Q#)::: világossá válik.</span><span class="sxs-lookup"><span data-stu-id="18b2d-138">Now the general run model of a :::no-loc(Q#)::: program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt=":::no-loc(Q#)::: program execution diagram" width="400">

<span data-ttu-id="18b2d-139">Először is az adott futtatáshoz megadott meghívónak hozzá kell férnie az ugyanabban a névtérben definiált összes más callables és típushoz.</span><span class="sxs-lookup"><span data-stu-id="18b2d-139">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="18b2d-140">Emellett a [ :::no-loc(Q#)::: könyvtárak](xref:microsoft.quantum.libraries)bármelyikének hozzáférését is elérheti, de ezeket a teljes névvel vagy a fent ismertetett utasítások használatával kell hivatkozni `open` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-140">It also access those from any of the [:::no-loc(Q#)::: libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="18b2d-141">A meghívót ezután futtathatja a *[célszámítógépen](xref:microsoft.quantum.machines)* .</span><span class="sxs-lookup"><span data-stu-id="18b2d-141">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)* .</span></span>
<span data-ttu-id="18b2d-142">Ilyen célszámítógépek lehetnek a tényleges kvantum-hardverek vagy a QDK részeként elérhető több szimulátorok.</span><span class="sxs-lookup"><span data-stu-id="18b2d-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="18b2d-143">Erre a célra a leghasznosabb célszámítógép a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)egy példánya, `QuantumSimulator` amely úgy számítja ki a program viselkedését, mintha egy zaj nélküli kvantum-számítógépen futna.</span><span class="sxs-lookup"><span data-stu-id="18b2d-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="18b2d-144">Eddig azt ismertetjük, hogy mi történik, ha egy adott :::no-loc(Q#)::: hívás fut.</span><span class="sxs-lookup"><span data-stu-id="18b2d-144">So far, we've described what happens when a specific :::no-loc(Q#)::: callable is being run.</span></span>
<span data-ttu-id="18b2d-145">Függetlenül attól, hogy :::no-loc(Q#)::: egy önálló alkalmazásban vagy egy gazdagép programban használ-e, ez az általános folyamat több vagy kevesebb, mint a QDK rugalmassága---.</span><span class="sxs-lookup"><span data-stu-id="18b2d-145">Regardless of whether :::no-loc(Q#)::: is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="18b2d-146">A Quantum Development Kit Meghívási módjai közötti különbségek tehát azt mutatják be, hogy *how* a :::no-loc(Q#)::: hívható hívása hogyan fut, és milyen módon adja vissza az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="18b2d-146">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that :::no-loc(Q#)::: callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="18b2d-147">Pontosabban a különbségek a következő körben forognak:</span><span class="sxs-lookup"><span data-stu-id="18b2d-147">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="18b2d-148">Annak jelzése, :::no-loc(Q#)::: hogy melyik meghívót kell futtatni</span><span class="sxs-lookup"><span data-stu-id="18b2d-148">Indicating which :::no-loc(Q#)::: callable is to be run</span></span>
- <span data-ttu-id="18b2d-149">A lehetséges hívható argumentumok megadása</span><span class="sxs-lookup"><span data-stu-id="18b2d-149">How potential callable arguments are provided</span></span>
- <span data-ttu-id="18b2d-150">Azon célszámítógép meghatározása, amelyen futtatni szeretné</span><span class="sxs-lookup"><span data-stu-id="18b2d-150">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="18b2d-151">A visszaadott eredmények</span><span class="sxs-lookup"><span data-stu-id="18b2d-151">How any results are returned</span></span>

<span data-ttu-id="18b2d-152">Először is megbeszéljük, hogy ez hogyan történik az :::no-loc(Q#)::: önálló alkalmazás parancssorból való használatával, majd folytassa a Python és a C# gazdagép-programok használatát.</span><span class="sxs-lookup"><span data-stu-id="18b2d-152">First, we discuss how this is done with the :::no-loc(Q#)::: standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="18b2d-153">Fenntartjuk a Jupyter-jegyzetfüzetek önálló alkalmazását az :::no-loc(Q#)::: utolsó számára, mivel az első háromtól eltérően az elsődleges funkció nem a helyi fájlok körébe kerül :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-153">We reserve the standalone application of :::no-loc(Q#)::: Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local :::no-loc(Q#)::: file.</span></span>

> [!NOTE]
> <span data-ttu-id="18b2d-154">Habár nem mutatjuk be ezeket a példákat, a futtatási módszerek közötti egyetlen egység az, hogy a programon belülről kinyomtatott összes üzenet :::no-loc(Q#)::: ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) például: vagy [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ) általában mindig a megfelelő konzolra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="18b2d-154">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the :::no-loc(Q#)::: program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="18b2d-155">:::no-loc(Q#)::: a parancssorból</span><span class="sxs-lookup"><span data-stu-id="18b2d-155">:::no-loc(Q#)::: from the command prompt</span></span>
<span data-ttu-id="18b2d-156">A programok írásához legkönnyebben elsajátíthatja az első lépéseket, :::no-loc(Q#)::: hogy elkerülje a különálló fájlok és a második nyelv használatának elkerülését.</span><span class="sxs-lookup"><span data-stu-id="18b2d-156">One of the easiest ways to get started writing :::no-loc(Q#)::: programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="18b2d-157">A Visual Studio Code vagy a Visual Studio és a QDK bővítmény lehetővé teszi a zökkenőmentes munkafolyamatot, amelyben a :::no-loc(Q#)::: callables-t csak egyetlen :::no-loc(Q#)::: fájlból futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="18b2d-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run :::no-loc(Q#)::: callables from only a single :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="18b2d-158">Ehhez a következő lépéssel fogjuk futtatni a programot:</span><span class="sxs-lookup"><span data-stu-id="18b2d-158">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="18b2d-159">parancsot a parancssorban.</span><span class="sxs-lookup"><span data-stu-id="18b2d-159">at the command prompt.</span></span>
<span data-ttu-id="18b2d-160">A legegyszerűbb munkafolyamat az, amikor a terminál címtárának helye megegyezik a fájl nevével :::no-loc(Q#)::: , amely könnyen kezelhető a :::no-loc(Q#)::: fájl szerkesztésével együtt a vs Code integrált termináljának használatával, például:.</span><span class="sxs-lookup"><span data-stu-id="18b2d-160">The simplest workflow is when the terminal's directory location is the same as the :::no-loc(Q#)::: file, which can be easily handled alongside :::no-loc(Q#)::: file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="18b2d-161">A [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) azonban számos lehetőséget is elfogad, és a program más helyről is futtatható, ha egyszerűen megadja a `--project <PATH>` :::no-loc(Q#)::: fájl helyét.</span><span class="sxs-lookup"><span data-stu-id="18b2d-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the :::no-loc(Q#)::: file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="18b2d-162">Belépési pont hozzáadása a :::no-loc(Q#)::: fájlhoz</span><span class="sxs-lookup"><span data-stu-id="18b2d-162">Add entry point to :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="18b2d-163">A legtöbb :::no-loc(Q#)::: fájl egynél több meghívót tartalmaz, ezért a fordítónak természetesen azt is tudnia kell, hogy *melyik* meghívásos futtatásra van szükség a parancs megadásakor `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-163">Most :::no-loc(Q#)::: files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="18b2d-164">Ez a fájl egyszerű módosításával történik :::no-loc(Q#)::: :</span><span class="sxs-lookup"><span data-stu-id="18b2d-164">This is done with a simple change to the :::no-loc(Q#)::: file itself:</span></span> 
    - <span data-ttu-id="18b2d-165">Adjon hozzá egy sort, amely `@EntryPoint()` közvetlenül megelőzi a meghívót.</span><span class="sxs-lookup"><span data-stu-id="18b2d-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="18b2d-166">Ezért a fenti fájl a következő lesz:</span><span class="sxs-lookup"><span data-stu-id="18b2d-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="18b2d-167">Most a `dotnet run` parancssorból érkező hívás a `MeasureSuperposition` futtatáshoz vezet, és a visszaadott érték közvetlenül a terminálra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="18b2d-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="18b2d-168">Így a rendszer `One` vagy kinyomtatja a következőt: `Zero` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="18b2d-169">Vegye figyelembe, hogy nem számít, hogy ha több callables van definiálva, csak a `MeasureSuperposition` futtatásra kerül.</span><span class="sxs-lookup"><span data-stu-id="18b2d-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="18b2d-170">Emellett nem jelent problémát, ha a meghívó a nyilatkozata előtt is tartalmaz [dokumentációs megjegyzéseket](xref:microsoft.quantum.guide.filestructure#documentation-comments) , az `@EntryPoint()` attribútum egyszerűen elhelyezhető.</span><span class="sxs-lookup"><span data-stu-id="18b2d-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="18b2d-171">Hívható argumentumok</span><span class="sxs-lookup"><span data-stu-id="18b2d-171">Callable arguments</span></span>

<span data-ttu-id="18b2d-172">Eddig csak olyan műveletet vettünk figyelembe, amely nem vesz fel bemeneteket.</span><span class="sxs-lookup"><span data-stu-id="18b2d-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="18b2d-173">Tegyük fel, hogy hasonló műveletet hajtottunk végre, de több qubits---az argumentumként megadott számú értéket.</span><span class="sxs-lookup"><span data-stu-id="18b2d-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="18b2d-174">Egy ilyen művelet a következőképpen írható</span><span class="sxs-lookup"><span data-stu-id="18b2d-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="18b2d-175">ahol a visszaadott érték a mérési eredmények tömbje.</span><span class="sxs-lookup"><span data-stu-id="18b2d-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="18b2d-176">Vegye figyelembe, hogy [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) a és [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) a [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) névterek esetében további `open` utasításokra van szükség mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="18b2d-176">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="18b2d-177">Ha az `@EntryPoint()` attribútumot az új művelet előtt helyezi át (vegye figyelembe, hogy egy fájlban csak egy ilyen sor lehet), és a futtatására tett kísérlet egyszerűen `dotnet run` olyan hibaüzenetet eredményez, amely azt jelzi, hogy milyen további parancssori kapcsolók szükségesek, és hogyan fejezheti ki őket.</span><span class="sxs-lookup"><span data-stu-id="18b2d-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="18b2d-178">A parancssor általános formátuma ténylegesen `dotnet run [options]` , a hívható argumentumok pedig itt vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="18b2d-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="18b2d-179">Ebben az esetben az argumentum `n` hiányzik, és azt mutatja, hogy meg kell adnia a beállítást `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="18b2d-180">A qubits való futtatáshoz `MeasureSuperpositionArray` ezért használjuk a következőt: `n=4`</span><span class="sxs-lookup"><span data-stu-id="18b2d-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="18b2d-181">a következőhöz hasonló kimenetet eredményez</span><span class="sxs-lookup"><span data-stu-id="18b2d-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="18b2d-182">Ez a tanfolyam több argumentumra is kiterjed.</span><span class="sxs-lookup"><span data-stu-id="18b2d-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="18b2d-183">A ben definiált argumentumok nevét `camelCase` a fordító csak kis mértékben módosítja :::no-loc(Q#)::: bemenetként.</span><span class="sxs-lookup"><span data-stu-id="18b2d-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as :::no-loc(Q#)::: inputs.</span></span> <span data-ttu-id="18b2d-184">Például, ha `n` a helyett a fenti nevet használtuk `numQubits` , akkor ez a bemenet a parancssoron keresztül lesz megadva a `--num-qubits 4` helyett `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="18b2d-185">A hibaüzenet más lehetőségeket is tartalmaz, amelyek használhatók, beleértve a célszámítógép módosításának módját is.</span><span class="sxs-lookup"><span data-stu-id="18b2d-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="18b2d-186">Különböző célszámítógépek</span><span class="sxs-lookup"><span data-stu-id="18b2d-186">Different target machines</span></span>

<span data-ttu-id="18b2d-187">Mivel a műveleteik eredményei a tényleges qubits a várt eredmények voltak, egyértelmű, hogy a parancssorból az alapértelmezett célszámítógép a teljes állapotú kvantum-szimulátor `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="18b2d-188">Azonban arra is utasíthatja a callables, hogy egy adott célszámítógépen fusson a `--simulator` (vagy a gyorsírással) lehetőséggel `-s` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="18b2d-189">Futtathatja például a következőt [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="18b2d-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="18b2d-190">Ekkor a kinyomtatott kimenet</span><span class="sxs-lookup"><span data-stu-id="18b2d-190">The printed output is then</span></span>

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

<span data-ttu-id="18b2d-191">Az ezekkel a mérőszámokkal kapcsolatos részletekért lásd [: erőforrás-kalkulátor: a jelentett mérőszámok](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="18b2d-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="18b2d-192">Parancssori Futtatás összegzése</span><span class="sxs-lookup"><span data-stu-id="18b2d-192">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt=":::no-loc(Q#)::: program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="18b2d-193">Nem :::no-loc(Q#)::: `dotnet run` Beállítások</span><span class="sxs-lookup"><span data-stu-id="18b2d-193">Non-:::no-loc(Q#)::: `dotnet run` options</span></span>

<span data-ttu-id="18b2d-194">Ahogy azt röviden említettük a `--project` kapcsolóval, a [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) a :::no-loc(Q#)::: meghívásos argumentumokhoz nem kapcsolódó beállításokat is elfogadja.</span><span class="sxs-lookup"><span data-stu-id="18b2d-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the :::no-loc(Q#)::: callable arguments.</span></span>
<span data-ttu-id="18b2d-195">Ha mindkét típusú beállítást megadja, a `dotnet` -specifikus beállításokat elsőként kell megadni, majd egy elválasztó karakter `--` , majd a :::no-loc(Q#)::: -specifikus beállításokat.</span><span class="sxs-lookup"><span data-stu-id="18b2d-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the :::no-loc(Q#):::-specific options.</span></span>
<span data-ttu-id="18b2d-196">Például megadhat egy elérési utat, valamint a fenti művelethez tartozó qubits `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-196">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="18b2d-197">:::no-loc(Q#)::: gazdagép-programokkal</span><span class="sxs-lookup"><span data-stu-id="18b2d-197">:::no-loc(Q#)::: with host programs</span></span>

<span data-ttu-id="18b2d-198">Ha a :::no-loc(Q#)::: fájl a kezünkben van, a művelet vagy a függvény közvetlenül a parancssorból való meghívására szolgáló alternatíva egy másik klasszikus nyelven üzemelő *gazda program* használata.</span><span class="sxs-lookup"><span data-stu-id="18b2d-198">With our :::no-loc(Q#)::: file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="18b2d-199">Pontosabban megteheti a Python vagy a .NET nyelv, például a C# vagy az F # kombinációját (a rövidség kedvéért csak a C# adatokat fogjuk részletezni).</span><span class="sxs-lookup"><span data-stu-id="18b2d-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="18b2d-200">Az együttműködési képesség engedélyezéséhez valamivel több beállítás szükséges, de ezek a részletek a [telepítési útmutatókban](xref:microsoft.quantum.install)találhatók.</span><span class="sxs-lookup"><span data-stu-id="18b2d-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="18b2d-201">Dióhéjban a helyzet most már tartalmaz egy gazda programfájlt (például `*.py` vagy `*.cs` ) a fájllal megegyező helyen :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-201">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="18b2d-202">Most már a futtatott *gazda* program fut, és a futása közben :::no-loc(Q#)::: a fájl adott műveleteit és funkcióit is meghívhatja :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-202">It's now the *host* program that gets run, and while it is running, it can call specific :::no-loc(Q#)::: operations and functions from the :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="18b2d-203">Az együttműködési képesség lényege, hogy a :::no-loc(Q#)::: fordító a :::no-loc(Q#)::: fájl tartalmát elérhetővé teszi a gazda program számára, hogy azok meghívhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="18b2d-203">The core of the interoperability is based on the :::no-loc(Q#)::: compiler making the contents of the :::no-loc(Q#)::: file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="18b2d-204">A gazda program használatának egyik legfőbb előnye, hogy a program által visszaadott klasszikus adatmennyiséget a :::no-loc(Q#)::: gazdagép nyelvén lehet tovább feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="18b2d-204">One of the main benefits of using a host program is that the classical data returned by the :::no-loc(Q#)::: program can then be further processed in the host language.</span></span>
<span data-ttu-id="18b2d-205">Ez állhat néhány speciális adatfeldolgozásból (például egy olyanra, amely nem hajtható végre belsőleg :::no-loc(Q#)::: ), majd az :::no-loc(Q#)::: eredmények alapján további műveleteket hívhat meg, vagy az eredmények ábrázolására is alkalmas :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-205">This could consist of some advanced data processing (for example, something that can't be performed internally in :::no-loc(Q#):::), and then calling further :::no-loc(Q#)::: actions based on those results, or something as simple as plotting the :::no-loc(Q#)::: results.</span></span>

<span data-ttu-id="18b2d-206">Az általános séma itt látható, és megbeszéljük a Python és a C# adott implementációit alább.</span><span class="sxs-lookup"><span data-stu-id="18b2d-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="18b2d-207">Az F # gazda programot használó minta a .net-es [együttműködési mintákon](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)érhető el.</span><span class="sxs-lookup"><span data-stu-id="18b2d-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt=":::no-loc(Q#)::: program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="18b2d-208">Az `@EntryPoint()` :::no-loc(Q#)::: alkalmazásokhoz használt attribútum nem használható a gazdagép-programokkal.</span><span class="sxs-lookup"><span data-stu-id="18b2d-208">The `@EntryPoint()` attribute used for :::no-loc(Q#)::: applications cannot be used with host programs.</span></span>
> <span data-ttu-id="18b2d-209">A rendszer hibát jelez, ha az :::no-loc(Q#)::: egy gazdagép által hívott fájlban szerepel.</span><span class="sxs-lookup"><span data-stu-id="18b2d-209">An error will be raised if it is present in the :::no-loc(Q#)::: file being called by a host.</span></span> 

<span data-ttu-id="18b2d-210">A különböző gazdagépekkel való munkavégzéshez nincs szükség módosításra a `*.qs` :::no-loc(Q#)::: fájlokhoz.</span><span class="sxs-lookup"><span data-stu-id="18b2d-210">To work with different host programs, there are no changes required to a `*.qs` :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="18b2d-211">A következő gazda program-implementációk mindegyike ugyanazzal a :::no-loc(Q#)::: fájllal működik:</span><span class="sxs-lookup"><span data-stu-id="18b2d-211">The following host program implementations all work with the same :::no-loc(Q#)::: file:</span></span>

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

<span data-ttu-id="18b2d-212">Válassza ki a megfelelő gazdagép-nyelvhez tartozó fület.</span><span class="sxs-lookup"><span data-stu-id="18b2d-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="18b2d-213">Python</span><span class="sxs-lookup"><span data-stu-id="18b2d-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="18b2d-214">A Python-gazda program a következőképpen épül fel:</span><span class="sxs-lookup"><span data-stu-id="18b2d-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="18b2d-215">Importálja a modult `qsharp` , amely regisztrálja a modul-betöltőt az :::no-loc(Q#)::: együttműködési képességhez.</span><span class="sxs-lookup"><span data-stu-id="18b2d-215">Import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="18b2d-216">Ez lehetővé teszi :::no-loc(Q#)::: , hogy a névterek Python-modulokként jelenjenek meg, amelyekről "importálhatók" :::no-loc(Q#)::: callables.</span><span class="sxs-lookup"><span data-stu-id="18b2d-216">This allows :::no-loc(Q#)::: namespaces to appear as Python modules, from which we can "import" :::no-loc(Q#)::: callables.</span></span>
    <span data-ttu-id="18b2d-217">Ne feledje, hogy a callables nem :::no-loc(Q#)::: maga az importált, hanem a Python-Csonkok, amelyek lehetővé teszik a hívását.</span><span class="sxs-lookup"><span data-stu-id="18b2d-217">Note that it is technically not the :::no-loc(Q#)::: callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="18b2d-218">Ezek a Python-osztályok objektumaiként viselkednek.</span><span class="sxs-lookup"><span data-stu-id="18b2d-218">These behave as objects of Python classes.</span></span> <span data-ttu-id="18b2d-219">Ezen objektumok módszereit használva megadjuk azokat a célszámítógépeken, amelyeken a műveletet a program futtatásakor küldi el a rendszer.</span><span class="sxs-lookup"><span data-stu-id="18b2d-219">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="18b2d-220">Importálja azokat a :::no-loc(Q#)::: callables, amelyeket a rendszer közvetlenül meghív---ebben az esetben, `MeasureSuperposition` és `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-220">Import those :::no-loc(Q#)::: callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="18b2d-221">Ha a `qsharp` modult importálta, a callables közvetlenül a :::no-loc(Q#)::: könyvtár névteréről is importálhatja.</span><span class="sxs-lookup"><span data-stu-id="18b2d-221">With the `qsharp` module imported, you can also import callables directly from the :::no-loc(Q#)::: library namespaces.</span></span>

3. <span data-ttu-id="18b2d-222">A többi Python-kód között mostantól meghívhatja ezeket a callables az adott célszámítógépeken, és hozzárendelheti azok változóhoz való visszatérését (ha értéket adnak vissza) a további használatra.</span><span class="sxs-lookup"><span data-stu-id="18b2d-222">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="18b2d-223">Megcélzott gépek meghatározása</span><span class="sxs-lookup"><span data-stu-id="18b2d-223">Specifying target machines</span></span>
<span data-ttu-id="18b2d-224">Egy adott célszámítógépen futtatandó művelet meghívása az importált objektumon különböző Python-módszerekkel történik.</span><span class="sxs-lookup"><span data-stu-id="18b2d-224">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="18b2d-225">A (z `.simulate(<args>)` ) például a használatával `QuantumSimulator` futtatja a műveletet, míg `.estimate_resources(<args>)` a (z `ResourcesEstimator` ).</span><span class="sxs-lookup"><span data-stu-id="18b2d-225">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="18b2d-226">Bemenetek továbbítása a Q-ba\#</span><span class="sxs-lookup"><span data-stu-id="18b2d-226">Passing inputs to Q\#</span></span>
<span data-ttu-id="18b2d-227">A :::no-loc(Q#)::: meghívható argumentumokat kulcsszó típusú argumentum formájában kell megadni, ahol a kulcsszó az argumentum neve a :::no-loc(Q#)::: meghívásos definícióban.</span><span class="sxs-lookup"><span data-stu-id="18b2d-227">Arguments for the :::no-loc(Q#)::: callable should be provided in the form of a keyword argument, where the keyword is the argument name in the :::no-loc(Q#)::: callable definition.</span></span>
<span data-ttu-id="18b2d-228">Ez `MeasureSuperpositionArray.simulate(n=4)` érvényes, míg `MeasureSuperpositionArray.simulate(4)` hiba történt.</span><span class="sxs-lookup"><span data-stu-id="18b2d-228">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="18b2d-229">Ezért a Python-gazda program</span><span class="sxs-lookup"><span data-stu-id="18b2d-229">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="18b2d-230">a következőhöz hasonló kimenetet eredményez:</span><span class="sxs-lookup"><span data-stu-id="18b2d-230">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="18b2d-231">:::no-loc(Q#):::Kód használata más projektekről vagy csomagokból</span><span class="sxs-lookup"><span data-stu-id="18b2d-231">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="18b2d-232">Alapértelmezés szerint a `import qsharp` parancs betölti az `.qs` aktuális mappában található összes fájlt, és a :::no-loc(Q#)::: műveleteit és funkcióit elérhetővé teszi a Python-szkripten belülről való használatra.</span><span class="sxs-lookup"><span data-stu-id="18b2d-232">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="18b2d-233">:::no-loc(Q#):::A kód egy másik mappából való betöltéséhez az [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) -val egy projektre mutató hivatkozást adhat hozzá `.csproj` :::no-loc(Q#)::: (azaz egy projekt, amely hivatkozik `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="18b2d-233">To load :::no-loc(Q#)::: code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="18b2d-234">Ez a parancs lefordítja a `.qs` mappában található összes fájlt, amely tartalmazza a `.csproj` és almappáit.</span><span class="sxs-lookup"><span data-stu-id="18b2d-234">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="18b2d-235">Emellett rekurzív módon betölti az `PackageReference` adott fájlban hivatkozott vagy projekteken keresztül hivatkozott csomagokat is :::no-loc(Q#)::: `ProjectReference` `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-235">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="18b2d-236">A következő Python-kód például egy külső projektet importál, amely az aktuális mappához viszonyított elérési útra hivatkozik, és meghívja az egyik :::no-loc(Q#)::: műveletét:</span><span class="sxs-lookup"><span data-stu-id="18b2d-236">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its :::no-loc(Q#)::: operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="18b2d-237">Ez a következőhöz hasonló kimenetet eredményez:</span><span class="sxs-lookup"><span data-stu-id="18b2d-237">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="18b2d-238">A kódot tartalmazó külső csomagok betöltéséhez :::no-loc(Q#)::: használja az [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)-t.</span><span class="sxs-lookup"><span data-stu-id="18b2d-238">To load external packages containing :::no-loc(Q#)::: code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="18b2d-239">Ha az :::no-loc(Q#)::: aktuális mappában található kód külső projekttől vagy csomagtól függ, a futtatásakor hibák jelenhetnek meg `import qsharp` , mivel a függőségek még nincsenek betöltve.</span><span class="sxs-lookup"><span data-stu-id="18b2d-239">If the :::no-loc(Q#)::: code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="18b2d-240">A szükséges külső csomagok vagy projektek a parancsban való betöltéséhez győződjön meg arról, :::no-loc(Q#)::: `import qsharp` hogy a Python-szkripttel rendelkező mappa tartalmaz egy `.csproj` hivatkozást tartalmazó fájlt `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-240">To load required external packages or :::no-loc(Q#)::: projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="18b2d-241">A ben `.csproj` adja hozzá a tulajdonságot a következőhöz: `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-241">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="18b2d-242">Ez :::no-loc(Q#)::: a művelet arra utasítja, hogy rekurzív módon töltse be `ProjectReference` `PackageReference` `.csproj` a parancsban található összes vagy elemet `import qsharp` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-242">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="18b2d-243">Íme például egy egyszerű `.csproj` fájl, amely a :::no-loc(Q#)::: csomag automatikus betöltését okozza `Microsoft.Quantum.Chemistry` :</span><span class="sxs-lookup"><span data-stu-id="18b2d-243">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

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
> <span data-ttu-id="18b2d-244">Jelenleg ezt az egyéni `<IQSharpLoadAutomatically>` tulajdonságot a Python-gazdagépek igénylik, de a jövőben ez a `.csproj` Python-szkripttel megegyező mappában található fájl alapértelmezett viselkedése lehet.</span><span class="sxs-lookup"><span data-stu-id="18b2d-244">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="18b2d-245">A rendszer jelenleg a `<QsharpCompile>` `.csproj` következő beállítást veszi figyelembe a Python-gazdagépek esetében, és a mappában található összes `.qs` fájl `.csproj` (beleértve az almappákat is) be van töltve és le van fordítva.</span><span class="sxs-lookup"><span data-stu-id="18b2d-245">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="18b2d-246">`.csproj`A beállítások támogatása a jövőben is javulni fog (további részletekért lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="18b2d-246">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="18b2d-247">C#</span><span class="sxs-lookup"><span data-stu-id="18b2d-247">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="18b2d-248">A C# gazda program több összetevővel rendelkezik, és nagyon szorosan együttműködik a QDK egyes összetevőivel, például a szimulátorokkal, amelyek a C# nyelvre épülnek.</span><span class="sxs-lookup"><span data-stu-id="18b2d-248">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="18b2d-249">A :::no-loc(Q#)::: fordító itt működik, ha egy egyenértékű névvel ellátott C#-névteret hoz létre a :::no-loc(Q#)::: fájl névterében :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-249">The :::no-loc(Q#)::: compiler works here by generating an equivalently named C# namespace from the :::no-loc(Q#)::: namespace in our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="18b2d-250">Ezzel egyenértékű névvel ellátott C# osztályt hoz létre minden egyes :::no-loc(Q#)::: definiált callables vagy típushoz.</span><span class="sxs-lookup"><span data-stu-id="18b2d-250">It further generates an equivalently named C# class for each of the :::no-loc(Q#)::: callables or types defined therein.</span></span>

<span data-ttu-id="18b2d-251">Első lépésként a gazda programunkban használt osztályokat tesszük elérhetővé a következő `using` utasításokkal, amelyek nagyjából analagous a `open` fájl utasításait :::no-loc(Q#)::: :</span><span class="sxs-lookup"><span data-stu-id="18b2d-251">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our :::no-loc(Q#)::: file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the :::no-loc(Q#)::: namespace available
```

<span data-ttu-id="18b2d-252">Ezután deklaráljuk a C#-névteret, néhány más bitet és darabot (lásd az alábbi teljes kódrészletet), majd a klasszikus programozást (például a callables számítási argumentumait :::no-loc(Q#)::: ).</span><span class="sxs-lookup"><span data-stu-id="18b2d-252">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the :::no-loc(Q#)::: callables).</span></span>
<span data-ttu-id="18b2d-253">Az utóbbi nem szükséges az esetünkben, de az ilyen jellegű használatról a .net-es  [együttműködési minta](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)tartalmaz példát.</span><span class="sxs-lookup"><span data-stu-id="18b2d-253">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="18b2d-254">Célgépek</span><span class="sxs-lookup"><span data-stu-id="18b2d-254">Target machines</span></span>

<span data-ttu-id="18b2d-255">A szolgáltatásba való visszatéréshez :::no-loc(Q#)::: létre kell hoznia a célszámítógép egy példányát.</span><span class="sxs-lookup"><span data-stu-id="18b2d-255">Getting back to :::no-loc(Q#):::, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="18b2d-256">Más célszámítógépek használata olyan egyszerű, mint egy másik példány létrehozása, bár ennek a módja, és a visszatérések feldolgozása némileg eltérő lehet.</span><span class="sxs-lookup"><span data-stu-id="18b2d-256">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="18b2d-257">A rövidség kedvéért most ragaszkodunk a [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) szolgáltatáshoz, és belefoglaljuk az [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [alábbiakat](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="18b2d-257">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="18b2d-258">A műveletekben létrehozott minden C# osztálynak :::no-loc(Q#)::: van egy `Run` metódusa, amely az első argumentum, amelynek a célszámítógép-példánynak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="18b2d-258">Each C# class generated from the :::no-loc(Q#)::: operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="18b2d-259">Tehát a futtatásához `MeasureSuperposition` használjuk a következőt: `QuantumSimulator` `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-259">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="18b2d-260">A visszaadott eredmények ezután a C#-változókhoz rendelhetők:</span><span class="sxs-lookup"><span data-stu-id="18b2d-260">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="18b2d-261">A `Run` metódus aszinkron módon fut, mert ez a valódi kvantum-hardver esetében ez a helyzet, ezért a `await` kulcsszó blokkolja a további feldolgozást, amíg a feladat be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="18b2d-261">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="18b2d-262">Ha a :::no-loc(Q#)::: hívható nem rendelkezik visszaadott értékkel (például visszatérési típussal rendelkezik `Unit` ), akkor a Futtatás továbbra is ugyanúgy végezhető el, ha nem rendel hozzá egy változóhoz.</span><span class="sxs-lookup"><span data-stu-id="18b2d-262">If the :::no-loc(Q#)::: callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="18b2d-263">Ebben az esetben a teljes sor csupán a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="18b2d-263">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="18b2d-264">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="18b2d-264">Arguments</span></span>

<span data-ttu-id="18b2d-265">A :::no-loc(Q#)::: meghívóhoz tartozó bármely argumentum egyszerűen a célszámítógép után további argumentumként lesz átadva.</span><span class="sxs-lookup"><span data-stu-id="18b2d-265">Any arguments to the :::no-loc(Q#)::: callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="18b2d-266">Így a qubits eredményei `MeasureSuperpositionArray` a `n=4` következőn keresztül lettek beolvasva</span><span class="sxs-lookup"><span data-stu-id="18b2d-266">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="18b2d-267">A teljes C# gazda program így néz ki:</span><span class="sxs-lookup"><span data-stu-id="18b2d-267">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="18b2d-268">A C#-fájl helyén a gazda program a parancssorból is futtatható. Ehhez írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="18b2d-268">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="18b2d-269">Ebben az esetben a-konzolra írt kimenetet a következőhöz hasonló módon fogja látni:</span><span class="sxs-lookup"><span data-stu-id="18b2d-269">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="18b2d-270">A fordítóprogram névterekkel való együttműködése miatt előfordulhat, hogy a :::no-loc(Q#)::: callables az utasítás nélkül elérhetővé tesszük `using NamespaceName;` , és egyszerűen csak a C# névtér címére kell illeszkedni.</span><span class="sxs-lookup"><span data-stu-id="18b2d-270">Due to the compiler's interoperability with namespaces, we could alternatively make our :::no-loc(Q#)::: callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="18b2d-271">Ez azt helyettesíti, hogy `namespace host` `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-271">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="18b2d-272">Beleértve a források becslését</span><span class="sxs-lookup"><span data-stu-id="18b2d-272">Including the resources estimator</span></span>

<span data-ttu-id="18b2d-273">A [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) kimenet beolvasásához némileg eltérő implementáció szükséges.</span><span class="sxs-lookup"><span data-stu-id="18b2d-273">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="18b2d-274">Először is, ahelyett, hogy egy `using` utasítással (például a következővel) változóként kívánja létrehozni őket `QuantumSimulator` , az osztály objektumainak közvetlen létrehozását</span><span class="sxs-lookup"><span data-stu-id="18b2d-274">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="18b2d-275">Figyelje meg, hogy a több művelet által használt egyetlen cél szimulátor helyett :::no-loc(Q#)::: mindegyikhez létrehozunk egyet.</span><span class="sxs-lookup"><span data-stu-id="18b2d-275">Notice that instead of a single target simulator to be used by multiple :::no-loc(Q#)::: operations, we have instantiated one for each.</span></span> <span data-ttu-id="18b2d-276">Ennek az az oka, hogy maga az objektum is módosul, ha célként használt gépekként használják őket, és ezek eredményeit később a Class metódussal lehet lekérni `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-276">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="18b2d-277">A műveleteknek az erőforrás-becslések való futtatásához használjuk a következőt</span><span class="sxs-lookup"><span data-stu-id="18b2d-277">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="18b2d-278">majd az eredményeket tabulátorral elválasztott értékként (TSV) a és a karakterrel kell beolvasni `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-278">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="18b2d-279">Tehát a teljes C# gazda program mind a, mind a `QuantumSimulator` formáját a `ResourcesEstimator` következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="18b2d-279">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="18b2d-280">amely a következőhöz hasonló kimenetet eredményezhet</span><span class="sxs-lookup"><span data-stu-id="18b2d-280">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="18b2d-281">:::no-loc(Q#)::: Jupyter notebookok</span><span class="sxs-lookup"><span data-stu-id="18b2d-281">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
<span data-ttu-id="18b2d-282">:::no-loc(Q#)::: A Jupyter notebookok az I :::no-loc(Q#)::: kernelt használják, amely lehetővé teszi az callables egyetlen jegyzetfüzetben való definiálását, fordítását és futtatását :::no-loc(Q#)::: ---az összes útmutató, Megjegyzés és egyéb tartalom mellett.</span><span class="sxs-lookup"><span data-stu-id="18b2d-282">:::no-loc(Q#)::: Jupyter Notebooks make use of the I:::no-loc(Q#)::: kernel, which allows you to define, compile, and run :::no-loc(Q#)::: callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="18b2d-283">Ez azt jelenti, hogy habár lehetséges a fájlok importálása és használata `*.qs` :::no-loc(Q#)::: , nem szükségesek a futtatási modellben.</span><span class="sxs-lookup"><span data-stu-id="18b2d-283">This means that while it is possible to import and use the contents of `*.qs` :::no-loc(Q#)::: files, they are not necessary in the run model.</span></span>

<span data-ttu-id="18b2d-284">Itt részletesen ismertetjük, hogyan futtatjuk a :::no-loc(Q#)::: fent meghatározott műveleteket, de a Jupyter notebookok használatának szélesebb körű bemutatása a :::no-loc(Q#)::: [notebookok bevezetője :::no-loc(Q#)::: és Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="18b2d-284">Here, we will detail how to run the :::no-loc(Q#)::: operations defined above, but a more broad introduction to using :::no-loc(Q#)::: Jupyter Notebooks is provided at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="18b2d-285">Műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="18b2d-285">Defining operations</span></span>

<span data-ttu-id="18b2d-286">Egy :::no-loc(Q#)::: Jupyter notebook a kódot ugyanúgy kell megadnia, :::no-loc(Q#)::: mint egy fájl névterében :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-286">In a :::no-loc(Q#)::: Jupyter Notebook, you enter :::no-loc(Q#)::: code just as we would from inside the namespace of a :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="18b2d-287">Így lehetővé tehetjük a callables való hozzáférést a [ :::no-loc(Q#)::: szabványos könyvtárakból](xref:microsoft.quantum.qsharplibintro) a `open` megfelelő névterekhez tartozó utasításokkal.</span><span class="sxs-lookup"><span data-stu-id="18b2d-287">So, we can enable access to callables from the [:::no-loc(Q#)::: standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="18b2d-288">Ha egy cellát egy ilyen utasítással futtat, a névterek definíciói a munkaterület teljes területén elérhetők.</span><span class="sxs-lookup"><span data-stu-id="18b2d-288">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="18b2d-289">A [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic) és a [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (például [`H`](xref:Microsoft.Quantum.Intrinsic.H) és) Callables [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) automatikusan elérhetők a Jupyter-jegyzetfüzetekben lévő cellákban definiált műveletekhez :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="18b2d-289">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in :::no-loc(Q#)::: Jupyter Notebooks.</span></span>
> <span data-ttu-id="18b2d-290">Ez azonban nem igaz a külső forrásfájlok által bevitt kód esetében :::no-loc(Q#)::: (a [jegyzetfüzetek bevezetője :::no-loc(Q#)::: és Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)között látható folyamat).</span><span class="sxs-lookup"><span data-stu-id="18b2d-290">However, this is not true for code brought in from external :::no-loc(Q#)::: source files (a process shown at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="18b2d-291">Hasonlóképpen, a definiált műveletekhez csak a :::no-loc(Q#)::: kód írása és a cella futtatása szükséges.</span><span class="sxs-lookup"><span data-stu-id="18b2d-291">Similarly, defining operations requires only writing the :::no-loc(Q#)::: code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining :::no-loc(Q#)::: operations" width="773">

<span data-ttu-id="18b2d-292">A kimenet ezután felsorolja ezeket a műveleteket, amelyek ezután meghívhatók a jövőbeli cellákból.</span><span class="sxs-lookup"><span data-stu-id="18b2d-292">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="18b2d-293">Célgépek</span><span class="sxs-lookup"><span data-stu-id="18b2d-293">Target machines</span></span>

<span data-ttu-id="18b2d-294">Az adott célszámítógépeken futó műveletek futtatásának funkciói az [I :::no-loc(Q#)::: Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp)segítségével érhetők el.</span><span class="sxs-lookup"><span data-stu-id="18b2d-294">The functionality to run operations on specific target machines is provided via [I:::no-loc(Q#)::: Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="18b2d-295">Például a a (z) `%simulate` `QuantumSimulator` és a következőt `%estimate` használja `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="18b2d-295">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="18b2d-296">Bemenetek átadása a függvényeknek és műveleteknek</span><span class="sxs-lookup"><span data-stu-id="18b2d-296">Passing inputs to functions and operations</span></span>

<span data-ttu-id="18b2d-297">Ha át szeretné adni a bemeneteket a :::no-loc(Q#)::: műveletekhez, az argumentumok a `key=value` Run Magic parancsba párokként adhatók át.</span><span class="sxs-lookup"><span data-stu-id="18b2d-297">To pass inputs to the :::no-loc(Q#)::: operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="18b2d-298">Tehát a következő `MeasureSuperpositionArray` négy qubits futtatható `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="18b2d-298">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation with arguments" width="773">

<span data-ttu-id="18b2d-299">Ez a minta hasonlóan használható a `%estimate` és más futtatási parancsokhoz is.</span><span class="sxs-lookup"><span data-stu-id="18b2d-299">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="18b2d-300">:::no-loc(Q#):::Kód használata más projektekről vagy csomagokból</span><span class="sxs-lookup"><span data-stu-id="18b2d-300">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="18b2d-301">Alapértelmezés szerint a :::no-loc(Q#)::: Jupyter notebook betölti az `.qs` aktuális mappában található összes fájlt, és a :::no-loc(Q#)::: műveleteit és funkcióit elérhetővé teszi a notebookon belülről való használatra.</span><span class="sxs-lookup"><span data-stu-id="18b2d-301">By default, a :::no-loc(Q#)::: Jupyter Notebook loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="18b2d-302">A [ `%who` Magic parancs](xref:microsoft.quantum.iqsharp.magic-ref.who) felsorolja az összes jelenleg elérhető :::no-loc(Q#)::: műveletet és funkciót.</span><span class="sxs-lookup"><span data-stu-id="18b2d-302">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available :::no-loc(Q#)::: operations and functions.</span></span>

<span data-ttu-id="18b2d-303">:::no-loc(Q#):::A kód egy másik mappából való betöltéséhez használhatja a [ `%project` Magic parancsot](xref:microsoft.quantum.iqsharp.magic-ref.project) a `.csproj` projekthez tartozó fájlra mutató hivatkozás hozzáadásához :::no-loc(Q#)::: (azaz a projekt, amely hivatkozik `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="18b2d-303">To load :::no-loc(Q#)::: code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="18b2d-304">Ez a parancs lefordítja a `.qs` `.csproj` (és almappákat) tartalmazó mappában található összes fájlt.</span><span class="sxs-lookup"><span data-stu-id="18b2d-304">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="18b2d-305">Emellett rekurzív módon betölti az `PackageReference` adott fájlban hivatkozott vagy projekteken keresztül hivatkozott csomagokat is :::no-loc(Q#)::: `ProjectReference` `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-305">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="18b2d-306">A következő cellák például egy :::no-loc(Q#)::: külső projektből származó műveletet szimulálnak, ahol a projekt elérési útja az aktuális mappához képest hivatkozik:</span><span class="sxs-lookup"><span data-stu-id="18b2d-306">As an example, the following cells simulate a :::no-loc(Q#)::: operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation from an external project" width="773">

<span data-ttu-id="18b2d-307">A kódot tartalmazó külső csomagok betöltéséhez :::no-loc(Q#)::: használja a [ `%package` Magic parancsot](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="18b2d-307">To load external packages containing :::no-loc(Q#)::: code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="18b2d-308">A csomagok betöltése a csomag részét képező szerelvényekben található bármely egyéni mágikus parancsot vagy kódolókat is elérhetővé tesz.</span><span class="sxs-lookup"><span data-stu-id="18b2d-308">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="18b2d-309">Ha külső csomagokat vagy projekteket szeretne betölteni a :::no-loc(Q#)::: Jegyzetfüzet intialization, győződjön meg arról, hogy a notebook mappa tartalmaz egy `.csproj` hivatkozást tartalmazó fájlt `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-309">To load external packages or :::no-loc(Q#)::: projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="18b2d-310">A ben `.csproj` adja hozzá a tulajdonságot a következőhöz: `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="18b2d-310">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="18b2d-311">Ez :::no-loc(Q#)::: arra utasítja a rendszer, hogy rekurzív módon töltse be a `ProjectReference` `PackageReference` `.csproj` Jegyzetfüzet betöltési idején található bármely vagy elemeket.</span><span class="sxs-lookup"><span data-stu-id="18b2d-311">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="18b2d-312">Íme például egy egyszerű `.csproj` fájl, amely a :::no-loc(Q#)::: csomag automatikus betöltését okozza `Microsoft.Quantum.Chemistry` :</span><span class="sxs-lookup"><span data-stu-id="18b2d-312">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

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
> <span data-ttu-id="18b2d-313">Jelenleg ezt az egyéni `<IQSharpLoadAutomatically>` tulajdonságot :::no-loc(Q#)::: Jupyter notebook gazdagépek igénylik, de a jövőben ez lehet egy, a `.csproj` Jegyzetfüzet-fájllal azonos mappában található fájl alapértelmezett viselkedése.</span><span class="sxs-lookup"><span data-stu-id="18b2d-313">Currently this custom `<IQSharpLoadAutomatically>` property is required by :::no-loc(Q#)::: Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="18b2d-314">Jelenleg a `<QsharpCompile>` `.csproj` Jupyter notebook gazdagépek figyelmen kívül hagyják a beállítást :::no-loc(Q#)::: , és a `.qs` mappában található összes fájl `.csproj` (beleértve az almappákat is) be van töltve és le van fordítva.</span><span class="sxs-lookup"><span data-stu-id="18b2d-314">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by :::no-loc(Q#)::: Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="18b2d-315">`.csproj`A beállítások támogatása a jövőben is javulni fog (további részletekért lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="18b2d-315">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
