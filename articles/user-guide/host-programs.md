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
# <a name="ways-to-run-a-q-program"></a>Q # program futtatásának módjai

A Quantum Development Kit egyik legnagyobb erőssége a platformok és a fejlesztői környezetek rugalmassága.
Ez azonban azt is jelenti, hogy az új Q #-felhasználók a [telepítési útmutatóban](xref:microsoft.quantum.install)található számos lehetőség alapján megzavarják vagy elárasztják magukat.
Ezen az oldalon elmagyarázza, hogy mi történik a Q # program futtatásakor, és hasonlítsa össze a felhasználók által megtehető különböző módokat.

Az elsődleges különbség az, hogy a Q # futtatható:
- önálló alkalmazásként, ahol a Q # az egyetlen érintett nyelv, és a program közvetlenül hívja meg a programot. Két metódus valójában a következő kategóriába tartozik:
  - a parancssori felület
  - Q# nyelvű Jupyter-notebookok
- egy további, Pythonban vagy .NET nyelven írt (pl. C# vagy F #) *befogadó programmal*, amely ezután meghívja a programot, és folytatja a visszaadott eredmények feldolgozását.

Ha szeretné jobban megérteni ezeket a folyamatokat és azok különbségeit, tekintse meg az egyszerű Q # programot, és hasonlítsa össze a végrehajtható módszereket.

## <a name="basic-q-program"></a>Alapszintű Q # program

Egy alapszintű kvantum-program a qubit előállítását is magában foglalhatja az államok $ \ket $ és a $ \ket $ értékkel egyenlő arányban {0} {1} , a mérést és az eredményt visszaadva, amely a két, azonos valószínűséggel rendelkező állapot közül véletlenszerűen fog állni.
Ennek a folyamatnak a lényege a [Quantum Random Number Generator](xref:microsoft.quantum.quickstarts.qrng) rövid útmutatója.

A Q # esetében ezt a következő kód hajtja végre:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Ez a kód azonban önmagában nem hajtható végre a Q # használatával.
Ehhez egy [művelet](xref:microsoft.quantum.guide.basics#q-operations-and-functions)törzsét kell kiállítania, amely akkor kerül végrehajtásra, amikor a---vagy közvetlenül, vagy egy másik művelet hívja meg. Ezért a következő űrlapon is írhat egy műveletet:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Definiált egy műveletet, `MeasureSuperposition` amely nem vesz fel bemeneteket, és eredmény típusú értéket ad [Result](xref:microsoft.quantum.guide.types)vissza.

Habár az ezen a lapon szereplő példák csak a Q #- *műveletekből*állhatnak, az összes, a q # *függvényre*vonatkozó fogalmat is tárgyaljuk, ezért ezek együttesen *callables*. A különbségeket a [Q # alapjai: Operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions)(műveletek és függvények) ismertetik, és az ezek meghatározásával kapcsolatos további részleteket a [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions)szolgáltatásban találja.

### <a name="callable-defined-in-a-q-file"></a>Meghívható definiálva egy Q # fájlban

A meghívásos pontosan a meghívott és a Q # által futtatott.
Azonban ehhez több kiegészítésre van szükség, amely egy teljes `*.qs` Q # fájlból áll.

Az összes Q # típus és callables (az Ön által definiált és a nyelvhez tartozók) a *névterekben*vannak definiálva, amelyek minden olyan teljes nevet megadnak, amelyre hivatkozni lehet.

Például a és a [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) műveletek a és a [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) névterekben találhatók (a [Q # standard kódtárak](xref:microsoft.quantum.qsharplibintro)része).
Így mindig meghívhatják a *teljes* nevüket, de mindig megtehetik, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` hogy ez nagyon zsúfolt programkódot eredményez.

Ehelyett `open` az utasítások lehetővé teszik, hogy a callables tömör gyorsírással legyenek hivatkozva, ahogy a fenti műveleti törzsben tettük.
A művelethez tartozó teljes Q # fájl ezért a saját névtér definiálását jelenti, a callables a művelet által használt névterek megnyitásával, majd a művelettel:

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
> A névterek a megnyitásakor is *aliasként* használhatók, ami akkor lehet hasznos, ha a hívható/Type nevek két névtérben ütköznek.
> Tegyük fel például, hogy a `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` fentieket fogjuk használni, majd meghívjuk a- `H` on keresztül `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Ennek egyetlen kivétele a [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) névtér, amely mindig automatikusan megnyílik.
> Ezért a callables, mint a [`Length`](xref:microsoft.quantum.core.length) mindig közvetlenül használhatók.

### <a name="execution-on-target-machines"></a>Végrehajtás a célszámítógépen

Most a Q # program általános végrehajtási modellje világossá válik.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Először is a végrehajtáshoz megadott meghívásos hozzáférés minden más, ugyanabban a névtérben definiált callables és típushoz elérhető.
Emellett a [Q #-tárak](xref:microsoft.quantum.libraries)bármelyikéhez hozzáfér, de a teljes névvel vagy a `open` fent ismertetett utasítások használatával kell hivatkozni rájuk.

A meghívót a rendszer ezután a *[célszámítógépen](xref:microsoft.quantum.machines)* hajtja végre.
Ilyen célszámítógépek lehetnek a tényleges kvantum-hardverek vagy a QDK részeként elérhető több szimulátorok.
Erre a célra a leghasznosabb célszámítógép a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)egy példánya, `QuantumSimulator` amely úgy számítja ki a program viselkedését, mintha egy zaj nélküli kvantum-számítógépen hajtották végre.

Eddig azt is ismertetjük, hogy mi történik, ha egy adott Q # meghívót hajt végre.
Függetlenül attól, hogy a Q # egy önálló alkalmazásban vagy egy gazda programban van használatban, ez az általános folyamat több vagy kevesebb, mint a QDK rugalmassága---.
A kvantum-fejlesztési készletbe való hívás különböző módjai közötti különbségek így felfedik a Q # hívható hívásának *módját* , és hogy milyen módon adja vissza az eredményeket.
Pontosabban a különbségek körül forog 
1. annak jelzése, hogy melyik Q # hívható legyen végrehajtva.
2. a lehetséges hívható argumentumok megadása
3. annak a célszámítógépnek a meghatározása, amelyre a szolgáltatást végre szeretné hajtani, és
4. az eredmények visszaadása.

Először is megbeszéljük, hogy ez hogyan történik a Q # önálló alkalmazás parancssorból való használatával, majd folytassa a Python és a C# gazdagép-programok használatát.
Fenntartjuk a Q # Jupyter-jegyzetfüzetek önálló alkalmazását, mert az első háromtól eltérően az elsődleges funkció nem a helyi Q # fájl körébe kerül.

> [!NOTE]
> Habár nem mutatjuk be ezeket a példákat, a végrehajtási módszerek egyike az, hogy a Q # programon belülről kinyomtatott összes üzenet (például: [`Message`](xref:microsoft.quantum.intrinsic.message) vagy [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ) általában mindig a megfelelő konzolra lesz kinyomtatva.

## <a name="q-from-the-command-line"></a>Q # a parancssorból
A Q # programok írásához legkönnyebben elsajátíthatja az első lépéseket, hogy elkerülje a különálló fájlok és a második nyelv összetételét.
A Visual Studio Code vagy a Visual Studio és a QDK bővítmény használatával zökkenőmentes munkafolyamatot használhat, amelyben a Q # callables csak egyetlen Q # fájlból fut.

Ebben az esetben végső soron a program végrehajtásának meghívása a következővel:
```dotnetcli
dotnet run
```
a parancssorban.
A legegyszerűbb munkafolyamat az, amikor a terminál címtárának helye megegyezik a Q # fájllal, amely könnyen kezelhető a Q # fájl szerkesztése mellett az integrált terminál használatával a VS Code-ban, például:.
A [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) azonban számos lehetőséget is elfogad, és a program más helyről is futtatható, ha egyszerűen megadja a `--project <PATH>` Q # fájl helyét.


### <a name="add-entry-point-to-q-file"></a>Belépési pont hozzáadása a Q # fájlhoz

A legtöbb Q # fájl egynél több meghívót tartalmaz, ezért természetesen a fordítónak tudnia kell, hogy *melyik* meghívásos végrehajtásra van szükség a `dotnet run` parancs megadásakor.
Ez a Q # fájl egyszerű módosításával történik: 
    - Adjon hozzá egy sort, amely `@EntryPoint()` közvetlenül megelőzi a meghívót.

Ezért a fenti fájl a következő lesz:
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

Most pedig a `dotnet run` parancssorból érkező hívás `MeasureSuperposition` fut, és a visszaadott érték közvetlenül a terminálra lesz kinyomtatva.
Így a rendszer `One` vagy kinyomtatja a következőt: `Zero` . 

Vegye figyelembe, hogy nem számít, hogy ha több callables van definiálva, csak a `MeasureSuperposition` futtatásra kerül.
Emellett nem jelent problémát, ha a meghívó a nyilatkozata előtt is tartalmaz [dokumentációs megjegyzéseket](xref:microsoft.quantum.guide.filestructure#documentation-comments) , az `@EntryPoint()` attribútum egyszerűen elhelyezhető.

### <a name="callable-arguments"></a>Hívható argumentumok

Eddig csak olyan műveletet vettünk figyelembe, amely nem vesz fel bemeneteket.
Tegyük fel, hogy hasonló műveletet hajtottunk végre, de több qubits---az argumentumként megadott számú értéket.
Egy ilyen művelet a következőképpen írható
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
ahol a visszaadott érték a mérési eredmények tömbje.
Vegye figyelembe, hogy [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) [`ForEach`](xref:microsoft.quantum.arrays.foreach) a és [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) a [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) névterek esetében további `open` utasításokra van szükség mindegyikhez.

Ha az `@EntryPoint()` attribútumot az új művelet előtt helyezi át (vegye figyelembe, hogy egy fájlban csak egy ilyen sor lehet), és a futtatásának megkísérlése egyszerűen `dotnet run` olyan hibaüzenetet eredményez, amely azt jelzi, hogy milyen további parancssori kapcsolók szükségesek, és hogyan fejezheti ki őket.

A parancssor általános formátuma ténylegesen `dotnet run [options]` , a hívható argumentumok pedig itt vannak megadva.
Ebben az esetben az argumentum `n` hiányzik, és azt mutatja, hogy meg kell adnia a beállítást `-n <n>` . A qubits való futtatáshoz `MeasureSuperpositionArray` ezért használjuk a következőt: `n=4`

```dotnetcli
dotnet run -n 4
```

a következőhöz hasonló kimenetet eredményez

```output
[Zero,One,One,One]
```

Ez a tanfolyam több argumentumra is kiterjed.

> [!NOTE]
> A ben definiált argumentumok nevét `camelCase` a fordító a Q # bemenetként fogadja el kis mértékben. Például, ha `n` a helyett a fenti nevet használtuk `numQubits` , akkor ez a bemenet a parancssoron keresztül lesz megadva a `--num-qubits 4` helyett `-n 4` .

A hibaüzenet más lehetőségeket is tartalmaz, amelyek használhatók, beleértve a célszámítógép módosításának módját is.

### <a name="different-target-machines"></a>Különböző célszámítógépek

Mivel a műveleteik eredményei a tényleges qubits a várt eredmények voltak, egyértelmű, hogy a parancssorból az alapértelmezett célszámítógép a teljes állapotú quauntum szimulátor `QuantumSimulator` .
Azonban arra is utasíthatja a callables, hogy egy adott célszámítógépen fusson a `--simulator` (vagy a gyorsírással) lehetőséggel `-s` .

Futtathatja például a következőt [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

Ekkor a kinyomtatott kimenet

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

Az ezekkel a mérőszámokkal kapcsolatos részletekért lásd [: erőforrás-kalkulátor: a jelentett mérőszámok](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Parancssori végrehajtás összegzése
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Nem Q # `dotnet run` kapcsolók

Ahogy a fentiekben röviden említettük `--project` , a [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) a Q # hívható argumentumokhoz nem kapcsolódó beállításokat is elfogadja.
Ha mindkét típusú beállítást megadja, a `dotnet` -specifikus beállításokat elsőként kell megadni, majd egy elválasztó karakter `--` , majd a Q #-specifikus beállításokat.
Például a specifiying egy elérési utat a fenti művelethez tartozó qubits együtt hajthat végre `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Q # gazdagép-programokkal

A Q # fájllal együtt a művelet vagy a függvény közvetlenül a parancssorból való meghívására szolgáló alternatíva egy másik klasszikus nyelven *futtatott gazda program* használata. Pontosabban megteheti a Python vagy a .NET nyelv, például a C# vagy az F # kombinációját (a rövidség kedvéért csak a C# adatokat fogjuk részletezni).
Az együttműködési képesség engedélyezéséhez valamivel több beállítás szükséges, de ezek a részletek a [telepítési útmutatókban](xref:microsoft.quantum.install)találhatók.

Dióhéjban a helyzet most már tartalmaz egy gazda programfájlt (például `*.py` vagy `*.cs` ) a Q # fájllal megegyező helyen.
Most már a futtatott *gazda* program, a végrehajtásuk során pedig a q # fájl adott q # műveleteit és funkcióit hívhatja meg.
Az együttműködési képesség lényege a Q # fordítóprogramon alapul, amely a Q # fájl tartalmát elérhetővé teszi a gazda program számára, hogy azok meghívhatók legyenek.

A gazda program használatának egyik legfőbb előnye, hogy a Q # program által visszaadott klasszikus adatmennyiséget a gazdagép nyelvén lehet tovább feldolgozni.
Ez néhány speciális adatfeldolgozásból állhat (például a Q #-ban belsőleg nem hajtható végre), majd az eredmények alapján további Q # műveletek is meghívhatók, vagy a Q # találatok ábrázolásával.

Az általános séma itt látható, és megbeszéljük a Python és a C# adott implementációit alább. Az F # gazda programot használó minta a .net-es [együttműködési mintákon](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)érhető el.

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> A `@EntryPoint()` Q # parancssori alkalmazásokhoz használt attribútum nem használható gazda programokkal.
> Egy hiba akkor jelenik meg, ha a Q # fájlban szerepel a gazdagép által meghívva. 

A különböző gazdagép-programokkal való együttműködéshez nem szükséges módosítani a `*.qs` Q #-fájl módosításait.
A következő gazda program-implementációk mindegyike ugyanazzal a Q # fájllal működik:

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

Válassza ki a megfelelő gazdagép-nyelvhez tartozó fület.

### <a name="python"></a>[Python](#tab/tabid-python)
A Python-gazda program a következőképpen épül fel:
1. Importálja a modult `qsharp` , amely a Q # együttműködési képességhez regisztrálja a modul betöltőjét. 
    Ez lehetővé teszi, hogy a Q # névterek Python-modulokként jelenjenek meg, amelyekről "import" Q # callables lehet.
    Vegye figyelembe, hogy a Q # callables nem az importált, hanem a Python-Csonkok, amelyek lehetővé teszik a hívását.
    Ezek a Python-osztályok objektumaiként viselkednek, és a metódusok segítségével határozzák meg, hogy a rendszer hogyan küldje el a műveletet a művelet végrehajtásához.

2. Importálja a Q # callables, melyeket a rendszer közvetlenül meghív---ebben az esetben, `MeasureSuperposition` és `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Az `qsharp` importált modullal közvetlenül a Q # Library-névterekről is importálhatja a callables.

3. A többi Python-kód között mostantól meghívhatja ezeket a callables az adott célszámítógépeken, és hozzárendelheti azok változóhoz való visszatérését (ha értéket adnak vissza) a további használatra.

#### <a name="specifying-target-machines"></a>Megcélzott gépek meghatározása
Egy adott célszámítógépen futtatandó művelet meghívása az importált objektumon különböző Python-módszerekkel történik.
A (z `.simulate(<args>)` ) például a használatával `QuantumSimulator` futtatja a műveletet, míg `.estimate_resources(<args>)` a (z `ResourcesEstimator` ).

#### <a name="passing-inputs-to-q"></a>Bemenetek továbbítása a Q-ba\#
A Q # meghívható argumentumait kulcsszó típusú argumentum formájában kell megadni, ahol a kulcsszó az argumentum neve a Q # meghívható definíciójában.
Ez `MeasureSuperpositionArray.simulate(n=4)` érvényes, míg `MeasureSuperpositionArray.simulate(4)` hiba történt.

Ezért a Python-gazda program 

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

a következőhöz hasonló kimenetet eredményez:

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

A C# gazda program több összetevővel rendelkezik, és nagyon szorosan együttműködik a QDK egyes összetevőivel, például a szimulátorokkal, amelyek a C# nyelvre épülnek.

A Q # fordítóprogram egy egyenértékű, C# névtér létrehozásával működik a q # névtérben a q # fájlban.
Ezzel egyenértékű névvel ellátott C# osztályt hoz létre minden olyan Q # callables vagy típushoz, amelyet itt definiáltak.

Első lépésként a gazda programunkban használt osztályokat tesszük elérhetővé az `using` utasításokkal, amelyek nagyjából analagous a `open` Q # fájl utasításait:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Ezután deklaráljuk a C#-névteret, néhány más bitet és darabot (lásd az alábbi teljes kódrészletet), majd a klasszikus programozást (például a Q # callables tartozó számítási argumentumokat).
Az utóbbi nem szükséges az esetünkben, de az ilyen jellegű használatról a .net-es [együttműködési minta](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)tartalmaz példát.

#### <a name="target-machines"></a>Célgépek

A Q #-ra való visszalépéshez létre kell hoznia egy példányt a célszámítógépen, amelyről végrehajtjuk a műveletet.

```csharp
            using var sim = new QuantumSimulator();
```

Más célszámítógépek használata olyan egyszerű, mint egy másik példány létrehozása, bár ennek a módja, és a visszatérések feldolgozása némileg eltérő lehet.
A rövidség kedvéért most ragaszkodunk a [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) szolgáltatáshoz, és belefoglaljuk az [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [alábbiakat](#including-the-resources-estimator).

A Q # műveletekben létrehozott minden C# osztálynak van egy `Run` metódusa, amely az első argumentum, amelynek a célszámítógép-példánynak kell lennie.
Tehát a futtatásához `MeasureSuperposition` használjuk a következőt: `QuantumSimulator` `MeasureSuperposition.Run(sim)` .
A visszaadott eredmények ezután a C#-változókhoz rendelhetők:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> A `Run` metódus aszinkron módon van végrehajtva, mert ez a valódi kvantum-hardver esetében ez lesz, ezért a `await` kulcsszó a feladat befejezéséig blokkolja a további végrehajtást.

Ha a Q # hívható nem rendelkezik visszaadott értékkel (azaz visszatérési típussal `Unit` ), a végrehajtás továbbra is ugyanúgy végezhető el, amíg hozzá nem rendel egy változóhoz.
Ebben az esetben a teljes sor csupán a következő elemekből áll: 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argumentumok

A Q # meghívható összes argumentuma egyszerűen átadja a afer további argumentumként.
Így a qubits eredményei `MeasureSuperpositionArray` a `n=4` következőn keresztül lettek beolvasva 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

A teljes C# gazda program így néz ki:

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

A C#-fájl helyén a gazda program a parancssorból is futtatható. Ehhez írja be a következőt:
```dotnetcli
dotnet run
```
Ebben az esetben a-konzolra írt kimenetet a következőhöz hasonló módon fogja látni: 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> A fordítók névterekkel való együttműködése miatt előfordulhat, hogy a Q # callables az utasítás nélkül elérhetővé válik `using NamespaceName;` , és egyszerűen csak a C# névtér címére lesz kiválasztva.
> Ez azt helyettesíti, hogy `namespace host` `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Beleértve a források becslését

A [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) kimenet beolvasásához némileg eltérő implementáció szükséges.

Először is, ahelyett, hogy egy `using` utasítással (például a következővel) változóként kívánja létrehozni őket `QuantumSimulator` , az osztály objektumainak közvetlen létrehozását

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Figyelje meg, hogy egy cél-szimulátor helyett több Q # művelet is használható, mindegyikhez létrehozunk egyet. Ennek az az oka, hogy maga az objektum is módosul, ha célként használt gépekként használják őket, és ezek eredményeit később a Class metódussal lehet lekérni `.ToTSV()` .

A műveleteknek az erőforrás-becslések való futtatásához használjuk a következőt

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
majd az eredményeket tabulátorral elválasztott értékként (TSV) a és a karakterrel kell beolvasni `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .

Tehát a teljes C# gazda program mind a, mind a `QuantumSimulator` formáját a `ResourcesEstimator` következőket teszi:

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


amely a következőhöz hasonló kimenetet eredményezhet

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

## <a name="q-jupyter-notebooks"></a>Q# nyelvű Jupyter-notebookok
A q # Jupyter notebookok használják az IQ # kernelt, amely lehetővé teszi a Q # callables egyetlen jegyzetfüzetben való definiálását, fordítását és futtatását---az összes útmutatást, megjegyzést és egyéb tartalmat.
Ez azt jelenti, hogy habár lehetséges a Q # fájlok importálása és használata `*.qs` , nem szükségesek a végrehajtási modellben.

Itt részletesen ismertetjük, hogyan futtathatja a fentebb definiált Q #-műveleteket, de a Q # Jupyter jegyzetfüzetek használatának szélesebb körű bemutatása a q [# és a Jupyter jegyzetfüzetek](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)esetében érhető el.

### <a name="defining-operations"></a>Műveletek definiálása

A Q # Jupyter Notebookban a q # kódot kell megadnia, ugyanúgy, mint a Q # fájl névterében.

Így engedélyezhető a [Q # standard könyvtár](xref:microsoft.quantum.qsharplibintro) callables való hozzáférés a `open` megfelelő névterekhez tartozó utasításokkal.
Ha egy cellát egy ilyen utasítással futtat, a névterek definíciói a munkaterület teljes területén elérhetők.

> [!NOTE]
> A [Microsoft. Quantum. belső](xref:microsoft.quantum.intrinsic) és a [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (például [`H`](xref:microsoft.quantum.intrinsic.h) és) Callables [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) automatikusan elérhetők a Q # Jupyter jegyzetfüzetekben található cellákban definiált műveletekhez.
> Ez azonban nem igaz a külső Q # forrásfájlok esetében beérkező kód esetén (a [q # és a Jupyter notebookok bevezetőjét bemutató](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)folyamat). 
> 

Hasonlóképpen, a definiált műveletekhez csak a Q # kód írása és a cella futtatása szükséges.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

A kimenet ezután felsorolja ezeket a műveleteket, amelyek ezután meghívhatók a jövőbeli cellákból.

### <a name="target-machines"></a>Célgépek

Az adott célszámítógépeken futó műveletek futtatásának funkciói az [IQ # Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp)használatával érhetők el.
Például a a (z) `%simulate` `QuantumSimulator` és a következőt `%estimate` használja `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Bemenetek átadása a függvényeknek és műveleteknek

Jelenleg a végrehajtási mágikus parancsok csak olyan műveletekkel használhatók, amelyek nem rendelkeznek argumentumokkal. Tehát a futtatáshoz `MeasureSuperpositionArray` definiálnia kell egy "burkoló" műveletet, amely ezután meghívja a műveletet a következő argumentumokkal:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Ez a művelet természetesen a `%estimate` és más végrehajtási parancsokkal is használható.
