---
title: vektorok és mátrixok a kvantum-számítástechnikai leírásban: megismerheti a vektorok és mátrixok használatának alapjait.
Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. vectors MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: cikk No-Loc:
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

# <a name="vectors-and-matrices"></a>Vektorok és mátrixok

A kvantum-számítástechnika megismeréséhez elengedhetetlen a vektorok és mátrixok megismerése. Egy rövid bevezetést biztosítunk, és az érdekelt olvasóknak javasoljuk, hogy szabványos referenciát olvassanak a lineáris algebra, például a *furcsa, a G (1993) számára. A lineáris algebra bemutatása (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* vagy online referenciák, például [lineáris algebra](http://joshua.smcvt.edu/linearalgebra/).

A dimenzió (vagy a méret) n egy oszlop vektora (vagy egy egyszerű [*vektora*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ $ $ $ egy $ $ oszlopként rendezett, n komplex szám $ (v_1, v_2, \ldots, v_n) gyűjteménye $ :

$$v=\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n\end{bmatrix}$$

A Vector v szabványa $ a $ következőképpen van definiálva: $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ . A vektorok egység normának számítanak (vagy más néven [*egység vektornak*](https://en.wikipedia.org/wiki/Unit_vector)nevezik), ha a norma értéke $ 1 $ . A [*vektoros v adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ a $ $ v ^ \dagger $ -t jelöli, és a következő sor-vektorra van beállítva $ \* $ , amely a komplex konjugátumot jelöli.

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

A két vektor együttes összeszorzásának leggyakoribb módja a [*belső termék*](https://en.wikipedia.org/wiki/Inner_product_space), más néven a dot termék.  A belső termék lehetővé teszi egy vektor kivetítését egy másikra, és felbecsülhetetlen értékű, hogy leírja, hogyan lehet egy vektort más egyszerűbb vektorok összegével kifejezni.  Az $ u $ és $ v közötti $ $ \left \langle \right \rangle $ belső termék az u és v

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Ez a jelölés azt is lehetővé teszi, hogy a Vector v szabványa $ $ $ \sqrt { \langle v, v \rangle } $ formában legyen megírva.

Egy c számú vektort is használhatunk egy olyan új vektor létrehozásához, $ $ amelynek a bejegyzései a c értékkel vannak megszorozva $ $ . Az u és v két vektort is hozzáadhat $ $ $ $ egy olyan új vektor létrehozásához, amelynek bejegyzései az $ u $ és v bejegyzéseinek összege $ $ . Ezek a műveletek az alábbi ábrán láthatók:

$$\mathrm{Ha } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { és}~
v=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} , ~ \mathrm { majd}~
Au + BV=\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} .
$$

Az [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $ m n méretű mátrix \times $ egy olyan MN komplex számokból álló gyűjtemény, amelyeknek $ az értéke $ $ m $ és n oszlopban van rendezve $ $ , ahogy az alábbi ábrán látható:

$$M= 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
\ddots\\\\
M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}\\\\
\end{bmatrix}.$$

Vegye figyelembe, hogy az n dimenzió vektora $ $ egyszerűen az $ n 1 méretű mátrix \times $ . Csakúgy, mint a vektorok esetében, egy c számú mátrixot is használhatunk egy olyan $ $ új mátrix beszerzéséhez, ahol minden egyes bejegyzés a c értékkel van megszorozva $ $ , és két mátrixot is hozzáadhat egy olyan új mátrix létrehozásához, amelynek bejegyzései a két mátrix megfelelő bejegyzéseinek összege. 

## <a name="matrix-multiplication-and-tensor-products"></a>Mátrix – szorzási és a tenser-termékek

A n p dimenzióval rendelkező, m n és n dimenziót tartalmazó két mátrixot is szorozzuk $ $ $ \times $ $ $ $ \times $ kell, hogy egy új, m p-es mátrixot kapjon a $ $ $ \times $ következő módon:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\
    M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
    \ddots\\\\
    M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\
\ddots\\\\
N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { np}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1p}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\
\ddots\\\\
P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}
\end{bmatrix}
\end{align}

ahol a $ P bejegyzéseinek $ $ P_ { ik } = \sum _j M_ { ij } N_ { JK } $ . Például a $ P_ 11 bejegyzés a { } $ N első sorának belső terméke, $ $ amely az első oszlop $ $ . Vegye figyelembe, hogy mivel a vektor egyszerűen egy mátrix speciális esete, ez a definíció a mátrix-vektoros szorzásra terjed ki. 

A rendszer az összes olyan mátrixot felveszi, amely a sorok és oszlopok száma, illetve a vektorok, amelyek csak $ 1 oszlopnak felelnek meg $ . Egy speciális négyzetes mátrix az [*azonosító mátrix*](https://en.wikipedia.org/wiki/Identity_matrix), $ \boldone $ amely az összes átlós elemmel egyenlő 1 értékkel, $ $ a többi elem pedig $ 0 $ :

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

Az a négyzetes mátrix esetében $ $ mondjuk, hogy a $ B mátrix a $ saját [*inverze*](https://en.wikipedia.org/wiki/Invertible_matrix) , ha $ AB = ba = \boldone $ . A mátrix inverzének nem kell léteznie, de ha létezik, egyedi, és $ egy ^-1 jelölést jelölünk { } $ . 

Az m mátrix $ $ adjoint vagy a konjugátum átültetése $ egy olyan $ mátrix, $ $ amely $ N_ { ij } = M_ { Ji } ^ \* $ -t tartalmaz. Az m adjoint $ $ általában az m ^ jelöli $ \dagger $ . Tegyük fel, hogy a mátrix $ u egy $ [*egységes*](https://en.wikipedia.org/wiki/Unitary_matrix) $ , ha uu ^ \dagger = u ^ \dagger u = \boldone $ vagy azzal egyenértékű, $ u ^ { -1 } = u ^ \dagger $ .  Az egységes mátrixok legfontosabb tulajdonsága az, hogy megőrzik a vektorok normáit.  Ez azért történik, mert 

$$\langlev, v \rangle = v ^ \dagger v ^ = u ^ \dagger { -1 } u v = v ^ \dagger u ^ \dagger u v = \langle u, u v \rangle .$$  

Az $ m mátrix $ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , ha $ m = m ^ \dagger $ .

Végezetül, a kétféle, m n és n méretű, a p-s mérettel rendelkező két mátrixos [*termék (vagy*](https://en.wikipedia.org/wiki/Tensor_product) Kronecker-termék) $ $ $ \times $ $ $ $ \times $ nagyobb $ = \otimes $ $ , mint az MP NQ, a mérete pedig \times $ $ m $ és $ n $ , amely az alábbiak szerint érhető el:

\begin{align}
    M \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ M_ { 1N }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ M_ { MN  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ  }\\\\
        \ddots\\\\
        N_ { P1 } ~~ \cdots ~~ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Ez jobban szemlélteti néhány példát:

$$
    \begin{bmatrix}
        \\\\b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}a c \\\\ a d \\\\ a e \\\\ b c \\\\ d \\\\\end{bmatrix}
$$

és

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h\end{bmatrix}
     =
    \begin{bmatrix}
    egy\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    d\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AK \ AF \ be \ BF\\\\
    AG \ ah \ BG \ BH\\\\
    CE \ CF \ de \ DF\\\\
    CG \ CH \ DG \ DH \end{bmatrix} .
$$

A legtöbbet a következő, a TEN-termékekkel kapcsolatos utolsó hasznos jelölési konvenció az, hogy bármely vektoros $ v $ -vagy mátrix $ $ -m, $ v ^ { \otimes n } $ vagy $ M ^ { \otimes n } $ rövid kéz egy $ n $ -szor ismétlődő tenser termékhez.  Például:

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ – 1 \end{bmatrix} ^ { \otimes 2 1 – 1 } = \begin{bmatrix} \\\\ \\\\ – 1 \\\\ 1 \end{bmatrix} ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 0 1 0 } = \begin{bmatrix} & \\\\ & \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 2 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & 1 0 0 \\\\ & & 1 0 0 & \\\\ & 1 0 0 1 & & \\\\ & & & \end{bmatrix} 0 0.
\end{align}
