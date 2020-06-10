---
title: Kvantumorákulumok
description: Megtudhatja, hogyan dolgozhat a használatával, és meghatározhatja a Quantum Oracles és a Black Box olyan műveleteit, amelyek bemenetként használhatók egy másik algoritmushoz.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
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
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630318"
---
# <a name="quantum-oracles"></a>Quantum jóslatok

Az Oracle $O $ egy olyan "fekete doboz" művelet, amelyet bemenetként használ egy másik algoritmus.
Ezeket a műveleteket gyakran egy klasszikus függvénnyel határozzák meg $f: \\ {0, 1 \\ } ^ n \to \\ {0, 1 \\ } ^ m, $ amely egy $n $ bites bináris bemenetet hoz létre, és egy $m $ bites bináris kimenetet állít elő.
Ehhez vegye fontolóra egy adott bináris bemenet $x = (x_ {0 } , X_ {1 } , \dots, X_ {n-1 } ) $ értéket.
Qubit-állapotokat is címkézheti $ \ket { \vec{x } } = \ket{X_ {0 } } \otimes \ket{X_ {1} \otimes \cdots \otimes } \ket{X_ {n-1 } } $.

Először megpróbáljuk meghatározni $O, $ hogy $O \ket {x } = \ket{f (x)} $, de ez néhány problémával is rendelkezik.
Először is, $f $ lehet, hogy a bemeneti és a kimeneti ($n \ne m $ ) mérete eltérő, így a $O alkalmazásával $ megváltoztathatja a regisztrációban lévő qubits számát.
Másodszor, még akkor is, ha $n = m $ , a függvény nem lehet invertálható: ha $f (x) = f (y) $ egyes $x \ne y esetében $ , akkor $O \ket {x } = O \ket {y } $, de $O ^ \dagger o \ket {x } \ne o ^ \dagger o \ket {y } $.
Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $O ^ \dagger $ , és az Oracles-nek meg kell adni egy adjoint.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján
Mindkét probléma megoldásához bemutatjuk a $m qubits második regisztrációját $ , hogy megtartsa a választ.
Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $x \in \\ {0, 1 \\ } ^ n $ és $y \in \\ {0, 1 \\ } ^ m $ ,

$ $ \begin{align}
    O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.
\end{align}
$$

Most $O = O ^ \dagger az $ építőiparban, így mindkét korábbi problémát megoldottuk.

> [!TIP]
> Ha szeretné látni, hogy $O = O ^ {\dagger } $, vegye figyelembe, hogy $O ^ 2 = \boldone $ óta $a \oplus b \oplus b = a $ minden $a, b \in \{ 0, 1 \} $.
> Ennek eredményeképpen $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.

Fontos, hogy ily módon Definiáljon egy Oracle-t úgy, hogy az egyes számítási alapú állapotok esetében a $ \ket{x } \ket{y } $ is meghatározza, hogy a $O hogyan $ viselkedik más állapotok esetén.
Ez közvetlenül attól a ténytől függ, hogy a $O $ , mint az összes kvantum-művelet, lineáris állapotban van.
Vegye figyelembe a Hadamard műveletet (például: $H \ket{0 } = \ket { +} $ és $H \ket{1 } = \ket { -} $).
Ha tudni szeretné, hogyan viselkednek $H $ a $ \ket { +} $-ra, akkor a $H $ lineáris,

$ $ \begin{align}
H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (h \ket {0 } + h \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .
\end{align}
$$

Ha az Oracle-$Ot definiáljuk $ , hasonlóképpen használhatjuk, hogy { } $n + m qubits bármely állam $ \ket \psi $ $

$ $ \begin{align}
\ket { \psi } & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y}
\end{align}
$$

ahol a $ \alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m \to \mathbb{C $, a } $ \ket { \psi $ állapot együtthatóit jelöli } . Így

$ $ \begin{align}
O \ket { \psi } & = O \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y \oplus f (x)}.
\end{align}
$$

## <a name="phase-oracles"></a>Jóslatok fázisa
Azt is megteheti, $ hogy a $f egy Oracle-$OBA kódoljuk $ egy olyan _fázis_ alkalmazásával, amely a $O bemenetén alapul $ .
Előfordulhat például, hogy meghatározhatjuk $O $ például $ $ \begin{align}
    O \ket{x } = (-1) ^ {f (x)} \ket{x } .
\end{align}
$ $, Ha az Oracle egy fázisban kezdetben egy számítási alapon, a $ \ket{x } $ értékben működik, akkor ez a fázis globális fázis, ezért nem észlelhető.
Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.
Tegyük fel például, hogy egy fázis orcale $O _f $ egy qubit függvény $f $ .
Ezután $ $ \begin{align}
    O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.
\end{align}
$$

Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.

Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.
A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.


További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.
