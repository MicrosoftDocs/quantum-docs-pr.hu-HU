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
# <a name="quantum-simulators-and-host-applications"></a>Kvantumszimulátorok és gazdaalkalmazások

## <a name="what-youll-learn"></a>Ismertetett témák

> [!div class="checklist"]
> * A kvantumalgoritmusok végrehajtásának módja
> * A jelenlegi kiadás részét képező kvantumszimulátorok
> * C#-illesztő írása a kvantumalgoritmushoz

## <a name="the-quantum-development-kit-execution-model"></a>A Quantum Development Kit végrehajtási modellje

A [kvantumprogram írásával](xref:microsoft.quantum.write-program) foglalkozó részben végrehajtottuk a kvantumalgoritmust úgy, hogy átadtunk egy `QuantumSimulator` objektumot az algoritmusosztály `Run` metódusához.
A `QuantumSimulator` osztály végrehajtja a kvantumalgoritmust a kvantumállapot-vektorok teljes szimulálásával, ami tökéletes a `Teleport` futtatásához és teszteléséhez.
A kvantumállapot-vektorokról további információt az [alapfogalmak útmutatójában](xref:microsoft.quantum.concepts.intro) talál.

Egyéb célgépek is használhatók a kvantumalgoritmusok futtatására.
A gép a felelős a kvantumprimitívek implementálásáért az algoritmushoz.
Ezekbe beletartoznak olyan primitív műveletek, mint a H, a CNOT és a Mérték, továbbá a qubitek kezelése és nyomkövetése.
A kvantumgépek különböző osztályai ugyanazon kvantumalgoritmus különböző végrehajtási modelljeit képviselik.

Minden egyes kvantumgéptípus a primitívek más-más implementációját biztosíthatja.
A kvantumszámítógép fejlesztői csomag részét képező nyomkövetési szimulátora például nem hajt végre semmilyen szimulációt,
hanem az algoritmus kapu-, qubit- és egyéb erőforrás-felhasználását követi nyomon.

### <a name="quantum-machines"></a>Kvantumgépek

A jövőben további kvantumgéposztályokat fogunk meghatározni további szimulációtípusok és a topológiai kvantumszámítógépeken történő végrehajtás támogatása érdekében.
Ha az algoritmus számára lehetővé tesszük, hogy változatlan maradjon, miközben a mögöttes gépimplementáció módosul, az megkönnyíti az algoritmusok tesztelését és hibakeresését egy szimulációban, majd futtatásukat valódi hardveren, miközben biztos lehet benne, hogy az algoritmusok nem változtak.

### <a name="whats-included-in-this-release"></a>A kiadás tartalma

A kvantumfejlesztő készlet ezen kiadása több kvantumgéposztályt tartalmaz.
Mindegyik meg van határozva a `Microsoft.Quantum.Simulation.Simulators` névtérben.

* Egy [teljes körű funkciókkal rendelkező vektorszimulátor](xref:microsoft.quantum.machines.full-state-simulator), a `QuantumSimulator` osztály.
* Egy [egyszerű erőforrás-kalkulátor](xref:microsoft.quantum.machines.resources-estimator), a `ResourcesEstimator` osztály, ami lehetővé teszi a kvantumalgoritmusok futtatásához szükséges erőforrások átfogó elemzését.
* Egy [nyomkövetés-alapú erőforrás-kalkulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro), a `QCTraceSimulator` osztály, ami lehetővé teszi az algoritmus teljes hívási gráfjának erőforrás-felhasználási elemzését.
* Egy [Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator), a `ToffoliSimulator` osztály.

## <a name="writing-a-host-application"></a>Gazdaalkalmazás írása

A [kvantumprogram írásával](xref:microsoft.quantum.write-program) foglalkozó részben egy egyszerű C#-illesztőt írtunk a teleportációs algoritmushoz. A C#-illesztőnek 4 fő célja van:

* A célgép létrehozása
* A kvantumalgoritmushoz szükséges összes argumentum kiszámítása
* A kvantumalgoritmus futtatása a szimulátorral
* A művelet eredményének feldolgozása

Tárgyaljuk meg részletesebben az egyes lépéseket.

### <a name="constructing-the-target-machine"></a>A célgép létrehozása

A kvantumgépek normál .NET-osztályok példányai, így a .NET-osztályokhoz hasonlóan a konstruktoruk meghívásával jönnek létre.
Egyes szimulátorok, mint például a `QuantumSimulator`, implementálják a .NET <xref:System.IDisposable?displayProperty=nameWithType> felületet, ezért be kell őket ágyazni egy C# `using` utasításba.

### <a name="computing-arguments-for-the-algorithm"></a>Számítási argumentumok az algoritmushoz

A `Teleport` példában néhány viszonylag mesterséges argumentumot számítottunk ki, amelyet átadtunk a kvantumalgoritmusnak.
Jellemzőbb azonban, hogy a kvantumalgoritmusnak jelentős mennyiségű adatra van szüksége, és ezt legegyszerűbben klasszikus illesztőkkel biztosíthatjuk.

Ha például vegyészeti szimulációkat végez, a kvantumalgoritmusnak molekuláris orbitális interakciós integrálok nagy táblázatára van szüksége.
Ezek általában az algoritmus futtatásakor megadott fájlból kerülnek beolvasásra.
Mivel a Q# nem rendelkezik a fájlrendszer elérését szolgáló mechanizmussal, az a legjobb, ha az ilyen típusú adatokat egy klasszikus illesztő gyűjti, majd átadja a kvantumalgoritmus `Run` metódusának.

Egy másik eset, ahol a klasszikus illesztő kulcsfontosságú szerepet tölt be, a variációs metódusoké.
Az algoritmusok ezen osztályában a kvantumállapot bizonyos klasszikus paraméterek alapján áll össze, és ezt az állapotot használják néhány, az érdeklődésre számot tartó érték kiszámításához.
A paramétereket a rendszer valamilyen típusú hegymászó keresési vagy gépi tanulási algoritmus és az újrafuttatott kvantumalgoritmus alapján módosítja.
Ilyen algoritmusok esetén az a legjobb, ha önmagában a hegymászó keresési algoritmust tisztán klasszikus függvényként implementáljuk, amit a klasszikus illesztő hív meg. A hegymászó jellegű keresés eredményeit a rendszer továbbadja a kvantumalgoritmus következő végrehajtásának.

### <a name="running-the-quantum-algorithm"></a>A kvantumalgoritmus futtatása

Ez a rész általában eléggé magától értetődő.
Minden Q#-művelet egy olyan osztályba sorolódik be, ami egy statikus `Run` metódust biztosít.
A metódushoz az argumentumokat a művelet összevont argumentumrekordja adja meg, valamint azt az argumentumot is megadja, amelyet a szimulátor elsőnek hajt végre. Egy olyan műveletnek, amely az `(a: String, (b: Double, c: Double))` típusú nevesített rekordot várja, az összevont párja `(String a, Double b, Double c)` típusú.


Néhány részlet a `Run` metódusnak átadott argumentumokkal kapcsolatban:

* A tömböket `Microsoft.Quantum.Simulation.Core.QArray<T>` objektumba kell ágyazni.
    Egy `QArray` osztály olyan konstruktorral rendelkezik, amely a megfelelő objektumok bármely rendezett gyűjteményét (`IEnumerable<T>`) képes használni.
* A Q#-ban az üres rekordot a `()`, a C#-ben a `QVoid.Instance` jelzi.
* A nem üres rekordok .NET `ValueTuple` példányokként jelennek meg.
* A Q# felhasználó által definiált típusai az alaptípusaikként lesznek átadva.
* Egy művelet vagy függvény `Run` metódusba való átadásához be kell szereznie a művelet vagy függvény osztályának egy példányát a szimulátor `Get<>` metódusával.

### <a name="processing-the-results"></a>Eredmények feldolgozása

A kvantumalgoritmus eredményeit a `Run` metódus adja vissza.
A `Run` metódus aszinkron módon megy végbe, így a <xref:System.Threading.Tasks.Task`1> egy példányát eredményezi.
Több lehetőség is van, hogy megkapjuk a művelet tényleges eredményeit. A legegyszerűbb a `Task`[`Result` tulajdonságának használata](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
de más technikák, például a [`Wait` metódus](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) vagy a C# [`await` kulcsszó](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) is rendelkezésre állnak.

Az argumentumokhoz hasonlóan a Q#-rekordok `ValueTuple` példányként, a Q#-tömbök pedig `QArray` példányként jelennek meg.
A felhasználó által definiált típusok az alaptípusaikként lesznek visszaadva.
Az üres `()` rekordot a rendszer a `QVoid` osztály egy példányaként adja vissza.

Számos kvantumalgoritmus jelentős utófeldolgozást igényel, hogy hasznos válaszokat lehessen kinyerni.
Shor algoritmusának kvantumrésze például csak egy adott szám együtthatóit megkereső számítás első lépése.

A legtöbb esetben az a legegyszerűbb és legkönnyebb, ha ezt a fajta utófeldolgozást a klasszikus illesztőben végzi el.
Csak a klasszikus illesztő tudja jelenteni az eredményeket a felhasználónak, vagy kiírni azokat egy lemezre.
A klasszikus illesztő hozzáfér az analitikai kódtárakhoz és más, a Q#-ban nem elérhető matematikai függvényekhez.


## <a name="failures"></a>Hibák

Ha a rendszer eléri a Q# `fail` utasítást egy művelet végrehajtása közben, `ExecutionFailException` kivételt ad vissza.

A `Run` metódus `System.Task` használata miatt, a `fail` utasítás eredményeként kapott kivétel egy `System.AggregateException` kivételbe lesz csomagolva.
Annak érdekében, hogy megtalálja a hiba pontos okát, iterálnia kell a `AggregateException` 
`InnerExceptions` elembe, például:

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

## <a name="other-classical-languages"></a>További klasszikus nyelvek

Míg a megadott minták a C#, az F# és a Python nyelvet használják, a Quantum Development Kit a klasszikus gazdaprogramok írását más nyelveken is támogatja.
Ha például Visual Basicben szeretne egy gazdaprogramot írni, [minden további nélkül megteheti](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
