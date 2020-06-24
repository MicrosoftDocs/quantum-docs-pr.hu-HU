---
title: Összefonódások megismerése Q# nyelven
description: Ismerje meg, hogyan írhat kvantumprogramot Q# nyelven. Bell-állapotot jelző alkalmazás fejlesztése a Quantum Development Kit (QDK) használatával
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 294366b884da93f11c60cfdbdce9b40cf5202b0d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274762"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Oktatóanyag: Összefonódások megismerése Q\# nyelven

Ebben az oktatóanyagban bemutatjuk, hogyan írhat olyan Q# nyelvű programot, amely qubiteket manipulál és mér meg, valamint szemlélteti a szuperpozíció és az összefonódás hatásait.
Az útmutató végigvezet a QDK telepítésén, a program létrehozásán, majd a program kvantumszimulátoron való végrehajtásán.  

Írni fog egy Bell nevű alkalmazást a kvantum-összefonódás szemléltetése céljából.
A Bell név a Bell-állapotokra utal. Ezek két qubit konkrét kvantumállapotát jelentik, amelyekkel szemléltethetők a szuperpozíció és a kvantum-összefonódás legegyszerűbb példái.

## <a name="prerequisites"></a>Előfeltételek

Ha készen áll a kódolásra, először végezze el a következő lépéseket: 

* Telepítse a [Pythonhoz](xref:microsoft.quantum.install.python) vagy a [.NET](xref:microsoft.quantum.install.cs)-hez készült Quantum Development Kitet.
* Ha a QDK már telepítve van, győződjön meg arról, hogy a legújabb verzióra van [frissítve](xref:microsoft.quantum.update).

A leírást a QDK telepítése nélkül is követheti, hogy áttekintést kapjon a Q# programozási nyelvről és a kvantum-számítástechnika alapvető koncepcióiról.

## <a name="demonstrating-qubit-behavior-with-q"></a>A qubitek viselkedésének szemléltetése a Q# segítségével

Emlékezzen vissza a [qubit egyszerű definíciójára](xref:microsoft.quantum.overview.understanding).  Míg a hagyományos bit egyetlen bináris értéket hordoz, ami 0 vagy 1 lehet, a [qubit](xref:microsoft.quantum.glossary#qubit) állapota a 0 és az 1 érték közötti **szuperpozícióban** is lehet.  Alapjában véve a qubit úgy képzelhető el, mint egy térbeli irány (más néven vektor).  A qubitek bármilyen lehetséges irányba mutathatnak. A két **klasszikus állapot** az a két irány, amelyek a 0 érték mérésének 100%-os esélyét és az 1 érték mérésének 100%-os esélyét jelentik.  Ennek a megjelenítésnek a formálisabb vizualizációja a [Bloch-gömb](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

A mérés ténye egy bináris eredményt ad, és megváltoztatja a qubit állapotát. A mérés egy bináris eredményt ad, amely 0 vagy 1 lehet.  A qubit a szuperpozícióból (amely bármilyen irányú lehet) az egyik klasszikus állapotba kerül.  Ezt követően ugyanannak a mérésnek a megismétlése – ha időközben nem végeztünk el semmilyen más műveletet – ugyanazt a bináris eredményt adja.  

Több qubit [**össze is fonható**](xref:microsoft.quantum.glossary#entanglement). Ha az összefonódott qubitek egyikéről mérést készítünk, a másik/többi állapotáról is információt kapunk.

Most már készen állunk annak szemléltetésére, hogy a Q# hogyan fejezi ki ezt a viselkedést.  A lehető legegyszerűbb programmal kezd, és azt építi fel a kvantum-szuperpozíció és a kvantum-összefonódás bemutatásához.

## <a name="setup"></a>Telepítés

Ez az oktatóprogram gazdaprogramokat használ, és két részből áll:

1. Több kvantumalgoritmusból, amelyek a Q# kvantumprogramozási nyelvvel lettek implementálva.
1. Egy gazdaprogramból, amely a Pythonhoz vagy a C# nyelven van implementálva, és amely a fő belépési pontként szolgál, valamint Q#-műveleteket hív meg a kvantumalgoritmusok végrehajtásához.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Válasszon egy helyet az alkalmazásnak

1. Hozzon létre egy `Bell.qs` nevű fájlt. Ez a fájl fogja tartalmazni a Q#-kódot.

1. Hozzon létre egy `host.py` nevű fájlt. Ez a fájl fogja tartalmazni a Python-gazdakódot.

#### <a name="c-command-line"></a>[C#-parancssor](#tab/tabid-csharp)

1. Új Q#-projekt létrehozása:

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Látható egy `.csproj` fájl, egy `Operations.qs` nevű Q#-fájl és egy `Driver.cs` nevű gazdaprogramot

1. A Q#-fájl átnevezése

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Új projekt létrehozása

   * A Visual Studio megnyitása
   * Lépjen a **Fájl** menübe, és válassza az **Új** -> **Projekt...** elemet.
   * A projektsablon intézőjében írja be a keresőmezőbe a(z) `Q#` kifejezést, majd válassza ki a(z) `Q# Application` sablont
   * Adja a projektnek a `Bell` nevet

1. A Q#-fájl átnevezése

   * Lépjen a **Megoldáskezelőbe**
   * Kattintson a jobb gombbal az `Operations.qs` fájlra
   * Nevezze át `Bell.qs` névre

* * *

## <a name="write-a-q-operation"></a>Q#-művelet írása

A célunk, hogy előkészítsünk két adott kvantumállapotú qubitet, és ezzel bemutassuk, hogyan módosítható a Q# használatával a qubitek állapota, és hogyan szemléltethetők a szuperpozíció és az összefonódás hatásai. Ezt darabonként fogjuk felépíteni a qubitek állapotának, műveleteinek és méréseinek bemutatása érdekében.

**Áttekintés:**  Az alább látható első kódban bemutatjuk, hogyan használható a Q# a qubitekhez.  Bemutatunk két műveletet – `M` és `X` –, amelyek átalakítják a qubitek állapotát. 

Ebben a kódrészletben meghatározunk egy `Set` műveletet, amelynek egyik paramétere egy qubit, a másik pedig a `desired`, amely a qubit kívánt állapotát jelöli.  A `Set` művelet elvégez egy mérést a qubiten az `M` művelet használatával.  A Q# használatakor a qubitek mérése mindig vagy `Zero` vagy `One` értéket ad vissza.  Ha a mérés által visszaadott érték nem egyenlő semelyik kívánt értékkel, a Set „megfordítja” a qubitet. Ez azt jelenti, hogy végrehajt egy `X` műveletet, amely módosítja a qubit állapotát, és az új állapotban megfordul annak a valószínűsége, hogy a mérés `Zero` vagy `One` értéket adjon vissza.  Ezután a `Set` művelet hatásának szemléltetésére a rendszer hozzáad egy `TestBellState` műveletet.  Ennek a műveletnek a bemenete egy `Zero` vagy `One`. A művelet néhányszor meghívja a `Set` műveletet ezzel a bemenettel, és megszámolja, hogy a qubit mérése hányszor adott `Zero`, és hányszor `One` eredményt. Természetesen a `TestBellState` művelet első szimulációjától egy olyan kimenetet várunk, amely azt mutatja, hogy minden `Zero` bemeneti paraméterrel rendelkező qubit a `Zero` eredményt adja vissza, és minden `One` bemeneti paraméterrel rendelkező qubit az `One` eredményt.  Később az `TestBellState` művelethez további kódot adunk hozzá a szuperpozíció és az összefonódás szemléltetése céljából.


### <a name="q-operation-code"></a>Q#-műveletkód

1. Cserélje le a Bell.qs fájl tartalmát a következő kódra:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Most már meghívható ez a művelet, hogy egy qubitet egy klasszikus állapotba állítson, és az esetek 100%-ában kizárólag `Zero` vagy `One` eredményt adjon vissza.  A `Zero` és az `One` állandók, amelyek a qubit mérésének két lehetséges eredményét jelölik.

    A `Set` művelet elvégzi a qubit mérését.
    Ha a qubit a kívánt állapotban van, a `Set` művelet békén hagyja. Ha nem, akkor pedig végrehajtja az `X` műveletet, amely a kívánt állapotba állítja a qubitet.

### <a name="about-q-operations"></a>A Q#-műveletek bemutatása

A Q#-műveletek kvantum-alrutinok. Vagyis meghívható rutinok, amelyek kvantumműveleteket tartalmaznak.

A műveletek argumentumai rekordként vannak meghatározva, zárójelek között.

A művelet visszatérési típusa a kettőspont után van meghatározva. Ebben az esetben a `Set` művelet nem ad vissza semmit, ezért a jelölése a következőt adja vissza: `Unit`. Ez a Q# nyelvű megfelelője az F# `unit` elemének, amely nagyjából hasonló a C# `void` és eleméhez a Python üres rekordjaihoz (`Tuple[()]`).

Az első Q#-műveletben két kvantumműveletet használt:

* Az [M](xref:microsoft.quantum.intrinsic.m) műveletet, amely megméri a qubit állapotát
* Az [X](xref:microsoft.quantum.intrinsic.x) műveletet, amely átállítja a qubit állapotát

A kvantumműveletek átalakítják a qubitek állapotát. Bizonyos esetekben a hagyományos logikai kapuk mintájára szokás kvantumkapukat emlegetni műveletek helyett. Ez a szokás a kvantum-számítástechnika korai időszakából ered, amikor az algoritmusok még csupán elméleti fogalmak voltak, és diagramként vizualizálták őket, hasonlóan a klasszikus számítástechnikában használt kapcsolási rajzokhoz.

### <a name="add-q-test-code"></a>Q#-tesztkód hozzáadása

1. Adja hozzá az alábbi műveletet a `Set` fájlhoz, a névtéren belül, a `Bell.qs` művelet végén:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Ennek a műveletnek (`TestBellState`) `count` iterációja ismétlődik, beállít egy megadott `initial` értéket egy qubiten, majd megméri (`M`) az eredményt. Statisztikát gyűjt arról, hogy hány nulla és egy értéket mért, és visszaküldi őket a hívónak. Még egy szükséges műveletet végrehajt. Visszaállítja a qubitet egy ismert állapotra (`Zero`), mielőtt visszaadja, hogy mások is lefoglalhassák ezt a qubitet egy ismert állapotban. Ez a `using` utasítás miatt szükséges.

### <a name="about-variables-in-q"></a>A Q# nyelvű változók bemutatása

A Q# változói alapértelmezés szerint nem módosíthatók; a kötésük után nem változtatható az értékük. A nem módosítható változók kötése a `let` kulcsszóval jelölhető. A műveleti argumentumok soha nem módosíthatók.

Ha olyan változóra van szüksége, amelynek értéke módosítható (mint a `numOnes` a fenti példában), a `mutable` kulcsszóval deklarálhatja a változót. A módosítható változók értéke a `set` utasítással módosítható.

A változó típusát mindkét esetben a fordító következteti ki. A Q#-ban nincs szükség a változók jegyzetekkel való ellátására.

### <a name="about-using-statements-in-q"></a>A Q# nyelvű `using` utasítások bemutatása

A `using` utasítás szintén a Q# nyelvre jellemző. Ezzel foglalhatók le qubitek a kódblokkokhoz. A Q#-ban az összes qubit lefoglalása és felszabadítása dinamikusan történik, tehát nem rögzített erőforrások, amelyek az összetett algoritmusok teljes élettartamára érvényesek. A `using` utasítás a blokk elején foglal le qubiteket, és a blokk végén felszabadítja őket.

## <a name="create-the-host-application-code"></a>A gazdaalkalmazás kódjának létrehozása

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Nyissa meg a `host.py` fájlt, és adja hozzá a következő kódot:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. Cserélje le a `Driver.cs` fájl tartalmát a következő kódra:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>A gazdaalkalmazás kódjának ismertetése

#### <a name="python"></a>[Python](#tab/tabid-python)

A Python-gazdaalkalmazás három részből áll:

* A kvantumalgoritmushoz szükséges összes argumentum kiszámítása. A példában a `count` 1000 értéken van rögzítve, és az `initial` a qubit kezdeti értéke.
* A kvantumalgoritmus futtatása az importált Q#-művelet `simulate()` metódusának meghívásával.
* A művelet eredményének feldolgozása. A példában a `res` kapja a művelet eredményét. Itt az eredmény a nullák (`num_zeros`) és egyesek (`num_ones`) szimulátor által mért számának a rekordja. A rekordot két mezőre bontjuk, és kiíratjuk az eredményeket.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

A C#-gazdaalkalmazás négy részből áll:

* Kvantumszimulátor létrehozása. A példában a `qsim` a szimulátor.
* A kvantumalgoritmushoz szükséges összes argumentum kiszámítása. A példában a `count` 1000 értéken van rögzítve, és az `initial` a qubit kezdeti értéke.
* A kvantumalgoritmus futtatása. Mindegyik Q#-művelet létrehoz egy azonos nevű C#-osztályt. Ez az osztály olyan `Run` metódussal rendelkezik, amely **aszinkron módon** hajtja végre a műveletet. A végrehajtás azért aszinkron módú, mert a tényleges hardveren végzett végrehajtás aszinkron módon fog történni. Mivel a `Run` metódus aszinkron módú, lekérjük a `Result` tulajdonságot; ez a feladat befejezéséig blokkolja a végrehajtást, és az eredményt szinkron módon adja vissza.
* A művelet eredményének feldolgozása. A példában a `res` kapja a művelet eredményét. Itt az eredmény a nullák (`numZeros`) és egyesek (`numOnes`) szimulátor által mért számának a rekordja. A rendszer ezt értékrekordként adja vissza C# nyelven. A rekordot két mezőre bontjuk, kiíratjuk az eredményeket, és megvárunk egy billentyűlenyomást.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Buildelés és futtatás

#### <a name="python"></a>[Python](#tab/tabid-python)

1. A terminálon futtassa a következő parancsot:

    ```
    python host.py
    ```

    Ez a parancs futtatja a gazdaalkalmazást, amely a Q#-műveletet szimulálja.

A következő eredmények jelennek meg:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Parancssor / Visual Studio Code](#tab/tabid-csharp)

1. A terminálon futtassa a következőt:

    ```dotnetcli
    dotnet run
    ```

    Ez a parancs automatikusan letölti az összes szükséges csomagot, buildeli az alkalmazást, majd futtatja a parancssorban.

1. Vagy nyomja le az **F1** billentyűt a Parancspaletta megnyitásához, és válassza a **Hibakeresés: Indítás hibakeresés nélkül** lehetőséget.
A rendszer kérheti egy új ``launch.json`` fájl létrehozását, amely leírja a program indításának módját.
Az alapértelmezett ``launch.json`` fájl a legtöbb alkalmazással megfelelően működik.

A következő eredmények jelennek meg:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Csak nyomja le az `F5` billentyűt, és a program létrejön és fut!

A következő eredmények jelennek meg:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Egy billentyű lenyomása után a program bezárul.

* * *

## <a name="prepare-superposition"></a>Szuperpozíció előkészítése

**Áttekintés** Most nézzük meg, hogyan fejezi ki a Q# a qubitek szuperpozícióba helyezésének különböző módjait.  Emlékezzünk arra, hogy a qubitek állapota a 0 és az 1 értéket egyszerre lefedő szuperpozícióban is lehet.  Ennek eléréséhez a `Hadamard` műveletet használjuk. Ha a qubit valamelyik klasszikus állapotban van (amikor a mérések mindig `Zero` vagy mindig `One` értéket adnak vissza), akkor a `Hadamard` vagy `H` művelet olyan állapotba helyezi a qubitet, amelyben a mérések 50%-ban `Zero` és 50%-ban `One` eredményt adnak.  Alapjában véve a qubit úgy képzelhető el, hogy félúton van a `Zero` és az `One` között.  Ilyenkor a `TestBellState` művelet szimulálása esetén azt fogjuk látni, hogy a mérések nagyjából azonos alkalommal adják ki a `Zero` és az `One` értéket.  

Először csak megpróbáljuk átállítani a qubitet (tehát ha `Zero` állapotban van, `One` állapotba állítjuk, és fordítva). Ezt úgy érhetjük el, ha végrehajtunk egy `X` műveletet, mielőtt megmérnénk az `TestBellState`-ben:

```qsharp
X(qubit);
let res = M(qubit);
```

Most (az `F5` lenyomása után) megfordulnak az eredmények:

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Azonban minden, amit eddig láttunk, klasszikus. Kérjünk le egy kvantumeredményt. Mindössze le kell cserélnünk az előző futtatás `X` műveletét egy `H` vagy egy Hadamard-műveletre. Ahelyett, hogy 0-ról 1-re teljesen átállítani a qubitet, csak félig fordítjuk át. A `TestBellState`-ben most így néznek ki a lecserélt sorok:

```qsharp
H(qubit);
let res = M(qubit);
```

Az eredmények most még érdekesebbek:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Minden méréskor egy klasszikus értéket kérünk, de a qubit félúton van 0 és 1 között, így (statisztikailag) az esetek felében 0, a másik felében 1 értéket kapunk. Ez az úgynevezett __szuperpozíció__, és az első valódi betekintést nyújtja a kvantumállapotba.

## <a name="prepare-entanglement"></a>Az összefonódás előkészítése

**Áttekintés:**  Most nézzek meg, hogyan fejezi ki a Q# a qubitek összefonódásának különböző módjait.  Először is az első qubitet a kezdeti állapotba, majd a `H` művelettel szuperpozícióba kell állítanunk.  Ezután, még mielőtt megmérnénk az első qubitet, végre kell hajtanunk egy új műveletet (`CNOT`), amelynek jelentése Controlled-Not (Nem szabályozott).  Ha ezt a műveletet végrehajtjuk két qubiten, akkor a második qubit át lesz állítva, ha az első qubit `One` volt.  Ekkor a két qubit összefonódik.  Az első qubit statisztikái nem változnak (mérés esetén 50%-os eséllyel lesz `Zero` vagy `One`), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk. A `CNOT` összekapcsolta a két qubitet, így bármi is történik az egyikkel, ugyanaz történik a másikkal is. Ha felcseréli a méréseket (a második qubitet mérve az első előtt), akkor is ugyanez történik. Az első mérés eredménye véletlenszerű lesz, a második pedig mindig ugyanaz, mint amit az elsőnél kaptunk.

Az első lépés, hogy 2 qubitet foglalunk le egy helyett a `TestBellState`-ben:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Így új műveletet (`CNOT`) adhatunk hozzá a mérés (`M`) előtt a `TestBellState`-ben:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Hozzáadtunk egy másik `Set` műveletet az első qubit inicializálásához, hogy biztosan mindig `Zero` állapotban legyen indításkor.

A felszabadítása előtt alaphelyzetbe is kell állítanunk a második qubitet.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

A teljes folyamatnak most így kell kinéznie:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Ha ezt lefuttatjuk, akkor pontosan ugyanazt a fifti-fifti eredményt fogjuk kapni, amit korábban is. Minket azonban az érdekel, hogy a második qubit hogyan reagál az első mérésére. Ez a statisztikát hozzáadjuk a `TestBellState` művelet új verziójához:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

Az új visszaadott érték (`agree`) minden olyan alkalmat nyomon követ, amikor az első qubit mérési eredménye megegyezik a második kvantumbitével. A gazdaalkalmazást is ennek megfelelően kell frissíteni:

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Most a parancs futtatásakor valami egészen különleges eredményt kapunk:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Ahogy az áttekintésben is említettük, az első qubit statisztikái nem változnak (50%-os eséllyel lesz 0 vagy 1), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk, mivel a két qubit össze van fonódva!

Gratulálunk, megírta az első kvantumprogramját!

## <a name="next-steps"></a>További lépések

A [Grover-keresés](xref:microsoft.quantum.quickstarts.search) című oktatóanyag ismerteti, hogyan lehet létrehozni és futtatni egy Grover-keresést, amely az egyik legnépszerűbb kvantum-számítástechnikai algoritmus, és remekül példázza, hogyan oldhatók meg valós problémák egy Q#-programmal és a kvantum-számítástechnika segítségével.  

A [Bevezetés a Quantum Development Kit használatába](xref:microsoft.quantum.welcome) című cikkben további módszereket is talál a Q# és a kvantumprogramozás elsajátítására.
