---
title: Quantum Oracles Description: megtudhatja, hogyan dolgozhat és határozhat meg a Quantum Oracles, Black Box műveleteit, amelyeket egy másik algoritmus bemenetként használ.
Szerző: cgranade UID: Microsoft. Quantum. Concepts. Oracles MS. Author: chgranad MS. Date: 07/11/2018 MS. topic: konceptuális No-Loc:
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
# <a name="quantum-oracles"></a>Quantum jóslatok

Az Oracle $ O $ egy "fekete doboz" művelet, amelyet bemenetként használ egy másik algoritmushoz.
Az ilyen műveletek gyakran az $ f: \\ { 0, 1 \\ } ^ n 0, 1 ^ m klasszikus függvénnyel vannak definiálva, \to \\ { \\ } $ amely egy $ n $ bites bináris bemenetet vesz igénybe, és egy $ m $ bites bináris kimenetet hoz létre.
Ehhez vegye fontolóra egy adott bináris bemeneti $ x-t = (X_ { 0 } , X_ { 1 } , \dots, X_ { n-1 } ) $ .
Az qubit-állapotokat $ \ket { \vec { x } } = \ket { X_ { 0 } } \otimes \ket { X_ { 1 } } \otimes \cdots \otimes \ket { X_ { n-1 } } $ értékre lehet felcímkézni.

Először megpróbáljuk meghatározni az o-t $ $ , hogy az $ o \ket { x } = \ket { f (x) } $ , de ez néhány problémával is rendelkezik.
Először $ $ is lehet, hogy a bemeneti és kimeneti (n m) értéknek eltérő a mérete $ \ne $ , így az $ O alkalmazása $ megváltoztathatja a regisztrációban lévő qubits számát.
Másodszor, még ha $ n = m is $ , a függvény nem lehet invertálható: Ha $ f (x) = f (y) $ egy $ x \ne y $ , akkor az $ o \ket { x } = o \ket { y, } $ de $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .
Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $ O ^ \dagger $ , és az Oracles-nek hozzá kell adni egy adjoint.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján
Mindkét problémát felhasználhatjuk egy második m qubits-regisztráció bevezetésével $ $ , hogy megtartsa a választ.
Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $ x \in \\ { 0, 1 \\ } ^ n $ és $ y \in \\ { 0, 1 \\ } ^ m $ értéknél.

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Most $ o = o ^ \dagger $ by Construction, így mindkét korábbi problémát megoldottuk.

> [!TIP]
>Ha szeretné megtekinteni, hogy az o $ = { \dagger } $ $ ^ 2 = \boldone $ $ egy \oplus b \oplus = , b:: $ $ \in \: No-Loc ({)::: 0, 1 \: :: No-Loc (}) $ :::.
>Ennek eredményeképpen az $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

Fontos, hogy az Oracle ily módon történő meghatározása az egyes számítási állapotok esetében $ \ket { x } \ket { y azt } $ is meghatározza, hogy az $ O hogyan $ viselkedik bármely más államban.
Ez azonnal az a tény, hogy az $ O $ , mint az összes kvantum-művelet, lineáris abban az állapotban, amelyben működik.
Vegye figyelembe a Hadamard műveletet, például: $ h \ket { 0 } = \ket { + } $ és $ h \ket { 1 } = \ket { - } $ .
Ha tudni szeretné, hogyan viselkedik $ a h, akkor a $ $ \ket { + } $ $ h $ lineáris,

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

Az Oracle O meghatározása esetén $ $ hasonlóképpen használhatjuk azt is, hogy az $ \ket { \psi } $ $ n + m qubits lévő állapotok a $ következőképpen írhatók:

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

ahol $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ az állapot együtthatóit jelöli $ \ket { \psi } $ . Így

$$
\begin{align}
O \ket { \psi } & = o \sum _{ x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum_ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Jóslatok fázisa
Azt is megteheti, $ hogy egy Oracle o-ra kódolja az f- $ t egy $ $ , a bemeneten alapuló _fázis_ alkalmazásával $ $ . Például meghatározhatjuk az O-t, $ $ hogy $$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Ha az Oracle egy fázisban először egy számítási állapotú x-ben működik $ \ket { } $ , akkor ez a fázis globális fázis, ezért nem észlelhető.
Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.
Tegyük fel például, hogy egy fázis Oracle $ $ -O_f az f qubit függvényhez $ $ .
Majd $$
\begin{align}
    O_f \ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0) – f (1) } \ket { + } .
\end{align}
$$

> [!NOTE]
>Vegye figyelembe, hogy $ z ^ { -1 } = z ^ { \dagger } = z $ és ezért $ z ^ { f (0)-f (1) } = z ^ { f (1)-f (0) } .$

Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.

Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.
A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.


További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.
