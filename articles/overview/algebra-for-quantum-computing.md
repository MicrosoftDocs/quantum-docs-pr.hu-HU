---
title: A kvantum-számítástechnika lineáris algebrája
description: Ismerje meg, hogy a lineáris algebra mely alapvető fogalmai szükségesek a kvantum-számítástechnika megértéséhez
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: d7a8dff8d491a9ce6451148d2d27121f1c190ed0
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759322"
---
# <a name="linear-algebra-for-quantum-computing"></a>A kvantum-számítástechnika lineáris algebrája

A lineáris algebra a kvantum-számítástechnika nyelve. A kvantumprogramok implementáláshoz és írásához nem kell ismerni, azonban széles körben használják a qubitek állapotának leírásához, a kvantumműveletekhez, valamint annak előrejelzéséhez, hogyan reagál egy kvantumszámítógép egy utasítássorozatra.

Ahogy a [kvantumfizika alapfogalmainak](xref:microsoft.quantum.overview.understanding) ismerete is segíthet megérteni a kvantum-számítástechnikát, úgy az alapvető lineáris algebra is segíthet megérteni a kvantumalgoritmusok működését. Legalább a **vektorok** és a **mátrixszorzás** fogalmával érdemes megismerkednie. Ha frissíteni szeretné tudását ezekkel az algebrai fogalmakkal kapcsolatban, az alábbi oktatóanyagok bemutatják az alapokat:

- [Jupyter-notebook-oktatóanyag a lineáris algebráról](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [Jupyter-notebook-oktatóanyag az összetett aritmetikáról](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [A kvantum-számítástechnika lineáris algebrája](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [A lineáris algebra alapjai](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Kvantumszámítások – Ismertető](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vektorok és mátrixok a kvantum-számítástechnikában

A [Kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding) témakörben láthatta, hogy a qubitek 1 vagy 0 állapotban, szuperpozícióban vagy mindkettőben lehetnek. A lineáris algebra használatával a qubit állapota vektorként van leírva, és az $\begin{bmatrix} a \\\\  b \end{bmatrix}$ egyoszlopos **mátrix** jelöli. Ezt más néven **kvantumállapot-vektornak** nevezik, és meg kell felelnie a következő követelménynek: $|a|^2 + |b|^2 = 1$.  

A mátrix elemei a qubit egyik vagy másik értékkel való egybeesésének valószínűségét jelölik, ahol $|a|^2$ annak a valószínűsége, hogy nullával esik egybe, a $|b|^2$ pedig annak a valószínűsége, hogy eggyel esik egybe. Az alábbi mátrixok mind érvényes kvantumállapot-vektorokat jelölnek:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

A [Kvantumszámítógépek és kvantumszimulátorok](xref:microsoft.quantum.overview.simulators) témakörben azt is láthatta, hogy kvantumműveletekkel módosítható a qubitek állapota.  A kvantumműveleteket mátrix is jelölheti. Ha egy kvantumműveletet egy qubitre alkalmaznak, az ezeket jelölő két mátrixot megszorozza a rendszer, és az eredmény a qubit művelet utáni új állapotának felel meg.  

Alább látható két gyakori kvantumművelet, mátrixszorzással megjelenítve.


Az [`X` műveletet](xref:microsoft.quantum.intrinsic.x) az $X$ Pauli-mátrix jelöli,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
és a segítségével egy qubit állapota átállítható 0-ról 1-re (vagy fordítva), például

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

A ['H' műveletet](xref:microsoft.quantum.intrinsic.h) a $H$ Hadamard-transzformáció jelöli,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 és a qubitet egy olyan szuperpozíciós állapotba helyezi, amelyben egyenlő eséllyel eshet egybe bármelyik értékkel, ahogy itt is látható:

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

A kvantumműveletet jelölő mátrix egy követelménnyel rendelkezik – **egységes** mátrixnak kell lennie. A mátrix akkor egységes, ha a mátrix **inverze** megegyezik a mátrix **konjugált transzponáltjával**.

## <a name="representing-two-qubit-states"></a>Kétqubites állapot jelölése

A fenti példákban az egyik qubit állapotát a $\begin{bmatrix} a \\\\  b \end{bmatrix}$ egyoszlopos mátrix írta le, a rajta végzett műveletet pedig a két mátrix összeszorzása. A kvantumszámítógépek azonban egynél több qubitet használnak, tehát hogyan írható le két qubit kombinált állapota? 

Ne feledje, hogy minden qubit egy vektortér, ezért nem lehet őket egyszerűen megszorozni. Ehelyett **tenzorszorzatot** kell használni, amely az egyes vektorterekből új vektorteret létrehozó, kapcsolódó művelet. Ezt az $\otimes$ szimbólum jelöli. Például az $\begin{bmatrix} a \\\\  b \end{bmatrix}$ és a $\begin{bmatrix} c \\\\  d \end{bmatrix}$ qubitállapot tenzorszorzata a következő módon számítható ki:

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Az eredmény egy négydimenziós mátrix, amelyben minden elem egy valószínűséget jelöl. Az $ac$ például annak a valószínűsége, hogy mindkét qubit 0-val esik egybe, az $ad$ annak a valószínűsége, hogy az egyik 0-val, a másik 1-gyel, és így tovább. 

Az $\begin{bmatrix} a \\\\  b \end{bmatrix}$ egyqubites állapotnak meg kell felelnie a következő követelménynek: $|a|^2 + |b|^2 = 1$. Erre a kvantumállapot jelölése érdekében van szükség. Az $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ kétqubites állapotnak meg kell felelnie a következő követelménynek: $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Összefoglalás

A lineáris algebra a kvantum-számítástechnika és a kvantumfizika leírásának szabványos nyelve. Annak ellenére, hogy a Microsoft Quantum Development Kit [kódtárai](xref:microsoft.quantum.libraries) anélkül is segítséget nyújtanak a fejlett kvantumalgoritmusok futtatásához, hogy meg kellene ismernie a mögöttes matematikai fogalmakat, az alapok ismerete segít a gyors kezdésben, és egy stabil alapot biztosít, amelyre építhet.

## <a name="next-steps"></a>További lépések

[A QDK telepítése](xref:microsoft.quantum.install)
