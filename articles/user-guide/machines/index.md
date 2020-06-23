---
title: Kvantumszimulátorok és gazdaalkalmazások | Microsoft Docs
description: Annak az ismertetése, hogyan lehet a kvantumszimulátorokat klasszikus számítástechnikai .NET nyelvvel (jellemzően C#-vel vagy Q#-val) vezérelni.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273526"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="fc757-103">Kvantumszimulátorok és gazdaalkalmazások</span><span class="sxs-lookup"><span data-stu-id="fc757-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="fc757-104">Ismertetett témák</span><span class="sxs-lookup"><span data-stu-id="fc757-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fc757-105">A kvantumalgoritmusok végrehajtásának módja</span><span class="sxs-lookup"><span data-stu-id="fc757-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="fc757-106">A jelenlegi kiadás részét képező kvantumszimulátorok</span><span class="sxs-lookup"><span data-stu-id="fc757-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="fc757-107">C#-illesztő írása a kvantumalgoritmushoz</span><span class="sxs-lookup"><span data-stu-id="fc757-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="fc757-108">A Quantum Development Kit végrehajtási modellje</span><span class="sxs-lookup"><span data-stu-id="fc757-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="fc757-109">A [kvantumprogram írásával](xref:microsoft.quantum.write-program) foglalkozó részben végrehajtottuk a kvantumalgoritmust úgy, hogy átadtunk egy `QuantumSimulator` objektumot az algoritmusosztály `Run` metódusához.</span><span class="sxs-lookup"><span data-stu-id="fc757-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="fc757-110">A `QuantumSimulator` osztály végrehajtja a kvantumalgoritmust a kvantumállapot-vektorok teljes szimulálásával, ami tökéletes a `Teleport` futtatásához és teszteléséhez.</span><span class="sxs-lookup"><span data-stu-id="fc757-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="fc757-111">A kvantumállapot-vektorokról további információt az [alapfogalmak útmutatójában](xref:microsoft.quantum.concepts.intro) talál.</span><span class="sxs-lookup"><span data-stu-id="fc757-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="fc757-112">Egyéb célgépek is használhatók a kvantumalgoritmusok futtatására.</span><span class="sxs-lookup"><span data-stu-id="fc757-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="fc757-113">A gép a felelős a kvantumprimitívek implementálásáért az algoritmushoz.</span><span class="sxs-lookup"><span data-stu-id="fc757-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="fc757-114">Ezekbe beletartoznak olyan primitív műveletek, mint a H, a CNOT és a Mérték, továbbá a qubitek kezelése és nyomkövetése.</span><span class="sxs-lookup"><span data-stu-id="fc757-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="fc757-115">A kvantumgépek különböző osztályai ugyanazon kvantumalgoritmus különböző végrehajtási modelljeit képviselik.</span><span class="sxs-lookup"><span data-stu-id="fc757-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="fc757-116">Minden egyes kvantumgéptípus a primitívek más-más implementációját biztosíthatja.</span><span class="sxs-lookup"><span data-stu-id="fc757-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="fc757-117">A kvantumszámítógép fejlesztői csomag részét képező nyomkövetési szimulátora például nem hajt végre semmilyen szimulációt,</span><span class="sxs-lookup"><span data-stu-id="fc757-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="fc757-118">hanem az algoritmus kapu-, qubit- és egyéb erőforrás-felhasználását követi nyomon.</span><span class="sxs-lookup"><span data-stu-id="fc757-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="fc757-119">Kvantumgépek</span><span class="sxs-lookup"><span data-stu-id="fc757-119">Quantum Machines</span></span>

<span data-ttu-id="fc757-120">A jövőben további kvantumgéposztályokat fogunk meghatározni további szimulációtípusok és a topológiai kvantumszámítógépeken történő végrehajtás támogatása érdekében.</span><span class="sxs-lookup"><span data-stu-id="fc757-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="fc757-121">Ha az algoritmus számára lehetővé tesszük, hogy változatlan maradjon, miközben a mögöttes gépimplementáció módosul, az megkönnyíti az algoritmusok tesztelését és hibakeresését egy szimulációban, majd futtatásukat valódi hardveren, miközben biztos lehet benne, hogy az algoritmusok nem változtak.</span><span class="sxs-lookup"><span data-stu-id="fc757-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="fc757-122">A kiadás tartalma</span><span class="sxs-lookup"><span data-stu-id="fc757-122">What's Included in this Release</span></span>

<span data-ttu-id="fc757-123">A kvantumfejlesztő készlet ezen kiadása több kvantumgéposztályt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="fc757-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="fc757-124">Mindegyik meg van határozva a `Microsoft.Quantum.Simulation.Simulators` névtérben.</span><span class="sxs-lookup"><span data-stu-id="fc757-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="fc757-125">Egy [teljes körű funkciókkal rendelkező vektorszimulátor](xref:microsoft.quantum.machines.full-state-simulator), a `QuantumSimulator` osztály.</span><span class="sxs-lookup"><span data-stu-id="fc757-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="fc757-126">Egy [egyszerű erőforrás-kalkulátor](xref:microsoft.quantum.machines.resources-estimator), a `ResourcesEstimator` osztály, ami lehetővé teszi a kvantumalgoritmusok futtatásához szükséges erőforrások átfogó elemzését.</span><span class="sxs-lookup"><span data-stu-id="fc757-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="fc757-127">Egy [nyomkövetés-alapú erőforrás-kalkulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro), a `QCTraceSimulator` osztály, ami lehetővé teszi az algoritmus teljes hívási gráfjának erőforrás-felhasználási elemzését.</span><span class="sxs-lookup"><span data-stu-id="fc757-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="fc757-128">Egy [Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator), a `ToffoliSimulator` osztály.</span><span class="sxs-lookup"><span data-stu-id="fc757-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="fc757-129">Gazdaalkalmazás írása</span><span class="sxs-lookup"><span data-stu-id="fc757-129">Writing a host application</span></span>

<span data-ttu-id="fc757-130">A [kvantumprogram írásával](xref:microsoft.quantum.write-program) foglalkozó részben egy egyszerű C#-illesztőt írtunk a teleportációs algoritmushoz.</span><span class="sxs-lookup"><span data-stu-id="fc757-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="fc757-131">A C#-illesztőnek 4 fő célja van:</span><span class="sxs-lookup"><span data-stu-id="fc757-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="fc757-132">A célgép létrehozása</span><span class="sxs-lookup"><span data-stu-id="fc757-132">Constructing the target machine</span></span>
* <span data-ttu-id="fc757-133">A kvantumalgoritmushoz szükséges összes argumentum kiszámítása</span><span class="sxs-lookup"><span data-stu-id="fc757-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="fc757-134">A kvantumalgoritmus futtatása a szimulátorral</span><span class="sxs-lookup"><span data-stu-id="fc757-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="fc757-135">A művelet eredményének feldolgozása</span><span class="sxs-lookup"><span data-stu-id="fc757-135">Processing the result of the operation</span></span>

<span data-ttu-id="fc757-136">Tárgyaljuk meg részletesebben az egyes lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fc757-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="fc757-137">A célgép létrehozása</span><span class="sxs-lookup"><span data-stu-id="fc757-137">Constructing the Target Machine</span></span>

<span data-ttu-id="fc757-138">A kvantumgépek normál .NET-osztályok példányai, így a .NET-osztályokhoz hasonlóan a konstruktoruk meghívásával jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="fc757-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="fc757-139">Egyes szimulátorok, mint például a `QuantumSimulator`, implementálják a .NET <xref:System.IDisposable?displayProperty=nameWithType> felületet, ezért be kell őket ágyazni egy C# `using` utasításba.</span><span class="sxs-lookup"><span data-stu-id="fc757-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="fc757-140">Számítási argumentumok az algoritmushoz</span><span class="sxs-lookup"><span data-stu-id="fc757-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="fc757-141">A `Teleport` példában néhány viszonylag mesterséges argumentumot számítottunk ki, amelyet átadtunk a kvantumalgoritmusnak.</span><span class="sxs-lookup"><span data-stu-id="fc757-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="fc757-142">Jellemzőbb azonban, hogy a kvantumalgoritmusnak jelentős mennyiségű adatra van szüksége, és ezt legegyszerűbben klasszikus illesztőkkel biztosíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="fc757-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="fc757-143">Ha például vegyészeti szimulációkat végez, a kvantumalgoritmusnak molekuláris orbitális interakciós integrálok nagy táblázatára van szüksége.</span><span class="sxs-lookup"><span data-stu-id="fc757-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="fc757-144">Ezek általában az algoritmus futtatásakor megadott fájlból kerülnek beolvasásra.</span><span class="sxs-lookup"><span data-stu-id="fc757-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="fc757-145">Mivel a Q# nem rendelkezik a fájlrendszer elérését szolgáló mechanizmussal, az a legjobb, ha az ilyen típusú adatokat egy klasszikus illesztő gyűjti, majd átadja a kvantumalgoritmus `Run` metódusának.</span><span class="sxs-lookup"><span data-stu-id="fc757-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="fc757-146">Egy másik eset, ahol a klasszikus illesztő kulcsfontosságú szerepet tölt be, a variációs metódusoké.</span><span class="sxs-lookup"><span data-stu-id="fc757-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="fc757-147">Az algoritmusok ezen osztályában a kvantumállapot bizonyos klasszikus paraméterek alapján áll össze, és ezt az állapotot használják néhány, az érdeklődésre számot tartó érték kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="fc757-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="fc757-148">A paramétereket a rendszer valamilyen típusú hegymászó keresési vagy gépi tanulási algoritmus és az újrafuttatott kvantumalgoritmus alapján módosítja.</span><span class="sxs-lookup"><span data-stu-id="fc757-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="fc757-149">Ilyen algoritmusok esetén az a legjobb, ha önmagában a hegymászó keresési algoritmust tisztán klasszikus függvényként implementáljuk, amit a klasszikus illesztő hív meg. A hegymászó jellegű keresés eredményeit a rendszer továbbadja a kvantumalgoritmus következő végrehajtásának.</span><span class="sxs-lookup"><span data-stu-id="fc757-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="fc757-150">A kvantumalgoritmus futtatása</span><span class="sxs-lookup"><span data-stu-id="fc757-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="fc757-151">Ez a rész általában eléggé magától értetődő.</span><span class="sxs-lookup"><span data-stu-id="fc757-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="fc757-152">Minden Q#-művelet egy olyan osztályba sorolódik be, ami egy statikus `Run` metódust biztosít.</span><span class="sxs-lookup"><span data-stu-id="fc757-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="fc757-153">A metódushoz az argumentumokat a művelet összevont argumentumrekordja adja meg, valamint azt az argumentumot is megadja, amelyet a szimulátor elsőnek hajt végre.</span><span class="sxs-lookup"><span data-stu-id="fc757-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="fc757-154">Egy olyan műveletnek, amely az `(a: String, (b: Double, c: Double))` típusú nevesített rekordot várja, az összevont párja `(String a, Double b, Double c)` típusú.</span><span class="sxs-lookup"><span data-stu-id="fc757-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="fc757-155">Néhány részlet a `Run` metódusnak átadott argumentumokkal kapcsolatban:</span><span class="sxs-lookup"><span data-stu-id="fc757-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="fc757-156">A tömböket `Microsoft.Quantum.Simulation.Core.QArray<T>` objektumba kell ágyazni.</span><span class="sxs-lookup"><span data-stu-id="fc757-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="fc757-157">Egy `QArray` osztály olyan konstruktorral rendelkezik, amely a megfelelő objektumok bármely rendezett gyűjteményét (`IEnumerable<T>`) képes használni.</span><span class="sxs-lookup"><span data-stu-id="fc757-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="fc757-158">A Q#-ban az üres rekordot a `()`, a C#-ben a `QVoid.Instance` jelzi.</span><span class="sxs-lookup"><span data-stu-id="fc757-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="fc757-159">A nem üres rekordok .NET `ValueTuple` példányokként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="fc757-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="fc757-160">A Q# felhasználó által definiált típusai az alaptípusaikként lesznek átadva.</span><span class="sxs-lookup"><span data-stu-id="fc757-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="fc757-161">Egy művelet vagy függvény `Run` metódusba való átadásához be kell szereznie a művelet vagy függvény osztályának egy példányát a szimulátor `Get<>` metódusával.</span><span class="sxs-lookup"><span data-stu-id="fc757-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="fc757-162">Eredmények feldolgozása</span><span class="sxs-lookup"><span data-stu-id="fc757-162">Processing the Results</span></span>

<span data-ttu-id="fc757-163">A kvantumalgoritmus eredményeit a `Run` metódus adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fc757-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="fc757-164">A `Run` metódus aszinkron módon megy végbe, így a <xref:System.Threading.Tasks.Task`1> egy példányát eredményezi.</span><span class="sxs-lookup"><span data-stu-id="fc757-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="fc757-165">Több lehetőség is van, hogy megkapjuk a művelet tényleges eredményeit.</span><span class="sxs-lookup"><span data-stu-id="fc757-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="fc757-166">A legegyszerűbb a `Task`[`Result` tulajdonságának használata](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span><span class="sxs-lookup"><span data-stu-id="fc757-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="fc757-167">de más technikák, például a [`Wait` metódus](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) vagy a C# [`await` kulcsszó](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) is rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="fc757-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="fc757-168">Az argumentumokhoz hasonlóan a Q#-rekordok `ValueTuple` példányként, a Q#-tömbök pedig `QArray` példányként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="fc757-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="fc757-169">A felhasználó által definiált típusok az alaptípusaikként lesznek visszaadva.</span><span class="sxs-lookup"><span data-stu-id="fc757-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="fc757-170">Az üres `()` rekordot a rendszer a `QVoid` osztály egy példányaként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fc757-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="fc757-171">Számos kvantumalgoritmus jelentős utófeldolgozást igényel, hogy hasznos válaszokat lehessen kinyerni.</span><span class="sxs-lookup"><span data-stu-id="fc757-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="fc757-172">Shor algoritmusának kvantumrésze például csak egy adott szám együtthatóit megkereső számítás első lépése.</span><span class="sxs-lookup"><span data-stu-id="fc757-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="fc757-173">A legtöbb esetben az a legegyszerűbb és legkönnyebb, ha ezt a fajta utófeldolgozást a klasszikus illesztőben végzi el.</span><span class="sxs-lookup"><span data-stu-id="fc757-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="fc757-174">Csak a klasszikus illesztő tudja jelenteni az eredményeket a felhasználónak, vagy kiírni azokat egy lemezre.</span><span class="sxs-lookup"><span data-stu-id="fc757-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="fc757-175">A klasszikus illesztő hozzáfér az analitikai kódtárakhoz és más, a Q#-ban nem elérhető matematikai függvényekhez.</span><span class="sxs-lookup"><span data-stu-id="fc757-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="fc757-176">Hibák</span><span class="sxs-lookup"><span data-stu-id="fc757-176">Failures</span></span>

<span data-ttu-id="fc757-177">Ha a rendszer eléri a Q# `fail` utasítást egy művelet végrehajtása közben, `ExecutionFailException` kivételt ad vissza.</span><span class="sxs-lookup"><span data-stu-id="fc757-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="fc757-178">A `Run` metódus `System.Task` használata miatt, a `fail` utasítás eredményeként kapott kivétel egy `System.AggregateException` kivételbe lesz csomagolva.</span><span class="sxs-lookup"><span data-stu-id="fc757-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="fc757-179">Annak érdekében, hogy megtalálja a hiba pontos okát, iterálnia kell a `AggregateException` 
`InnerExceptions` elembe, például:</span><span class="sxs-lookup"><span data-stu-id="fc757-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="fc757-180">További klasszikus nyelvek</span><span class="sxs-lookup"><span data-stu-id="fc757-180">Other Classical Languages</span></span>

<span data-ttu-id="fc757-181">Míg a megadott minták a C#, az F# és a Python nyelvet használják, a Quantum Development Kit a klasszikus gazdaprogramok írását más nyelveken is támogatja.</span><span class="sxs-lookup"><span data-stu-id="fc757-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="fc757-182">Ha például Visual Basicben szeretne egy gazdaprogramot írni, [minden további nélkül megteheti](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="fc757-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
