---
title: Tesztelés és hibakeresés
description: Megtudhatja, hogyan használhatók az egységes tesztek, a tények és a kijelentések, valamint a kvantum-programok tesztelésére és hibakeresésére szolgáló függvények.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 17a67f0a6fa7ffb9436828178acd93e1cb87a8cd
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233991"
---
# <a name="testing-and-debugging"></a>Tesztelés és hibakeresés

A klasszikus programozáshoz hasonlóan elengedhetetlen, hogy a kvantum-programok a kívánt módon működjenek, és hogy képes legyen diagnosztizálni a helytelen viselkedést.
Ebben a szakaszban a Q# kvantum-programok tesztelésére és hibakeresésére szolgáló eszközöket ismertetjük.

## <a name="unit-tests"></a>Egység tesztek

A klasszikus programok tesztelésének egyik gyakori módszere, ha olyan kisméretű programokat *ír,* amelyekben a kód egy könyvtárban fut, és a kimenetét egy bizonyos várt kimenethez hasonlítja össze.
Például gondoskodhat arról, hogy a visszaadott érték a következőt jeleníti meg: `Square(2)` `4` 1 – 2 ^ 2 = $4. *a priori*

Q# támogatja az egységek tesztelését a kvantum-programokhoz, és amelyek a [xUnit](https://xunit.github.io/) -egység tesztelési keretrendszerén belül is futtathatnak teszteket.

### <a name="creating-a-test-project"></a>Tesztelési projekt létrehozása

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Nyissa meg a Visual Studio 2019 alkalmazást. Lépjen a **fájl** menüre, és válassza az **új > projekt...** lehetőséget. A jobb felső sarokban keresse meg a `Q#` elemet, és válassza ki a **Q# teszt projekt** sablonját.

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A kedvenc parancssorában futtassa a következő parancsot:
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Az új projekt egyetlen fájllal rendelkezik `Tests.qs` , amely kényelmes helyet biztosít az új egység-tesztek definiálásához Q# .
Kezdetben ez a fájl egy minta egység tesztet tartalmaz, `AllocateQubit` amely ellenőrzi, hogy az újonnan lefoglalt qubit a $ \ket $ állapotban van-e, {0} és kinyomtat egy üzenetet:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Q#A Type és Returns argumentumot használó műveletek vagy függvények `Unit` `Unit` az attribútumon keresztül is megjelölhetik egységként `@Test("...")` . Az előző példában az attribútum argumentuma `"QuantumSimulator"` meghatározza azt a célt, amelyen a teszt fut. Egyetlen teszt több célponton is futhat. Adjon meg például egy attribútumot a `@Test("ResourcesEstimator")` előtt `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Mentse a fájlt, és futtassa az összes tesztet. Ekkor két egységre vonatkozó tesztnek kell lennie, amelyek közül az egyik, a pedig az `AllocateQubit` `QuantumSimulator` , ahol a fut `ResourcesEstimator` . 

A Q# fordító felismeri a beépített célokat `"QuantumSimulator"` , `"ToffoliSimulator"` és `"ResourcesEstimator"` érvényes futtatási célokat az egység-tesztekhez. A teljes nevet is megadhatja egy egyéni futtatási cél definiálásához. 

### <a name="running-no-locq-unit-tests"></a>Futó Q# egység tesztek

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Egyszeri egyszeri megoldás beállítása esetén lépjen a **teszt** menüre, és válassza a **tesztelési beállítások > az alapértelmezett processzor-architektúra > x64** elemet.

> [!TIP]
> A Visual Studio alapértelmezett processzor-architektúrájának beállítása az egyes megoldások megoldási beállítások ( `.suo` ) fájljában tárolódik.
> Ha törli ezt a fájlt, akkor a processzor architektúrája előtt ki kell választania az **x64** -et.

Hozza létre a projektet, nyissa meg a **teszt** menüt, és válassza a **Windows > test Explorer** lehetőséget. A **AllocateQubit** megjeleníti a tesztek listáját a **nem futtatott tesztek** csoportban. Válassza **az összes futtatása** lehetőséget, vagy futtassa ezt az egyéni tesztet.

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A tesztek futtatásához navigáljon a projekt mappájához (a mappát tartalmazó mappához `Tests.csproj` ), és futtassa a következő parancsot:

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

Az egységbeli tesztek a nevük vagy a futtatási cél szerint szűrhetők:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


**_

A belső függvény <xref:Microsoft.Quantum.Intrinsic.Message> típusa `(String -> Unit)` és engedélyezése lehetővé teszi a diagnosztikai üzenetek létrehozását.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Miután futtatott egy tesztet a test Explorerben, és rákattint a tesztre, megjelenik egy panel, amely a teszt futtatásával kapcsolatos információkat jeleníti meg: a Pass/Fail állapot, az eltelt idő és a kimenetre mutató hivatkozás. Kattintson az _ output * (*kimenet**) elemre a tesztelési kimenet új ablakban való megnyitásához.

![teszt kimenete](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

Az egyes tesztek esetén a Pass/Fail állapotot a konzolon kell kinyomtatni `dotnet test` .
A sikertelen tesztek esetén a kimenetek a konzolon is kinyomtathatók a hiba diagnosztizálásához.

**_

## <a name="facts-and-assertions"></a>Tények és kijelentések

Mivel a függvények Q# nem rendelkeznek _logikai_ mellékhatásokkal, a programon belül soha nem figyelheti meg, hogy egy adott Q# alkalmazásból más típusú effektusok is futnak, amelyek kimeneti típusa az üres rekord `()` .
Vagyis a célszámítógép dönthet úgy, hogy nem futtat olyan függvényt, amely visszaadja `()` azt a garanciát, hogy ez a mulasztás nem módosítja a következő Q# kódok viselkedését.
Ez a viselkedés lehetővé teszi, hogy a függvény visszaadja `()` (például `Unit` ) egy hasznos eszközt a bejelentésekhez és a hibakeresési logikához a Q# programokba. 

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

Itt a kulcsszó `fail` azt jelzi, hogy a számítás nem folytatódhat, és kivételt vet fel a programot futtató célszámítógépen Q# .
Definíció szerint az ilyen típusú hibák nem figyelhetők meg a belülről Q# , mert a célszámítógép már nem futtatja a Q# kódot egy utasítás elérése után `fail` .
Így ha folytatunk egy hívást a szolgáltatásba `PositivityFact` , biztos lehet abban, hogy a bemenete pozitív volt.

Vegye figyelembe, hogy ugyanaz a viselkedés valósítható meg, mint a `PositivityFact` [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) névtérből származó függvény használatával <xref:Microsoft.Quantum.Diagnostics> :

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

A _Assertions * másrészt a tényekhez hasonlóan használják, de a célszámítógép állapotától függően változhatnak. Ennek megfelelően a műveletekként vannak definiálva, míg a tények függvényekként vannak definiálva (ahogy az előző példában is látható).
A különbségtétel megértéséhez vegye figyelembe, hogy a következők valamelyikét kell használnia egy állításon belül:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Itt a műveletet használjuk a <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> rendelkezésre álló qubits számának visszaküldéséhez.
Mivel ez a program globális állapotától és a futtatási környezettől függ, a definíciójának is `AssertQubitsAreAvailable` egy műveletnek kell lennie.
Ezt a globális állapotot azonban használhatja arra, hogy egy egyszerű `Bool` értéket adjon meg bemenetként a `Fact` függvénynek.

Ezen ötletek alapján [a bevezetés](xref:microsoft.quantum.libraries.standard.prelude)két, különösen hasznos állítást kínál, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> és <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> mindkét modell a műveletekre épül `()` . Ezek a kijelentések mindegyike egy olyan Pauli-operátort mutat be, amely egy adott érdeklődési mérőszámot, egy kvantum-regisztrációt és egy feltételezett eredményt mutat be.
A szimuláció által végzett működést [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem)nem köti, és ezeket a méréseket anélkül hajthatja végre, hogy megzavarja a regisztrációt, amely megfelel az ilyen állításoknak.
A szimulátor ezután az `PositivityFact` előző függvényhez hasonló módon állíthatja le a számítást, ha a feltételezett eredmény nem figyelhető meg a gyakorlatban:

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Fizikai kvantum-hardveren, ahol a nem klónozási tétel megakadályozza a kvantum-állapot vizsgálatát, a `AssertMeasurement` és a `AssertMeasurementProbability` műveletek egyszerűen visszatérhetnek `()` más hatás nélkül.

A <xref:Microsoft.Quantum.Diagnostics> névtér több funkciót is biztosít a `Assert` család számára, amellyel további speciális feltételeket is megtudhat. 

## <a name="dump-functions"></a>Memóriakép függvények

A kvantum-programok hibaelhárításának elősegítése érdekében a <xref:Microsoft.Quantum.Diagnostics> névtér két olyan függvényt biztosít, amelyek a célszámítógép aktuális állapotát a következő fájlba tudják bemutatni: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> és <xref:Microsoft.Quantum.Diagnostics.DumpRegister> . A generált kimenet a célszámítógéptől függ.

### <a name="dumpmachine"></a>DumpMachine

A Quantum Development Kit részeként terjesztett teljes állapotú kvantum-szimulátor a teljes kvantum-rendszer [Wave függvényét](https://en.wikipedia.org/wiki/Wave_function) írja a komplex számok egydimenziós tömbje, amelyben az egyes elemek a számítás alapjául szolgáló "\ket{n} $" számítási valószínűségének amplitúdóját jelölik, ahol a $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ a BITS $ \{ b_i \} $ esetében. Például egy olyan gépen, amelyen csak két qubits van lefoglalva, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , a \end{align} $ $ hívás <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generálja ezt a kimenetet:

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
* **`    ---`**: Az amplitúdó fázisának grafikus ábrázolása (lásd a következő kimenetet).
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
  > A qubit azonosítója futásidőben van hozzárendelve, és nem feltétlenül igazodik azzal a sorrendtel, ahogy a qubit le lett foglalva, vagy a qubit-regisztráción belüli pozíciója.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > A Visual Studióban egy qubit-azonosítót is megtalálhat, ha egy töréspontot helyez el a kódban, és megvizsgál egy qubit változó értékét, például:
  > 
  > ![qubit-azonosító megjelenítése a Visual Studióban](~/media/qubit_id.png)
  >
  > az indextel rendelkező `0` qubit `register2` azonosító = `3` , a qubit with index `1` azonosítója = `2` .

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > A qubit megkeresheti a függvény használatával, és átadhatja <xref:Microsoft.Quantum.Intrinsic.Message> a qubit változót az üzenetben, például:
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


**_

Mivel <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a a névtér része  <xref:Microsoft.Quantum.Diagnostics> , hozzá kell adnia egy `open` utasítást az eléréséhez:

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

<xref:Microsoft.Quantum.Diagnostics.DumpRegister> ugyanúgy működik <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , mint az, hogy a qubits egy tömbjét is végrehajtja, amely az adatok mennyiségét csak a megfelelő qubits vonatkozó információkra korlátozza.

A szolgáltatáshoz hasonlóan <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a által generált információk is a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> célszámítógéptől függenek. Ahhoz, hogy a teljes állapotú kvantum-szimulátor a fájlba írja a Wave funkciót, a megadott qubits által generált kvantum alrendszer globális szakaszába kerül, amely ugyanabban a formátumban van <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .  Például: ismételje meg a gépet, amely csak két qubits foglal le, és a Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt} \ket {2} {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ hívás <xref:Microsoft.Quantum.Diagnostics.DumpRegister> a következő kimenet előállítására `qubit[0]` :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

ezt a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> kimenetet a következőre hívja `qubit[1]` elő:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Általánosságban elmondható, hogy egy másik regiszterrel összefoglalt regiszter állapota kevert állapot, nem pedig tiszta állapot. Ebben az esetben <xref:Microsoft.Quantum.Diagnostics.DumpRegister> a következő üzenetet jeleníti meg:

```
Qubits provided (0;) are entangled with some other qubit.
```

Az alábbi példa bemutatja, hogyan használható a kód a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> és <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a Q# kódban:

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

A (z `Assert` ) és a `Dump` functions és az Operations (funkciók és műveletek) esetében a Q# Visual Studio szabványos hibakeresési képességeinek egy részhalmazát támogatja: a [vonali töréspontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), az [F10 használatával történő léptetés](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), valamint a [klasszikus változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) mind lehetséges, ha a kódot a szimulátoron futtatják.

A Visual Studio Code-ban a hibakeresés a C# által a OmniSharp által működtetett Visual Studio Code-bővítmény által biztosított hibakeresési képességeket használja, és a [legújabb verziót](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)kell telepítenie. 
