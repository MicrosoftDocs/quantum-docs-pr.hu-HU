---
title: Q# programok tesztelése és hibakeresése
description: Ismerje meg, hogyan használhatja az egységteszteket, tényeket és állításokat, valamint a memóriaképi függvényeket a kvantumprogramok teszteléséhez és hibakereséséhez.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030582"
---
# <a name="testing-and-debugging"></a>Tesztelés és hibakeresés

Csakúgy, mint a klasszikus programozás, elengedhetetlen, hogy képes legyen ellenőrizni, hogy a kvantum programok járnak elhivatott, és hogy képes diagnosztizálni a kvantum program, amely helytelen.
Ebben a részben a Q# által a kvantumprogramok tesztelésére és hibakeresésére szolgáló eszközöket fedjük le.

## <a name="unit-tests"></a>Egységvizsgálatok

A klasszikus programok tesztelésének egyik gyakori megközelítése az egységteszteknek nevezett kis programok *írása,* amelyek kódot futtatnak egy könyvtárban, és összehasonlítják a kimenetet néhány várható kimenettel.
Például, mi május akar `Square(2)` `4`-hoz biztosít amit visszatér , óta tudjuk *a priori* amit $2^2 = 4$.

A Q# támogatja a kvantumprogramok egységtesztjeinek létrehozását, és az [xUnit](https://xunit.github.io/) egységtesztelési keretrendszeren belül tesztként hajtható végre.

### <a name="creating-a-test-project"></a>Tesztprojekt létrehozása

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Nyissa meg a Visual Studio 2019-et. Lépjen a `File` menübe, és válassza a lehetőséget. `New`  >  `Project...`
A jobb felső sarokban `Q#`keresse meg `Q# Test Project` a t, és jelölje ki a sablont.

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A kedvenc parancssorból futtassa a következő parancsot:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Az új projekt egyetlen `Tests.qs`fájllal fog rendelkezni, amely kényelmes helyet biztosít az új Q# egységtesztek meghatározásához.
Kezdetben ez a fájl `AllocateQubit` tartalmaz egy minta egység teszt, amely{0}ellenőrzi, hogy egy újonnan lefoglalt qubit van a $\ket $ állapotban, és kinyomtatja az üzenetet:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: Minden Q# művelet vagy függvény, `Unit` amely `Unit` egy típusú argumentumot `@Test("...")` vesz fel, és visszatér, egységtesztként jelölhető meg az attribútumon keresztül. Az attribútum `"QuantumSimulator"` fenti argumentuma azt a célt határozza meg, amelyen a tesztet végrehajtják. Egyetlen teszt több célon is végrehajtható. Például adjon hozzá `@Test("ResourcesEstimator")` egy `AllocateQubit`fenti attribútumot. 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Mentse a fájlt, és hajtsa végre az összes tesztet. Most már két egységtesztnek kell lennie, az egyiken az AllocateQubit végrehajtása a QuantumSimulatoron, a másik pedig a ResourceEstimator ban. 

A Q# fordító a "QuantumSimulator", "ToffoliSimulator" és "ResourcesEstimator" beépített célokat az egységtesztek érvényes végrehajtási célként ismeri fel. Az egyéni végrehajtási cél definiálásához bármilyen teljesen minősített nevet is meg adhat. 

### <a name="running-q-unit-tests"></a>Q# egységtesztek futtatása

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Megoldásonként egyszer ként nyissa meg `Test` a menüt, és válassza a lehetőséget. `Test Settings`  >  `Default Processor Architecture`  >  `X64`

> [!TIP]
> A Visual Studio alapértelmezett processzorarchitektúrás beállítása`.suo`az egyes megoldások megoldásbeállításaiban ( ) tárolódik.
> Ha törli ezt a fájlt, akkor `X64` újra ki kell választania processzorarchitektúrának.

Készítse el a `Test` projektet, `Windows`  >  `Test Explorer`lépjen a menübe, és válassza a lehetőséget. `AllocateQubit`megjelenik a `Not Run Tests` csoportteszteinek listájában. Válassza `Run All` ki vagy futtassa ezt az egyedi tesztet, és át kell mennie!

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

A tesztek futtatásához keresse meg a projekt `Tests.csproj`mappáját (a tartalmazó mappát), és hajtsa végre a parancsot:

```bash
$ dotnet restore
$ dotnet test
```

A kimenetnek a következőhöz hasonlónak kell lennie:

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

Az egységtesztek a nevük és/vagy a végrehajtási cél szerint szűrhetők:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

A belső függvény <xref:microsoft.quantum.intrinsic.message> típusa `(String -> Unit)` van, és lehetővé teszi a diagnosztikai üzenetek létrehozását.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Miután végrehajtott egy tesztet a Test Explorerben, és rákattintott a tesztre, egy panel jelenik meg a tesztvégrehajtással kapcsolatos információkkal: Átadott/sikertelen állapot, eltelt idő és "Kimenet" hivatkozás. Ha a "Kimenet" hivatkozásra kattint, a tesztkimenet egy új ablakban nyílik meg.

![vizsgálati kimenet](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

Az egyes tesztek áthaladási/sikertelenségi `dotnet test`állapotát a rendszer kinyomtatja a konzolra.
Sikertelen tesztek esetén a kimenetek is kivannak nyomtatva a konzolra, hogy segítsenek diagnosztizálni a hibát.

***

## <a name="facts-and-assertions"></a>Tények és állítások

Mivel a Q# függvényeknek _nincsenek logikai_ mellékhatásai, a Q# programon belül `()` nem figyelhető meg olyan függvény végrehajtásának _bármely más,_ amelynek kimeneti típusa az üres tuple.
Ez azt jelenti, hogy a célgép dönthet `()` úgy, hogy nem hajt végre olyan függvényt, amely azzal a garanciával tér vissza, hogy ez a mulasztás nem módosítja a következő Q# kód viselkedését.
Ez a `()` függvények visszaadását (azaz `Unit`) hasznos eszközzé teszi az állítások beágyazásához és a logika Q# programokba való beágyazásához. 

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

Itt a `fail` kulcsszó azt jelzi, hogy a számítás nem folytatódhat, ami kivételt jelent a Q# programot futtató célgépben.
Definíció szerint egy ilyen hiba nem figyelhető meg a Q#-on belül, `fail` mivel a utasítás elérése után nem fut további Q# kód.
Így, ha haladunk tovább `PositivityFact`a hívást , akkor biztos lehet benne, hogy a bemenet pozitív volt.

Ne feledje, hogy ugyanazt a viselkedést valósíthatjuk meg, mint `PositivityFact` a függvény használata a [`Fact`](xref:microsoft.quantum.diagnostics.fact) <xref:microsoft.quantum.diagnostics> névtérből:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Az állításokat*viszont a tényekhez hasonlóan használják, de függhetnek a célgép állapotától. Ennek megfelelően ezek műveletekként vannak meghatározva, míg a tények függvényként vannak meghatározva (a fentiek szerint).
A különbségtétel megértéséhez vegye figyelembe egy tény következő használatát egy állításon belül:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Itt a műveletet <xref:microsoft.quantum.environment.getqubitsavailabletouse> arra használjuk, hogy visszaadjuk a használható qubitek számát.
Mivel ez egyértelműen függ a globális állapotát a program `AssertQubitsAreAvailable` és a végrehajtási környezet, a mi meghatározása kell egy művelet is.
Azonban használhatja, hogy a globális `Bool` állapot hozamegy `Fact` egyszerű értéket, mint bemenet a függvény.

Ezekre az ötletekre építve [az előjáték](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assert> két <xref:microsoft.quantum.intrinsic.assertprob> különösen hasznos állítást kínál, és mindkettő tikulizált műveletként. `()` Ezek az állítások mindegyike egy Pauli operátort vesz igénybe, amely leírja egy adott érdeklődési tételmérést, egy kvantumregisztert, amelyen a mérést el kell végezni, és egy hipotetikus eredményt.
A szimulációval működő célgépeken nem köt [minket a klónozás nélküli tétel,](https://en.wikipedia.org/wiki/No-cloning_theorem)és az ilyen méréseket anélkül tudjuk elvégezni, hogy megzavarnánk az ilyen állításoknak átadott nyilvántartást.
A szimulátor a fenti `PositivityFact` függvényhez hasonlóan megszakíthatja a számítást, ha a gyakorlatban nem figyelhető meg a hipotetikus eredmény:

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

A fizikai kvantum hardver, ahol a nem-klónozó tétel megakadályozza vizsgálata kvantum állapot, a `Assert` és `AssertProb` a műveletek egyszerűen vissza `()` más hatása nélkül.

A <xref:microsoft.quantum.diagnostics> névtér számos további `Assert` funkciót biztosít a családnak, amelyek lehetővé teszik számunkra, hogy ellenőrizzük a fejlettebb feltételeket. 

## <a name="dump-functions"></a>Kiírási függvények

A kvantumprogramok hibaelhárításának <xref:microsoft.quantum.diagnostics> elősegítése érdekében a névtér két olyan funkciót <xref:microsoft.quantum.diagnostics.dumpmachine> kínál, amelyek a célgép aktuális állapotát egy fájlba képesek kiönteni: és <xref:microsoft.quantum.diagnostics.dumpregister>. Az egyes létrehozott kimenet a célgéptől függ.

### <a name="dumpmachine"></a>DumpMachine

A Quantum Development Kit részeként elosztott teljes állapotú kvantumszimulátor a teljes kvantumrendszer [hullámfunkcióját](https://en.wikipedia.org/wiki/Wave_function) írja be a fájlba, mint egy dimenziós komplex számokat tartalmazó tömb, amelyben minden elem a számítási alapállapot ($\ket{n}$) mérésének valószínűségét jelöli, ahol $\ket{n} = \ket{b_{n-1}... b_1b_0}$ bitek\{b_i\}$. Például egy olyan gépen, amelyen csak két qubit van lefoglalva, és kvantumállapotban $${1}\begin{align}{2}\ket{\psi} = \frac {\sqrt }{00} \ket - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ hívás <xref:microsoft.quantum.diagnostics.dumpmachine> generálja ezt a kimenetet:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Az első sor a megfelelő qubitek azonosítóival a diszatematikusok jelentős sorrendjében tartalmaz megjegyzést.
A többi sor a $\ket{n}$ alapállapot-vektor mérésének valószínűségi amplitúdóját írja le descartes-i és poláris formátumban egyaránt. Részletesen az első sorban:

* **`∣0❭:`** ez a sor `0` megfelel a számítási alap állapotának
* **`0.707107 +  0.000000 i`**: a valószínűségi amplitúdó descartes-i formátumban.
* **` == `**: `equal` a megjelölés mindkét egyenértékű ábrázolást elhatogatja.
* **`**********  `**: A grafikus ábrázolása nagysága, `*` a szám arányos a valószínűsége, hogy ezt az állapotot vektor.
* **`[ 0.500000 ]`**: a magnitúdó számértéke
* **`    ---`**: Az amplitúdó fázisának grafikus ábrázolása (lásd alább).
* **`[ 0.0000 rad ]`**: a fázis numerikus értéke (radiánban).

Mind a magnitúdó, mind a fázis grafikus ábrázolással jelenik meg. A magnitúdó ábrázolása egyenesen `*`előre: ez azt mutatja, egy bár, annál nagyobb a valószínűsége, annál nagyobb a sáv lesz. A fázishoz a következő szimbólumokat jelenítjük meg, amelyek a szöget jelölik a tartományok alapján:

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

A következő `DumpMachine` példák néhány gyakori állapotot mutatnak be:

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
  > A qubit azonosítója futásidőben van hozzárendelve, és nem feltétlenül igazodik a qubit kiosztási sorrendjéhez vagy a qubit regiszterben elfoglalt pozíciójához.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > A Visual Studio-ban úgy találhat ki qubit id azonosítót, hogy egy töréspontot helyez el a kódban, és megvizsgálja egy qubit változó értékét, például:
  > 
  > ![show qubit id a Visual Studio-ban](~/media/qubit_id.png)
  >
  > a qubit `0` index `register2` be van`3`kapcsolva = `1` , az`2`indexes qubit id= .

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > A qubit id-t a <xref:microsoft.quantum.intrinsic.message> függvény használatával és az üzenetben lévő qubit változó átadásával lehet kitalálni, például:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > amely ezt a kimenetet generálhatja:
  >```
  > 0=q:3; 1=q:2
  >```
  > ami azt jelenti, hogy `0` `register2` a be-`3`és az indexes qubit id= , az indexes `1` qubit id=`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine>a névtér <xref:microsoft.quantum.diagnostics> része, ezért a használatához hozzá kell `open` adnia egy utasítást:

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

<xref:microsoft.quantum.diagnostics.dumpregister>működik, <xref:microsoft.quantum.diagnostics.dumpmachine>kivéve azt is tart egy sor qubits korlátozni az információ mennyisége, hogy csak a vonatkozó, hogy a megfelelő qubits.

A <xref:microsoft.quantum.diagnostics.dumpmachine>rendszerhez is a <xref:microsoft.quantum.diagnostics.dumpregister> rendszer által generált információ a célgéptől függ. A teljes állapotú kvantum szimulátor azt írja a fájlba a hullám funkció akár egy globális fázisa a kvantum al-rendszer által generált megadott qubits ugyanabban a formátumban, mint <xref:microsoft.quantum.diagnostics.dumpmachine>.  Például, hogy újra egy gép csak két qubitkiosztott és a kvantum állapot $$ \begin{align}{1}\ket{\psi} ={2}\frac {\sqrt } \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket `qubit[0]` {1} \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ), \end{align} $$ hívás <xref:microsoft.quantum.diagnostics.dumpregister> generálja ezt a kimenetet:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

és <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[1]` felhívás generálja ezt a kimenetet:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Általában egy másik regiszterbe gabalyodott regiszter állapota vegyes állapot, nem pedig tiszta állapot. Ebben az <xref:microsoft.quantum.diagnostics.dumpregister> esetben a következő üzenetet adja ki:

```
Qubits provided (0;) are entangled with some other qubit.
```

A következő példa bemutatja, <xref:microsoft.quantum.diagnostics.dumpregister> hogyan <xref:microsoft.quantum.diagnostics.dumpmachine> használhatja mindkettőt és a Q# kódot:

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

`Assert` A `Dump` q# a szabványos Visual Studio hibakeresési képességek egy részét támogatja: [sortörési pontok beállítása](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [kódváltás f10 használatával történő léptetése](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) és a klasszikus [változók értékeinek vizsgálata](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) a szimulátoron történő kódfuttatássorán lehetséges.

A Visual Studio Code hibakeresési funkciói a C# for Visual Studio Code bővítmény Által biztosított hibakeresési lehetőségeket használják, amelyeket az OmniSharp hajt, és a [legújabb verzió](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)telepítését igényli. 
