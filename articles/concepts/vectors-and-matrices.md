---
title: Vektorok és mátrixok a kvantum-számítástechnikában
description: Megismerheti a vektorok és mátrixok használatának alapjait.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630201"
---
# <a name="vectors-and-matrices"></a>Vektorok és mátrixok

A kvantum-számítástechnika megismeréséhez elengedhetetlen a vektorok és mátrixok megismerése. Egy rövid bevezetést biztosítunk, és az érdekelt olvasóknak javasoljuk, hogy szabványos referenciát olvassanak a lineáris algebra, például a *furcsa, a G (1993) számára. A lineáris algebra bemutatása (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* vagy online referenciák, például [lineáris algebra](http://joshua.smcvt.edu/linearalgebra/).

A dimenzió (vagy a méret) $n egy oszlop vektora (vagy egyszerűen [*vektoros*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v a (z) $ $ $n $ komplex számok (v_1, v_2, \ldots, v_n) száma oszlopként rendezve:

$ $v = \begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

A vektoros $v normája $ $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $-ként van definiálva. A vektorok egység normának számítanak (vagy más néven [*egység vektoros*](https://en.wikipedia.org/wiki/Unit_vector)), ha a norma értéke $1 $ . A [*vektoros $v adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $v ^ \dagger van megadva, és az $ a következő sor vektorra van meghatározva, ahol a $ \* $ a komplex konjugátumot jelöli,

$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ * & \cdots & v_n ^ * \end{bmatrix}$$

A két vektor együttes összeszorzásának leggyakoribb módja a [*belső termék*](https://en.wikipedia.org/wiki/Inner_product_space), más néven a dot termék.  A belső termék lehetővé teszi egy vektor kivetítését egy másikra, és felbecsülhetetlen értékű, hogy leírja, hogyan lehet egy vektort más egyszerűbb vektorok összegével kifejezni.  A $u és $v közötti belső termék a $ $ $ \left \langle u, v \right \rangle $ értékkel van definiálva

$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Ez a jelölés azt is lehetővé teszi, hogy egy vektor $v a $ $ \sqrt { \langle v, v $ formátumban legyen megírva \rangle } .

Megszorozhat egy számmal $c vektort $ , amely egy olyan új vektort alkot, amelynek a bejegyzései megszorozzák a $c $ . Két vektort is hozzáadhat $u $ és $v $ egy olyan új vektor létrehozásához, amelynek bejegyzései a $u és $v bejegyzéseinek összege $ $ . Ezek a műveletek az alábbi ábrán láthatók:

$ $ \mathrm{If } ~ u = \begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{ bmatrix } .
$$

A $m \times n méretű [*mátrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $ egy $MN komplex számokból álló gyűjtemény, amely $ $m $ sorokban és $n $ oszlopokban van rendezve, ahogy az alábbi ábrán látható:

$ $M = \begin{bmatrix}
M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\
M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {MN } \\ \\ \end{ bmatrix } . $ $

Vegye figyelembe, hogy a Dimension $n vektora $ egyszerűen $n \times 1 méretű mátrix $ . Mint a vektorok esetében, egy számmal $c mátrixot is használhatunk $ egy olyan új mátrix beszerzéséhez, amelyben minden egyes bejegyzést megszoroznak a $cval $ , és két mátrixot is hozzáadhatunk egy olyan új mátrix létrehozásához, amelynek bejegyzései a két mátrix megfelelő bejegyzéseinek összege. 

## <a name="matrix-multiplication-and-tensor-products"></a>Mátrix – szorzási és a tenser-termékek

Két mátrixot is használhatunk $M $ a dimenzió $m \times n $ és az $N $ dimenzió $n a p \times $ , hogy egy új mátrix $P $ a dimenzió $m a \times a $ következő módon:

\begin{align}
& \begin{bmatrix}
    M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\
    M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {MN}
végénbmatrix}
megkezdésebmatrix}
N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\ \ddots\\\\
N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {np}
\end{ bmatrix } = \begin{bmatrix}
P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\
P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {mp}
végénbmatrix}
\end{align}

a $P bejegyzései $ $P _ {ik } = \ sum_j M_ {ij} N_ {JK } $. A $P _ {11 $ bejegyzés például a } $M első sorának belső terméke a $ $N első oszlopával $ . Vegye figyelembe, hogy mivel a vektor egyszerűen egy mátrix speciális esete, ez a definíció a mátrix-vektoros szorzásra terjed ki. 

A rendszer az összes olyan mátrixot felveszi, amely a sorok és oszlopok száma, illetve a vektorok, amelyek csak $1 oszlopnak felelnek meg $ . Egy speciális négyzetes mátrix az [*Identity Matrix*](https://en.wikipedia.org/wiki/Identity_matrix), a $ \boldone $ , amely az összes átlós elemet $1 értékkel, $ a fennmaradó elemek pedig $0 $ :

$ $ \boldone = \begin{bmatrix}
1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\
0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\
~ ~ \ddots\\\\
0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $

Négyzetes mátrix $A esetén $ a mátrix $B $ az [*inverz*](https://en.wikipedia.org/wiki/Invertible_matrix) , ha $AB = ba = \boldone $ . A mátrix inverzének nem kell léteznie, de ha létezik, egyedi, és azt $A ^ {-1 $ értékűre jelöljük } . 

Bármely mátrix-$M esetében $ a $M adjoint vagy konjugátum-átültetése $ egy olyan mátrix $N, $ amely $N _ {ij } = M_ {Ji } ^ \* $. A $M adjoint $ általában $M ^ \dagger van kijelölve $ . Tegyük fel, hogy a mátrix $U $ [*egységes*](https://en.wikipedia.org/wiki/Unitary_matrix) , ha $uu ^ \dagger = U ^ \dagger U = \boldone $ vagy azzal egyenértékű, $U ^ {-1 } = U ^ \dagger $ .  Az egységes mátrixok legfontosabb tulajdonsága az, hogy megőrzik a vektorok normáit.  Ez azért történik, mert 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $  

A mátrix $M $ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , ha $M = M ^ \dagger $ .

Végül a két [*mátrix (vagy*](https://en.wikipedia.org/wiki/Tensor_product) Kronecker termék) $M $ $m \times n $ és $N mérete $ $p \Times q $ nagyobb mátrix $P = M \otimes n $ méretű $mp \times nq $ , és a következő módon szerezhető be $ : $M és $N $ .

\begin{align}
    M \otimes N &= \begin{bmatrix}
        M_ {11 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ \ddots\\\\
        M_ {M1 } ~ ~ \cdots ~ ~ M_ {MN}
    végénbmatrix}
    \otimes \begin{bmatrix}
        N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots\\\\
        N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq}
    \end{ bmatrix } \\ \\ &= \begin{bmatrix}
        M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1N } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\
        M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {MN } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{bmatrix}
    \end{ bmatrix } .
\end{align}

Ez jobban szemlélteti néhány példát:

$ $ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}
        \begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}
        \\\\[1,5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}
    végénbmatrix}
    = \begin{ bmatrix } a c a \\ \\ d a \\ \\ e \\ \\ b c \\ \\ b d \\ \\ \endbmatrix}
$$

és

$ $ \begin{bmatrix}
        a \ b \\ \\ c \ d \end{bmatrix}
    \otimes \begin{bmatrix}
        e \ f \\ \\ g \ h \end{bmatrix}
     = \begin{bmatrix}
    a \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    d \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    végénbmatrix}
    = \begin{bmatrix}
    AE \ AF \ be \ BF \\ \\ AG \ ah \ BG \ bh \\ \\ CE \ CF \ de \ DF \\ \\ CG \ CH \ DG \ DH \end{ bmatrix } .
$$

A legtöbbször hasznos, a TEN-termékekkel kapcsolatos jelölési konvenció az, hogy bármely vektoros $v $ vagy mátrix $M $ , $v ^ {\otimes n } $ vagy $M ^ {\otimes n } $ rövid Hand egy $n $ -szor ismétlődő tízes termékhez.  Például:

\begin{align}
& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 0 0 0 \\ \\ \\ \\ \\ \\ \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end { bmatrix } .
\end{align}
