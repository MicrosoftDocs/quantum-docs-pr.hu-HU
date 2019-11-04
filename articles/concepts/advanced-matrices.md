---
title: Speciális mátrix-fogalmak | Microsoft Docs
description: Speciális mátrix-fogalmak
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183760"
---
# <a name="advanced-matrix-concepts"></a>Speciális mátrix-fogalmak #

Most kiterjesztjük a mátrixok manipulációját a [*Eigenvalues, a Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) és az [*exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) értékekre, amelyek a kvantum-algoritmusok leírásához és megvalósításához szükséges alapvető eszközkészletet alkotnak.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues és Eigenvectors ##

$M $ legyen egy négyzetes mátrix, és $v $ olyan vektor, amely nem az összes nulla vektor (azaz a vektor, amely az összes olyan bejegyzést tartalmazza, amely a $0 $ értékkel egyenlő).

Tegyük fel, hogy a $v $ $M $ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) , ha $MV = cv $ $c $ értékkel. Tegyük fel, hogy $c $ a eigenvector $v $ értéknek megfelelő [*sajátérték*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) . Általában a mátrix $M $ a vektort bármely más vektorba alakíthatja át, de egy eigenvector speciális, mert nem változik, kivéve, ha egy szám megszorozza. Vegye figyelembe, hogy ha a $v $ eigenvector a sajátérték $c $ értékkel rendelkezik, akkor $av $ is egy eigenvector (minden nem nulla $a $ esetén) ugyanazzal a sajátérték.

Az Identity Matrix esetében például minden Vector $v $ egy eigenvector, amely sajátérték $1 $.

Egy másik Példaként vegyünk egy $D $ [*átlós mátrixot*](https://en.wikipedia.org/wiki/Diagonal_matrix) , amely csak nullától eltérő bejegyzéseket tartalmaz az átlóban:

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.
$$

A vektorok

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0 \ End {bmatrix} és \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ Befejezés {bmatrix} $ $

Ennek a mátrixnak a eigenvectors a eigenvalues $d _1 $, $d _2 $ és $d _3 $. Ha $d _1 $, $d _2 $, és $d _3 $ egyedi számú, akkor ezek a vektorok (és azok többszörösei) az egyetlen eigenvectors a mátrix $D $. Az átlós mátrixok esetében általában könnyen olvasható a eigenvalues és a eigenvectors. A eigenvalues az átlóban megjelenő számok, a hozzájuk tartozó eigenvectors pedig az egység vektorok, amelyek egy bejegyzése $1 $, a fennmaradó bejegyzések pedig $0 $ értékűek.

Vegye figyelembe a fenti példában, hogy a $D $ eigenvectors a $3 $-dimenziós vektorok alapjául szolgál. Az alap olyan vektorok halmaza, amelyekben a vektorok lineáris kombinációként is írhatók. Explicit módon, $v _1 $, $v _2 $ és $v _3 $ Form, ha bármely vektor $v $ írható $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ értékkel $a _1 $, $a _2 $ és $a _3 $ esetében.

Ne felejtse el, hogy egy Hermitian mátrix (más néven önadjoint) egy összetett négyzetes mátrix, amely a saját összetett konjugátumával egyenlő, míg az egységes mátrix egy olyan összetett négyzetes mátrix, amelynek inverze egyenlő a komplex konjugátummal.
A Hermitian és az egységes mátrixok esetében, amelyek lényegében csak egyetlen, a Quantum Computing-ben észlelt mátrixok, egy általános eredmény az úgynevezett [*spektrális tétel*](https://en.wikipedia.org/wiki/Spectral_theorem), amely az alábbiakat állítja be: bármely Hermitian vagy egységes Matrix $M $ esetén létezik az egységes $U $ például, hogy $M = U ^ \dagger D U $ egy átlós mátrixhoz $D $. Továbbá a $D $ átlós bejegyzései a $M $ eigenvalues lesznek.

Már tudjuk, hogyan kell kiszámítani egy átlós mátrix $D $ eigenvalues és eigenvectors. Ennek a tételnek a használatával tudjuk, hogy ha $v $ eigenvector $D $ sajátérték $c $, azaz $Dv = CV $, akkor $U ^ \dagger v $ lesz $M $ sajátérték $c $-eigenvector. Ennek az az oka, hogy

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Mátrix exponenciális
A [*mátrix exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) meghatározása pontosan az exponenciális függvényhez hasonlóan is megadható.  A mátrix $A $ mátrixának exponenciális mátrixa a következőképpen fejezhető ki

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2!} + \frac{A ^ 3} {3!} + \cdots $ $

Ez azért fontos, mert a Quantum Mechanical Time Evolution az űrlap egy egységes mátrixa alapján van leírva, $e ^ {iB} $ a Hermitian Matrix $B $ esetében.  Emiatt a Matrix exponenciálisok végrehajtása a kvantum-számítástechnika alapvető részét képezi, és a Q # olyan belső rutinokat kínál, amelyek ezeknek a műveleteknek a leírására szolgálnak.
A mátrix exponenciális felszámításának számos módja van a klasszikus számítógépeken, és általában számszerűen közelíthető meg egy ilyen exponenciális megoldás.  Lásd: [*Cleve moleer és Charles van Loan. "Tizenkilenc kétes módszer a mátrix exponenciális kiszámítására." SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) az érintett kihívásokkal kapcsolatos további információkért.

A mátrix exponenciális kiszámításának legegyszerűbb módja a mátrix eigenvalues és eigenvectors.  Pontosabban, a fent tárgyalt spektrális tétel azt mondja, hogy minden Hermitian vagy egységes mátrixnál $A $ létezik egy egységes mátrix $U $ és egy átlós mátrix $D $, amely $A = U ^ \dagger D U $.  A unitarity tulajdonságai miatt a $A ^ 2 = U ^ \dagger D ^ 2 U $, és hasonlóképpen bármely Power $p $ $A ^ p = U ^ \dagger D ^ p U $.  Ha ezt a műveletet behelyettesítjük az operátor definíciójában, a következőt kapjuk:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2} {2!} + \cdots \right) U = U ^ \dagger \begin{bmatrix}\exp (D_{11}) & 0 & \cdots & 0\\\\ 0 & \exp (D_{22}) & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp (D_ {NN}) \end{bmatrix} U. $ $

Más szóval, ha a mátrix $A $ eigenbasis alakítja át, akkor a mátrix exponenciális felszámításának alapja a mátrix eigenvalues a szokásos exponenciális értékének kiszámítása.  A kvantum-számítástechnika számos művelete magában foglalja a mátrixok exponenciális használatát, ez a trükk a mátrix eigenbasis való átalakítását jelenti, hogy leegyszerűsítse a kezelő exponenciális megjelenítését, és számos olyan kvantum-algoritmus mögött van, mint például a Trotter – Suzuki stílusú Quantum szimulációs módszerek az útmutató későbbi részében.

Egy másik hasznos tulajdonság az, ha a $B $ is egységes és Hermitian, például $B = B ^{-1}= B ^ \dagger $, majd $B ^ 2 = \boldone $. Ha ezt a szabályt a mátrix exponenciális kiterjesztésére alkalmazza, valamint a $ \boldone $ és a $B $ kifejezések csoportosításával, úgy láthatja, hogy minden valós értékhez $x $ az identitás

$ $e ^ {iBx} = \boldone \cos (x) + iB\sin (x) $ $


rendelkezik. Ez a trükk különösen hasznos, mivel ez a művelet lehetővé teszi, hogy az exponenciálisan feltett műveleteket a mátrixban, még akkor is, ha a $B $ értéke exponenciálisan nagy, akkor is, ha a $B $ értéke egységes és Hermitian.
