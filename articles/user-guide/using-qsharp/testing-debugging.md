---
title: Tesztelés és hibakeresés
description: Megtudhatja, hogyan használhatók az egységes tesztek, a tények és a kijelentések, valamint a kvantum-programok tesztelésére és hibakeresésére szolgáló függvények.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630031"
---
# <a name="testing-and-debugging"></a>Tesztelés és hibakeresés

Csakúgy, mint a klasszikus programozás esetében, elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a kvantum programot, amely helytelen.
Ebben a szakaszban a Q # által nyújtott eszközöket fogjuk kiszolgálni a kvantum-programok teszteléséhez és hibakereséséhez.

## <a name="unit-tests"></a>Egység tesztek

A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat ír *, amelyekben* kód fut egy könyvtárban, és hasonlítsa össze a kimenetét a várt kimenettel.
Előfordulhat például, hogy vissza kívánja állítani a visszaadott `Square(2)` értéket `4` , mivel tudjuk, hogy *a priori a* következő: 2 ^ 2 = $4.

A Q # támogatja az egységnyi tesztek létrehozását a kvantum-programokhoz, amelyek a [xUnit](https://xunit.github.io/) egység tesztelési keretrendszerében tesztekként hajthatók végre.

### <a name="creating-a-test-project"></a>Tesztelési projekt létrehozása

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Nyissa meg a Visual Studio 2019 alkalmazást. Lépjen a `File` menüre, és válassza a elemet `New`  >  `Project...` .
A jobb felső sarokban keresse meg a `Q#` elemet, és válassza ki a `Q# Test Project` sablont.

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A kedvenc parancssorában futtassa a következő parancsot:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Az új projekt egyetlen fájllal fog rendelkezni `Tests.qs` , amely kényelmes helyet biztosít az új Q # egység tesztek definiálásához.
Kezdetben ez a fájl egy minta egység tesztet tartalmaz, `AllocateQubit` amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket $ állapotban van-e, {0} és kinyomtat egy üzenetet:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: új: minden olyan Q # művelet vagy függvény, amely `Unit` a Type és Returns argumentumot `Unit` fogadja, az attribútumon keresztül lehet kijelölni egység tesztként `@Test("...")` . A fenti attribútumhoz megadott argumentum `"QuantumSimulator"` meghatározza a teszt végrehajtásának célját. Egyetlen tesztet több célponton is végrehajthat. Adja meg például a `@Test("ResourcesEstimator")` fenti attribútumot `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Mentse a fájlt, és hajtsa végre az összes tesztet. Ebben az esetben két egységes tesztnek kell lennie, amelyek közül a AllocateQubit a QuantumSimulator hajtja végre, és a ResourceEstimator hajtja végre. 

A Q # Compiler a "QuantumSimulator", a "ToffoliSimulator" és a "ResourcesEstimator" beépített célokat ismeri fel érvényes végrehajtási célokként az egység tesztek számára. A teljes nevet is megadhatja egy egyéni végrehajtási cél definiálásához. 

### <a name="running-q-unit-tests"></a>Q # egység tesztek futtatása

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Egyszeri egyszeri megoldás beállítása esetén válassza a menü lehetőséget, majd a `Test` elemet `Test Settings`  >  `Default Processor Architecture`  >  `X64` .

> [!TIP]
> A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások ( `.suo` ) fájljában tárolódik.
> Ha törli ezt a fájlt, akkor újra ki kell választania `X64` a processzor architektúráját.

Hozza létre a projektet, lépjen a `Test` menüre, és válassza a elemet `Windows`  >  `Test Explorer` . `AllocateQubit`megjelenik a csoportban lévő tesztek listájában `Not Run Tests` . Válassza ki `Run All` vagy futtassa ezt az egyéni tesztet, és adja meg a következőt.

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A tesztek futtatásához navigáljon a projekt mappájához (a mappát tartalmazó mappához `Tests.csproj` ), és hajtsa végre a következő parancsot:

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

Az egységbeli tesztek a nevük és/vagy a végrehajtási cél alapján szűrhetők:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)` és engedélyezése lehetővé teszi a diagnosztikai üzenetek létrehozását.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt végrehajtásával kapcsolatos információkat tartalmazza: az átadott/sikertelen állapot, az eltelt idő és a "kimenet" hivatkozás. Ha a kimenet hivatkozásra kattint, a teszt kimenete új ablakban fog megnyílni.

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

Az egyes tesztek esetén a Pass/Fail állapotot a konzolon kell kinyomtatni `dotnet test` .
A sikertelen tesztek esetén a kimenetek a konzolon is kinyomtathatók a hiba diagnosztizálásához.

***

## <a name="facts-and-assertions"></a>Tények és kijelentések

Mivel a Q # függvények nem rendelkeznek _logikai_ mellékhatással, az olyan függvények végrehajtásának bármilyen _egyéb_ hatása, amelynek kimeneti típusa az üres rekord, `()` soha nem figyelhető meg a q # programon belülről.
Vagyis a célszámítógép dönthet úgy, hogy nem hajt végre olyan függvényt, amely visszaadja `()` azt a garanciát, hogy ez a mulasztás nem módosítja a következő Q # kód viselkedését.
Ez `()` `Unit` a függvény egy hasznos eszközt ad vissza, amely az állításokat és a hibakeresési logikát a Q # programokba ágyazza be. 

Vegyünk egy egyszerű példát:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, kivételt kell kiemelni a Q # programot futtató célszámítógépen.
Definíció szerint az ilyen típusú hibák nem figyelhetők meg a Q #-on belül, mert a rendszer nem futtat további Q # kódot egy `fail` utasítás elérésekor.
Így ha folytatunk egy hívást a `PositivityFact` szolgáltatásba, biztos lehet benne, hogy a bemenete pozitív volt.

Vegye figyelembe, hogy ugyanaz a viselkedés valósítható meg, mint a `PositivityFact` [`Fact`](xref:microsoft.quantum.diagnostics.fact) névtérből származó függvény használatával <xref:microsoft.quantum.diagnostics> :

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

Az egyéb *kijelentéseket*a tényekhez hasonlóan használják, de a célszámítógép állapotától függően változhatnak. Ennek megfelelően a műveletekként vannak definiálva, míg a tények függvényekként vannak definiálva (mint fent).
A különbségtétel megértéséhez vegye figyelembe, hogy a következők valamelyikét kell használnia egy állításon belül:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Itt a műveletet használjuk a <xref:microsoft.quantum.environment.getqubitsavailabletouse> rendelkezésre álló qubits számának visszaküldéséhez.
Mivel ez egyértelműen a program globális állapotától és a végrehajtási környezettől függ, a definíciójának is `AssertQubitsAreAvailable` egy műveletnek kell lennie.
Ezt a globális állapotot azonban használhatja arra, hogy egy egyszerű `Bool` értéket adjon meg bemenetként a `Fact` függvénynek.

Ezen ötletek kiépítésekor [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude) két, különösen hasznos állítást kínál, <xref:microsoft.quantum.intrinsic.assert> és <xref:microsoft.quantum.intrinsic.assertprob> mindkét modell a műveletre van kifejlesztve `()` . Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy olyan kvantum-regisztrációt, amelyre a mérést végzi, valamint egy feltételezett eredményt.
A szimulációval működő célszámítógépeken nem köti [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem), és elvégezheti az ilyen méréseket anélkül, hogy megzavarja volna az ilyen állításokra adott regisztrációt.
A szimulátor ezután a `PositivityFact` fenti függvényhez hasonlóan megszakítja a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:

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

Fizikai kvantummechanika esetén, ahol a nem klónozási tétel megakadályozza a kvantum állapot vizsgálatát, a `Assert` és a `AssertProb` műveletek egyszerűen visszatérhetnek `()` más hatás nélkül.

A <xref:microsoft.quantum.diagnostics> névtér a család számos további funkcióját biztosítja, `Assert` amelyek lehetővé teszik a speciális feltételek ellenőrzését. 

## <a name="dump-functions"></a>Memóriakép függvények

A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:microsoft.quantum.diagnostics> névtér két olyan függvényt biztosít, amelyek a célszámítógép aktuális állapotát a következő fájlba tudják bemutatni: <xref:microsoft.quantum.diagnostics.dumpmachine> és <xref:microsoft.quantum.diagnostics.dumpregister> . A generált kimenet a célszámítógéptől függ.

### <a name="dumpmachine"></a>DumpMachine

A Quantum Development Kit részeként terjesztett teljes állapotú kvantum-szimulátor a teljes kvantum-rendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja a komplex számok egydimenziós tömbje, amelyben az egyes elemek a számítás alapjául szolgáló "\ket{n} $" számítási valószínűségének amplitúdóját jelölik, ahol a $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ a BITS $ \{ b_i \} $ esetében. Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , a \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpmachine> generálja ezt a kimenetet:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.
A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{n} $ és a poláris formátumban egyaránt. Az első sorra vonatkozó részletek:

* **`∣0❭:`** Ez a sor a `0` számítási alap állapotnak felel meg.
* **`0.707107 +  0.000000 i`**: a valószínűségi amplitúdója Descartes formátumban.
* **` == `**: a `equal` jel elválasztja mindkét egyenértékű ábrázolást.
* **`**********  `**: A magnitúdó grafikus ábrázolása, amelynek száma arányos az `*` állapot-vektor mérésének valószínűségével.
* **`[ 0.500000 ]`**: a magnitúdó numerikus értéke
* **`    ---`**: Az amplitúdó fázisának grafikus ábrázolása (lásd alább).
* **`[ 0.0000 rad ]`**: a fázis numerikus értéke (radiánban).

A magnitúdó és a fázis is grafikus ábrázolással jelenik meg. A magnitúdó ábrázolása egyenesen előre látható: egy sáv `*` , annál nagyobb a valószínűsége annak, hogy a sáv nagyobb lesz. A fázisban a következő szimbólumok jelennek meg, amelyek a tartományon alapuló szöget jelölik:

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

Az alábbi példák `DumpMachine` néhány gyakori állapotot mutatnak be:

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


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Létrehozhat egy qubit-azonosítót a Visual Studióban, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > az indextel rendelkező `0` qubit `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Az üzenetben megtalálhatja a qubit azonosítóját <xref:microsoft.quantum.intrinsic.message> , és átadhatja a qubit változót, például:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > amely a következő kimenetet eredményezheti:
  >```
  > 0=q:3; 1=q:2
  >```
  > Ez azt jelenti, hogy az indextel rendelkező qubit `0` `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>a <xref:microsoft.quantum.diagnostics> névtér része, ezért a használatához hozzá kell adnia egy `open` utasítást:

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

<xref:microsoft.quantum.diagnostics.dumpregister>ugyanúgy működik <xref:microsoft.quantum.diagnostics.dumpmachine> , mint például a qubits egy tömbjét is, amely korlátozza az információk mennyiségét, hogy csak a megfelelő qubits legyenek érvényesek.

A szolgáltatáshoz hasonlóan <xref:microsoft.quantum.diagnostics.dumpmachine> a által generált információk is a <xref:microsoft.quantum.diagnostics.dumpregister> célszámítógéptől függenek. Ahhoz, hogy a teljes állapotú kvantum-szimulátor a fájlba írja a Wave funkciót, a megadott qubits által generált kvantum alrendszer globális szakaszába kerül, amely ugyanabban a formátumban van <xref:microsoft.quantum.diagnostics.dumpmachine> .  Például: ismételje meg a gépet, amely csak két qubits foglal le, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt} \ket {2} {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ hívás <xref:microsoft.quantum.diagnostics.dumpregister> a következő kimenet előállítására `qubit[0]` :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

ezt a <xref:microsoft.quantum.diagnostics.dumpregister> kimenetet a következőre hívja `qubit[1]` elő:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot. Ebben az esetben <xref:microsoft.quantum.diagnostics.dumpregister> a következő üzenetet jeleníti meg:

```
Qubits provided (0;) are entangled with some other qubit.
```

Az alábbi példa bemutatja, hogyan használhatja a <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> Q # kódját:

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

A (z `Assert` ) és a `Dump` functions és az Operations (feladatok és műveletek) esetében a Q # a szabványos Visual Studio hibakeresési képességeinek egy részhalmazát támogatja: a [vonali töréspontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), a [kód az F10 használatával](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) történő [megvizsgálása és a klasszikus változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) mind lehetséges a szimulátorban.

A Visual Studio Code-ban a hibakeresés a C# által a OmniSharp által működtetett Visual Studio Code-bővítmény által biztosított hibakeresési képességeket használja, és a [legújabb verziót](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)kell telepítenie. 
