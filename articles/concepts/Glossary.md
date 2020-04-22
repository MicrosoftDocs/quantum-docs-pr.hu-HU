---
title: Kvantumszámítástechnikai szószedet
description: A kvantum-számításban használt általános kifejezések, műveletek és objektumok szószedete.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482235"
---
# <a name="quantum-computing-glossary"></a>Kvantumszámítástechnikai szószedet

## <a name="adjoint"></a>Adjoint között

A [művelet](xref:microsoft.quantum.glossary#operation)összetett konjugátumát. Az [egységes](xref:microsoft.quantum.glossary#unitary-operator) kezelőt megvalósító műveletek esetében az adjoint a művelet inverze, és tőr szimbólum jelzi. Ha például a `U` művelet az $U$-t `Adjoint U` jelöli, akkor $U^\tőr$-t jelöl. További információ: [Adjoint](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Ancilla

A kvantumszámítógép ideiglenes memóriájaként szolgáló [qubit,](xref:microsoft.quantum.glossary#qubit) amely szükség szerint le van foglalva és levan foglalva.  További információ: [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Bell állam

Egyike a négy konkrét maximálisan [kusza](xref:microsoft.quantum.glossary#entanglement) [kvantum állapotok](xref:microsoft.quantum.glossary#quantum-state) két qubit. A négy állapot $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. A Bell állam is [ismert,](xref:microsoft.quantum.glossary#epr-pair)mint egy EPR pár .

## <a name="bloch-sphere"></a>Bloch gömb

Egy[egyqubit](xref:microsoft.quantum.glossary#qubit) [kvantumállapot](xref:microsoft.quantum.glossary#quantum-state) grafikus ábrázolása, mint egy pont egy háromdimenziós egységgömbben. További információ: [A Qubitek és átalakítások megjelenítése a Bloch-gömböt használva.](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)

## <a name="callable"></a>Hívható

Egy [művelet](xref:microsoft.quantum.glossary#operation) vagy [függvény](xref:microsoft.quantum.glossary#function) a Q# nyelven. További információt a [Művelet- és funkciótípusok](xref:microsoft.quantum.language.type-model#operation-and-function-types)című témakörben talál.

## <a name="clifford-group"></a>Clifford csoport

A [Bloch-gömb](xref:microsoft.quantum.glossary#bloch-sphere) oktántáit elfoglaló műveletek és a [Pauli-operátorok](xref:microsoft.quantum.glossary#pauli-operators)hatás-permutációi . Ezek közé tartozik a műveletek [$X$](xref:microsoft.quantum.intrinsic.x), [$Y $](xref:microsoft.quantum.intrinsic.y) [$Z $](xref:microsoft.quantum.intrinsic.z)$H [$](xref:microsoft.quantum.intrinsic.h) és [$S $](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Ellenőrzött

Olyan [kvantumművelet,](xref:microsoft.quantum.glossary#operation) amely egy vagy több [qubitet](xref:microsoft.quantum.glossary#qubit) vesz igénybe a célművelet lehetővé tételeként. További információ: [Controlled](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Dirac jelölés

Egy szimbolikus gyorsírás, amely leegyszerűsíti a [kvantumállapotok](xref:microsoft.quantum.glossary#quantum-state)képviseletét , más néven *bra-ket* jelölés.  A *melltartó* rész egy sorvektot jelöl, például $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ és a *ket* rész egy oszlopvektort jelöl, $\ket{B} = \begin{bmatrix} B{_1} \\ \\ B{_2} \end{bmatrix}$. További információ: [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue között

Az a tényező, amellyel egy adott [transzformáció eigenvektvivájának](xref:microsoft.quantum.glossary#eigenvector) nagysága az átalakulás alkalmazásával megváltozik.  Adott négyzetmátrix $M$ és egy eigenvector $v$, akkor $Mv = cv$, ahol a $c$ az eigenvalue, és bármilyen argumentum összetett száma lehet. További információt a [Speciális mátrixfogalmak](xref:microsoft.quantum.concepts.matrix-advanced)című témakörben talál.

## <a name="eigenvector"></a>Eigenvector

Olyan vektor, amelynek irányát egy adott transzformáció változatlanul módosítja, és amelynek nagyságát az adott vektor [igenértékének](xref:microsoft.quantum.glossary#eigenvalue)megfelelő tényező változtatja meg. Adott négyzetmátrix $M$ és egy eigenvalue $c$, akkor $Mv = cv$, ahol $v$ a mátrix eigenvectorja, és bármilyen argumentum összetett száma lehet. További információt a [Speciális mátrixfogalmak](xref:microsoft.quantum.concepts.matrix-advanced)című témakörben talál.

## <a name="entanglement"></a>Felakadás

A kvantumrészecskék, mint például [a qubitek,](xref:microsoft.quantum.glossary#qubit)összekapcsolhatók vagy *belegabalyodhatnak* úgy, hogy egymástól függetlenül nem lehet leírni őket. Mérési eredményeik akkor is korrelálnak, ha végtelenül messze vannak egymástól. A belegabalyodás elengedhetetlen a qubit [állapotának](xref:microsoft.quantum.glossary#quantum-state) [méréséhez.](xref:microsoft.quantum.glossary#measurement)  További információt a [Speciális mátrixfogalmak](xref:microsoft.quantum.concepts.matrix-advanced)című témakörben talál.

## <a name="epr-pair"></a>EPR pár

Az egyik a négy konkrét maximálisan kusza [kvantum államok](xref:microsoft.quantum.glossary#quantum-state) két [qubit .](xref:microsoft.quantum.glossary#qubit) A{1} négy állapot $\ket{\beta_{ij}} = (\mathbb \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Az EPR-pár bell [államként](xref:microsoft.quantum.glossary#bell-state) is ismert

## <a name="evolution"></a>Evolution

Hogyan változik a [kvantumállapot](xref:microsoft.quantum.glossary#quantum-state) az idő múlásával. További információ: [Matrix exponencials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Függvény
A Q# nyelv tisztán klasszikus (nem kvantum) szubrutintípusa. Bár a függvényeket kvantumalgoritmusokban használják, nem tudnak [qubitekre](xref:microsoft.quantum.glossary#qubit) vagy [hívási műveletekre hatni.](xref:microsoft.quantum.glossary#operation) További információt a [Művelet- és funkciótípusok](xref:microsoft.quantum.language.type-model#operation-and-function-types)című témakörben talál.

## <a name="gate"></a>Gate

Egy [kvantumművelet](xref:microsoft.quantum.glossary#operation)örökölt kifejezése, amely a klasszikus logikai kapuk koncepcióján alapul. A [kvantumáramkör](xref:microsoft.quantum.glossary#quantum-circuit-diagram) kapuk (vagy műveletek) hálózata, amely a klasszikus logikai áramkörök hasonló koncepcióján alapul.

## <a name="global-phase"></a>Globális fázis

Ha két [állapot](xref:microsoft.quantum.glossary#quantum-state) egyösszetett szám többszörösével $e^{i\phi}$-nal azonos, a rendszer azt állítja, hogy globális fázisig eltérő. A helyi fázisokkal ellentétben a globális fázisok nem figyelhetők meg semmilyen [mérhetőség révén.](xref:microsoft.quantum.glossary#measurement) További információ: [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard között

A Hadamard művelet (más néven a Hadamard kapu vagy átalakítani) jár el egy [qubit,](xref:microsoft.quantum.glossary#qubit) és teszi{1}azt még [szuperpozíció](xref:microsoft.quantum.glossary#superposition) $ ' ket{0}$ vagy $ \ket $ ha a qubit kezdetben a $ ket{0}$ állapotban. A Q#-ban ezt a műveletet az [`H`](xref:microsoft.quantum.intrinsic.h) előre definiált művelet alkalmazza.

## <a name="immutable"></a>Megváltoztathatatlan

Olyan változó, amelynek értéke nem módosítható. A Q# kulcsszóban egy nem módosítható `let` változó jön létre. A módosítható változók deklarálni a [deklarálható](xref:microsoft.quantum.glossary#immutable) kulcsszót, az érték módosításához pedig a `set` kulcsszót. *can* 

## <a name="measurement"></a>Mérés

A manipuláció a [qubit](xref:microsoft.quantum.glossary#qubit) (vagy meg a qubit), hogy a hozamok az eredmény egy megfigyelés, valójában megszerzése klasszikus bit. További információ: [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Változtatható

Olyan változó, amelynek értéke a létrehozása után módosítható. A Q# -ban egy változékony `mutable` változó deklarálva a kulcsszó használatával deklarálva, és a `set` kulcsszó használatával módosul. A `let` kulcsszóval létrehozott változók [nem módosíthatók,](xref:microsoft.quantum.glossary#immutable) és értékük nem módosítható.

## <a name="namespace"></a>Névtér

A kapcsolódó nevek (pl. [műveletek, függvények](xref:microsoft.quantum.glossary#operation)és [functions](xref:microsoft.quantum.glossary#function)felhasználó [által definiált típusok)](xref:microsoft.quantum.glossary#user-defined-type)gyűjteményének címkéje. Például a [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) névtér címkézi a szabványos könyvtárban definiált összes olyan szimbólumot, amely segít a kezdeti állapotok előkészítésében.

## <a name="operation"></a>Művelet

A kvantumvégrehajtás alapegysége Q#-ban. Nagyjából megegyezik a C, C++ vagy Python függvényével, vagy a C# vagy java statikus metódusával. További információt a [Művelet- és funkciótípusok](xref:microsoft.quantum.language.type-model#operation-and-function-types)című témakörben talál.

## <a name="operator-application"></a>Operátori alkalmazás

Kvantumműveletet hajt végre. Ez általában egy egységes mátrixot alkalmaz az aktuális kvantumállapot-vektorra.

## <a name="oracle"></a>Oracle

Egy szubrutin, amely adatoktól függő információkat szolgáltat egy kvantumalgoritmusnak futásidőben. A cél általában az, hogy a szuperpozícióban lévő bemeneteknek megfelelő kimenetek [szuperpozíciója.](xref:microsoft.quantum.glossary#superposition) További információ: [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Részleges alkalmazás

Függvény [vagy](xref:microsoft.quantum.glossary#function) [művelet hívása](xref:microsoft.quantum.glossary#operation) az összes szükséges bemenet nélkül. Ez egy új [hívable-t](xref:microsoft.quantum.glossary#callable) ad vissza, amely csak a hiányzó paramétereket (aláhúzásjelrel jelzi) kell megadni egy jövőbeli alkalmazás során. A függvényt `MyFunc(x : int, y : int) : int {return x + y;}` tekintve például részben alkalmazhatja `let NewFunc = MyFunc(_, 3)`azt egy új függvényre. Ezután később meghívhatja az új függvényt `NewFunc(2)` a hiányzó paraméterrel, amely az *5*értéket adja vissza.  További információ: [Részleges alkalmazás](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Pauli operátorok

Három 2 x 2 egységes mátrixból álló készlet, `Y` `Z` a `X`, és a kvantumműveletek. Az identitásmátrix ( $I$) gyakran szerepel a készletben is.  $I = \begin{bmatrix} \\ \\ 1 & 0 0 0 & 1 \end{bmatrix}$, \\ \\ $X = \begin{bmatrix} 0 & 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\ \\ & 0 \bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\ \\ 0 & -1 \end{b}$.   További információ: [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Kvantumáramkör-diagram

Egyszerű kvantumprogramok, például ![mintaáramköri diagram](~/media/qpe.png)műveletek (vagy [kapuk)](xref:microsoft.quantum.glossary#gate) [műveletek](xref:microsoft.quantum.glossary#operation) sorozatának grafikus ábrázolására szolgáló módszer. További információ: [Quantum circuits](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Kvantumkönyvtárak

Műveletek, [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) [gyűjteményei](xref:microsoft.quantum.glossary#operation)a Q# programok létrehozásához. A [Standard könyvtár](xref:microsoft.quantum.libraries.standard.intro) alapértelmezés szerint telepítve van. További könyvtárak a [kémia könyvtár,](xref:microsoft.quantum.chemistry.concepts.intro)a [Numerikus könyvtár](xref:microsoft.quantum.numerics.intro) és a [Gépi tanulási könyvtár.](xref:microsoft.quantum.machine-learning.concepts.intro)

## <a name="quantum-state"></a>Kvantumállapot

Egy elszigetelt kvantumrendszer pontos állapota, amelyből [mérési](xref:microsoft.quantum.glossary#measurement) valószínűségnyerhető. A kvantum-számítástechnika, a kvantum szimulátor használja ezt az információt, hogy szimulálja, hogyan qubits reagálnak a műveletekre. További információ: [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit között

A kvantuminformáció alapegysége, amely egy *kicsit* hasonló a klasszikus számítástechnikához. További információ: [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Ismétlés a sikerig

Egy kvantum algoritmus, ami probabilista módon sikeres. Sikertelenség esetén a rutin újra próbálkozik, amíg sikeres (vagy egy korlátot el nem ér). További információ: [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Standard kódtárak

[Műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok,](xref:microsoft.quantum.glossary#user-defined-type) amelyek a Q# fordítóval együtt vannak telepítve a telepítés során. A szokásos könyvtári implementáció agnosztikus a célgépek tekintetében. További információt a Szabványos könyvtárak című [témakörben](xref:microsoft.quantum.libraries.standard.intro)talál.

## <a name="superposition"></a>Szuperpozíció

A kvantum-számítástechnika azon fogalma, hogy a [qubit](xref:microsoft.quantum.glossary#qubit) két állapot lineáris kombinációja, $\ket{\0}$ és $\ket{\1}$, amíg meg nem [mérik.](xref:microsoft.quantum.glossary#measurement)  További információ: [Mi a kvantumszámítástechnika.](xref:microsoft.quantum.overview.what)

## <a name="target-machine"></a>Célgép

Olyan összeállítási cél, amely csökkenti az absztrakt kvantumprogramot a hardver vagy a szimuláció felé. Ez általában magában foglalja az újraírások számos célra, beleértve a kapu csere, kódolás hibajavítás, geometriai elrendezés és mások. További információ: [Quantum simulatorok és gazdaalkalmazások.](xref:microsoft.quantum.machines)

## <a name="teleportation"></a>Teleportáció

Az egyik [qubit](xref:microsoft.quantum.glossary#qubit) [egyik](xref:microsoft.quantum.glossary#quantum-state)helyről a másikra történő regenerálására szolgáló módszer, anélkül, hogy fizikailag mozgatná a qubitet, [a kuszaság](xref:microsoft.quantum.glossary#entanglement) és [a mérés](xref:microsoft.quantum.glossary#measurement)segítségével.  További információ: [Quantum áramkörök](xref:microsoft.quantum.concepts.circuits) és [az egész összerakása.](xref:microsoft.quantum.techniques.puttingittogether)

## <a name="tuple"></a>Tuple (tuple)

Vesszővel tagolt értékek gyűjteménye, amely egyetlen értékként működik. A tuple *típusát* a benne található értékek típusa határozza meg. A Q#-ban a törzsek [nem módosíthatók,](xref:microsoft.quantum.glossary#immutable) egymásba ágyazhatók, tömböket tartalmazhatnak, vagy tömbben használhatók. További információ: [Tuple types](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Egységes kezelő

Olyan operátor, amelynek inverzértéke megegyezik a [djointjával,](xref:microsoft.quantum.glossary#adjoint)azaz $UU^{\tőr} = \id$.

## <a name="user-defined-type"></a>Felhasználó által definiált típus

Beépített vagy korábban definiált típusok gyűjteménye, amelyeket egyetlen egységnek is lehet tekinteni. További információ: [Felhasználó által definiált típusok](xref:microsoft.quantum.language.type-model#user-defined-types).