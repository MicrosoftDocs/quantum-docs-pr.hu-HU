---
title: Pauli-mérések leírása: megtudhatja, hogyan dolgozhat az egy-és több qubit Pauli-mérési műveletekkel.
Szerző: bradben UID: Microsoft. Quantum. Concepts. Pauli MS. Author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuális No-Loc:
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

# <a name="pauli-measurements"></a>Pauli-mérések

Az előző megbeszélésekben a számítási szempontok alapján történik a mérés.
Valójában más gyakori mérések történnek a kvantum-számítástechnikaban, amelyek egy adott szempontból megfelelőek a számítási szempontok alapján.
A használata során Q# a leggyakrabban a legelterjedtebb típusú mérések lesznek a *Pauli-mérések*, amelyek általánosítják a számítási alapjait, hogy más alapértékekre, valamint a különböző qubits közötti paritásos méréseket is tartalmazzák.
Ilyen esetekben gyakori, hogy megbeszéljük a Pauli-operátorok mérését, általában egy operátort, például az $ x, Y, z $ vagy $ z \otimes z, x \otimes x, x \otimes Y $ és így tovább. 

> [!TIP]
> A-ben a Q# multi-Qubit Pauli-operátorokat általában típusú tömbök jelölik `Pauli[]` .
> Például az $ X \otimes Z Y jelöléséhez \otimes $ használhatja a tömböt `[PauliX, PauliZ, PauliY]` .

A kiértékelése a Pauli-operátorok esetében különösen gyakori a kvantum-hibák helyesbítésének almezőjében.
A-ben Q# egy hasonló konvenciót követünk, amely a mérések alternatív nézetét ismerteti.

A Pauli-mérések részleteinek megismerése előtt érdemes meggondolni, hogy a kvantum-számítógépeken belüli egyetlen qubit hogyan mérhető a kvantum állapot.
Képzelje el, hogy egy $ n $ -qubit kvantum-állapottal rendelkezik, majd az egyik qubit azonnal kiszámítja a $ 2 ^ n lehetőség felét, $ amelyet az állapot tartalmazhat.
Ez azt jelenti, hogy a mérték a kvantum-állapotot a két fél szóköz egyikére vetíti.
Általánosíthatja a mérést úgy gondoljuk, hogy ezt az adatelemzést is figyelembe vesszük.

Az alterületek tömör azonosításához szükség van egy nyelvre a leírásához.
A két alterület leírásának egyik módja, ha egy olyan mátrixon keresztül adja meg őket, amely csak két egyedi eigenvalues rendelkezik, az egyezmény szerint $ \pm 1 $ .
Az alterületek ily módon történő leírásának egyszerű példáját a $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & – 1 \end{bmatrix} .
\end{align}
$$

A Pauli-Z mátrix átlós elemeinek olvasásával $ $ láthatjuk, hogy a $ Z $ két eigenvectors, $ \ket { 0 } $ és $ \ket { 1 } $ , a megfelelő eigenvalues $ \pm 1 $ .
Így ha mérjük a qubit és a beszerzést `Zero` (amely a 0. állapotnak felel meg $ \ket { } $ ), tudjuk, hogy a qubit állapota a $ $ Z operátor + 1 $ eigenstate $ .
Hasonlóképpen, ha beszerezhetjük `One` , tudjuk, hogy a qubit állapota a $ -1 $ eigenstate $ $ . Ezt a folyamatot a Pauli-mérések nyelvén kell megtekinteni, amely a "Pauli Z" mérési módszernek $ $ felel meg, és teljes mértékben megfelel a számítási alapokra vonatkozó mérések elvégzésének.

A $ \times $ Z egységes átalakítását biztosító 2 2 mátrix $ $ is megfelel ennek a feltételnek.
Ez azt is megteheti, hogy egy $ = u ^ \dagger Z u-es mátrixot is használhat $ , ahol az $ u $ bármely más egységes mátrix, amely egy olyan mátrixot biztosít, amely meghatározza egy mérték két eredményét a $ \pm 1 $ eigenvectors.
A Pauli-mérések jelölése erre az egységes egyenértékűségre hivatkozik, $ Ha az X, Y, Z $ méréseket egyenértékű mértékegységként azonosítja, amelyet az egyik a qubit származó információk megszerzésére használhat.
Ezek a mérések az alábbiakban láthatók a kényelem érdekében.


|Pauli-mérés –  | egységes átalakítás  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ Y | $HS ^               {\dagger}$         |

Ez a nyelv használata esetén a "Y mérték $ $ " egyenértékű a $ HS ^ alkalmazásával, \dagger $ majd a számítási folyamat alapján történő méréssel, ahol a [`S`](xref:Microsoft.Quantum.Intrinsic.S) belső kvantum-művelet néha "Phase Gate" néven is ismert, és az egységes mátrix szimulálható.

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

Emellett a $ HS ^ \dagger $ a Quantum State Vector-re való alkalmazása, majd a Z mérése is megegyezik azzal $ $ , hogy a következő művelet egyenértékű `Measure([PauliY], [q])` :

```qsharp
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

A megfelelő állapotot a rendszer úgy fogja megtalálni, hogy visszaalakítja a számítási alapot, amely az $ sh- $ t a kvantum-állapot vektorára alkalmazza; a fenti kódrészletben a blokk használatával automatikusan kezeli az átalakítást a számítási alapra `within … apply` .

A-ben Q# azt mondjuk, hogy az eredmény---az, hogy az---állapottal való interakcióból kinyert klasszikus információ "j" értékkel van megadva, amely azt jelzi, hogy `Result` $ \in \\ { \texttt { } \texttt { } \\ } $ az eredmény az $ (-1) ^ j eigenspace, amely a $ Pauli operátort méri.


## <a name="multiple-qubit-measurements"></a>Többszörös qubit mérések

A több-qubit Pauli-operátorok mérései hasonló módon vannak definiálva, ahogy a következőkben is látható:

$$
Z: 1 0 0 0 0 \otimes = \begin{bmatrix} & & – 1 0 0 0 0 & \\\\ & & & \\\\ & & – 1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1.
$$

Így a két Pauli- $ Z operátorok kétféle $ $ $ , 1 és $ -1 eigenvalues álló mátrixot alkotnak $ .
Az qubit esethez hasonlóan mindkettő fél helyet jelent, ami azt jelenti, hogy az elérhető vektor területének fele a $ + 1 $ eigenspace és a fennmaradó fele az $ -1 $ eigenspace tartozik.
Általánosságban elmondható, hogy a kéttengelyes termék definíciója alapján a Pauli- $ Z operátorok és az identitás bármely tenser terméke is betartja $ ezt.
Példa:

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 &  0 &  0 &  0 \\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & – 1 &  0 \\\\
        0 &  0 & & – 1 \end{bmatrix} .
\end{align}
$$

Ahogy korábban is, az ilyen mátrixok egységes átalakítása a \pm 1 eigenvalues által megcímkézett két fél szóközt is ismerteti $ $ .
Például: $ X \otimes x h = h \otimes (z \otimes z) h h \otimes , $  az identitástól, amely a $ z = HXH $ .
Az qubit esethez hasonlóan mind a kétqubit Pauli-mérések $ u ^ (Z) u-vel írhatók \dagger \otimes \id $ $ 4 \times 4 $ egységes mátrixhoz $ u $ . A következő táblázatban szereplő transzformációk enumerálása.

> [!NOTE]
>Az alábbi táblázatban a $ \operatorname { swap használatával } $ jelezheti a mátrixot >$$
> \begin{align}
>     \operatorname{SWAP } &=
>     \left( \begin { mátrix}
>         1 & 0 & 0 & 0 \\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & 0 & 1 > \end { mátrix } \right ) >     \end{align}
> $$
> a belső művelet szimulálására szolgál [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .

|Pauli-mérés –     | egységes átalakítás  |
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes Z $ | $ \operatorname { swap } $|
|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { swap } $|
|$\boldone \otimes Y $ | $ (hs ^ \dagger \otimes \boldone ) \operatorname { swap } $|
|$Z \otimes Z $ | $ \operatorname { cnem } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { cnem } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimes Z $ | $ \operatorname { cnem } \_ { 10 } (hs ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { cnem } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { cnem } \_ { 10 } (h \otimes h) $|
|$Y \otimes X $ | $ \operatorname { cnem } \_ { 10 } (hs ^ \dagger \otimes H) $|
|$Z \otimes Y $ | $ \operatorname { cnem } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes Y $ | $ \operatorname { cnem } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimes Y $ | $ \operatorname { cnem } \_ { 10 } (hs ^ \dagger \otimes HS ^ \dagger ) $|

Itt a [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) művelet a következő okból jelenik meg.
A fenti indoklásnak megfelelően minden olyan Pauli-mérés, amely nem tartalmazza a $ \boldone $ mátrixot, egy egységes, z z-ig egyenlő $ \otimes $ .
A z z $ eigenvalues \otimes csak az $ egyes számítási alapú vektorokból álló qubits paritása függ, és a vezérelt nem műveletek szolgálnak a paritás kiszámításához és az első bites tároláshoz.
Ezután az első bit mérése után helyreállítjuk az eredményül kapott fél terület identitását, amely egyenértékű a Pauli-operátor mérésével.

Egy további Megjegyzés: Ha úgy gondolja, hogy $ a z z 1. és 1. számú mérési érték \otimes $ megegyeznek $ \otimes \mathbb { } $ $ \mathbb { , akkor ez a } \otimes $ feltételezés hamis lenne.
Ennek az az oka, hogy a $ z \otimes z-ig a eigenstate a $ kvantum-állapotot a $ $ $ fenti operátorok + 1 vagy-1 $ értékére méri.
$ \otimes \mathbb { } $ $ \mathbb { Az 1. és 1 } \otimes . szám mérésével $ a Quantum State Vector először az $ 1. fele, \otimes \mathbb { } $ majd egy $ \mathbb { 1 } \otimes $ . fél szóközre van húzva. Mivel négy számítási alap vektor létezik, mindkét mérés végrehajtása csökkenti az állapotot egy negyedéves területre, és így csökkenti azt egyetlen számítási célú vektorban.

## <a name="correlations-between-qubits"></a>Qubitek közötti korreláció
A Pauli-mátrixok, például az x x vagy a z z. a tízesebb termékek mérésének egy másik módja, $ \otimes $ $ \otimes $ hogy ezek a méretek lehetővé teszik a két qubits közötti összefüggésekben tárolt információk megtekintését.
$Az X mérésével \otimes \id $ megtekintheti az első qubit helyileg tárolt adatokat.
Habár a kvantum-számítástechnika mindkét típusú mérése egyenlően értékes, a korábbi megvilágítja a kvantum-számítástechnika erejét.
Ez azt mutatja, hogy a kvantum-számítástechnikaban gyakran a tanulni kívánt információ nem egyetlen qubit van tárolva, hanem nem helyileg, hanem az összes qubits, és ezért csak egy közös mérésen (például z z) keresztül történik $ \otimes $ .

A hibajavítás során például gyakran szeretnénk megismerni, hogy milyen hibák történtek, miközben a rendszer nem a védelemmel ellátott állapotról tanul.
A [bit-flip code minta](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) példa arra, hogyan végezhető el a mérések használata, például z z és z z $ \otimes \otimes \id $ $ \id \otimes \otimes $ . < --TODO: változtassa meg a minta böngészőre mutató hivatkozást, amint a bit-flip code minta be van kapcsolva. -->

Az önkényes Pauli-operátorok, például az $ X \otimes Y \otimes Z \otimes \boldone $ is mérhetők.
A Pauli-operátorok összes ilyen tenser-terméke csak két eigenvalues $ \pm 1 $ , és mindkét eigenspaces a teljes vektoros terület felét képezi.
Így a fent említett követelmények egybeesnek.

A-ben az Q# ilyen mérések a j értéket adják vissza, $ $ Ha a mérés eredménye a $ következő: eigenspace (-1) ^ j $ .
Mivel a Pauli-mérések beépített funkciója hasznos, Q# mert az ilyen operátorok méréséhez hosszú láncú vezérelt, nem kapuk és átalakítások szükségesek, hogy leírják a diagonalizing U Gate, amely a művelet kiépítéséhez $ $ szükséges a $ Z és a $ $ \id $ .
Az előre definiált mérések egyikének megadásához nem kell aggódnia, hogy hogyan alakíthatja át az adatokat, hogy a számítási alap a szükséges információkat tartalmazza.
Q# automatikusan kezeli az összes szükséges átalakítást.
További információ: [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) és [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) műveletek.

## <a name="the-no-cloning-theorem"></a>A No-Cloning tétel

A Quantum információi hatékonyak.
Lehetővé teszi, hogy elképesztően olyan dolgokat végezzenek, mint a faktorok száma exponenciálisan, mint a legismertebb klasszikus algoritmusok, vagy hatékonyan szimulálja a korrelált elektron-rendszereket, amelyekkel a klasszikusan exponenciálisan kell szimulálni a pontos műveleteket.
A kvantum-számítástechnika hatékonysága azonban korlátozott.
Az egyik ilyen korlátozást a *nem klónozási tétel* adja meg.

A No-Cloning tétel találó nevű.
Az általános kvantum-állapotok egy kvantum-számítógép általi klónozását nem teszi lehetővé.
A tétel bizonyítása rendkívül egyszerű.
Habár a nem klónozási tétel teljes bizonyítéka egy kicsit túl sok technikai megoldás a vitához, a további kiegészítő qubits nem a hatókörén belül.

Egy ilyen kvantum-számítógép esetében a klónozási műveletet egy egységes mátrixtal kell ismertetni.
Megtiltjuk a mérést, mivel az sérült a klónozott állapotot.
A klónozási művelet szimulálása érdekében azt szeretnénk, hogy az egységes mátrix a következő tulajdonságot használja. $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
bármilyen állapothoz $ \ket { \psi } $ .
A mátrixok szorzásának lineáris tulajdonsága azt jelenti, hogy bármely második kvantum $ \ket { \phi } $ -állapotnál

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right )) \right .
\end{align}
$$

Ez biztosítja a No-Cloningi tétel mögötti alapvető intuíciót: minden olyan eszközön, amely ismeretlen kvantum-állapotot másol, hibákat kell kimutatnia legalább néhány, az általa másolt államban.
Míg a legfontosabb feltételezés, hogy a Cloner lineárisan működik a bemeneti állapoton, megsértheti a kiegészítő qubits hozzáadását és mérését, az ilyen interakciók pedig a mérési statisztikán keresztül a rendszerre vonatkozó információkat is felhasználhatják, és meggátolják az ilyen esetekben történő pontos klónozást is.
A No-Cloning tétel részletesebb igazolását lásd: [További információ](xref:microsoft.quantum.more-information).

A No-Cloningi tétel fontos a kvantum-számítástechnika minőségi megismerése érdekében, mert ha a kvantum-állapotok költséges klónozását is lehetővé teszi, akkor közel varázslatos képességet kap a kvantum-állapotok megismeréséhez.
Valójában megsértheti a Heisenberg hencegő bizonytalansági elvét.
Azt is megteheti, hogy az optimális Cloner használatával egyetlen mintát vesz igénybe egy összetett kvantum-eloszlásból, és megtudhatja, hogy az adott disztribúcióról csak egyetlen mintából lehet tájékozódni.
Ez olyan lenne, mint egy érme tükrözése és a fejek betartása, majd egy barátomnak szól az eredményről, amelynek a válaszát "Ah az érme eloszlásának Bernoulli kell lennie a $ p = 0.512643 \ ldots $ !"  Egy ilyen utasítás nem sensical, mert egy kis információ (a fejek végeredménye) egyszerűen nem tudja biztosítani az elosztás kódolásához szükséges több bitet a jelentős előzetes információk nélkül.
Hasonlóképpen, az előzetes információk nélkül nem tudjuk tökéletesen klónozott állapotba állítani a kvantum-állapotot $ $ .

Az információk nem ingyenesek a Quantum Computing szolgáltatásban.
A mért qubit egyetlen kis mennyiségű információt biztosítanak, és a No-Cloning-tétel azt mutatja, hogy nincs olyan hátsó ajtó, amely kihasználható a rendszeren szerzett információk és a meghívott zavarok közötti alapvető kompromisszum körül.
