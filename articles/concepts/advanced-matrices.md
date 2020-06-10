---
title: Speciális mátrixfogalmak
description: Ismerje meg a eigenvectors, a eigenvalues és a mátrix exponenciális adatait, a kvantum-algoritmusok leírására és szimulálására szolgáló alapvető eszközöket.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630153"
---
# <a name="advanced-matrix-concepts"></a>Speciális mátrix-fogalmak #

Most kiterjesztjük a mátrixok manipulációját a [*Eigenvalues, a Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) és az [*exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) értékekre, amelyek a kvantum-algoritmusok leírásához és megvalósításához szükséges alapvető eszközkészletet alkotnak.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues és Eigenvectors ##

Legyen $M $ egy négyzetes mátrix, és $v $ olyan vektor, amely nem az összes nulla vektor (azaz a vektor, amely az összes olyan bejegyzést tartalmazza, amely a $0 értékkel egyenlő $ ).

Tegyük fel $ , hogy $v $M [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) , $ Ha $MV = cv $ bizonyos számú $c $ . Tegyük fel, hogy $c a $ eigenvector $v megfelelő [*sajátérték*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ . A mátrixok $M általában egy $ vektort is átalakíthat bármely más vektorba, de egy eigenvector speciális, mert változatlan marad, kivéve, ha egy szám megszorozza. Vegye figyelembe, hogy ha $v $ egy eigenvector, amely sajátérték $c $ , akkor $AV $ is egy eigenvector (minden nem nulla $a esetében $ ) ugyanazzal a sajátérték.

Az Identity Matrix esetében például minden vektor $v $ egy eigenvector, amely sajátérték $1 $ .

Egy másik Példaként vegyünk egy olyan [*átlós mátrixot*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D, $ amely csak nullától eltérő bejegyzéseket tartalmaz az átlóban:

$ $ \begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \end{ bmatrix } .
$$

A vektorok

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } és \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$

Ennek a mátrixnak a eigenvectors a eigenvalues $d _1 $ , $d _2 $ és $d _3 $ . Ha $d _1 $ , $d _2 $ , és $d _3 $ különböző számok, akkor ezek a vektorok (és azok többszörösei) a mátrix $D egyetlen eigenvectors $ . Az átlós mátrixok esetében általában könnyen olvasható a eigenvalues és a eigenvectors. A eigenvalues az átlóban megjelenő számok, a hozzájuk tartozó eigenvectors pedig az egység vektorok, amelyek egy bejegyzése $1 $ , a fennmaradó bejegyzések pedig $0 $ .

Vegye figyelembe a fenti példában, hogy a eigenvectors $D a $ $3 $ dimenziós vektorok alapjait alkotják. Az alap olyan vektorok halmaza, amelyekben a vektorok lineáris kombinációként is írhatók. Explicit módon $v _1 $ , $v _2 $ , és $v _3, $ ha bármilyen vektor $v $ írható $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ néhány szám $a _1 $ , $a _2 $ és $a _3 $ .

Ne felejtse el, hogy egy Hermitian mátrix (más néven önadjoint) egy összetett négyzetes mátrix, amely a saját összetett konjugátumával egyenlő, míg az egységes mátrix egy olyan összetett négyzetes mátrix, amelynek inverze egyenlő a komplex konjugátummal.
A Hermitian és az egységes mátrixok esetében, amelyek lényegében csak egyetlen, a Quantum Computing-ben észlelt mátrixok, egy általános eredmény a [*spektrális tétel*](https://en.wikipedia.org/wiki/Spectral_theorem), amely a következőket állítja be: bármely Hermitian vagy egységes mátrixú $M esetében $ létezik egy egységes $U, $ hogy $M = U ^ \dagger D u $ egy átlós mátrix $D $ . Emellett a $D átlós bejegyzései $ a $M eigenvalues lesznek $ .

Már tudjuk, hogyan kell kiszámítani egy átlós mátrix $D eigenvalues és eigenvectors $ . Ennek a tételnek a használatával tudjuk, hogy ha a $v $ $D $ sajátérték $c $ , például $DV = CV $ , akkor a $U ^ \dagger v $ eigenvector $M $ sajátérték $c $ . Ennek az az oka, hogy

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Mátrix exponenciális
A [*mátrix exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) meghatározása pontosan az exponenciális függvényhez hasonlóan is megadható.  Mátrix $A mátrixának exponenciális $ kifejezése

$ $ e ^ A = \boldone + a + \frac{A {2 } !} + \frac{A ^ 3 } {3!} + \cdots $ $

Ez azért fontos, mert a Quantum Mechanical Time Evolution leírását az űrlap egy egységes mátrixa írja le, $e ^ {iB } $ for Hermitian matrix $B $ .  Emiatt a Matrix exponenciálisok végrehajtása a kvantum-számítástechnika alapvető részét képezi, és a Q # olyan belső rutinokat kínál, amelyek ezeknek a műveleteknek a leírására szolgálnak.
A mátrix exponenciális felszámításának számos módja van a klasszikus számítógépeken, és általában számszerűen közelíthető meg egy ilyen exponenciális megoldás.  Lásd: [*Cleve moleer és Charles van Loan. "Tizenkilenc kétes módszer a mátrix exponenciális kiszámítására." SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) az érintett kihívásokkal kapcsolatos további információkért.

A mátrix exponenciális kiszámításának legegyszerűbb módja a mátrix eigenvalues és eigenvectors.  A fent tárgyalt spektrális tétel azt mondja, hogy minden Hermitian vagy egységes mátrixnál $A $ létezik egy egységes mátrix $U $ és egy átlós mátrix $D $ , amely $A = u ^ \dagger D u $ .  A unitarity tulajdonságai miatt $A ^ 2 = U ^ \dagger D ^ 2 U $ és hasonló módon bármely power $p $ $A ^ p = u ^ \dagger D ^ p U $ .  Ha ezt a műveletet behelyettesítjük az operátor definíciójában, a következőt kapjuk:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!}) + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $

Más szóval, ha a mátrix eigenbasis alakítja át a $A, $ majd a mátrix exponenciális megszámításával egyenértékű a mátrix eigenvalues.  A Quantum Computing számos művelete magában foglalja a mátrixok exponenciális használatát, ez a trükk a mátrix eigenbasis való átalakítását mutatja be, amely egyszerűbbé teszi az operátor exponenciális megjelenítését, és számos olyan kvantum-algoritmus mögött található, mint például a Trotter – Suzuki stílusú kvantum-szimulációs módszerek, amelyeket az útmutató későbbi szakaszában ismertetünk.

Egy másik hasznos tulajdonság az, ha a $B $ egységes és Hermitian, például $B = b ^ {-1 } = B ^ \dagger, $ majd $B ^ 2 = \boldone $ . Ha ezt a szabályt a mátrix exponenciális kiterjesztésére, valamint a $ \boldone $ és a $B feltételek csoportosítására alkalmazza $ , akkor láthatja, hogy a valódi érték $x $ az identitást.

$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $


rendelkezik. Ez a trükk különösen hasznos, mivel ez a művelet lehetővé teszi, hogy az egyes műveletek mátrixa exponenciálisan megtörténjen, még akkor is, ha a $B dimenziója $ exponenciálisan nagy, a speciális esetre, ha a $B $ mind az egységes, mind a Hermitian.
