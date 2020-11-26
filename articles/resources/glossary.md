---
title: Quantum Computing Szószedet leírása: A kvantum-számítástechnika során használt általános feltételek, műveletek és objektumok glosszáriuma.
Szerző: bradben MS. Author: v-benbra MS. Date: 9/1/2020 MS. topic: cikk UID: Microsoft. Quantum. Szószedet No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="quantum-computing-glossary"></a>Quantum Computing – Szószedet

## <a name="adjoint"></a>Adjoint

Egy [művelet](xref:microsoft.quantum.glossary#operation)összetett konjugált átültetése. Az [egységes](xref:microsoft.quantum.glossary#unitary-operator) operátort megvalósító műveletek esetében a adjoint a művelet inverze, és egy tőr szimbólum jelzi. Ha például a művelet `U` az u egységes operátort jelöli $ $ , akkor `Adjoint U` az $ u ^ \dagger $ érték jelenik meg. További információ: a rendszerbeli [alkalmazás](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="ancilla"></a>Ancilla

Egy [qubit](xref:microsoft.quantum.glossary#qubit) , amely ideiglenes memóriát szolgál a kvantum-számítógép számára, és igény szerint le van foglalva és le van foglalva.  További információ: [több qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Harang állapota

Két qubits négy specifikus, maximálisan [összekeverhető](xref:microsoft.quantum.glossary#entanglement) [Quantum állapotának](xref:microsoft.quantum.glossary#quantum-state) egyike. A négy állam meghatározása: $ \ket { \beta _ { ij } } = ( \mathbb { I } \otimes X ^ iZ ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . A Bell-állapotot [EPR-pároknak](xref:microsoft.quantum.glossary#epr-pair)is nevezzük.

## <a name="bloch-sphere"></a>Bloch gömb

Egy[qubit](xref:microsoft.quantum.glossary#qubit) [kvantum-állapot](xref:microsoft.quantum.glossary#quantum-state) grafikus ábrázolása egy háromdimenziós egység gömb elemeként. További információ:  [qubits és átalakítások megjelenítése a Bloch szférával](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Használata hívható

Egy [művelet](xref:microsoft.quantum.glossary#operation) vagy [függvény](xref:microsoft.quantum.glossary#function) a [ Q# nyelven](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language).
További információ: [ Q# programok](xref:microsoft.quantum.guide.programs)

## <a name="clifford-group"></a>Clifford-csoport

Azok a műveletek [összessége, amelyek](xref:microsoft.quantum.glossary#bloch-sphere) elfoglalják a octants és a [Pauli-operátorok](xref:microsoft.quantum.glossary#pauli-operators)hatását. Ezek közé tartoznak a következő műveletek: [ $ X $ ](xref:Microsoft.Quantum.Intrinsic.X), [ $ Y $ ](xref:Microsoft.Quantum.Intrinsic.Y), [ $ Z $ ](xref:Microsoft.Quantum.Intrinsic.Z), [ $ H $ ](xref:Microsoft.Quantum.Intrinsic.H) és [ $ S $ ](xref:Microsoft.Quantum.Intrinsic.S).

## <a name="controlled"></a>Ellenőrzött

Olyan Quantum [művelet](xref:microsoft.quantum.glossary#operation) , amely egy vagy több [qubits](xref:microsoft.quantum.glossary#qubit) használ a cél művelethez. További információ: a rendszerbeli [alkalmazás](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="dirac-notation"></a>Dirac jelölése

Egy szimbolikus Gyorsírás, amely leegyszerűsíti a [kvantum-állapotok](xref:microsoft.quantum.glossary#quantum-state), más néven a *Bra-ket* jelölések megjelenítését.  A *melltartó* a sor vektort jelöli, például a $ \bra { } = \begin{bmatrix} { _1 egy } & { _2, } \end{bmatrix} $ a *ket* pedig egy oszlop vektort, $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b { _2 } \end{bmatrix} $ . További információ: Dirac- [jelölés](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Sajátérték

Az a tényező, amellyel egy adott átalakítás [eigenvector](xref:microsoft.quantum.glossary#eigenvector) nagysága megváltozik az átalakítás alkalmazásával.  A Square Matrix $ M $ és egy eigenvector $ v $ , majd az $ MV = CV $ , ahol a $ c $ a sajátérték, és az argumentumok összetett száma lehet. További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Egy olyan vektor, amelynek irányát egy adott átalakítás nem változtatja meg, és amelynek nagyságrendjét a vektor [sajátérték](xref:microsoft.quantum.glossary#eigenvalue)megfelelő tényező módosítja. A Square Matrix $ M $ és a sajátérték $ c $ , majd az $ MV = CV $ , ahol $ a v a $ mátrix eigenvector, és az argumentumok összetett száma lehet. További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Összefonódás

A *kvantum-részecskék* (például a [qubits](xref:microsoft.quantum.glossary#qubit)) csatlakoztathatók vagy összekapcsolhatók úgy, hogy ne legyenek egymástól függetlenül. A mérési eredmények akkor is összekapcsolhatók, ha a rendszer végtelenül elválasztja őket. A felakadás elengedhetetlen a qubit [állapotának](xref:microsoft.quantum.glossary#quantum-state) [méréséhez](xref:microsoft.quantum.glossary#measurement) .  További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR pár

Két [qubits](xref:microsoft.quantum.glossary#qubit)négy specifikus, maximálisan összekeverhető [Quantum állapotának](xref:microsoft.quantum.glossary#quantum-state) egyike. A négy állam meghatározása: $ \ket { \beta _ { ij } } = ( \mathbb { 1 } \otimes X ^ iZ ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Egy EPR pár más néven [Bell-állapot](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evolution

A [kvantum-állapot](xref:microsoft.quantum.glossary#quantum-state) időbeli változásának módja. További információ: [mátrix exponenciálisok](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Függvény
Egy alrutin típusa a Q# tisztán determinisztikus nyelven. Míg a függvények a kvantum-algoritmusokon belül vannak használatban, nem működhetnek [qubits](xref:microsoft.quantum.glossary#qubit) vagy hívási [műveleteken](xref:microsoft.quantum.glossary#operation). További információ: [ Q# programok](xref:microsoft.quantum.guide.programs)

## <a name="gate"></a>Kapu

Egy örökölt kifejezés bizonyos belső kvantum- [műveletekhez](xref:microsoft.quantum.glossary#operation)a klasszikus logikai kapuk fogalma alapján. A [kvantum-kör](xref:microsoft.quantum.glossary#quantum-circuit-diagram) kapuk hálózata, a klasszikus logikai áramkörök hasonló fogalma alapján.

## <a name="global-phase"></a>Globális fázis

Ha két [állam](xref:microsoft.quantum.glossary#quantum-state) azonos egy összetett számú $ e ^ i értékkel, azt { \phi } $ mondják, hogy eltérnek a globális fázistól. A helyi fázisokkal ellentétben a globális fázisok nem figyelhetők meg semmilyen [méréssel](xref:microsoft.quantum.glossary#measurement). További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

A Hadamard művelet (más néven Hadamard-kapu vagy átalakító) egyetlen [qubit](xref:microsoft.quantum.glossary#qubit) viselkedik, és 0 vagy 1 páros [felállásba](xref:microsoft.quantum.glossary#superposition) helyezi, $ \ket { } $ $ \ket { } $ Ha a qubit kezdetben $ \ket { 0 } $ állapotban van. A-ben Q# ezt a műveletet az előre meghatározott művelet alkalmazza [`H`](xref:Microsoft.Quantum.Intrinsic.H) .

## <a name="immutable"></a>Nem módosítható

Olyan változó, amelynek értéke nem módosítható. A alkalmazásban egy nem módosítható változó Q# jön létre a `let` kulcsszó használatával. A *módosítható* változók bejelentéséhez használja a [változékony](xref:microsoft.quantum.glossary#immutable) kulcsszót a bevalláshoz, és a `set` kulcsszót az érték módosításához. 

## <a name="measurement"></a>Mérés

A megfigyelés eredményét eredményező [qubit](xref:microsoft.quantum.glossary#qubit) (vagy qubits-készlet) manipulációja, amely a klasszikus bitek beszerzését eredményezi. További információ: [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Változtatható

Egy változó, amelynek az értéke a létrehozása után módosítható. A-ben változtatható változót Q# a kulcsszó használatával deklaráljuk, `mutable` és a kulcsszó használatával módosították `set` . A `let` kulcsszóval létrehozott változók nem [változtathatók](xref:microsoft.quantum.glossary#immutable) meg, és az értékük nem módosítható.

## <a name="namespace"></a>Névtér

A kapcsolódó nevek (például [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function)és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type)) gyűjteményének címkéje. A [Microsoft. Quantum.](xref:Microsoft.Quantum.Preparation) a névtér például a standard könyvtárban definiált összes szimbólumot felcímkézi a kezdeti állapotok előkészítéséhez.

## <a name="operation"></a>Művelet

A kvantum-számítás alapegysége a-ben Q# . Ez nagyjából megfelel a C, C++ vagy Python függvénynek, illetve a C# vagy a Java statikus metódusának. További információ: [ Q# programok](xref:microsoft.quantum.guide.programs).

## <a name="oracle"></a>Oracle

Egy olyan alrutin, amely Adatfüggő adatokat biztosít a kvantum-algoritmusnak futásidőben. A cél az, hogy a kimenetek [a](xref:microsoft.quantum.glossary#superposition) helyükön lévő bemeneteknek megfelelő kimenetet adjanak. További információ: [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Részleges alkalmazás

[Függvény](xref:microsoft.quantum.glossary#function) vagy [művelet](xref:microsoft.quantum.glossary#operation) hívása az összes szükséges bemenet nélkül. Ez egy új [meghívót](xref:microsoft.quantum.glossary#callable) ad vissza, amely csak a hiányzó (aláhúzásjel által jelzett) paramétereket adja meg, amelyeket egy későbbi alkalmazásban kell megadni. További információ: [részleges alkalmazás](xref:microsoft.quantum.qsharp.partialapplication).

## <a name="pauli-operators"></a>Pauli-operátorok

3 2 x 2 egységes mátrixok halmaza, amely a `X` `Y` és a `Z` Quantum művelet. Az Identity Matrix ( $ I $ ) gyakran szerepel a készletben is.  $= \begin{bmatrix} 1 & 0 0 \\\\ & 1 \end{bmatrix} $ , $ X 0 1 = \begin{bmatrix} & \\\\ & 0 \end{bmatrix} $ , $ Y = \begin{bmatrix} 0 & – i 0 \\\\ & \end{bmatrix} $ , $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} $ .   További információ: [qubit műveletek](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Quantum Circuit diagram

Egy módszer, amely grafikusan ábrázolja a [Gates](xref:microsoft.quantum.glossary#gate) sorozatot az egyszerű kvantum-programokhoz, például: 

![Minta áramköri diagram](~/media/qpe.png). 

További információ: kvantum- [áramkörök](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Kvantum-kódtárak

A programok létrehozásához szükséges [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) gyűjteményei Q# . A [standard szintű függvénytár](xref:microsoft.quantum.libraries.standard.intro) alapértelmezés szerint telepítve van. A rendelkezésre álló további könyvtárak a [kémiai könyvtár](xref:microsoft.quantum.chemistry.concepts.intro), a [numerikus könyvtár](xref:microsoft.quantum.numerics.intro) és a [Machine learning-könyvtár](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Kvantum állapota

Egy elkülönített kvantumrendszer pontos állapota, amelyből kinyerhető a [mérési](xref:microsoft.quantum.glossary#measurement) valószínűség. A Quantum Computing használatával a Quantum Simulator ezt az információt használja annak szimulálása érdekében, hogy a qubits hogyan válaszolnak a műveletekre. További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

A kvantum-információk alapszintű egysége, amely *a klasszikus* számítástechnikai funkciókhoz hasonlít. További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Ismétlés a sikerig

Olyan kvantum-algoritmusokban gyakran használt koncepció, amely egy bizonyos feltétel teljesülése esetén ismételten alkalmazza a számítást. Ha a feltétel nem teljesül, gyakran javításra van szükség a következő iteráció megadásával. További információ: [ Q# felhasználói útmutató](xref:microsoft.quantum.guide)

## <a name="standard-libraries"></a>Szabványos kódtárak

A telepítés során a fordítóval együtt telepített [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) Q# . A standard szintű függvénytár-implementáció agnosztikus a célszámítógépek tekintetében. További információ: [standard könyvtárak](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Szuperpozíció

A Quantum Computing koncepciója, amely szerint a [qubit](xref:microsoft.quantum.glossary#qubit) két állapot lineáris kombinációja, $ \ket { 0 } $ és $ \ket { 1 } $ , amíg meg nem történik a [mérés](xref:microsoft.quantum.glossary#measurement).  További információ: a [kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Célszámítógép

Fordítási cél, amely egy absztrakt kvantum-programot csökkenti a hardver vagy a szimuláció irányába. Ez általában számos célra, például a kapu cseréjére, a hibajavítások kódolására, a geometriai elrendezésre és egyebekre vonatkozó újraírásokat tartalmaz. További információ: [Quantum simulators and Host Applications](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportáció

Az egyik [qubit](xref:microsoft.quantum.glossary#qubit) az adatok vagy a kvantum- [állapotok](xref:microsoft.quantum.glossary#quantum-state)egy helyről a másikra való újragenerálásának módszere a qubit fizikai áthelyezése nélkül a [felakadás](xref:microsoft.quantum.glossary#entanglement) és a [mérés](xref:microsoft.quantum.glossary#measurement)használatával.  További információ: a [kvantum-áramkörök](xref:microsoft.quantum.concepts.circuits) és a megfelelő Kata a [Quantum katas](xref:microsoft.quantum.overview.katas)szolgáltatásban.

## <a name="tuple"></a>Rekord

Vesszővel tagolt értékek gyűjteménye, amely egyetlen értékként viselkedik. A rekord *típusát* a benne található értékek típusai határozzák meg. A-ben a Q# rekordok nem módosítható, és beágyazható, tömböket tartalmazhat, vagy egy tömbben használható. [immutable](xref:microsoft.quantum.glossary#immutable) További információ: [rekordok](xref:microsoft.quantum.qsharp.valueliterals#tuple-literals).

## <a name="unitary-operator"></a>Egységes operátor

Egy operátor, amelynek inverze megegyezik a [adjoint](xref:microsoft.quantum.glossary#adjoint), azaz a $ uu ^ értékkel { \dagger } = \id $ .

## <a name="user-defined-type"></a>Felhasználó által definiált típus

Olyan egyéni típus, amely egy vagy több névvel ellátott vagy névtelen elemet tartalmazhat. További információ: [type deklarációs] Microsoft. Quantum. qsharp. typedeclarations # Type-deklarációs).
