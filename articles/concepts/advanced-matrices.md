---
title: részletes mátrix – fogalmak leírása: Ismerje meg a eigenvectors, a eigenvalues és a mátrix exponenciálisait, a kvantum-algoritmusok leírásához és szimulálásához használt alapvető eszközöket.
Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. Matrix – speciális MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Speciális mátrix-fogalmak #

Most kiterjesztjük a mátrixok manipulációját a [*Eigenvalues, a Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) és az [*exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) értékekre, amelyek a kvantum-algoritmusok leírásához és megvalósításához szükséges alapvető eszközkészletet alkotnak.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues és Eigenvectors ##

Legyen $ $ egy négyzetes mátrix, a $ v pedig $ egy olyan vektor, amely nem az összes nulla vektor (azaz a vektor és az összes bejegyzés értéke $ 0 $ ).

Tegyük fel, hogy a $ v $ egy [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) , $ Ha az $ $ MV = CV $ néhány c számú $ $ . A $ c érték azt jelenti $ , hogy a [*sajátérték*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) megfelelő a eigenvector $ v $ . Az M mátrix általában $ egy $ vektort alakíthat át bármilyen más vektorba, de egy eigenvector speciális, mert változatlan marad, kivéve, ha egy szám megszorozza. Vegye figyelembe, hogy ha $ $ a v egy eigenvector a sajátérték $ c $ -vel, akkor $ $ az AV is egy eigenvector (bármilyen nullától $ $ eltérő), ugyanazzal a sajátérték.

Az Identity Matrix esetében például minden vektor $ v $ egy eigenvector, amely sajátérték $ 1 $ .

Egy másik Példaként vegyünk egy olyan, a D típusú [*átlós mátrixot*](https://en.wikipedia.org/wiki/Diagonal_matrix) , $ $ amely csak nullától eltérő bejegyzéseket tartalmaz az átlóban:

$$
\begin{bmatrix}
d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix} .
$$

A vektorok

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} és \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

Ennek a mátrixnak a eigenvectors a eigenvalues $ d_1 $ , $ d_2 $ és $ d_3 $ . Ha $ d_1 $ , $ d_2 $ és $ d_3 $ különböző számok, akkor ezek a vektorok (és azok többszörösei) a d mátrix egyetlen eigenvectors $ $ . Az átlós mátrixok esetében általában könnyen olvasható a eigenvalues és a eigenvectors. A eigenvalues az átlóban megjelenő számok, a hozzájuk tartozó eigenvectors pedig az egység vektorok, amelyek egy bejegyzése $ 1 $ , a fennmaradó bejegyzések pedig 0 értékűek $ $ .

Vegye figyelembe a fenti példában, hogy a D eigenvectors a $ $ $ 3 $ dimenziós vektorok alapját képezi. Az alap olyan vektorok halmaza, amelyekben a vektorok lineáris kombinációként is írhatók. Explicit módon, $ v_1 $ , $ v_2 $ és $ v_3 formában, $ Ha bármelyik Vector $ v $ $ = a_1 v_1 + a_2 v_2 + a_3 v_3 $ néhány szám $ a_1 $ , $ a_2 $ és a_3 számára $ $ .

Ne felejtse el, hogy egy Hermitian mátrix (más néven adjoint) egy összetett négyzet alakú mátrix, amely a saját összetett konjugált átültetésével egyenlő, míg az egységes mátrix egy olyan összetett négyzetes mátrix, amelynek az inverze megegyezik a adjoint vagy összetett konjugátum-átültetéssel.
A Hermitian és az egységes mátrixok esetében, amelyek lényegében csak egyetlen, a Quantum Computing-ben észlelt mátrixok, egy általános eredmény a [*spektrális tétel*](https://en.wikipedia.org/wiki/Spectral_theorem), amely a következőket állítja be: bármely Hermitian vagy egységes mátrixú $ m esetében $ létezik egy egységes $ U, $ például $ m = u ^ \dagger D u egy $ átlós mátrix d-hez $ $ . Továbbá a D átlós bejegyzései $ $ az M eigenvalues lesznek $ $ .

Már tudjuk, hogyan számítjuk ki a eigenvalues és a eigenvectors egy átlós mátrix D-ben $ $ . A tétel használatával tudjuk, hogy ha a $ v $ egy eigenvector, $ a $ sajátérték $ c $ , azaz a $ DV = CV, az $ $ U ^ \dagger v $ $ $ a sajátérték c eigenvector lesz $ $ . Ennek az az oka, hogy

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Mátrix exponenciális
A [*mátrix exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) meghatározása pontosan az exponenciális függvényhez hasonlóan is megadható.  Az a mátrix exponenciálisa lehet $ a $ következőképpen kifejezve

$$
e ^ A = \boldone + a + a \frac { ^ 2 } { 2! } + \frac { ^ 3 } { 3!}+\cdots
$$

Ez azért fontos, mert a Quantum Mechanical Time Evolution leírását az $ e ^ { } $ Hermitian Matrix $ B $ .  Emiatt a Matrix exponenciálisok végrehajtása a kvantum-számítástechnika alapvető része, és mint ilyen, Q# belső rutinokat kínál ezeknek a műveleteknek a leírásához.
A mátrix exponenciális felszámításának számos módja van a klasszikus számítógépeken, és általában számszerűen közelíthető meg egy ilyen exponenciális megoldás.  Lásd: [*Cleve moleer és Charles van Loan. "Tizenkilenc kétes módszer a mátrix exponenciális kiszámítására." SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) az érintett kihívásokkal kapcsolatos további információkért.

A mátrix exponenciális kiszámításának legegyszerűbb módja a mátrix eigenvalues és eigenvectors.  Pontosabban, a fentiekben tárgyalt spektrális tétel azt mondja, hogy minden Hermitian vagy egységes mátrixnál $ $ létezik egy egységes mátrix $ U $ és egy átlós mátrix $ d, $ például $ egy = u ^ \dagger D u $ .  A unitarity tulajdonságai miatt $ egy ^ 2 = u ^ d ^ \dagger 2 u $ , és hasonlóképpen bármely Power $ p a $ $ ^ = \dagger $ p u ^ p ^ p u.  Ha ezt a műveletet behelyettesítjük az operátor definíciójában, a következőt kapjuk:

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { ! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 0 & \cdots & \\\\ 0 & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$

Más szóval, ha az a mátrix eigenbasis alakítja át a mátrixot, $ $ akkor a mátrix exponenciális értéke a mátrix eigenvalues szokásos exponenciális számításával egyenértékű.  A Quantum Computing számos művelete magában foglalja a mátrixok exponenciális használatát, ez a trükk a mátrix eigenbasis való átalakítását mutatja be, amely egyszerűbbé teszi az operátor exponenciális megjelenítését, és számos olyan kvantum-algoritmus mögött található, mint például a Trotter – Suzuki stílusú kvantum-szimulációs módszerek, amelyeket az útmutató későbbi szakaszában ismertetünk.

Egy másik hasznos tulajdonság az, ha a $ B $ mind az egységes, mind a Hermitian, azaz $ b = b ^ { -1 } = b ^, \dagger $ majd $ b ^ 2 = \boldone $ . Ha ezt a szabályt a mátrix exponenciális kiterjesztésére, valamint a $ \boldone $ és a B kifejezés csoportosítására $ alkalmazza $ , akkor láthatja, hogy bármely valós érték $ x $ az identitás

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


rendelkezik. Ez a trükk különösen hasznos, mivel ez a művelet lehetővé teszi, hogy a mátrix exponenciális értékekkel rendelkezzen, még akkor is, ha a $ b dimenzió $ exponenciálisan nagy méretű, a speciális esetben, ha a $ b az $ egységes és a Hermitian.
