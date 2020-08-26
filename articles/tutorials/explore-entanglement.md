---
title: A felakadás megismerése Q#
description: Megtudhatja, hogyan írhat Quantum programot a alkalmazásban Q# . Bell-állapotot jelző alkalmazás fejlesztése a Quantum Development Kit (QDK) használatával
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: d815a9a25b8ba5e9489b6d3d27fb0d64ab4aaa1d
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863436"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Oktatóanyag: Összefonódások megismerése Q\# nyelven

Ebben az oktatóanyagban bemutatjuk, hogyan írhat olyan Q# programot, amely manipulálja és méri a qubits, és bemutatja a Felfekvés és a felakadás hatásait.

Írni fog egy Bell nevű alkalmazást a kvantum-összefonódás szemléltetése céljából.
A Bell név a Bell-állapotokra utal. Ezek két qubit konkrét kvantumállapotát jelentik, amelyekkel szemléltethetők a szuperpozíció és a kvantum-összefonódás legegyszerűbb példái.

## <a name="pre-requisites"></a>Előfeltételek

Ha készen áll a kódolásra, először végezze el a következő lépéseket: 

* [Telepítse](xref:microsoft.quantum.install) a Quantum Development Kit-t az előnyben részesített nyelvi és fejlesztési környezet használatával.
* Ha a QDK már telepítve van, győződjön meg arról, hogy a legújabb verzióra van [frissítve](xref:microsoft.quantum.update).

A QDK telepítése nélkül is követheti az elbeszélést, így áttekintheti a Q# programozási nyelv áttekintését és a kvantum-számítástechnika első fogalmait.

## <a name="in-this-tutorial-youll-learn-how-to"></a>Ebből az oktatóanyagból az alábbiakat sajátíthatja el:

> [!div class="checklist"]
> * Műveletek létrehozása és egyesítése a Q-ban\#
> * Hozzon létre olyan műveleteket, amelyek a qubits a helyükre helyezik, összekeverik és mérik.
> * Bemutatja a kvantum-felakadás egy Q# program futtatásával szimulátorban. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>A qubit viselkedésének bemutatása a QDK

Míg a hagyományos bit egyetlen bináris értéket hordoz, ami 0 vagy 1 lehet, a [qubit](xref:microsoft.quantum.glossary#qubit) állapota a 0 és az 1 érték közötti **szuperpozícióban** is lehet.  Elméletileg a qubit állapota absztrakt (más néven vektoros) térben is megtekinthető.  A qubit-állapot lehet a lehetséges irányok bármelyike. A két **klasszikus állapot** az a két irány, amelyek a 0 érték mérésének 100%-os esélyét és az 1 érték mérésének 100%-os esélyét jelentik.

A mérés ténye egy bináris eredményt ad, és megváltoztatja a qubit állapotát.
A mérés bináris értéket állít elő (0 vagy 1).  A qubit a szuperpozícióból (amely bármilyen irányú lehet) az egyik klasszikus állapotba kerül.  Ezt követően ugyanannak a mérésnek a megismétlése – ha időközben nem végeztünk el semmilyen más műveletet – ugyanazt a bináris eredményt adja.  

Több qubit [**össze is fonható**](xref:microsoft.quantum.glossary#entanglement).  Ha az összefonódott qubitek egyikéről mérést készítünk, a másik/többi állapotáról is információt kapunk.

Most már készen áll annak bemutatására, hogy Q# ez hogyan fejezi ki ezt a viselkedést.  A lehető legegyszerűbb programmal kezd, és azt építi fel a kvantum-szuperpozíció és a kvantum-összefonódás bemutatásához.

## <a name="creating-a-no-locq-project"></a>Projekt létrehozása Q#

Első lépésként hozzon létre egy új Q# projektet. Ebben az oktatóanyagban ezt a környezetet fogjuk használni a [ Q# vs Code-alkalmazások](xref:microsoft.quantum.install.standalone)alapján.

Új projekt létrehozásához a VS Code-ban: 

1. Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.
2. Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.
3. Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.
4. A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.

Ebben az esetben a projektet hívjuk `Bell` . Ez két fájlt hoz létre: `Bell.csproj` a projektfájlt és egy olyan `Program.qs` alkalmazás sablonját, Q# amelyet az alkalmazás írásához fogunk használni. A tartalomnak a `Program.qs` következőket kell tartalmaznia:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>A Q- \# alkalmazás írása
 
Célunk, hogy előkészítsünk két qubits egy konkrét kvantum-állapotban, amely azt mutatja be, hogyan lehet a qubits-ben működni, Q# hogy megváltoztassák az állapotukat, és bemutatják a Felfekvés és a felakadás hatását. A qubit-állapotok, a műveletek és a mérések bevezetéséhez egy darabot hozunk létre.

### <a name="initialize-qubit-using-measurement"></a>Qubit inicializálása mérés használatával

Az alábbi első kódban bemutatjuk, hogyan dolgozhat a qubits a alkalmazásban Q# .  Két műveletet fogunk bevezetni [`M`](xref:microsoft.quantum.intrinsic.m) , [`X`](xref:microsoft.quantum.intrinsic.x) amely átalakítja a qubit állapotát. Ebben a kódrészletben meghatározunk egy `SetQubitState` műveletet, amelynek egyik paramétere egy qubit, a másik pedig a `desired`, amely a qubit kívánt állapotát jelöli.  A `SetQubitState` művelet elvégez egy mérést a qubiten az `M` művelet használatával.  A-ben Q# a qubit-mérések mindig a vagy a értéket adja vissza `Zero` `One` .  Ha a mérés olyan értéket ad vissza, amely nem egyenlő a kívánt értékkel, a `SetQubitState` "megfordítja" a qubit, azaz végrehajt egy `X` műveletet, amely a qubit állapotát olyan új állapotra módosítja, amelyben a visszaadott mérés valószínűsége `Zero` és fordított állapotú `One` . Így mindig a `SetQubitState` kívánt állapotba helyezi a cél qubit.

Cserélje le a tartalmát a `Program.qs` következő kódra:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Most már meghívható ez a művelet, hogy egy qubitet egy klasszikus állapotba állítson, és az esetek 100%-ában kizárólag `Zero` vagy `One` eredményt adjon vissza.
A `Zero` és az `One` állandók, amelyek a qubit mérésének két lehetséges eredményét jelölik.

A `SetQubitState` művelet elvégzi a qubit mérését. Ha a qubit a kívánt állapotban van, a `SetQubitState` művelet békén hagyja. Ha nem, akkor pedig végrehajtja az `X` műveletet, amely a kívánt állapotba állítja a qubitet.

#### <a name="about-no-locq-operations"></a>Tudnivalók a Q# műveletekről

A Q# művelet egy kvantum-alrutin. Ez egy meghívásos rutin, amely más kvantum-műveletekre irányuló hívásokat is tartalmaz.

A műveletek argumentumai rekordként vannak meghatározva, zárójelek között.

A művelet visszatérési típusa a kettőspont után van meghatározva. Ebben az esetben a `SetQubitState` művelet nem ad vissza semmit, ezért a jelölése a következőt adja vissza: `Unit`. Ez egyenértékű az Q# `unit` F #-ban, amely nagyjából a C#-ban van, `void` és egy üres rekord ( `Tuple[()]` ) a Pythonban.

Az első művelet során két Quantum műveletet használt Q# :

* A [`M`](xref:microsoft.quantum.intrinsic.m) művelet, amely a qubit állapotát méri
* A [`X`](xref:microsoft.quantum.intrinsic.x) qubit állapotát tükröző művelet

A kvantumműveletek átalakítják a qubitek állapotát. Bizonyos esetekben a hagyományos logikai kapuk mintájára szokás kvantumkapukat emlegetni műveletek helyett. Ez a szokás a kvantum-számítástechnika korai időszakából ered, amikor az algoritmusok még csupán elméleti fogalmak voltak, és diagramként vizualizálták őket, hasonlóan a klasszikus számítástechnikában használt kapcsolási rajzokhoz.

### <a name="counting-measurement-outcomes"></a>Mérési eredmények számlálása

Ezután a `SetQubitState` művelet hatásának szemléltetésére a rendszer hozzáad egy `TestBellState` műveletet. Ennek a műveletnek a bemenete egy `Zero` vagy `One`. A művelet néhányszor meghívja a `SetQubitState` műveletet ezzel a bemenettel, és megszámolja, hogy a qubit mérése hányszor adott `Zero`, és hányszor `One` eredményt. Természetesen a `TestBellState` művelet első szimulációjától egy olyan kimenetet várunk, amely azt mutatja, hogy minden `Zero` bemeneti paraméterrel rendelkező qubit a `Zero` eredményt adja vissza, és minden `One` bemeneti paraméterrel rendelkező qubit az `One` eredményt. További bekapcsolás esetén a rendszer hozzáad egy kódot, amely `TestBellState` bemutatja a felfekvést és a felakadás.

Adja hozzá az alábbi műveletet a `SetQubitState` fájlhoz, a névtéren belül, a `Program.qs` művelet végén:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Vegye figyelembe, hogy a `return` ( `Message` ) [Microsoft. Quantum. belső. Message] függvénnyel egy, a-konzolon a (

Ennek a műveletnek (`TestBellState`) `count` iterációja ismétlődik, beállít egy megadott `initial` értéket egy qubiten, majd megméri (`M`) az eredményt. Statisztikát gyűjt arról, hogy hány nulla és egy értéket mért, és visszaküldi őket a hívónak. Még egy szükséges műveletet végrehajt. Visszaállítja a qubitet egy ismert állapotra (`Zero`), mielőtt visszaadja, hogy mások is lefoglalhassák ezt a qubitet egy ismert állapotban. Ez a `using` utasítás miatt szükséges.

#### <a name="about-variables-in-q"></a>A Q változók\#

Alapértelmezés szerint a változói Q# nem változtathatók meg; az értékük a kötés után nem módosítható. A nem módosítható változók kötése a `let` kulcsszóval jelölhető. A műveleti argumentumok soha nem módosíthatók.

Ha olyan változóra van szüksége, amelynek értéke módosítható (mint a `numOnes` a fenti példában), a `mutable` kulcsszóval deklarálhatja a változót. A módosítható változók értéke a `setQubitState` utasítással módosítható.

A változó típusát mindkét esetben a fordító következteti ki. Q# a változókhoz nem szükséges semmilyen típusú Megjegyzés.

#### <a name="about-using-statements-in-q"></a>A `using` Q utasításai\#

Az `using` utasítás szintén speciális Q# . Ezzel foglalhatók le qubitek a kódblokkokhoz. A-ben az Q# összes qubits dinamikusan van lefoglalva és felszabadítva, ahelyett, hogy rögzített erőforrásokkal rendelkezik egy összetett algoritmus teljes élettartama alatt. A `using` utasítás a blokk elején foglal le qubiteket, és a blokk végén felszabadítja őket.

## <a name="run-the-code-from-the-command-prompt"></a>Futtassa a kódot a parancssorból.

A kód futtatásához meg kell adnia azt a fordítót, *amely* a parancs megadásakor hívható `dotnet run` . Ez a fájl egyszerű módosításával történik Q# egy olyan vonal hozzáadásával, amely `@EntryPoint()` közvetlenül megelőzi a meghívót: a művelet ebben az `TestBellState` esetben. A teljes kódnak a következőket kell tennie:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

A program futtatásához meg kell adni a `count` parancssorból a és a `initial` argumentumot. Választhatja például a következőt: `count = 1000` és `initial = One` . Írja be a következő parancsot:

```dotnetcli
dotnet run --count 1000 --initial One
```

A következő kimenetnek kell megjelennie:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Ha a-vel próbálkozik, `initial = Zero` vegye figyelembe a következőket:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Szuperpozíció előkészítése

Most nézzük meg, hogyan Q# fejezheti be a qubits a saját pozícióban.  Emlékezzünk arra, hogy a qubitek állapota a 0 és az 1 értéket egyszerre lefedő szuperpozícióban is lehet.  Ennek eléréséhez a `Hadamard` műveletet használjuk. Ha a qubit valamelyik klasszikus állapotban van (amikor a mérések mindig `Zero` vagy mindig `One` értéket adnak vissza), akkor a `Hadamard` vagy `H` művelet olyan állapotba helyezi a qubitet, amelyben a mérések 50%-ban `Zero` és 50%-ban `One` eredményt adnak.  Alapjában véve a qubit úgy képzelhető el, hogy félúton van a `Zero` és az `One` között.  Ilyenkor a `TestBellState` művelet szimulálása esetén azt fogjuk látni, hogy a mérések nagyjából azonos alkalommal adják ki a `Zero` és az `One` értéket.  

### <a name="x-flips-qubit-state"></a>`X` qubit állapotának tükrözése

Először csak megpróbáljuk átállítani a qubitet (tehát ha `Zero` állapotban van, `One` állapotba állítjuk, és fordítva). Ezt úgy érhetjük el, ha végrehajtunk egy `X` műveletet, mielőtt megmérnénk az `TestBellState`-ben:

```qsharp
X(qubit);
let res = M(qubit);
```

A rendszer most visszafordítja az eredményeket:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Most vizsgáljuk meg a qubits kvantum-tulajdonságait.

### <a name="h-prepares-superposition"></a>`H` felkészíti a felfekvést

Mindössze le kell cserélnünk az előző futtatás `X` műveletét egy `H` vagy egy Hadamard-műveletre. Ahelyett, hogy 0-ról 1-re teljesen átállítani a qubitet, csak félig fordítjuk át. A `TestBellState`-ben most így néznek ki a lecserélt sorok:

```qsharp
H(qubit);
let res = M(qubit);
```

Az eredmények most még érdekesebbek:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Minden méréskor egy klasszikus értéket kérünk, de a qubit félúton van 0 és 1 között, így (statisztikailag) az esetek felében 0, a másik felében 1 értéket kapunk.
Ez az úgynevezett **szuperpozíció**, és az első valódi betekintést nyújtja a kvantumállapotba.

## <a name="prepare-entanglement"></a>Az összefonódás előkészítése

Most nézzük meg, hogyan Q# fejezi ki a qubits-k összekeverhető módjait.
Először is az első qubitet a kezdeti állapotba, majd a `H` művelettel szuperpozícióba kell állítanunk.  Ezután az első qubit mérése előtt egy új műveletet () használunk `CNOT` , amely a vezérlést nem jelenti.  Ha ezt a műveletet végrehajtjuk két qubiten, akkor a második qubit át lesz állítva, ha az első qubit `One` volt.  Ekkor a két qubit összefonódik.  Az első qubit statisztikái nem változnak (mérés esetén 50%-os eséllyel lesz `Zero` vagy `One`), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk. A `CNOT` összekapcsolta a két qubitet, így bármi is történik az egyikkel, ugyanaz történik a másikkal is. Ha felcseréli a méréseket (a második qubitet mérve az első előtt), akkor is ugyanez történik. Az első mérés eredménye véletlenszerű lesz, a második pedig mindig ugyanaz, mint amit az elsőnél kaptunk.

Első lépésként két qubits kell lefoglalni a következő helyett `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Így új műveletet (`CNOT`) adhatunk hozzá a mérés (`M`) előtt a `TestBellState`-ben:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Hozzáadtunk egy másik `SetQubitState` műveletet az első qubit inicializálásához, hogy biztosan mindig `Zero` állapotban legyen indításkor.

A felszabadítása előtt alaphelyzetbe is kell állítanunk a második qubitet.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

A teljes folyamatnak most így kell kinéznie:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

Az új visszaadott érték (`agree`) minden olyan alkalmat nyomon követ, amikor az első qubit mérési eredménye megegyezik a második kvantumbitével.

A beszerzett kód futtatása:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Ahogy az áttekintésben is említettük, az első qubit statisztikái nem változnak (50%-os eséllyel lesz 0 vagy 1), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk, mivel a két qubit össze van fonódva!

## <a name="next-steps"></a>További lépések

A megjelenő "a"-ben a a legelterjedtebb számítási algoritmusok segítségével [megtudhatja](xref:microsoft.quantum.quickstarts.search) , hogyan hozhatja létre és futtathatja a következőt: a a legtöbbet használt, legtöbbet a legtöbbet Q# kihasználó program, amely a kvantum-számítástechnikai  

[A Quantum Development Kit első lépéseinek](xref:microsoft.quantum.welcome) megismerése és a kvantummechanika további módjai Q# .
