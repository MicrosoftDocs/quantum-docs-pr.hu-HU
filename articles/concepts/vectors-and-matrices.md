---
title: Vektorok és mátrixok | Microsoft Docs
description: Vektorok és mátrixok
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183743"
---
# <a name="vectors-and-matrices"></a>Vektorok és mátrixok

A kvantum-számítástechnika megismeréséhez elengedhetetlen a vektorok és mátrixok megismerése. Egy rövid bevezetést biztosítunk, és az érdekelt olvasóknak javasoljuk, hogy szabványos referenciát olvassanak a lineáris algebra, például a *furcsa, a G (1993) számára. A lineáris algebra bemutatása (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* vagy online referenciák, például [lineáris algebra](http://joshua.smcvt.edu/linearalgebra/).

Az oszlop vektora (vagy egyszerűen [*vektoros*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ dimenzió (vagy méret) $n $ $n $ komplex számokból álló gyűjtemény (v_1, v_2, \ldots, v_n) $, oszlopként rendezve:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

A Vector $v $ értékének normái a $ \sqrt{\sum\_i | v\_i | ^ 2} $ értéket határozzák meg. A vektorok egység normának számítanak (vagy más néven [*egység vektor*](https://en.wikipedia.org/wiki/Unit_vector)), ha a norma értéke $1 $. A [*vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ adjoint a $v ^ \dagger $-t jelöli, és úgy van definiálva, hogy a következő sor vektor legyen, ahol a $\*$ a komplex konjugátumot jelöli,

$ $ \begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix}v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

A két vektor együttes összeszorzásának leggyakoribb módja a [*belső termék*](https://en.wikipedia.org/wiki/Inner_product_space), más néven a dot termék.  A belső termék lehetővé teszi egy vektor kivetítését egy másikra, és felbecsülhetetlen értékű, hogy leírja, hogyan lehet egy vektort más egyszerűbb vektorok összegével kifejezni.  A belső termék a $u $ és a $v $ közötti, dejegyzett $ \left\langle u, v\right\rangle $ a következőképpen van definiálva:

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Ez a jelölés azt is lehetővé teszi, hogy a vektoros $v $ a $ \sqrt{\langle v, v\rangle} $ formátumban legyen megírva.

Egy $c $ számú vektort is használhatunk egy olyan új vektor létrehozásához, amelynek bejegyzései $c $ szorzattal vannak megszorozva. Két vektort is hozzáadhat $u $ és $v $ értékkel egy olyan új vektor létrehozásához, amelynek bejegyzései a $u $ és $v $ bejegyzéseinek összege. Ezek a műveletek az alábbi ábrán láthatók:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots @no__ t_10_ \\ v_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}.
$$

$M \times n $ méretű [*mátrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) a $MN $ komplex számok gyűjteménye, amelyek $m $ sorokban és $n $ oszlopban vannak rendezve, ahogy az alábbi ábrán látható:

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN}\\@no__ t_11_ \end{bmatrix}. $ $

Vegye figyelembe, hogy $n $ dimenzió vektora egyszerűen $n \times $1 méretű mátrix. Mint a vektorok esetében, egy $c $ számú mátrixot is használhatunk egy olyan új mátrix beszerzéséhez, amelyben minden egyes bejegyzést megszoroznak a $c $ értékkel, és két mátrixot is felvehetünk egy olyan új mátrix létrehozásához, amelynek bejegyzései a két mátrix megfelelő bejegyzéseinek összege. 

## <a name="matrix-multiplication-and-tensor-products"></a>Mátrix – szorzási és a tenser-termékek

Két mátrixot is használhatunk $M $ dimenzióval $m \times n $ és $N $ dimenzió $n \times p $, hogy egy új mátrix $P $ dimenzió $m \times p $ a következők szerint:

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \ BEGIN {bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1p}\\\\ N_{21} ~ ~ N_{22} ~ ~ \cdots ~ ~ N_ {2p}\\\\ \ddots\\\\ N_ {N1} ~ ~ N_ {N2} ~ ~ \cdots ~ ~ N_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1p}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2p}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {mp} \end{bmatrix} \end{align}

$P $ $P _ {ik} = \sum_j M_ {ij} N_ {JK} $ bejegyzései. Például a $P _{11}$ bejegyzés a $M $ első sorának belső terméke, $N $ első oszlopával. Vegye figyelembe, hogy mivel a vektor egyszerűen egy mátrix speciális esete, ez a definíció a mátrix-vektoros szorzásra terjed ki. 

A rendszer az összes olyan mátrixot felveszi, amely a sorok és oszlopok száma, illetve a vektorok, amelyek csak $1 $ oszlopnak felelnek meg. Egy speciális négyzetes mátrix az [*Identity Matrix*](https://en.wikipedia.org/wiki/Identity_matrix)($ \boldone $), amelynek minden átlós eleme $1 $, a fennmaradó elemek pedig $0 $:

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

A négyzetes mátrix $A $ esetén azt mondjuk [ *, hogy a*](https://en.wikipedia.org/wiki/Invertible_matrix) $AB = ba = \boldone $ mátrix $B $. A mátrix inverzének nem kell léteznie, de ha létezik, egyedi, és azt $A ^{-1}$ értékre jelöljük. 

Bármely mátrix $M $ esetén a adjoint vagy a konjugátum átültetése $M $ mátrix $N $, amely $N _ {ij} = M_ {Ji} ^\*$. A $M $ adjoint általában $M ^ \dagger $ jelöli. Tegyük fel, hogy egy Matrix $U $ egy [*egységes*](https://en.wikipedia.org/wiki/Unitary_matrix) , ha $uu ^ \Dagger = u ^ \dagger U = \boldone $ vagy azzal egyenértékű, $U ^{-1} = U ^ \dagger $.  Az egységes mátrixok legfontosabb tulajdonsága az, hogy megőrzik a vektorok normáit.  Ez azért történik, mert 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

$M $ mátrixot [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , ha $M = M ^ \dagger $.

Végül a két [*mátrix (vagy*](https://en.wikipedia.org/wiki/Tensor_product) Kronecker termék) $M $ méret $m \times n $ és $N $ méret $p \times q $ nagyobb mátrix $P = M\otimes n $ méretű $mp \times NQ $, és az $M $ és $N $ értéktől kezdve a következő módon szerezhető be:

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1N} \\\\ \ddots\\\\ M_ {M1} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1NÉ}\\\\ \ddots @no__ t_8_ \\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1NÉ}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {1N} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1NÉ}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {M1} \begin{bmatrix} N_{11} ~ ~ \ cdots ~ ~ N_ {1NÉ}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {MN} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1NÉ}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end {bmatrix} \end{bmatrix}.
\end{align}

Ez jobban szemlélteti néhány példát:

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} @no__ t_10_ \\[1,5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ a d \\\\ egy e \\\\ b c \\\\ b d \\\\ be\end {bmatrix} $ $

és

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\@no__ t_7_ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ be \ BF \\@no__ t_15_ AG \ ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ CH \ DG \ DH \end{bmatrix}.
$$

A legtöbbször hasznos, a TEN-termékekkel kapcsolatos, a $v $ vagy Matrix $M $, $v ^ {\otimes n} $ vagy a $M ^ {\otimes n} $ értékkel rendelkező, a $n USD-vel ismétlődő kétbájtos termékre vonatkozó végleges jelölési konvenció.  Példa:

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ End {bmatrix}.
\end{align}

