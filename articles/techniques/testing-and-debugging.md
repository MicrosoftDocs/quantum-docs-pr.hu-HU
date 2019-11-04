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
# <a name="testing-and-debugging"></a>Tesztelés és hibakeresés

Csakúgy, mint a klasszikus programozás esetében, elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a kvantum programot, amely helytelen.
Ebben a szakaszban a Q # által nyújtott eszközöket fogjuk kiszolgálni a kvantum-programok teszteléséhez és hibakereséséhez.

## <a name="unit-tests"></a>Egység tesztek

A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat ír *, amelyekben* kód fut egy könyvtárban, és hasonlítsa össze a kimenetét a várt kimenettel.
Előfordulhat például, hogy azt szeretnénk, hogy a `Square(2)` visszaadja `4`ét, mert tudjuk, hogy *a priori* 2 ^ 2 = $4.

A Q # támogatja az egységnyi tesztek létrehozását a kvantum-programokhoz, amelyek a [xUnit](https://xunit.github.io/) egység tesztelési keretrendszerében tesztekként hajthatók végre.

### <a name="creating-a-test-project"></a>Tesztelési projekt létrehozása

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Nyissa meg a Visual Studio 2019 alkalmazást. Lépjen a `File` menüre, és válassza a `New` > `Project...`lehetőséget.
A Project template Explorerben `Installed` > `Visual C#`alatt válassza ki a `Q# Test Project` sablont.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A kedvenc parancssorában futtassa a következő parancsot:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Mindkét esetben az új projekt két fájl megnyitását fogja megnyitni.
Az első fájl, `Tests.qs`, kényelmes helyet biztosít az új Q # egység tesztek definiálásához.
Kezdetben ez a fájl egy minta egység tesztelési `AllocateQubitTest` tartalmaz, amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket{0}$ állapotban van-e, és kinyomtat egy üzenetet:

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Bármely Q # művelet, amely kompatibilis a `(Unit => Unit)` vagy az `(Unit -> Unit)`-kompatibilis funkcióval, egységként való tesztelésként hajtható végre. 

A második fájl `TestSuiteRunner.cs` olyan metódust tartalmaz, amely felfedi a Q # Unit teszteket, és futtatja őket. Ezt a módszert `TestTarget` `OperationDriver` attribútummal kell megjegyzetni.
A `OperationDriver` attribútum a Microsoft. Quantum. szimulációs. xUnit xUnit bővítményének részét képezi.
Az Unit Testing Framework meghívja a `TestTarget` metódust minden Q # egység által észlelt teszthez.
A keretrendszer `op` argumentumon keresztül továbbítja az egység teszt leírását a metódusnak. A következő kódrészlet:
```csharp
op.TestOperationRunner(sim);
```
végrehajtja az egység tesztjét `QuantumSimulator`on.

Alapértelmezés szerint az egység teszt-felderítési mechanizmusa az összes Q # függvényt vagy kompatibilis típusú műveletet keresi, amelyek megfelelnek a következő tulajdonságokkal:
* Ugyanabban a szerelvényben található, mint a metódus `OperationDriver` attribútummal való megjegyzése.
* Ugyanabban a névtérben található, mint az `OperationDriver` attribútummal jegyzett metódus.
* `Test`végződésű névvel rendelkezik.

Az egység tesztelési funkcióinak és műveleteinek egy szerelvénye, egy névtere és egy utótagja a `OperationDriver` attribútum nem kötelező paramétereinek használatával állítható be:
* `AssemblyName` paraméter beállítja annak a szerelvénynek a nevét, amelyet tesztek keres.
* `TestNamespace` paraméter beállítja annak a névtérnek a nevét, amelyet tesztek keres.
* `Suffix` beállítja a műveleti vagy a függvények neveinak az egység-tesztelésnek megfelelő utótagját.

Továbbá a `TestCasePrefix` opcionális paraméterrel megadhat egy előtagot a tesztelési eset nevéhez. A művelet neve előtt megjelenő előtag megjelenik a tesztelési esetek listájában. A `TestCasePrefix = "QSim:"` például a talált tesztek listájában `QSim:AllocateQubitTest`ként fog megjelenni `AllocateQubitTest`. Ez akkor lehet hasznos, ha például azt szeretné, hogy a rendszer melyik szimulátort használja a tesztek futtatásához.

### <a name="running-q-unit-tests"></a>Q # egység tesztek futtatása

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Egyszeri egyszeri megoldás beállítása esetén lépjen `Test` menüre, és válassza `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások (`.suo`) fájljában tárolódik.
> Ha törli ezt a fájlt, akkor újra ki kell választania `X64` a processzor architektúrájának megfelelően.

Hozza létre a projektet, lépjen a `Test` menüre, és válassza a `Windows` > `Test Explorer`lehetőséget. a `AllocateQubitTest` megjelennek a `Not Run Tests` csoportban lévő tesztek listájában. Válassza ki `Run All` vagy futtassa ezt az egyéni tesztet, és adja meg a következőt.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A tesztek futtatásához navigáljon a projekt mappájához (a `Tests.csproj`tartalmazó mappához), és hajtsa végre a következő parancsot:

```bash
$ dotnet restore
$ dotnet test
```

A következőhöz hasonló kimenetnek kell megjelennie:

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

## <a name="logging-and-assertions"></a>Naplózás és kijelentések

Az egyik fontos következménye annak, hogy a Q #-ban lévő függvények ne legyenek mellékhatásai az, hogy olyan függvényt hajtson végre, amelynek kimeneti típusa az üres rekord `()` a Q # programon belül soha nem figyelhető meg.
Vagyis a célszámítógép úgy is dönthet, hogy nem hajt végre olyan függvényt, amely `()`t ad vissza, és ezzel garantálja, hogy ez a mulasztás nem módosítja a következő Q # kód viselkedését.
Ez lehetővé teszi a függvények visszaadását `()` egy hasznos eszközként, amely az állításokat és a hibakeresési logikát a Q # programokba ágyazza be. 

### <a name="logging"></a>Naplózás

A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)`, és lehetővé teszi a diagnosztikai üzenetek létrehozását.

A `QuantumSimulator` `onLog` művelettel határozható meg a Q # Code-hívások `Message`akor végrehajtott műveletek. Alapértelmezés szerint a naplózott üzenetek standard kimenetre vannak kinyomtatva.

A Unit test Suite meghatározásakor a naplózott üzenetek a teszt kimenetére irányíthatók. Ha egy projekt a Q # teszt Project sablonból jön létre, az átirányítás előre be van állítva a csomaghoz, és alapértelmezés szerint a következőképpen jön létre:

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt végrehajtásával kapcsolatos információkat tartalmazza: az átadott/sikertelen állapot, az eltelt idő és a "kimenet" hivatkozás. Ha a kimenet hivatkozásra kattint, a teszt kimenete új ablakban fog megnyílni.

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

Az egyes tesztek Pass/Fail állapotának kinyomtatását a konzolon `dotnet test`.
A sikertelen tesztek esetén a fenti `output.WriteLine(msg)` hívás eredményeként naplózott kimenetek is kinyomtathatók a konzolon a hiba diagnosztizálásához.

***

### <a name="assertions"></a>Állításokat

Ugyanezt a logikát alkalmazhatja az érvényesítések megvalósítására is. Vegyünk egy egyszerű példát:

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, kivételt kell kiemelni a Q # programot futtató célszámítógépen.
Definíció szerint az ilyen típusú hibák nem figyelhetők meg a Q #-on belül, mert egy `fail` utasítás elérésekor nem fut további Q # kód.
Így ha folytatjuk a `AssertPositive`meghívását, biztos lehet abban, hogy a bemenete pozitív volt.

Ezen ötletek kiépítésekor [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude) két különösen hasznos állítást kínál, <xref:microsoft.quantum.intrinsic.assert> és <xref:microsoft.quantum.intrinsic.assertprob> mind a modellként, mind a `()`. Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy olyan kvantum-regisztrációt, amelyre a mérést végzi, valamint egy feltételezett eredményt.
A szimulációval működő célszámítógépeken nem köti [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem), és elvégezheti az ilyen méréseket anélkül, hogy megzavarja volna az ilyen állításokra adott regisztrációt.
A szimulátor ezután a fenti `AssertPositive` függvényhez hasonlóan megszakítja a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:

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

Fizikai kvantum-hardveren, ahol a klónozás nélküli tétel megakadályozza a kvantum-állapot vizsgálatát, a `Assert` és a `AssertProb` műveletek egyszerűen visszatérhetnek a `()` más hatás nélkül.

A <xref:microsoft.quantum.diagnostics> névtér a `Assert` család számos további funkcióját biztosítja, amelyek lehetővé teszik a fejlettebb feltételek ellenőrzését. 

## <a name="dump-functions"></a>Memóriakép függvények

A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:microsoft.quantum.diagnostics> névtér két olyan függvényt kínál, amely a célszámítógép aktuális állapotával (<xref:microsoft.quantum.diagnostics.dumpmachine> és <xref:microsoft.quantum.diagnostics.dumpregister>) képes a fájlba való kiírásra. A generált kimenet a célszámítógéptől függ.

### <a name="dumpmachine"></a>DumpMachine

A Quantum Development Kit részeként elosztott teljes állapotú kvantum-szimulátor a teljes kvantumrendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja be, amely a komplex számok egydimenziós tömbje, amelyben az egyes elemek a a számítási alap állapotának kiszámítása valószínűsége $ \ket{n} $, ahol $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ a BITS $\{b_i\}$ esetében. Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ hívó <xref:microsoft.quantum.diagnostics.dumpmachine> generálja ezt a kimenetet :

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.
A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{n} $ és a poláris formátumban egyaránt. Az első sorra vonatkozó részletek:

* **`∣0❭:`** ez a sor a `0` számítási alap állapotának felel meg
* **`0.707107 +  0.000000 i`** : a valószínűségi amplitúdó a Descartes formátumban.
* **` == `** : a `equal` aláírja a elválasztja mindkét egyenértékű ábrázolást.
* **`**********  `** : a magnitúdó grafikus ábrázolása, a `*` száma arányos az állapot-vektor mérési valószínűségével.
* **`[ 0.500000 ]`** : a magnitúdó numerikus értéke
* **`    ---`** : az amplitúdó fázisának grafikus ábrázolása (lásd alább).
* **`[ 0.0000 rad ]`** : a fázis numerikus értéke (radiánban).

A magnitúdó és a fázis is grafikus ábrázolással jelenik meg. A magnitúdó ábrázolása egyenesen előre látható: az `*`egy sávot mutat, annál nagyobb a valószínűsége annak, hogy a sáv nagyobb lesz. A fázisban a következő szimbólumok jelennek meg, amelyek a tartományon alapuló szöget jelölik:

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

Az alábbi példák a gyakori állapotok `DumpMachine` mutatják be:

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
  > A qubit azonosítója futásidőben van hozzárendelve, és nem szükségszerűen igazodik azzal a sorrendtel, ahogy a qubit le lett foglalva, vagy a qubit-regisztráción belüli pozíciója.


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Létrehozhat egy qubit-azonosítót a Visual Studióban, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > a (z) `register2` indextel `0` qubit azonosító =`3`, az index `1` azonosítójú qubit azonosítója =`2`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Qubit-azonosítót a <xref:microsoft.quantum.intrinsic.message> függvénnyel talál, és átadhatja a qubit változót az üzenetben, például:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > amely a következő kimenetet eredményezheti:
  >```
  > 0=q:3; 1=q:2
  >```
  > Ez azt jelenti, hogy a `register2` qubit rendelkező `0` azonosítója =`3`, a qubit index `1` azonosítója =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics> névtér része, ezért a használatához hozzá kell adnia egy `open` utasítást:

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


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> úgy működik, mint <xref:microsoft.quantum.diagnostics.dumpmachine>, kivéve, ha a qubits egy tömbjét is végrehajtja, amely korlátozza az adatok mennyiségét, hogy csak a megfelelő qubits legyenek érvényesek.

A <xref:microsoft.quantum.diagnostics.dumpmachine>hoz hasonlóan a <xref:microsoft.quantum.diagnostics.dumpregister> által generált információk a célszámítógéptől függenek. A teljes állapotú kvantum-szimulátor esetében a Wave függvény a megadott qubits által generált kvantum alrendszerek globális fázisára mutat, a <xref:microsoft.quantum.diagnostics.dumpmachine>formátumával megegyező formátumban.  Tegyük fel például, hogy egy gép csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[0]` hozza létre ezt a kimenetet:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

és a <xref:microsoft.quantum.diagnostics.dumpregister> meghívása `qubit[1]` a kimenetet hozza létre:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot. Ebben az esetben a <xref:microsoft.quantum.diagnostics.dumpregister> a következő üzenetet jeleníti meg:

```
Qubits provided (0;) are entangled with some other qubit.
```

Az alábbi példa bemutatja, hogyan használhatja a Q # Code-ban <xref:microsoft.quantum.diagnostics.dumpregister> és <xref:microsoft.quantum.diagnostics.dumpmachine> is:

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

## <a name="debugging"></a>Hibakeresés

`Assert` és `Dump` függvények és műveletek mellett a Q # a standard Visual Studio hibakeresési képességeinek egy részhalmazát támogatja: [vonali töréspontok beállítása, kód átadása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)az [F10 használatával](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) és [a klasszikus változók értékeinek vizsgálata ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)a szimulátoron a kód végrehajtása során minden lehetséges.

A Visual Studio Code-ban való hibakeresés még nem támogatott.

