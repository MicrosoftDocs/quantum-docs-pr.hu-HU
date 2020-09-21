---
title: Programok futtatásának módjai Q#
description: A programok futtatásának különböző módjai – áttekintés Q# . A parancssorból, a Q# Jupyter-jegyzetfüzetből és a klasszikus gazdagép-programokból Python vagy .net nyelven.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: f24c608ffc6522cb50f512de1a02b3db4b290e83
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759816"
---
# <a name="ways-to-run-a-no-locq-program"></a>Programok futtatásának módjai Q#

A Quantum Development Kit egyik legnagyobb erőssége a platformok és a fejlesztői környezetek rugalmassága.
Ez azonban azt is jelenti, hogy az új Q# felhasználók a [telepítési útmutatóban](xref:microsoft.quantum.install)található számos lehetőség alapján megzavarják vagy elárasztják magukat.
Ezen az oldalon elmagyarázza, hogy mi történik a Q# program futtatásakor, és hasonlítsa össze a felhasználók által megtehető különböző módokat.

Az elsődleges különbség az, hogy a Q# következőket lehet futtatni:
- önálló alkalmazásként, ahol az az Q# egyetlen érintett nyelv, és a program közvetlenül hívja meg a programot. Két metódus valójában a következő kategóriába tartozik:
  - a parancssori felület
  - Q# Jupyter notebookok
- egy további, Pythonban vagy .NET nyelven írt (pl. C# vagy F #) *befogadó programmal*, amely ezután meghívja a programot, és folytatja a visszaadott eredmények feldolgozását.

Ha szeretné jobban megérteni ezeket a folyamatokat és azok különbségeit, tekintse meg Q# az egyszerű programot, és hasonlítsa össze a végrehajtható módszereket.

## <a name="basic-no-locq-program"></a>Alapszintű Q# program

Egy alapszintű kvantum-program a qubit előállítását is magában foglalhatja az államok $ \ket $ és a $ \ket $ értékkel egyenlő arányban {0} {1} , a mérést és az eredményt visszaadva, amely a két, azonos valószínűséggel rendelkező állapot közül véletlenszerűen fog állni.
Ennek a folyamatnak a lényege a [Quantum Random Number Generator](xref:microsoft.quantum.quickstarts.qrng) rövid útmutatója.

A-ben Q# ezt a következő kód hajtja végre:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Ez a kód azonban önmagában nem hajtható végre Q# .
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

Habár az ezen a lapon szereplő példák csak a Q# *műveletekből*állnak, az összes olyan fogalmat, amelyet a függvények is érintenek, Q# *functions*és ezért a *callables*együttesen hivatkozunk rájuk. A különbségeket az [ Q# alapjai: Operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), valamint az azok definiálásával kapcsolatos további információk a [Operations and functions (műveletek és függvények](xref:microsoft.quantum.guide.operationsfunctions)) című cikkben találhatók.

### <a name="callable-defined-in-a-no-locq-file"></a>Meghívható definiálva egy Q# fájlban

A hívható pontosan az, amit a meghívott és futtat Q# .
Azonban ehhez több kiegészítésre van szükség, amely egy teljes fájlt tartalmaz `*.qs` Q# .

Az összes Q# típus-és callables (az Ön által definiált és a nyelvhez tartozók is) a *névterekben*vannak definiálva, amelyek minden olyan teljes nevet megadnak, amelyre hivatkozni lehet.

Például a és a [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) műveletek a és a [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) névterekben találhatók (a [ Q# standard könyvtárak](xref:microsoft.quantum.qsharplibintro)része).
Így mindig meghívhatják a *teljes* nevüket, de mindig megtehetik, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` hogy ez nagyon zsúfolt programkódot eredményez.

Ehelyett `open` az utasítások lehetővé teszik, hogy a callables tömör gyorsírással legyenek hivatkozva, ahogy a fenti műveleti törzsben tettük.
A Q# műveletet tartalmazó teljes fájl ezért a saját névterek definiálását, a callables, a művelet által használt névterek megnyitását, majd a műveletet:

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

Mostantól a program általános végrehajtási modellje is Q# világossá válik.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Először is a végrehajtáshoz megadott meghívásos hozzáférés minden más, ugyanabban a névtérben definiált callables és típushoz elérhető.
Emellett a [ Q# könyvtárak](xref:microsoft.quantum.libraries)bármelyikének hozzáférését is elérheti, de ezeket a teljes névvel vagy a fent ismertetett utasítások használatával kell hivatkozni `open` .

A meghívót a rendszer ezután a *[célszámítógépen](xref:microsoft.quantum.machines)* hajtja végre.
Ilyen célszámítógépek lehetnek a tényleges kvantum-hardverek vagy a QDK részeként elérhető több szimulátorok.
Erre a célra a leghasznosabb célszámítógép a [teljes állapotú szimulátor](xref:microsoft.quantum.machines.full-state-simulator)egy példánya, `QuantumSimulator` amely úgy számítja ki a program viselkedését, mintha egy zaj nélküli kvantum-számítógépen hajtották végre.

Eddig azt ismertetjük, hogy mi történik, ha egy adott Q# hívás végrehajtása folyamatban van.
Függetlenül attól, hogy Q# egy önálló alkalmazásban vagy egy gazdagép programban használ-e, ez az általános folyamat több vagy kevesebb, mint a QDK rugalmassága---.
A *kvantum-fejlesztési* készletbe való hívás különböző módjai közötti különbségek így felfedik a Q# hívható hívásának módját, és hogy milyen módon adja vissza az eredményeket.
Pontosabban a különbségek körül forog 
1. annak jelzése Q# , hogy melyik meghívást kell végrehajtani,
2. a lehetséges hívható argumentumok megadása
3. annak a célszámítógépnek a meghatározása, amelyre a szolgáltatást végre szeretné hajtani, és
4. az eredmények visszaadása.

Először is megbeszéljük, hogy ez hogyan történik az Q# önálló alkalmazás parancssorból való használatával, majd folytassa a Python és a C# gazdagép-programok használatát.
Fenntartjuk a Jupyter-jegyzetfüzetek önálló alkalmazását az Q# utolsó számára, mivel az első háromtól eltérően az elsődleges funkció nem a helyi fájlok körébe kerül Q# .

> [!NOTE]
> Habár nem mutatjuk be ezeket a példákat, a végrehajtási módszerek közötti egyetlen egység, hogy a programon belülről kinyomtatott összes üzenet Q# (például: [`Message`](xref:microsoft.quantum.intrinsic.message) vagy [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ) általában mindig a megfelelő konzolra lesz kinyomtatva.

## <a name="no-locq-from-the-command-prompt"></a>Q# a parancssorból
A programok írásához legkönnyebben elsajátíthatja az első lépéseket, Q# hogy elkerülje a különálló fájlok és a második nyelv használatának elkerülését.
A Visual Studio Code vagy a Visual Studio és a QDK bővítmény lehetővé teszi a zökkenőmentes munkafolyamatot, amelyben a Q# callables-t csak egyetlen Q# fájlból futtatjuk.

Ebben az esetben végső soron a program végrehajtásának meghívása a következővel:
```dotnetcli
dotnet run
```
parancsot a parancssorban.
A legegyszerűbb munkafolyamat az, amikor a terminál címtárának helye megegyezik a fájl nevével Q# , amely könnyen kezelhető a Q# fájl szerkesztésével együtt a vs Code integrált termináljának használatával, például:.
A [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) azonban számos lehetőséget is elfogad, és a program más helyről is futtatható, ha egyszerűen megadja a `--project <PATH>` Q# fájl helyét.


### <a name="add-entry-point-to-no-locq-file"></a>Belépési pont hozzáadása a Q# fájlhoz

A legtöbb Q# fájl egynél több meghívót tartalmaz, ezért természetesen a fordítónak tudnia kell, hogy *melyik* meghívásos végrehajtásra van szükség a `dotnet run` parancs megadásakor.
Ez a fájl egyszerű módosításával történik Q# : 
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

Most a `dotnet run` parancssorból érkező hívás a `MeasureSuperposition` futtatáshoz vezet, és a visszaadott érték közvetlenül a terminálra lesz kinyomtatva.
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

Ha az `@EntryPoint()` attribútumot az új művelet előtt helyezi át (vegye figyelembe, hogy egy fájlban csak egy ilyen sor lehet), és a futtatására tett kísérlet egyszerűen `dotnet run` olyan hibaüzenetet eredményez, amely azt jelzi, hogy milyen további parancssori kapcsolók szükségesek, és hogyan fejezheti ki őket.

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
> A ben definiált argumentumok nevét `camelCase` a fordító csak kis mértékben módosítja Q# bemenetként. Például, ha `n` a helyett a fenti nevet használtuk `numQubits` , akkor ez a bemenet a parancssoron keresztül lesz megadva a `--num-qubits 4` helyett `-n 4` .

A hibaüzenet más lehetőségeket is tartalmaz, amelyek használhatók, beleértve a célszámítógép módosításának módját is.

### <a name="different-target-machines"></a>Különböző célszámítógépek

Mivel a műveleteik eredményei a tényleges qubits a várt eredmények voltak, egyértelmű, hogy a parancssorból az alapértelmezett célszámítógép a teljes állapotú kvantum-szimulátor `QuantumSimulator` .
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

### <a name="non-no-locq-dotnet-run-options"></a>Nem Q# `dotnet run` Beállítások

Ahogy azt röviden említettük a `--project` kapcsolóval, a [ `dotnet run` parancs](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) a Q# meghívásos argumentumokhoz nem kapcsolódó beállításokat is elfogadja.
Ha mindkét típusú beállítást megadja, a `dotnet` -specifikus beállításokat elsőként kell megadni, majd egy elválasztó karakter `--` , majd a Q# -specifikus beállításokat.
Például a specifiying egy elérési utat a fenti művelethez tartozó qubits együtt hajthat végre `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q# gazdagép-programokkal

Ha a Q# fájl a kezünkben van, a művelet vagy a függvény közvetlenül a parancssorból való meghívására szolgáló alternatíva egy másik klasszikus nyelven üzemelő *gazda program* használata. Pontosabban megteheti a Python vagy a .NET nyelv, például a C# vagy az F # kombinációját (a rövidség kedvéért csak a C# adatokat fogjuk részletezni).
Az együttműködési képesség engedélyezéséhez valamivel több beállítás szükséges, de ezek a részletek a [telepítési útmutatókban](xref:microsoft.quantum.install)találhatók.

Dióhéjban a helyzet most már tartalmaz egy gazda programfájlt (például `*.py` vagy `*.cs` ) a fájllal megegyező helyen Q# .
Most már a futtatott *gazda* program fut, és a végrehajtásuk során a Q# fájl adott műveleteit és funkcióit is meghívhatja Q# .
Az együttműködési képesség lényege, hogy a Q# fordító a Q# fájl tartalmát elérhetővé teszi a gazda program számára, hogy azok meghívhatók legyenek.

A gazda program használatának egyik legfőbb előnye, hogy a program által visszaadott klasszikus adatmennyiséget a Q# gazdagép nyelvén lehet tovább feldolgozni.
Ez állhat néhány speciális adatfeldolgozásból (például egy olyan dologból, amely nem hajtható végre belsőleg Q# ), majd az Q# eredmények alapján további műveleteket hívhat meg, vagy az eredmények ábrázolására is alkalmas Q# .

Az általános séma itt látható, és megbeszéljük a Python és a C# adott implementációit alább. Az F # gazda programot használó minta a .net-es [együttműködési mintákon](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)érhető el.

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> Az `@EntryPoint()` Q# alkalmazásokhoz használt attribútum nem használható a gazdagép-programokkal.
> A rendszer hibát jelez, ha az Q# egy gazdagép által hívott fájlban szerepel. 

A különböző gazdagépekkel való munkavégzéshez nincs szükség módosításra a `*.qs` Q# fájlokhoz.
A következő gazda program-implementációk mindegyike ugyanazzal a Q# fájllal működik:

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
1. Importálja a modult `qsharp` , amely regisztrálja a modul-betöltőt az Q# együttműködési képességhez. 
    Ez lehetővé teszi Q# , hogy a névterek Python-modulokként jelenjenek meg, amelyekről "importálhatók" Q# callables.
    Ne feledje, hogy a callables nem Q# maga az importált, hanem a Python-Csonkok, amelyek lehetővé teszik a hívását.
    Ezek a Python-osztályok objektumaiként viselkednek, és a metódusok segítségével határozzák meg, hogy a rendszer hogyan küldje el a műveletet a művelet végrehajtásához.

2. Importálja azokat a Q# callables, amelyeket a rendszer közvetlenül meghív---ebben az esetben, `MeasureSuperposition` és `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Ha a `qsharp` modult importálta, a callables közvetlenül a Q# könyvtár névteréről is importálhatja.

3. A többi Python-kód között mostantól meghívhatja ezeket a callables az adott célszámítógépeken, és hozzárendelheti azok változóhoz való visszatérését (ha értéket adnak vissza) a további használatra.

#### <a name="specifying-target-machines"></a>Megcélzott gépek meghatározása
Egy adott célszámítógépen futtatandó művelet meghívása az importált objektumon különböző Python-módszerekkel történik.
A (z `.simulate(<args>)` ) például a használatával `QuantumSimulator` futtatja a műveletet, míg `.estimate_resources(<args>)` a (z `ResourcesEstimator` ).

#### <a name="passing-inputs-to-q"></a>Bemenetek továbbítása a Q-ba\#
A Q# meghívható argumentumokat kulcsszó típusú argumentum formájában kell megadni, ahol a kulcsszó az argumentum neve a Q# meghívásos definícióban.
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

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Q#Kód használata más projektekről vagy csomagokból

Alapértelmezés szerint a `import qsharp` parancs betölti az `.qs` aktuális mappában található összes fájlt, és a Q# műveleteit és funkcióit elérhetővé teszi a Python-szkripten belülről való használatra.

Q#A kód egy másik mappából való betöltéséhez az [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) -val egy projektre mutató hivatkozást adhat hozzá `.csproj` Q# (azaz egy projekt, amely hivatkozik `Microsoft.Quantum.Sdk` ).
Ez a parancs lefordítja a `.qs` mappában található összes fájlt, amely tartalmazza a `.csproj` és almappáit. Emellett rekurzív módon betölti az `PackageReference` adott fájlban hivatkozott vagy projekteken keresztül hivatkozott csomagokat is Q# `ProjectReference` `.csproj` .

A következő Python-kód például egy külső projektet importál, amely az aktuális mappához viszonyított elérési útra hivatkozik, és meghívja az egyik Q# műveletét:

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

Ez a következőhöz hasonló kimenetet eredményez:

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

A kódot tartalmazó külső csomagok betöltéséhez Q# használja az [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)-t.

Ha az Q# aktuális mappában található kód külső projekttől vagy csomagtól függ, a futtatásakor hibák jelenhetnek meg `import qsharp` , mivel a függőségek még nincsenek betöltve.
A szükséges külső csomagok vagy projektek a parancsban való betöltéséhez győződjön meg arról, Q# `import qsharp` hogy a Python-szkripttel rendelkező mappa tartalmaz egy `.csproj` hivatkozást tartalmazó fájlt `Microsoft.Quantum.Sdk` . A ben `.csproj` adja hozzá a tulajdonságot a következőhöz: `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` . Ez Q# a művelet arra utasítja, hogy rekurzív módon töltse be `ProjectReference` `PackageReference` `.csproj` a parancsban található összes vagy elemet `import qsharp` .

Íme például egy egyszerű `.csproj` fájl, amely a Q# csomag automatikus betöltését okozza `Microsoft.Quantum.Chemistry` :

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
> Jelenleg ezt az egyéni `<IQSharpLoadAutomatically>` tulajdonságot a Python-gazdagépek igénylik, de a jövőben ez a `.csproj` Python-szkripttel megegyező mappában található fájl alapértelmezett viselkedése lehet.

> [!NOTE]
> A rendszer jelenleg a `<QsharpCompile>` `.csproj` következő beállítást veszi figyelembe a Python-gazdagépek esetében, és a mappában található összes `.qs` fájl `.csproj` (beleértve az almappákat is) be van töltve és le van fordítva. `.csproj`A beállítások támogatása a jövőben is javulni fog (további részletekért lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).


### <a name="c"></a>[C#](#tab/tabid-csharp)

A C# gazda program több összetevővel rendelkezik, és nagyon szorosan együttműködik a QDK egyes összetevőivel, például a szimulátorokkal, amelyek a C# nyelvre épülnek.

A Q# fordító itt működik, ha egy egyenértékű névvel ellátott C#-névteret hoz létre a Q# fájl névterében Q# .
Ezzel egyenértékű névvel ellátott C# osztályt hoz létre minden egyes Q# definiált callables vagy típushoz.

Első lépésként a gazda programunkban használt osztályokat tesszük elérhetővé a következő `using` utasításokkal, amelyek nagyjából analagous a `open` fájl utasításait Q# :

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Ezután deklaráljuk a C#-névteret, néhány más bitet és darabot (lásd az alábbi teljes kódrészletet), majd a klasszikus programozást (például a callables vonatkozó számítási argumentumokat Q# ).
Az utóbbi nem szükséges az esetünkben, de az ilyen jellegű használatról a .net-es  [együttműködési minta](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)tartalmaz példát.

#### <a name="target-machines"></a>Célgépek

A szolgáltatásba való visszatéréshez Q# létre kell hoznia a célszámítógép egy példányát.

```csharp
            using var sim = new QuantumSimulator();
```

Más célszámítógépek használata olyan egyszerű, mint egy másik példány létrehozása, bár ennek a módja, és a visszatérések feldolgozása némileg eltérő lehet.
A rövidség kedvéért most ragaszkodunk a [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) szolgáltatáshoz, és belefoglaljuk az [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [alábbiakat](#including-the-resources-estimator).

A műveletekben létrehozott minden C# osztálynak Q# van egy `Run` metódusa, amely az első argumentum, amelynek a célszámítógép-példánynak kell lennie.
Tehát a futtatásához `MeasureSuperposition` használjuk a következőt: `QuantumSimulator` `MeasureSuperposition.Run(sim)` .
A visszaadott eredmények ezután a C#-változókhoz rendelhetők:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> A `Run` metódus aszinkron módon van végrehajtva, mert ez a valódi kvantum-hardver esetében ez lesz, ezért a `await` kulcsszó a feladat befejezéséig blokkolja a további végrehajtást.

Ha a Q# hívható nem rendelkezik visszaadott értékkel (azaz visszatérési típussal `Unit` ), a végrehajtás továbbra is ugyanúgy végezhető el, ha nem rendel hozzá egy változóhoz.
Ebben az esetben a teljes sor csupán a következő elemekből áll: 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argumentumok

A felhívható argumentumok egyszerűen átadhatók Q# a afer további argumentumként.
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
> A fordítóprogram névterekkel való együttműködése miatt előfordulhat, hogy a Q# callables az utasítás nélkül elérhetővé tesszük `using NamespaceName;` , és egyszerűen csak a C# névtér címére kell illeszkedni.
> Ez azt helyettesíti, hogy `namespace host` `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Beleértve a források becslését

A [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) kimenet beolvasásához némileg eltérő implementáció szükséges.

Először is, ahelyett, hogy egy `using` utasítással (például a következővel) változóként kívánja létrehozni őket `QuantumSimulator` , az osztály objektumainak közvetlen létrehozását

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Figyelje meg, hogy a több művelet által használt egyetlen cél szimulátor helyett Q# mindegyikhez létrehozunk egyet. Ennek az az oka, hogy maga az objektum is módosul, ha célként használt gépekként használják őket, és ezek eredményeit később a Class metódussal lehet lekérni `.ToTSV()` .

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

## <a name="no-locq-jupyter-notebooks"></a>Q# Jupyter notebookok
Q# A Jupyter notebookok az I Q# kernelt használják, amely lehetővé teszi az callables egyetlen jegyzetfüzetben való definiálását, fordítását és futtatását Q# ---az összes útmutató, Megjegyzés és egyéb tartalom mellett.
Ez azt jelenti, hogy habár lehetséges a fájlok tartalmának importálása és használata `*.qs` Q# , nem szükségesek a végrehajtási modellben.

Itt részletesen ismertetjük, hogyan futtatjuk a Q# fent meghatározott műveleteket, de a Jupyter notebookok használatának szélesebb körű bemutatása a Q# [notebookok bevezetője Q# és Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Műveletek definiálása

Egy Q# Jupyter notebook a kódot ugyanúgy kell megadnia, Q# mint egy fájl névterében Q# .

Így lehetővé tehetjük a callables való hozzáférést a [ Q# szabványos könyvtárakból](xref:microsoft.quantum.qsharplibintro) a `open` megfelelő névterekhez tartozó utasításokkal.
Ha egy cellát egy ilyen utasítással futtat, a névterek definíciói a munkaterület teljes területén elérhetők.

> [!NOTE]
> A [Microsoft. Quantum. belső](xref:microsoft.quantum.intrinsic) és a [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (például [`H`](xref:microsoft.quantum.intrinsic.h) és) Callables [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) automatikusan elérhetők a Jupyter-jegyzetfüzetekben lévő cellákban definiált műveletekhez Q# .
> Ez azonban nem igaz a külső forrásfájlok által bevitt kód esetében Q# (a [jegyzetfüzetek bevezetője Q# és Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)között látható folyamat). 
> 

Hasonlóképpen, a definiált műveletekhez csak a Q# kód írása és a cella futtatása szükséges.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

A kimenet ezután felsorolja ezeket a műveleteket, amelyek ezután meghívhatók a jövőbeli cellákból.

### <a name="target-machines"></a>Célgépek

Az adott célszámítógépeken futó műveletek futtatásának funkciói az [I Q# Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp)segítségével érhetők el.
Például a a (z) `%simulate` `QuantumSimulator` és a következőt `%estimate` használja `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>Bemenetek átadása a függvényeknek és műveleteknek

Ahhoz, hogy a műveletek továbbítva legyenek a Q# műveletekhez, az argumentumok párokként adhatók át `key=value` a végrehajtási Magic parancsnak.
Tehát a következő `MeasureSuperpositionArray` négy qubits futtatható `%simulate MeasureSuperpositionArray n=4` :

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

Ez a minta a `%estimate` és más végrehajtási parancsokkal is használható.

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Q#Kód használata más projektekről vagy csomagokból

Alapértelmezés szerint a Q# Jupyter notebook betölti az `.qs` aktuális mappában található összes fájlt, és a Q# műveleteit és funkcióit elérhetővé teszi a notebookon belülről való használatra. A [ `%who` Magic parancs](xref:microsoft.quantum.iqsharp.magic-ref.who) felsorolja az összes jelenleg elérhető Q# műveletet és funkciót.

Q#A kód egy másik mappából való betöltéséhez használhatja a [ `%project` Magic parancsot](xref:microsoft.quantum.iqsharp.magic-ref.project) a `.csproj` projekthez tartozó fájlra mutató hivatkozás hozzáadásához Q# (azaz a projekt, amely hivatkozik `Microsoft.Quantum.Sdk` ). Ez a parancs lefordítja a `.qs` `.csproj` (és almappákat) tartalmazó mappában található összes fájlt. Emellett rekurzív módon betölti az `PackageReference` adott fájlban hivatkozott vagy projekteken keresztül hivatkozott csomagokat is Q# `ProjectReference` `.csproj` . 

A következő cellák például egy Q# külső projektből származó műveletet szimulálnak, ahol a projekt elérési útja az aktuális mappához képest hivatkozik:

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

A kódot tartalmazó külső csomagok betöltéséhez Q# használja a [ `%package` Magic parancsot](xref:microsoft.quantum.iqsharp.magic-ref.package).
A csomagok betöltése a csomag részét képező szerelvényekben található bármely egyéni mágikus parancsot vagy kódolókat is elérhetővé tesz.

Ha külső csomagokat vagy projekteket szeretne betölteni a Q# Jegyzetfüzet intialization, győződjön meg arról, hogy a notebook mappa tartalmaz egy `.csproj` hivatkozást tartalmazó fájlt `Microsoft.Quantum.Sdk` . A ben `.csproj` adja hozzá a tulajdonságot a következőhöz: `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` . Ez Q# arra utasítja a rendszer, hogy rekurzív módon töltse be a `ProjectReference` `PackageReference` `.csproj` Jegyzetfüzet betöltési idején található bármely vagy elemeket.

Íme például egy egyszerű `.csproj` fájl, amely a Q# csomag automatikus betöltését okozza `Microsoft.Quantum.Chemistry` :

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
> Jelenleg ezt az egyéni `<IQSharpLoadAutomatically>` tulajdonságot Q# Jupyter notebook gazdagépek igénylik, de a jövőben ez lehet egy, a `.csproj` Jegyzetfüzet-fájllal azonos mappában található fájl alapértelmezett viselkedése.

> [!NOTE]
> Jelenleg a `<QsharpCompile>` `.csproj` Jupyter notebook gazdagépek figyelmen kívül hagyják a beállítást Q# , és a `.qs` mappában található összes fájl `.csproj` (beleértve az almappákat is) be van töltve és le van fordítva. `.csproj`A beállítások támogatása a jövőben is javulni fog (további részletekért lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).
