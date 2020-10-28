---
title: Qubit programok írása és szimulálása a-ben Q#
description: Lépésenkénti oktatóanyag egy olyan kvantum-program írásához és szimulálásához, amely az egyes qubit szintjén működik
author: gillenhaalb
ms.author: a-gibec
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1bb66ae0fe7de785c417b0bef480e52adea5534d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691713"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Oktatóanyag: qubit-szintű programok írása és szimulálása a Q-ban\#

Üdvözöljük a Quantum Development Kit oktatóanyagban, amely egy alapszintű, egyedi qubits működő kvantum-program írását és szimulálása. 

Bár Q# elsődlegesen a nagy léptékű kvantum-programok magas szintű programozási nyelve lett létrehozva, a kvantum-programok alacsonyabb szintjének feltárására is használható: közvetlenül az adott qubits kezelése.
A rugalmasság Q# lehetővé teszi, hogy a felhasználók bármilyen ilyen szintű absztrakciót megközelítsék a kvantum-rendszereket, és ebben az oktatóanyagban magukra a qubits.
Pontosabban tekintse meg a [Quantum Fourier-transzformáció](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)csuklyáját, amely egy olyan alrutin, amely a sok nagyobb kvantum-algoritmus szerves részét képezi.

Vegye figyelembe, hogy a kvantum-adatok feldolgozásának alacsony szintű nézetét gyakran a "[Quantum áramkörök](xref:microsoft.quantum.concepts.circuits)" kifejezés írja le, amely a kapuk szekvenciális alkalmazását jelöli a rendszer adott qubits.

Így az egy-és többqubitos műveletek, amelyeket szekvenciálisan alkalmazunk, könnyen szerepelhetnek egy "áramköri diagramban".
Ebben az esetben egy műveletet határozunk meg Q# a teljes három qubit Quantum Fourier-transzformáció végrehajtásához, amely az alábbi, áramkörként szolgáló módon működik:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Előfeltételek

* [Telepítse](xref:microsoft.quantum.install) a Quantum Development Kit-t az előnyben részesített nyelvi és fejlesztési környezet használatával.
* Ha a QDK már telepítve van, győződjön meg arról, hogy a legújabb verzióra van [frissítve](xref:microsoft.quantum.update).


## <a name="in-this-tutorial-youll-learn-how-to"></a>Ebből az oktatóanyagból az alábbiakat sajátíthatja el:

> [!div class="checklist"]
> * Adja meg a kvantum-műveleteket a ben Q#
> * Műveletek meghívása Q# közvetlenül a parancssorból vagy egy klasszikus gazda program használatával
> * Quantum művelet szimulálása qubit-kiosztásból a mérési kimenetre
> * Figyelje meg, hogyan fejlődik a Quantum System szimulált wavefunction a művelet során

A Quantum program a Microsoft Quantum Development Kit-vel való futtatása általában két részből áll:
1. Maga a program, amely a Quantum programozási nyelv használatával lett megvalósítva Q# , majd egy kvantum-számítógépen vagy kvantum-szimulátoron futtatva fut. Ezek a következőkből állnak 
    - Q# műveletek: a kvantum-regisztráción alapuló alrutinok, és 
    - Q# függvények: a kvantum-algoritmuson belül használt klasszikus alrutinok.
2. A kvantum-program meghívásához használt belépési pont, és annak a célként megadott számítógépnek a megadása, amelyen futnia kell.
    Ezt közvetlenül a parancssorból vagy a klasszikus programozási nyelv, például a Python vagy a C# használatával írt gazda program segítségével teheti meg.
    Ez az oktatóanyag a tetszőleges módszerre vonatkozó utasításokat tartalmazza.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Qubits foglalása és a kvantum-műveletek definiálása

Az oktatóanyag első része a művelet definiálását jelenti Q# `Perform3qubitQFT` , amely a Quantum Fourier-transzformációt három qubits hajtja végre. 

Emellett a [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) függvény segítségével megfigyelheti, hogy a három qubit szimulált wavefunction hogyan fejlődik a művelet során.

Az első lépés a Q# projekt és a fájl létrehozása.
Az ehhez szükséges lépések a program meghívásához használt környezettől függenek, és a részleteket a megfelelő [telepítési útmutatókban](xref:microsoft.quantum.install)találja.

Lépésről lépésre végigvezeti a fájl összetevőin, de a kód az alábbi teljes blokkként is elérhető.

### <a name="namespaces-to-access-other-no-locq-operations"></a>Névterek más műveletekhez való hozzáféréshez Q#
Először a fájlban definiáljuk a névteret, `NamespaceQFT` amelyet a fordító fog elérni.
A meglévő műveletek használatának elvégzéséhez Q# nyissa meg a megfelelő `Microsoft.Quantum.<>` névtereket.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Műveletek definiálása argumentumokkal és visszaadott értékekkel
Ezután definiáljuk a `Perform3qubitQFT` műveletet:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Egyelőre a művelet nem vesz fel argumentumokat, és nem ad vissza semmit---ebben az esetben írunk, hogy egy olyan objektumot ad vissza `Unit` , amely a `void` C#-ban vagy egy üres rekordban van, `Tuple[()]` a Pythonban.
Később módosítjuk, hogy a mérési eredmények tömbjét adja vissza, ekkor a rendszer a következőt váltja ki: `Unit` `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Qubits foglalása a `using`
Q#A művelet keretében először három qubits-regisztrációt osztunk ki a `using` nyilatkozattal:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

A `using` esetében a qubits automatikusan le lesznek foglalva a $ \ket {0} $ állapotba. Ezt a és a használatával is [`Message(<string>)`](xref:Microsoft.Quantum.Intrinsic.Message) ellenőrizheti [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) , amely kinyomtat egy karakterláncot és a rendszer aktuális állapotát a konzolra.

> [!NOTE]
> A `Message(<string>)` és a `DumpMachine()` függvények (és/ [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) vagy [`Microsoft.Quantum.Diagnostics`](xref:Microsoft.Quantum.Diagnostics) ) egyaránt közvetlenül a konzolra nyomtathatnak. A tényleges kvantum-számításokhoz hasonlóan a nem Q# teszi lehetővé, hogy közvetlenül hozzáférhessenek a qubit állapotokhoz.
> `DumpMachine`A célszámítógép aktuális állapotának kinyomtatásakor azonban értékes információkat biztosíthat a hibakereséshez és a tanuláshoz, amikor a teljes állapotú szimulátorral együtt használja.


### <a name="applying-single-qubit-and-controlled-gates"></a>Qubit és vezérelt kapuk alkalmazása

Ezután alkalmazzuk a kaput, amely magában foglalja a műveletet.
Q# a névtérben már számos alapvető kvantum-kapu található [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) , és ezek nem kivételek. 

Egy Q# műveleten belül a callables meghívására szolgáló utasítások természetesen szekvenciális sorrendben lesznek futtatva.
Ezért az elsőként alkalmazandó kapu a [`H`](xref:Microsoft.Quantum.Intrinsic.H) (Hadamard) az első qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Ha egy műveletet egy adott qubit szeretne alkalmazni egy regiszterből (azaz egy `Qubit` tömbből), a `Qubit[]` szabványos index jelölést használjuk.
Tehát a [`H`](xref:Microsoft.Quantum.Intrinsic.H) regisztráció első qubit a következő formában kell alkalmazni `qs` :

```qsharp
            H(qs[0]);
```

A `H` (Hadamard) kapunak az egyes qubits való alkalmazása mellett a QFT-áramkör elsősorban vezérelt [`R1`](xref:Microsoft.Quantum.Intrinsic.R1) forgásokból áll.
Egy `R1(θ, <qubit>)` általános művelet változatlanul hagyja a qubit $ \ket {0} $ összetevőjét, miközben a ($e ^ {i\theta} $ elforgatását alkalmazza a $ \ket {1} $ összetevőre.

#### <a name="controlled-operations"></a>Vezérelt műveletek

Q# lehetővé teszi a művelet futtatásának feltételét egy vagy több vezérlő qubits.
Általánosságban elmondható, hogy a hívás a következővel van ellátva `Controlled` , és a Műveleti argumentumok a következőképpen változnak:

 `Op(<normal args>)` $ \to $ `Controlled Op([<control qubits>], (<normal args>))` .

Vegye figyelembe, hogy a vezérlő qubits tömbként kell megadni, még akkor is, ha az egyetlen qubit.

A után `H` láthatjuk, hogy a következő kapuk az `R1` első qubit eljáró kapuk (és a második/harmadik által vezérelt):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Ezeket a következővel hívjuk

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Vegye figyelembe, hogy a [`PI()`](xref:Microsoft.Quantum.Math.PI) függvényt a [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) névtérből használjuk a PI radiánban kifejezett rotációk definiálásához.
Emellett a `Double` következőt osztjuk (például `2.0` ), mert egy egész számmal való osztás `2` hibát jelez. 

> [!TIP]
> `R1(π/2)` és `R1(π/4)` egyenértékűek a `S` és a `T` műveletekkel (a-ben is `Microsoft.Quantum.Intrinsic` ).


A kapcsolódó `H` műveletek és a vezérelt rotációk alkalmazása után a második és a harmadik qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

[`SWAP`](xref:Microsoft.Quantum.Intrinsic.SWAP)az áramkör betöltéséhez csak egy kaput kell alkalmazni:

```qsharp
            SWAP(qs[2], qs[0]);
```

Erre azért van szükség, mert a Quantum Fourier-transzformáció természete fordított sorrendben jeleníti meg a qubits, így a Swapek lehetővé teszik a rutinok zökkenőmentes integrálását a nagyobb algoritmusokra.

Ezért befejeztük a Quantum Fourier-transzformáció qubit-műveletének írását a Q# műveletbe:

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

De nem hívhatunk meg egy napot.
A qubits a \ket $ állapotban voltak {0} , amikor kiosztottuk őket, és hasonlóan az életben is, ugyanúgy Q# kell elhagyni a dolgokat, ahogy azt találtuk (vagy még jobb!).

### <a name="deallocate-qubits"></a>Qubits felszabadítása

A [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) művelet elvégzése előtt ismét meghívjuk a művelet utáni állapotot, végül pedig [`ResetAll`](xref:Microsoft.Quantum.Intrinsic.resetall) a qubit-regisztrációra, hogy alaphelyzetbe állítsa a qubits $ \ket $-re a következő {0} művelet végrehajtása előtt:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Annak megkövetelése, hogy az összes fel nem foglalt qubits legyen explicit módon beállítva a $ \ket $ értékre {0} Q# , mivel ez lehetővé teszi, hogy más műveletek pontosan megismerjék az állapotukat, amikor megkezdik az azonos qubits (kevés erőforrás) használatát.
Ez azt is biztosítja, hogy a rendszer semmilyen más qubits ne legyen összekeverve.
Ha az alaphelyzetbe állítást a foglalási blokk végén nem hajtja végre, a rendszer `using` futásidejű hibát jelez.

A teljes Q# fájlnak így kell kinéznie:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


A Q# fájl és a művelet befejezése után a Quantum program készen áll a hívásra és a szimulált állapotra.

## <a name="run-the-program"></a>A program futtatása

Miután definiálta a Q# műveletet egy `.qs` fájlban, most meg kell hívnia ezt a műveletet, és figyelnie kell a visszaadott klasszikus adattípusokat.
Egyelőre nem ad vissza semmit (ne felejtse el, hogy a fent megadott művelet visszaadja `Unit` a műveletet), de ha később módosítjuk a Q# műveletet a mérési eredmények () egy tömbje visszaadására `Result[]` , ezt a megoldást fogjuk kezelni.

Míg a Q# program a meghívásához használt környezetek között mindenütt elérhető, ennek a módja természetesen változhat. Ezért egyszerűen kövesse a beállításnak megfelelő lapon található utasításokat: az alkalmazásból való munka vagy a Q# Python-vagy C#-beli gazda program használata.

#### <a name="command-prompt"></a>[Parancssor](#tab/tabid-cmdline)

A Q# program parancssorból való futtatásához csak kis módosításra van szükség a Q# fájlban.

Egyszerűen vegyen fel `@EntryPoint()` egy sort a művelet definícióját megelőzően:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

A program futtatásához nyissa meg a terminált a projekt mappájában, és írja be a következőt:

```dotnetcli
dotnet run
```

A befejezést követően a és a `Message` `DumpMachine` kimenetek a konzolon láthatók.


#### <a name="python"></a>[Python](#tab/tabid-python)

Hozzon létre egy Python-gazda fájlt: `host.py` .

A gazda fájl a következőképpen lett kiépítve: 
1. Először importáljuk a `qsharp` modult, amely regisztrálja a modul-betöltőt az Q# együttműködési képességhez. 
    Ez lehetővé teszi Q# , hogy a névterek (például a `NamespaceQFT` fájlban definiált Q# ) Python-modulokként jelenjenek meg, amelyből importálhat Q# műveleteket.
2. Ezután importálja Q# azokat a műveleteket, amelyeket a rendszer közvetlenül hív meg---ebben az esetben `Perform3qubitQFT` .
    Csak a beléptetési pontot kell importálnia egy Q# programba (például _nem_ olyan műveletekre, mint a `H` és `R1` , amelyeket más műveletek hívnak meg, Q# de a klasszikus gazdagép soha nem).
3. A Q# műveletek vagy függvények szimulálása során az űrlap használatával `<Q#callable>.simulate(<args>)` futtassa őket a `QuantumSimulator()` célszámítógépen. 

> [!NOTE]
> Ha azt szeretnénk, hogy egy másik gépen, például a-ben hívjuk a műveletet, `ResourceEstimator()` egyszerűen használjuk a következőt: `<Q#callable>.estimate_resources(<args>)` .
> Általánosságban elmondható, Q# hogy a műveletek a futtatott gépektől függetlenek, de bizonyos funkciók, például `DumpMachine` eltérően viselkednek.

4. A szimuláció végrehajtásakor a művelet hívása a fájlban meghatározott értékeket ad vissza Q# .
    Egyelőre nem tért vissza, de később láthatjuk az értékek hozzárendelésének és feldolgozásának példáját.
    A kezünkben és a klasszikusan megjelenő eredményekkel bármit megtehetünk, amit szeretne.

A teljes `host.py` fájlnak a következőnek kell lennie:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Futtassa a Python-fájlt, és nyomtassa ki a konzolon az `Message` `DumpMachine` alábbi és kimenetek láthatók. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

A [telepítési útmutatóban](xref:microsoft.quantum.install.cs)szereplő utasításokat követve hozzon létre egy C#-gazdagépet, és nevezze át a következőre: `host.cs` .

A C#-gazdagép négy részből áll:
1. Kvantumszimulátor létrehozása.
    Az alábbi kódban ez a változó `qsim` .
2. A kvantumalgoritmushoz szükséges összes argumentum kiszámítása.
    Ebben a példában nincs ilyen.
3. A kvantumalgoritmus futtatása. 
    Minden Q# művelet létrehoz egy azonos nevű C#-osztályt. 
    Ez az osztály olyan `Run` metódust tartalmaz, amely **aszinkron módon** futtatja a műveletet.
    A Futtatás aszinkron, mert a tényleges hardveren való futtatása aszinkron módon történik. 
    Mivel a `Run` metódus aszinkron módon van meghívva, a `Wait()` metódust hívjuk. ez letiltja a futtatást, amíg a feladat be nem fejeződik, és szinkron módon visszaadja az eredményt. 
4. Dolgozza fel a művelet visszaadott eredményét.
    Egyelőre a művelet nem ad vissza semmit.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Futtassa az alkalmazást, és a kimenetnek meg kell egyeznie az alábbi értékkel.
Egy billentyű lenyomása után a program bezárul.
**_

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Ha a teljes állapotú szimulátorra hívja fel a hívást, a a `DumpMachine()` Quantum State wavefunction adatforrásként-ábrázolását adja meg. Egy $n $-qubit rendszer lehetséges állapotai a $2 ^ n $ számítási alapú állapotok szerint jeleníthetők meg, amelyek mindegyike egy megfelelő összetett együtthatóval (egyszerűen egy amplitúdóval és egy szakasszal) rendelkezik.
A számítási állapot megfelel az összes lehetséges bináris sztringnek, $n $---, amely a qubit-állapotok összes lehetséges kombinációja $ \ket {0} $ és $ \ket {1} $, ahol az egyes bináris számjegyek egy adott qubit felelnek meg.

Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.
A Qubit a `2` "legjelentősebb" érték azt jelenti, hogy az alapul szolgáló \ket{i} $ bináris ábrázolásban a Qubit állapota `2` a bal szélső számjegynek felel meg. Például a $ \ket {6} = \ket {110} $ a qubits és a $ `2` `1` \ket {1} $ és a qubit $ `0` \ket {0} $ értéket tartalmazza.


A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{i} $ és a poláris formátumban egyaránt.
A bemeneti állapot első sorában, a $ \ket {000} $: _ értéknél **`|0>:`** Ez a sor a `0` számítási alap állapotnak felel meg (mivel a kezdeti állapot utáni kiosztása $ \ket {000} $ volt, azt várnánk, hogy ez az egyetlen olyan állapot, amelynek a valószínűségi amplitúdója ezen a ponton).
* **`1.000000 +  0.000000 i`** : a valószínűségi amplitúdója Descartes formátumban.
* **` == `** : a `equal` jel elválasztja mindkét egyenértékű ábrázolást.
* **`********************`** : A magnitúdó grafikus ábrázolása, amelynek száma arányos az `*` állapot-vektor mérésének valószínűségével. 
* **`[ 1.000000 ]`** : a magnitúdó numerikus értéke
* **`    ---`** : Az amplitúdó fázisának grafikus ábrázolása.
* **`[ 0.0000 rad ]`** : a fázis numerikus értéke (radiánban).

A magnitúdó és a fázis is grafikus ábrázolással jelenik meg. A magnitúdó ábrázolása egyszerű: megmutatja, hogy egy sáv `*` , annál nagyobb a valószínűsége, annál nagyobb lesz a sáv. A fázisban tekintse meg a [tesztelés és hibakeresés: kiírási függvények](xref:microsoft.quantum.guide.testingdebugging#dump-functions) a lehetséges szimbólum-ábrázolásokhoz a szög tartományai alapján lehetőséget.


A kinyomtatott kimenet tehát azt szemlélteti, hogy a programozott kapuk átalakították az állapotukat

$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $

a következőre: 

$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

Ez pontosan a 3 qubit Fourier-transzformáció viselkedését képezi. 

Ha kíváncsi a más bemeneti állapotokra is, javasoljuk, hogy játsszon a qubit-műveletek alkalmazásával a transzformáció előtt.

## <a name="adding-measurements"></a>Mérések hozzáadása

Sajnos a kvantummechanika sarokköve azt jelzi, hogy egy valódi Quantum rendszernek nem lehet ilyen `DumpMachine` funkciója. Ehelyett a mérések segítségével kell kinyerni az adatokat, amelyek általánosságban nem csak a teljes kvantum-állapotot biztosítják, de a rendszer is jelentősen megváltoztatható.
Számos kvantum-mérés létezik, de az alapszintű: az egyetlen qubits kivetítéses mérésekre koncentrálunk.
A mérések egy adott alapon (például a $ \{ \ket {0} , \ket {1} \} $) számított érték alapján a qubit-állapotot a rendszer az adott állapotban mérte meg,---így megsemmisíti a kettő közötti felfekvést.

A programokon belüli mérések megvalósításához Q# a `M` (kezdő) műveletet használjuk `Microsoft.Quantum.Intrinsic` , amely egy `Result` típust ad vissza.

Először is módosítjuk a `Perform3QubitQFT` műveletet, hogy a függvény helyett a mérési eredmények egy tömbjét adják vissza `Result[]` `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Tömb definiálása és inicializálása `Result[]`

A qubits (azaz az utasítás előtt) lefoglalása előtt `using` deklaráljuk és kössük ezt a hossz-3 tömböt (egyet `Result` az egyes qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

A `mutable` `resultArray` megjelenő kulcsszó lehetővé teszi, hogy a változó később a kódban legyen felkötve---például a mérési eredmények hozzáadásakor.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Mérések végrehajtása `for` hurokban és eredmények hozzáadása a tömbhöz

A blokkon belüli Fourier-transzformációs műveletek után `using` szúrja be a következő kódot:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
A tömbben [`IndexRange`](xref:Microsoft.Quantum.Arrays.IndexRange) hívott függvény (például a qubits tömbje `qs` ) a tömbben lévő indexek tartományát adja vissza. Itt használjuk a `for` hurokban, hogy szekvenciálisan mérjük az egyes qubit az utasítás használatával `M(qs[i])` .
Az egyes mért `Result` típusok ( `Zero` vagy `One` ) bekerülnek a megfelelő index helyére `resultArray` egy Update-and-reassign utasítással.

> [!NOTE]
> Az utasítás szintaxisa egyedi Q# , de megfelel a hasonló változó ismételt hozzárendelésének, `resultArray[i] <- M(qs[i])` más nyelveken, például F # és R nyelven.

A kulcsszó `set` mindig a használatával kötött változók ismételt hozzárendelésére szolgál `mutable` .

#### <a name="return-resultarray"></a>Visszatérési `resultArray`

Mind a három qubits, mind a hozzá tartozó eredmények alapján a `resultArray` qubits alaphelyzetbe állítása és felszabadítása is biztonságos.
A `using` blokk bezárását követően szúrja be a következőt

```qsharp
        return resultArray;
```
végső soron a művelet eredményét adja vissza. 

### <a name="understanding-the-effects-of-measurement"></a>A mérés következményeinek megértése

Módosítsa a függvények elhelyezését `DumpMachine` , hogy az állapotot a mérések előtt és után adja vissza.
A végső műveleti kódnak a következőhöz hasonlóan kell kinéznie: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Ha a parancssorból dolgozik, a visszaadott tömb egyszerűen a Futtatás végén közvetlenül a konzolon jelenik meg.
Ellenkező esetben frissítse a gazdagép programját a visszaadott tömb feldolgozásához.

#### <a name="command-prompt"></a>[Parancssor](#tab/tabid-cmdline)

Ha jobban meg szeretné ismerni a visszaadott tömböt, amelyet a konzolon fog kinyomtatni, a `Message` következő utasítás előtt hozzáadhat egy másikat a Q# fájlhoz `return` :

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Futtassa a projektet, és a kimenetnek a következőhöz hasonlóan kell kinéznie:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Frissítse Python-programját a következőre:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Futtassa a fájlt, és a kimenetnek a következőhöz hasonlóan kell kinéznie:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Most, hogy a művelet visszaad egy eredményt, cserélje le a metódust a `Wait()` tulajdonság beolvasására `Result` . Ez továbbra is ugyanazokat a szinkronkat hajtja végre, mint korábban, és ezt az értéket közvetlenül a változóhoz kötheti `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Futtassa a projektet, és a kimenetnek a következőhöz hasonlóan kell kinéznie:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Ez a kimenet néhány különböző dolgot mutat be:
1. A visszaadott eredménynek az előzetes méréssel való összevetése `DumpMachine` egyértelműen _nem_ mutatja be az QFT utáni pozíciót az alapállapotok alapján.
    A mérések csak egyetlen alap állapotot adnak vissza, amelynek valószínűségét az adott állapot amplitúdója határozza meg a rendszer wavefunction.
2. Az utólagos mérés után azt `DumpMachine` látjuk, hogy a mérés magára az állapotra _változik_ , és az alapszintű, a mért értéknek megfelelő egységes állapotba állítja azt.

Ha többször is megismétli ezt a műveletet, akkor az eredmények statisztikái megkezdik a QFT-állapot ugyanilyen súlyozott feltételét, amely az egyes lövések véletlenszerű eredményét idézi elő.
_Azonban_ a nem hatékony és még mindig nem tökéletes, ezért csak az alapállapotok relatív amplitúdóit fogja reprodukálni, nem a közöttük lévő relatív fázisokat.
Az utóbbi nem jelent problémát ebben a példában, de a relatív fázisok akkor jelennek meg, ha a QFT összetettebb inputot kap a $ \ket {000} $ értéknél.

#### <a name="partial-measurements"></a>Részleges mérések 
Annak megismeréséhez, hogy a regisztráció egyes qubits milyen hatással lehetnek a rendszerek állapotára, próbálja meg hozzáadni a következőt a `for` hurokon belül a mérési sor után:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Vegye figyelembe, hogy a `IntAsString` hozzáadni kívánt függvény eléréséhez hozzá kell adnia 
```qsharp
    open Microsoft.Quantum.Convert;
```
a többi névtér- `open` utasítással.

Az eredményül kapott kimenetben látni fogja a fokozatos kivetítést az alterületekre, ahogy az egyes qubit mérik.


## <a name="use-the-no-locq-libraries"></a>A Q# kódtárak használata
Ahogy azt a bevezetésben is említettük, a nagy része az, Q# hogy lehetővé teszi, hogy elvonta az egyes qubits foglalkozó aggodalmakat.
Ha teljes körű, alkalmazható kvantum-programokat szeretne fejleszteni, ne aggódjon, hogy egy `H` adott művelet egy adott rotáció előtt vagy után leáll-e. 

A Q# kódtárak tartalmazzák a [QFT](xref:Microsoft.Quantum.Canon.QFT) műveletet, amely egyszerűen elvégezhető, és tetszőleges számú qubits alkalmazható.
A kipróbáláshoz adjon meg egy új műveletet a Q# fájlban, amelynek a tartalma megegyezik `Perform3QubitQFT` , de az elsőtől `H` a `SWAP` helyébe két egyszerű sor lép:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
Az első sor egyszerűen létrehoz egy [`BigEndian`](xref:Microsoft.Quantum.Arithmetic.BigEndian) kifejezést a qubits lefoglalt tömbből, `qs` amely a [QFT](xref:Microsoft.Quantum.Canon.QFT) művelet argumentumként való végrehajtása.
Ez megfelel a regisztrációban szereplő qubits index szerinti rendezésének.

Ahhoz, hogy hozzáférhessenek ezekhez a műveletekhez, adja hozzá a `open` megfelelő névterekhez tartozó utasításokat a fájl elejéhez Q# :
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Most állítsa be úgy a gazda programot, hogy meghívja az új művelet nevét (pl. `PerformIntrinsicQFT` ), és adjon neki egy örvényt.

Ha szeretné megtekinteni a Q# könyvtári műveletek valódi előnyeit, módosítsa a qubits számát a következőre `3` :
```qsharp
        mutable resultArray = new Result[4];

        using (qs = Qubit[4]) {
            //...
        }
```
Így alkalmazhatja a megfelelő QFT az adott számú qubits, anélkül, hogy aggódnia kellene az új `H` műveletek és Forgások az egyes qubit.

Vegye figyelembe, hogy a Quantum Simulator exponenciálisan több időt vesz igénybe a qubits számának növelésével,---pontosan miért várjuk a valódi kvantum-hardvereket!
