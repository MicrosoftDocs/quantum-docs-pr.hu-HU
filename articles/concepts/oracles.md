---
title: Quantum Oracles | Microsoft Docs
description: Quantum jóslatok
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184712"
---
# <a name="quantum-oracles"></a>Quantum jóslatok

Az Oracle $O $ egy olyan "fekete Box" művelet, amelyet bemenetként használ egy másik algoritmushoz.
Ezeket a műveleteket gyakran egy klasszikus függvénnyel határozzák meg $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, amely $n $ bites bináris bemenetet vesz igénybe, és $m $ bites bináris kimenetet hoz létre.
Ehhez vegye fontolóra egy adott bináris bemenet $x = (X_{0}, X_{1}, \dots, X_ {n-1}) $ értéket.
Qubit-állapotokat is címkézheti $ \ket{\vec{x}} = \ket{X_{0}} \otimes \ket{X_{1}} \otimes \cdots \otimes \ket{X_{n-1}} $.

Először megpróbáljuk meghatározni $O $-t, hogy $O \ket{x} = \ket{f (x)} $, de ez néhány problémával is rendelkezik.
Először is, $f $ lehet, hogy a bemeneti és a kimeneti érték ($n \ne m $) eltérő méretű, például a $O $ alkalmazása a qubits számát módosítja a regisztrációban.
Másodszor, még akkor is, ha $n = m $, a függvény nem lehet invertálható: Ha $f (x) = f (y) $ for some $x \ne y $, akkor $O \ket{x} = O\ket {y} $, de $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.
Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $O ^ \dagger $, és az Oracles-nek meg kell határoznia egy adjoint.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján
Mindkét probléma megoldásához bemutatjuk a $m $ qubits második regisztrációját, hogy megtartsa a választ.
Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $x \in \\{0, 1\\} ^ n $ és $y \in \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{align} $ $

Most $O = O ^ \dagger $ by Construction, így mindkét korábbi problémát megoldottuk.

> [!TIP]
> Ha szeretné látni, hogy $O = O ^ {\dagger} $, vegye figyelembe, hogy $O ^ 2 = \boldone $, mivel $a \oplus b \oplus b = a $ minden $a, b \in \{0, 1\}$.
> Ennek eredményeképpen $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.

Fontos, hogy az Oracle ily módon történő meghatározása az egyes számítási alapú állapotok esetében a $ \ket{x}\ket{y} $ azt is meghatározza, hogy a $O $ hogyan viselkedik bármely más államban.
Ez közvetlenül attól a ténytől függ, hogy $O $, az összes kvantum-művelethez hasonlóan lineáris állapotban van.
Vegye figyelembe a Hadamard műveletet, amely például a $H \ket{0} = \ket{+} $ és $H \ket{1} = \ket{-}$ értékkel van meghatározva.
Ha tudni szeretné, hogy $H $ hogyan viselkedik a $ \ket{+} $-ben, akkor a $H $ lineáris,

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ ket {+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.
\end{align} $ $

Oracle $O $ megadása esetén hasonlóképpen használhatjuk azt is, hogy a (z) $n + m $ qubits bármely állapota $ \ket{\psi} $-ként írható

$ $ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \end{align} $ $

ahol a $ \alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ a $ \ket{\psi} $ állapot együtthatóit jelöli. Így

$ $ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0 , 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\} ^ n, y \in \\{0 , 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y \oplus f (x)}.
\end{align} $ $

## <a name="phase-oracles"></a>Jóslatok fázisa
Azt is megteheti, hogy a $f $-t egy Oracle $O $-be kódolva egy _fázist_ alkalmazva a $O $ értékre való bevitel alapján.
Például meghatározhatjuk $O $-t úgy, hogy $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.
\end{align} $ $, ha az Oracle egy fázisban kezdetben egy számítási alapon, a $ \ket{x} $ értékben működik, akkor ez a fázis globális fázis, ezért nem észlelhető.
Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.
Vegyünk például egy fázis orcale $O _f $-t egy qubit függvényhez $f $.
Ezután $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{align} $ $

Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.

Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.
A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.


További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.
