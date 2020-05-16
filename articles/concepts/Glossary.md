---
title: Quantum Computing – Szószedet
description: A Quantum computingban használt általános feltételek, műveletek és objektumok glosszáriuma.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: cbc473eb14d8afd255a7072475dc054e18b98e3e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426704"
---
# <a name="quantum-computing-glossary"></a>Quantum Computing – Szószedet

## <a name="adjoint"></a>Adjoint

Egy [művelet](xref:microsoft.quantum.glossary#operation)összetett konjugált átültetése. Az [egységes](xref:microsoft.quantum.glossary#unitary-operator) operátort megvalósító műveletek esetében a adjoint a művelet inverze, és egy tőr szimbólum jelzi. Ha például a művelet `U` az egységes operátort jelöli $U $, akkor a `Adjoint U` $U ^ \dagger $ értéket jelöli. További információ: [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

Egy [qubit](xref:microsoft.quantum.glossary#qubit) , amely ideiglenes memóriát szolgál a kvantum-számítógép számára, és igény szerint le van foglalva és le van foglalva.  További információ: [több qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Harang állapota

Két qubits négy specifikus, maximálisan [összekeverhető](xref:microsoft.quantum.glossary#entanglement) [Quantum állapotának](xref:microsoft.quantum.glossary#quantum-state) egyike. A négy állapot definiálva van $ \ket{\ beta_ {ij}} = (\mathbb{I} \otimes X ^ iZ ^ j) (\ket {00} + \ket {11} )/\sqrt {2} $. A Bell-állapotot [EPR-pároknak](xref:microsoft.quantum.glossary#epr-pair)is nevezzük.

## <a name="bloch-sphere"></a>Bloch gömb

Egy[qubit](xref:microsoft.quantum.glossary#qubit) [kvantum-állapot](xref:microsoft.quantum.glossary#quantum-state) grafikus ábrázolása egy háromdimenziós egység gömb elemeként. További információ: [qubits és átalakítások megjelenítése a Bloch szférával](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Használata hívható

Egy [művelet](xref:microsoft.quantum.glossary#operation) vagy [függvény](xref:microsoft.quantum.glossary#function) a Q # nyelven. További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Clifford-csoport

Azok a műveletek [összessége, amelyek](xref:microsoft.quantum.glossary#bloch-sphere) elfoglalják a octants és a [Pauli-operátorok](xref:microsoft.quantum.glossary#pauli-operators)hatását. Ezek közé tartoznak a következő műveletek: [$X $](xref:microsoft.quantum.intrinsic.x), [$Y $](xref:microsoft.quantum.intrinsic.y), [$Z $](xref:microsoft.quantum.intrinsic.z), [$H $](xref:microsoft.quantum.intrinsic.h) és [$S $](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Ellenőrzött

Olyan Quantum [művelet](xref:microsoft.quantum.glossary#operation) , amely egy vagy több [qubits](xref:microsoft.quantum.glossary#qubit) használ a cél művelethez. További információ: [ellenőrzött és adjoint műveletek](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Dirac jelölése

Egy szimbolikus Gyorsírás, amely leegyszerűsíti a [kvantum-állapotok](xref:microsoft.quantum.glossary#quantum-state), más néven a *Bra-ket* jelölések megjelenítését.  A *melltartó* része egy sor vektort jelöl, például: $ \bra{A} = \begin{bmatrix} a {_1} & a {_2} \end{bmatrix} $, és a *ket* rész egy oszlop vektort jelöl, $ \ket{B} = \begin{bmatrix} B {_1} \\ \\ b {_2} \end{bmatrix} $. További információ: Dirac- [jelölés](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Sajátérték

Az a tényező, amellyel egy adott átalakítás [eigenvector](xref:microsoft.quantum.glossary#eigenvector) nagysága megváltozik az átalakítás alkalmazásával.  Egy négyzetes mátrix $M $ és egy eigenvector $v $, majd $Mv = CV $, ahol $c $ a sajátérték, és az argumentumok összetett száma lehet. További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Egy olyan vektor, amelynek irányát egy adott átalakítás nem változtatja meg, és amelynek nagyságrendjét a vektor [sajátérték](xref:microsoft.quantum.glossary#eigenvalue)megfelelő tényező módosítja. Egy négyzetes mátrix $M $ és egy sajátérték $c $, majd $Mv = CV $, ahol a $v $ a mátrix eigenvector, és az argumentumok összetett száma lehet. További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Felakadás

A *kvantum-részecskék* (például a [qubits](xref:microsoft.quantum.glossary#qubit)) csatlakoztathatók vagy összekapcsolhatók úgy, hogy ne legyenek egymástól függetlenül. A mérési eredmények akkor is összekapcsolhatók, ha a rendszer végtelenül elválasztja őket. A felakadás elengedhetetlen a qubit [állapotának](xref:microsoft.quantum.glossary#quantum-state) [méréséhez](xref:microsoft.quantum.glossary#measurement) .  További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR pár

Két [qubits](xref:microsoft.quantum.glossary#qubit)négy specifikus, maximálisan összekeverhető [Quantum állapotának](xref:microsoft.quantum.glossary#quantum-state) egyike. A négy állapot definiálva van $ \ket{\ beta_ {ij}} = (\mathbb {1} \Otimes X ^ iZ ^ j) (\ket {00} + \ket {11} )/\sqrt {2} $. Egy EPR pár más néven [Bell-állapot](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evolution

A [kvantum-állapot](xref:microsoft.quantum.glossary#quantum-state) időbeli változásának módja. További információ: [mátrix exponenciálisok](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Függvény
A Q # nyelvben található, tisztán klasszikus (nem Quantum) típusú alrutin. Míg a függvények a kvantum-algoritmusokon belül vannak használatban, nem működhetnek [qubits](xref:microsoft.quantum.glossary#qubit) vagy hívási [műveleteken](xref:microsoft.quantum.glossary#operation). További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>Kapu

Egy kvantum- [művelet](xref:microsoft.quantum.glossary#operation)örökölt kifejezése a klasszikus logikai kapuk fogalma alapján. A [kvantum-áramkör](xref:microsoft.quantum.glossary#quantum-circuit-diagram) a klasszikus logikai áramkörök hasonló fogalma alapján kapuk (vagy műveletek) hálózata.

## <a name="global-phase"></a>Globális fázis

Ha két [állapot](xref:microsoft.quantum.glossary#quantum-state) megegyezik egy összetett szám többszörösével, $e ^ {i\phi} $, azt mondják, hogy eltérnek a globális fázistól. A helyi fázisokkal ellentétben a globális fázisok nem figyelhetők meg semmilyen [méréssel](xref:microsoft.quantum.glossary#measurement). További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

A Hadamard művelet (más néven Hadamard-kapu vagy átalakító) egyetlen [qubit](xref:microsoft.quantum.glossary#qubit) viselkedik, és a $ \ket $ vagy $ \ket $ páros [pozícióba](xref:microsoft.quantum.glossary#superposition) helyezi, {0} {1} Ha a qubit kezdetben $ \ket {0} $ állapotban van. A Q # esetében ezt a műveletet az előre definiált művelet alkalmazza [`H`](xref:microsoft.quantum.intrinsic.h) .

## <a name="immutable"></a>Nem módosítható

Olyan változó, amelynek értéke nem módosítható. A Q #-ban egy nem módosítható változó jön létre a `let` kulcsszó használatával. A *módosítható* változók bejelentéséhez használja a [változékony](xref:microsoft.quantum.glossary#immutable) kulcsszót a bevalláshoz, és a `set` kulcsszót az érték módosításához. 

## <a name="measurement"></a>Mérés

A megfigyelés eredményét eredményező [qubit](xref:microsoft.quantum.glossary#qubit) (vagy qubits-készlet) manipulációja, amely a klasszikus bitek beszerzését eredményezi. További információ: [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Változtatható

Egy változó, amelynek az értéke a létrehozása után módosítható. A Q # változóban változtatható változót a kulcsszó használatával kell deklarálni, `mutable` és a kulcsszó használatával kell módosítani `set` . A `let` kulcsszóval létrehozott változók nem [változtathatók](xref:microsoft.quantum.glossary#immutable) meg, és az értékük nem módosítható.

## <a name="namespace"></a>Névtér

A kapcsolódó nevek (például [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function)és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type)) gyűjteményének címkéje. A [Microsoft. Quantum.](xref:microsoft.quantum.preparation) a névtér például a standard könyvtárban definiált összes szimbólumot felcímkézi a kezdeti állapotok előkészítéséhez.

## <a name="operation"></a>Művelet

A Quantum végrehajtás alapegysége a Q #-ban. Ez nagyjából megfelel a C, C++ vagy Python függvénynek, illetve a C# vagy a Java statikus metódusának. További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>Kezelő alkalmazás

Quantum művelet végrehajtása. Ez általában egy egységes mátrixot alkalmaz az aktuális kvantum-állapot vektorára.

## <a name="oracle"></a>Oracle

Egy olyan alrutin, amely Adatfüggő adatokat biztosít a kvantum-algoritmusnak futásidőben. A cél az, hogy a kimenetek [a](xref:microsoft.quantum.glossary#superposition) helyükön lévő bemeneteknek megfelelő kimenetet adjanak. További információ: [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Részleges alkalmazás

[Függvény](xref:microsoft.quantum.glossary#function) vagy [művelet](xref:microsoft.quantum.glossary#operation) hívása az összes szükséges bemenet nélkül. Ez egy új [meghívót](xref:microsoft.quantum.glossary#callable) ad vissza, amely csak a hiányzó (aláhúzásjel által jelzett) paramétereket adja meg, amelyeket egy későbbi alkalmazásban kell megadni. Például a függvény `MyFunc(x : int, y : int) : int {return x + y;}` használatával részben alkalmazhat egy új függvényt `let NewFunc = MyFunc(_, 3)` . Az új függvényt később is meghívhatja a hiányzó paraméterrel, `NewFunc(2)` amely az *5*értéket adja vissza.  További információ: [részleges alkalmazás](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Pauli-operátorok

Három 2 x 2 egységes mátrix, azaz a `X` `Y` és a `Z` Quantum művelet. Az Identity Matrix, $I $, gyakran szerepel a készletben is.  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix} $, $X = \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{bmatrix} $, $Y = \begin{bmatrix} 0 &-i \\ \\ & 0 \end{bmatrix} $, $Z = \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix} $.   További információ: [qubit műveletek](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Quantum Circuit diagram

Egy metódus, amely grafikusan ábrázolja az egyszerű kvantum-programok [műveleteinek](xref:microsoft.quantum.glossary#operation) (vagy [kapuinak](xref:microsoft.quantum.glossary#gate)) sorát, például a ![ minta áramköri diagramot ](~/media/qpe.png) . További információ: kvantum- [áramkörök](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Kvantum-kódtárak

A Q # programok létrehozásához használható [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) gyűjteményei. A [standard szintű függvénytár](xref:microsoft.quantum.libraries.standard.intro) alapértelmezés szerint telepítve van. A rendelkezésre álló további könyvtárak a [kémiai könyvtár](xref:microsoft.quantum.chemistry.concepts.intro), a [numerikus könyvtár](xref:microsoft.quantum.numerics.intro) és a [Machine learning-könyvtár](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Kvantum állapota

Egy elkülönített kvantumrendszer pontos állapota, amelyből kinyerhető a [mérési](xref:microsoft.quantum.glossary#measurement) valószínűség. A Quantum Computing használatával a Quantum Simulator ezt az információt használja annak szimulálása érdekében, hogy a qubits hogyan válaszolnak a műveletekre. További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

A kvantum-információk alapszintű egysége, amely *a klasszikus* számítástechnikai funkciókhoz hasonlít. További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Ismétlés a sikerig

A probabilistically által sikeresnek bizonyuló kvantum-algoritmus. Hiba esetén a rutin újra próbálkozik, amíg a művelet sikertelen lesz (vagy elérte a korlátot). További információ: REPEAT to [Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Standard kódtárak

A telepítés során a Q # fordítóprogrammal együtt telepített [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) . A standard szintű függvénytár-implementáció agnosztikus a célszámítógépek tekintetében. További információ: [standard könyvtárak](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Szuperpozíció

A Quantum Computing koncepciója, amely szerint a [qubit](xref:microsoft.quantum.glossary#qubit) két állapot lineáris kombinációja, $ \ket{\0} $ és $ \ket{\1} $, amíg meg nem történik a [mérés](xref:microsoft.quantum.glossary#measurement).  További információ: a [kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Célszámítógép

Fordítási cél, amely egy absztrakt kvantum-programot csökkenti a hardver vagy a szimuláció irányába. Ez általában számos célra, például a kapu cseréjére, a hibajavítások kódolására, a geometriai elrendezésre és egyebekre vonatkozó újraírásokat tartalmaz. További információ: [Quantum simulators and Host Applications](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportáció

Az egyik [qubit](xref:microsoft.quantum.glossary#qubit) az adatok vagy a kvantum- [állapotok](xref:microsoft.quantum.glossary#quantum-state)egy helyről a másikra való újragenerálásának módszere a qubit fizikai áthelyezése nélkül a [felakadás](xref:microsoft.quantum.glossary#entanglement) és a [mérés](xref:microsoft.quantum.glossary#measurement)használatával.  További információ: a [kvantum-áramkörök](xref:microsoft.quantum.concepts.circuits) és a megfelelő Kata a [Quantum katas](xref:microsoft.quantum.overview.katas)szolgáltatásban.

## <a name="tuple"></a>Rekord

Vesszővel tagolt értékek gyűjteménye, amely egyetlen értékként viselkedik. A rekord *típusát* a benne található értékek típusai határozzák meg. A Q #- [ban a rekordok](xref:microsoft.quantum.glossary#immutable) nem módosítható, és beágyazható, tömböket tartalmazhat, vagy egy tömbben használható. További információ: a [rekord típusai](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Egységes operátor

Egy operátor, amelynek inverze egyenlő a [adjoint](xref:microsoft.quantum.glossary#adjoint), azaz $uu ^ {\dagger} = \id $.

## <a name="user-defined-type"></a>Felhasználó által definiált típus

Beépített vagy korábban definiált típusok gyűjteménye, amelyek egyetlen egységként is szerepelhetnek. További információ: [felhasználó által definiált típusok](xref:microsoft.quantum.guide.types#user-defined-types).