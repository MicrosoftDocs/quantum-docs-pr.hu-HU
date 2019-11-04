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
# <a name="quantum-oracles"></a><span data-ttu-id="7a34b-103">Quantum jóslatok</span><span class="sxs-lookup"><span data-stu-id="7a34b-103">Quantum Oracles</span></span>

<span data-ttu-id="7a34b-104">Az Oracle $O $ egy olyan "fekete Box" művelet, amelyet bemenetként használ egy másik algoritmushoz.</span><span class="sxs-lookup"><span data-stu-id="7a34b-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="7a34b-105">Ezeket a műveleteket gyakran egy klasszikus függvénnyel határozzák meg $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, amely $n $ bites bináris bemenetet vesz igénybe, és $m $ bites bináris kimenetet hoz létre.</span><span class="sxs-lookup"><span data-stu-id="7a34b-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="7a34b-106">Ehhez vegye fontolóra egy adott bináris bemenet $x = (X_{0}, X_{1}, \dots, X_ {n-1}) $ értéket.</span><span class="sxs-lookup"><span data-stu-id="7a34b-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="7a34b-107">Qubit-állapotokat is címkézheti $ \ket{\vec{x}} = \ket{X_{0}} \otimes \ket{X_{1}} \otimes \cdots \otimes \ket{X_{n-1}} $.</span><span class="sxs-lookup"><span data-stu-id="7a34b-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="7a34b-108">Először megpróbáljuk meghatározni $O $-t, hogy $O \ket{x} = \ket{f (x)} $, de ez néhány problémával is rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="7a34b-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="7a34b-109">Először is, $f $ lehet, hogy a bemeneti és a kimeneti érték ($n \ne m $) eltérő méretű, például a $O $ alkalmazása a qubits számát módosítja a regisztrációban.</span><span class="sxs-lookup"><span data-stu-id="7a34b-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="7a34b-110">Másodszor, még akkor is, ha $n = m $, a függvény nem lehet invertálható: Ha $f (x) = f (y) $ for some $x \ne y $, akkor $O \ket{x} = O\ket {y} $, de $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.</span><span class="sxs-lookup"><span data-stu-id="7a34b-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="7a34b-111">Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $O ^ \dagger $, és az Oracles-nek meg kell határoznia egy adjoint.</span><span class="sxs-lookup"><span data-stu-id="7a34b-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="7a34b-112">Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján</span><span class="sxs-lookup"><span data-stu-id="7a34b-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="7a34b-113">Mindkét probléma megoldásához bemutatjuk a $m $ qubits második regisztrációját, hogy megtartsa a választ.</span><span class="sxs-lookup"><span data-stu-id="7a34b-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="7a34b-114">Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $x \in \\{0, 1\\} ^ n $ és $y \in \\{0, 1\\} ^ m $,</span><span class="sxs-lookup"><span data-stu-id="7a34b-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="7a34b-115">$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="7a34b-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="7a34b-116">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a34b-116">\end{align} $$</span></span>

<span data-ttu-id="7a34b-117">Most $O = O ^ \dagger $ by Construction, így mindkét korábbi problémát megoldottuk.</span><span class="sxs-lookup"><span data-stu-id="7a34b-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="7a34b-118">Ha szeretné látni, hogy $O = O ^ {\dagger} $, vegye figyelembe, hogy $O ^ 2 = \boldone $, mivel $a \oplus b \oplus b = a $ minden $a, b \in \{0, 1\}$.</span><span class="sxs-lookup"><span data-stu-id="7a34b-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="7a34b-119">Ennek eredményeképpen $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.</span><span class="sxs-lookup"><span data-stu-id="7a34b-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="7a34b-120">Fontos, hogy az Oracle ily módon történő meghatározása az egyes számítási alapú állapotok esetében a $ \ket{x}\ket{y} $ azt is meghatározza, hogy a $O $ hogyan viselkedik bármely más államban.</span><span class="sxs-lookup"><span data-stu-id="7a34b-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="7a34b-121">Ez közvetlenül attól a ténytől függ, hogy $O $, az összes kvantum-művelethez hasonlóan lineáris állapotban van.</span><span class="sxs-lookup"><span data-stu-id="7a34b-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="7a34b-122">Vegye figyelembe a Hadamard műveletet, amely például a $H \ket{0} = \ket{+} $ és $H \ket{1} = \ket{-}$ értékkel van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="7a34b-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="7a34b-123">Ha tudni szeretné, hogy $H $ hogyan viselkedik a $ \ket{+} $-ben, akkor a $H $ lineáris,</span><span class="sxs-lookup"><span data-stu-id="7a34b-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="7a34b-124">$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ ket {+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="7a34b-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="7a34b-125">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a34b-125">\end{align} $$</span></span>

<span data-ttu-id="7a34b-126">Oracle $O $ megadása esetén hasonlóképpen használhatjuk azt is, hogy a (z) $n + m $ qubits bármely állapota $ \ket{\psi} $-ként írható</span><span class="sxs-lookup"><span data-stu-id="7a34b-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="7a34b-127">$ $ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a34b-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="7a34b-128">ahol a $ \alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ a $ \ket{\psi} $ állapot együtthatóit jelöli.</span><span class="sxs-lookup"><span data-stu-id="7a34b-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="7a34b-129">Így</span><span class="sxs-lookup"><span data-stu-id="7a34b-129">Thus,</span></span>

<span data-ttu-id="7a34b-130">$ $ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0 , 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\} ^ n, y \in \\{0 , 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="7a34b-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="7a34b-131">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a34b-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="7a34b-132">Jóslatok fázisa</span><span class="sxs-lookup"><span data-stu-id="7a34b-132">Phase oracles</span></span>
<span data-ttu-id="7a34b-133">Azt is megteheti, hogy a $f $-t egy Oracle $O $-be kódolva egy _fázist_ alkalmazva a $O $ értékre való bevitel alapján.</span><span class="sxs-lookup"><span data-stu-id="7a34b-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="7a34b-134">Például meghatározhatjuk $O $-t úgy, hogy $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.</span><span class="sxs-lookup"><span data-stu-id="7a34b-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="7a34b-135">\end{align} $ $, ha az Oracle egy fázisban kezdetben egy számítási alapon, a $ \ket{x} $ értékben működik, akkor ez a fázis globális fázis, ezért nem észlelhető.</span><span class="sxs-lookup"><span data-stu-id="7a34b-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="7a34b-136">Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="7a34b-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="7a34b-137">Vegyünk például egy fázis orcale $O _f $-t egy qubit függvényhez $f $.</span><span class="sxs-lookup"><span data-stu-id="7a34b-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="7a34b-138">Ezután $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.</span><span class="sxs-lookup"><span data-stu-id="7a34b-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="7a34b-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a34b-139">\end{align} $$</span></span>

<span data-ttu-id="7a34b-140">Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.</span><span class="sxs-lookup"><span data-stu-id="7a34b-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="7a34b-141">Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="7a34b-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="7a34b-142">A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="7a34b-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="7a34b-143">További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.</span><span class="sxs-lookup"><span data-stu-id="7a34b-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
