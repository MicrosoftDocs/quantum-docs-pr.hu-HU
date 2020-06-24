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
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 747c08df110f1f10efe552628d15e3500509b690
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269558"
---
# <a name="quantum-oracles"></a><span data-ttu-id="a1e81-103">Quantum jóslatok</span><span class="sxs-lookup"><span data-stu-id="a1e81-103">Quantum Oracles</span></span>

<span data-ttu-id="a1e81-104">Az Oracle $O $ egy olyan "fekete doboz" művelet, amelyet bemenetként használ egy másik algoritmus.</span><span class="sxs-lookup"><span data-stu-id="a1e81-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="a1e81-105">Ezeket a műveleteket gyakran egy klasszikus függvénnyel határozzák meg $f: \\ {0, 1 \\ } ^ n \to \\ {0, 1 \\ } ^ m, $ amely egy $n $ bites bináris bemenetet hoz létre, és egy $m $ bites bináris kimenetet állít elő.</span><span class="sxs-lookup"><span data-stu-id="a1e81-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="a1e81-106">Ehhez vegye fontolóra egy adott bináris bemenet $x = (x_ {0 } , X_ {1 } , \dots, X_ {n-1 } ) $ értéket.</span><span class="sxs-lookup"><span data-stu-id="a1e81-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="a1e81-107">Qubit-állapotokat is címkézheti $ \ket { \vec{x } } = \ket{X_ {0 } } \otimes \ket{X_ {1} \otimes \cdots \otimes } \ket{X_ {n-1 } } $.</span><span class="sxs-lookup"><span data-stu-id="a1e81-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="a1e81-108">Először megpróbáljuk meghatározni $O, $ hogy $O \ket {x } = \ket{f (x)} $, de ez néhány problémával is rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="a1e81-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="a1e81-109">Először is, $f $ lehet, hogy a bemeneti és a kimeneti ($n \ne m $ ) mérete eltérő, így a $O alkalmazásával $ megváltoztathatja a regisztrációban lévő qubits számát.</span><span class="sxs-lookup"><span data-stu-id="a1e81-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="a1e81-110">Másodszor, még akkor is, ha $n = m $ , a függvény nem lehet invertálható: ha $f (x) = f (y) $ egyes $x \ne y esetében $ , akkor $O \ket {x } = O \ket {y } $, de $O ^ \dagger o \ket {x } \ne o ^ \dagger o \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="a1e81-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="a1e81-111">Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $O ^ \dagger $ , és az Oracles-nek meg kell adni egy adjoint.</span><span class="sxs-lookup"><span data-stu-id="a1e81-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="a1e81-112">Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján</span><span class="sxs-lookup"><span data-stu-id="a1e81-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="a1e81-113">Mindkét probléma megoldásához bemutatjuk a $m qubits második regisztrációját $ , hogy megtartsa a választ.</span><span class="sxs-lookup"><span data-stu-id="a1e81-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="a1e81-114">Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $x \in \\ {0, 1 \\ } ^ n $ és $y \in \\ {0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="a1e81-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="a1e81-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-115">$$ \begin{align}</span></span>
    <span data-ttu-id="a1e81-116">O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="a1e81-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="a1e81-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-117">\end{align}</span></span>
$$

<span data-ttu-id="a1e81-118">Most $O = O ^ \dagger az $ építőiparban, így mindkét korábbi problémát megoldottuk.</span><span class="sxs-lookup"><span data-stu-id="a1e81-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="a1e81-119">Ha szeretné látni, hogy $O = O ^ {\dagger } $, vegye figyelembe, hogy $O ^ 2 = \boldone $ óta $a \oplus b \oplus b = a $ minden $a, b \in \{ 0, 1 \} $.</span><span class="sxs-lookup"><span data-stu-id="a1e81-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="a1e81-120">Ennek eredményeképpen $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.</span><span class="sxs-lookup"><span data-stu-id="a1e81-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="a1e81-121">Fontos, hogy ily módon Definiáljon egy Oracle-t úgy, hogy az egyes számítási alapú állapotok esetében a $ \ket{x } \ket{y } $ is meghatározza, hogy a $O hogyan $ viselkedik más állapotok esetén.</span><span class="sxs-lookup"><span data-stu-id="a1e81-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="a1e81-122">Ez közvetlenül attól a ténytől függ, hogy a $O $ , mint az összes kvantum-művelet, lineáris állapotban van.</span><span class="sxs-lookup"><span data-stu-id="a1e81-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="a1e81-123">Vegye figyelembe a Hadamard műveletet (például: $H \ket{0 } = \ket { +} $ és $H \ket{1 } = \ket { -} $).</span><span class="sxs-lookup"><span data-stu-id="a1e81-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="a1e81-124">Ha tudni szeretné, hogyan viselkednek $H $ a $ \ket { +} $-ra, akkor a $H $ lineáris,</span><span class="sxs-lookup"><span data-stu-id="a1e81-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="a1e81-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-125">$$ \begin{align}</span></span>
<span data-ttu-id="a1e81-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (h \ket {0 } + h \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="a1e81-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="a1e81-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-127">\end{align}</span></span>
$$

<span data-ttu-id="a1e81-128">Ha az Oracle-$Ot definiáljuk $ , hasonlóképpen használhatjuk, hogy { } $n + m qubits bármely állam $ \ket \psi $ $</span><span class="sxs-lookup"><span data-stu-id="a1e81-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="a1e81-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-129">$$ \begin{align}</span></span>
<span data-ttu-id="a1e81-130">\ket { \psi } & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="a1e81-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="a1e81-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-131">\end{align}</span></span>
$$

<span data-ttu-id="a1e81-132">ahol a $ \alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m \to \mathbb{C $, a } $ \ket { \psi $ állapot együtthatóit jelöli } .</span><span class="sxs-lookup"><span data-stu-id="a1e81-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="a1e81-133">Így</span><span class="sxs-lookup"><span data-stu-id="a1e81-133">Thus,</span></span>

<span data-ttu-id="a1e81-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-134">$$ \begin{align}</span></span>
<span data-ttu-id="a1e81-135">O \ket { \psi } & = O \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="a1e81-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="a1e81-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="a1e81-137">Jóslatok fázisa</span><span class="sxs-lookup"><span data-stu-id="a1e81-137">Phase oracles</span></span>
<span data-ttu-id="a1e81-138">Azt is megteheti, $ hogy a $f egy Oracle-$OBA kódoljuk $ egy olyan _fázis_ alkalmazásával, amely a $O bemenetén alapul $ .</span><span class="sxs-lookup"><span data-stu-id="a1e81-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="a1e81-139">Előfordulhat például, hogy meghatározhatjuk $O $ például $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="a1e81-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="a1e81-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="a1e81-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-141">\end{align}</span></span>
<span data-ttu-id="a1e81-142">$ $, Ha az Oracle egy fázisban kezdetben egy számítási alapon, a $ \ket{x } $ értékben működik, akkor ez a fázis globális fázis, ezért nem észlelhető.</span><span class="sxs-lookup"><span data-stu-id="a1e81-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="a1e81-143">Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="a1e81-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="a1e81-144">Tegyük fel például, hogy egy fázis orcale $O _f $ egy qubit függvény $f $ .</span><span class="sxs-lookup"><span data-stu-id="a1e81-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="a1e81-145">Ezután $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="a1e81-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.</span><span class="sxs-lookup"><span data-stu-id="a1e81-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="a1e81-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e81-147">\end{align}</span></span>
$$

<span data-ttu-id="a1e81-148">Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.</span><span class="sxs-lookup"><span data-stu-id="a1e81-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="a1e81-149">Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="a1e81-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="a1e81-150">A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="a1e81-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="a1e81-151">További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.</span><span class="sxs-lookup"><span data-stu-id="a1e81-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
