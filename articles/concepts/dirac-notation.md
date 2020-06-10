---
title: Dirac-jelölés
description: Ismerje meg, hogyan használhatja a Dirac jelölést a kvantum állapotok, valamint a kvantum-műveletek szimulálása érdekében.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
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
ms.openlocfilehash: 958910452109fc722999acddd70894c458e38357
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630385"
---
# <a name="dirac-notation"></a><span data-ttu-id="380ae-103">Dirac jelölése</span><span class="sxs-lookup"><span data-stu-id="380ae-103">Dirac Notation</span></span>

<span data-ttu-id="380ae-104">Míg az oszlop vektoros jelölése mindenütt szerepel a lineáris algebraban, sokszor nehézkes a Quantum computingban, különösen ha több qubits van szó.</span><span class="sxs-lookup"><span data-stu-id="380ae-104">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="380ae-105">Ha például a $ \psi $ -t egy vektorra definiáljuk, nem egyértelmű, hogy a $ \psi $ egy sor vagy egy oszlop vektora.</span><span class="sxs-lookup"><span data-stu-id="380ae-105">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="380ae-106">Így ha a $ \phi $ és a $ \psi $ a vektorok, akkor ugyanilyen módon nem egyértelmű, ha a $ \phi \psi $ még definiálva van, mert a $ \phi $ és a $ \psi alakzatai $ nem lehetnek egyértelműek a környezetben.</span><span class="sxs-lookup"><span data-stu-id="380ae-106">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="380ae-107">A vektorok alakzataival kapcsolatos kétértelműség mellett még a korábban bevezetett lineáris algebrai-jelölést használó egyszerű vektorok is nagyon nehézkesek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="380ae-107">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="380ae-108">Ha például egy olyan $n $ -qubit állapotot szeretnénk leírni, amelyben minden qubit $0 értéket vesz igénybe, $ akkor formálisan kifejezjük az állapotot</span><span class="sxs-lookup"><span data-stu-id="380ae-108">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="380ae-109">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="380ae-109">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="380ae-110">Természetesen a TEN-termék kiértékelése nem praktikus, mert a vektor egy exponenciálisan nagy térben található, ezért ez a jelölés valójában az előző jelöléssel megadható állapot legjobb leírása.</span><span class="sxs-lookup"><span data-stu-id="380ae-110">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="380ae-111">A [*Dirac-jelöléssel*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) megoldhatja ezeket a problémákat úgy, hogy egy új nyelvet mutat be a kvantummechanika pontos igényeinek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="380ae-111">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="380ae-112">Ezért azt javasoljuk, hogy az olvasó ne tekintse meg az ebben a szakaszban szereplő példákat a kvantum-állapotok leírására szolgáló merev vényként, hanem az olvasót, hogy megtekintse ezeket olyan javaslatokként, amelyek segítségével tömören kifejezni a kvantum-ötleteket.</span><span class="sxs-lookup"><span data-stu-id="380ae-112">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="380ae-113">A Dirac két típusa létezik: a *melltartó* vektora és a *ket* vektor, így nevezték el, mert ha együtt *braket* vagy belső terméket alkotnak.</span><span class="sxs-lookup"><span data-stu-id="380ae-113">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="380ae-114">Ha a $ \psi $ egy oszlopos vektor, akkor a Dirac-jelöléssel a $ \ket \psi $ értékkel írhatjuk { } , ahol a $ \ket { \cdot } $ azt jelzi, hogy az egység oszlop vektoros, azaz a *két* pont vektora.</span><span class="sxs-lookup"><span data-stu-id="380ae-114">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="380ae-115">Hasonlóképpen, a "\psi ^ \dagger" oszlop a $ $ \bra \psi $ értékkel van kifejezve { } .</span><span class="sxs-lookup"><span data-stu-id="380ae-115">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="380ae-116">Más szóval a $ \psi ^ \dagger $ beszerzéséhez a "Wise összetett ragozás" kifejezést kell alkalmazni a $ \psi átültetésének elemeire $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-116">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="380ae-117">A melltartó-ket jelölés közvetlenül azt jelenti, hogy a $ \braket { \psi | \psi } $ a Vector $ \psi belső terméke $ , amely magában foglalja a $1 definícióját $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-117">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="380ae-118">Általánosságban elmondható, hogy ha a $ \psi $ és a $ \phi $ a Quantum State vectors a belső termékük a $ \braket { \phi | \psi } $, ami azt jelenti, hogy a $ \ket \psi $ érték mérésének valószínűsége $ { } \ket { \phi } $ a $ | \braket { \phi | \psi } | ^ 2 $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-118">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="380ae-119">A következő egyezmény a nulla és egy (az qubit számítási alap állapotú) értékek kódolására szolgáló kvantum-állapotok leírására szolgál:</span><span class="sxs-lookup"><span data-stu-id="380ae-119">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

<span data-ttu-id="380ae-120">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .</span><span class="sxs-lookup"><span data-stu-id="380ae-120">$$ \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad \begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="380ae-121">Példa: a Hadamard műveletet jelképező Dirac-jelöléssel</span><span class="sxs-lookup"><span data-stu-id="380ae-121">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="380ae-122">A következő jelölést gyakran használják olyan állapotok leírására, amelyek a Hadamard-kapunak a $ \ket{0 } $ és a $ \ket{1 $ értékre való alkalmazásából erednek } (amelyek a Bloch szférában a $ + x $ és a $-x $ utasításoknak felelnek meg):</span><span class="sxs-lookup"><span data-stu-id="380ae-122">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

<span data-ttu-id="380ae-123">$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}.</span><span class="sxs-lookup"><span data-stu-id="380ae-123">$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="380ae-124">Ezek az állapotok a Dirac-jelöléssel is kiterjeszthetők a $ \ket{0 } $ és a $ \ket{1 $ összegű összegek használatával } :</span><span class="sxs-lookup"><span data-stu-id="380ae-124">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

<span data-ttu-id="380ae-125">$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).</span><span class="sxs-lookup"><span data-stu-id="380ae-125">$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="380ae-126">Számítási alapú vektorok</span><span class="sxs-lookup"><span data-stu-id="380ae-126">Computational basis vectors</span></span>
<span data-ttu-id="380ae-127">Ez azt mutatja be, hogy az ilyen állapotok milyen gyakran nevezik *számítási alapnak*: minden egyes kvantum-állapot mindig kifejezhető számítási alapú vektorok összegével, és az ilyen összegeket egyszerűen Dirac-jelöléssel lehet kifejezni.</span><span class="sxs-lookup"><span data-stu-id="380ae-127">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="380ae-128">A Converse az is igaz, hogy a $ \ket { +} $ és a $ \ket-} $ állapotú Államok a { kvantum-állapotok alapjául is szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="380ae-128">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="380ae-129">Ezt a tényt láthatja, hogy</span><span class="sxs-lookup"><span data-stu-id="380ae-129">You can see this from the fact that</span></span>

<span data-ttu-id="380ae-130">$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).</span><span class="sxs-lookup"><span data-stu-id="380ae-130">$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="380ae-131">Példaként tekintse meg a braket $ \braket{0 | 1 $ Dirac, } amely az $0 és $1 közötti belső termék $ $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-131">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="380ae-132">A következőképpen írható</span><span class="sxs-lookup"><span data-stu-id="380ae-132">It can be written as</span></span> 

<span data-ttu-id="380ae-133">$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end { bmatrix } = 0. $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-133">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="380ae-134">Ez azt jelzi, hogy a $ \ket{0 } $ és a $ \ket{1 } $ a merőleges vektorok, ami azt jelenti, hogy a $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-134">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="380ae-135">Szintén definíció szerint $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , ami azt jelenti, hogy a két számítási alap vektor is hívható *orthonormal*.</span><span class="sxs-lookup"><span data-stu-id="380ae-135">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="380ae-136">Ezek a orthonormal tulajdonságok az alábbi példában is hasznosak.</span><span class="sxs-lookup"><span data-stu-id="380ae-136">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="380ae-137">Ha a $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 $ értékkel rendelkezik } , akkor a $ \braket{1 | 0 } = 0 $ a $1 mérési valószínűsége $</span><span class="sxs-lookup"><span data-stu-id="380ae-137">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="380ae-138">$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-138">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="380ae-139">Tenser termék jelölése</span><span class="sxs-lookup"><span data-stu-id="380ae-139">Tensor product notation</span></span>
<span data-ttu-id="380ae-140">A Dirac-jelölés magában foglalja az implicit tenser termék struktúráját is.</span><span class="sxs-lookup"><span data-stu-id="380ae-140">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="380ae-141">Ez azért fontos, mert a kvantum-számítástechnika esetében a két, nem korrelált kvantum-regiszter által ismertetett állapot-vektor a két állapotú vektor kétszintű terméke.</span><span class="sxs-lookup"><span data-stu-id="380ae-141">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="380ae-142">A tensing termék szerkezetének tömör leírása vagy ennek hiánya létfontosságú, ha meg szeretné magyarázni a kvantum-számításokat.</span><span class="sxs-lookup"><span data-stu-id="380ae-142">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="380ae-143">A tenser-termék szerkezete azt feltételezi, hogy a $ \psi \otimes \phi $ bármilyen két Quantum State-vektorhoz ($ \phi $ és $ \psi $ as $ \ket { \psi } \ket \phi $) írhatjuk { } , esetenként kifejezetten $ \ket \psi \otimes \ket \phi $-ként írva, { } { } $ a vektorok között azonban a $ \otimes írása nem szükséges.</span><span class="sxs-lookup"><span data-stu-id="380ae-143">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="380ae-144">Például a nulla állapotba inicializált két qubits állapotot a következő adja meg:</span><span class="sxs-lookup"><span data-stu-id="380ae-144">For example, the state with two qubits initialized to the zero state is given by</span></span>

<span data-ttu-id="380ae-145">$ $ \begin{ bmatrix } 1 0 0 0 \\ \\ \\ \\ \\ \\ \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="380ae-145">$$ \begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="380ae-146">Hasonlóképpen, a $ \ket{p } $ for integer $p $ egy olyan kvantum-állapotot jelöl, amely bináris formátumban kódolja az egész számot $p $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-146">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="380ae-147">Ha például az $5-es számot $ egy aláíratlan bináris kódolással szeretnénk kifejezni, akkor a következőhöz hasonló módon fejezzük ki:</span><span class="sxs-lookup"><span data-stu-id="380ae-147">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

<span data-ttu-id="380ae-148">$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .</span><span class="sxs-lookup"><span data-stu-id="380ae-148">$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="380ae-149">Ezen a jelölésen belül a $ \ket{0 } $ nem igényel egyetlen qubit állapotot, hanem egy *qubit-regisztrációt* , amely a $0-es bináris kódolást tárolja $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-149">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="380ae-150">A két jelölés közötti különbségek általában a kontextusból törlődnek.</span><span class="sxs-lookup"><span data-stu-id="380ae-150">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="380ae-151">Ez az egyezmény hasznos lehet az első példa leegyszerűsítéséhez, amely a következő módokon írható:</span><span class="sxs-lookup"><span data-stu-id="380ae-151">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

<span data-ttu-id="380ae-152">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="380ae-152">$$ \begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="380ae-153">Példa: a Dirac-jelöléssel való Felfekvés leírása</span><span class="sxs-lookup"><span data-stu-id="380ae-153">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="380ae-154">Egy másik példa arra, hogy miként használható a Dirac-jelölés a kvantum-állapot leírására, az alábbi egyenértékű módokat kell figyelembe vennie egy olyan kvantum-állapot megírásához, amely egyenlő arányban van az összes lehetséges hosszúságú $n$</span><span class="sxs-lookup"><span data-stu-id="380ae-154">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

<span data-ttu-id="380ae-155">$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .</span><span class="sxs-lookup"><span data-stu-id="380ae-155">$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="380ae-156">Itt is csoda, hogy az összeg az $0-tól a $ $2 ^ {n-1 értéktől a } $ $n $ bitek esetében.</span><span class="sxs-lookup"><span data-stu-id="380ae-156">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="380ae-157">Először is vegye figyelembe, hogy 2 ^ {n } $ különböző konfiguráció van, amelyeket $n $ bitek is igénybe vehetnek.</span><span class="sxs-lookup"><span data-stu-id="380ae-157">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="380ae-158">Ezt úgy tekintheti meg, hogy az egyik bit $2 értéket vehet igénybe, $ de két bit $4 $ értéket és így tovább.</span><span class="sxs-lookup"><span data-stu-id="380ae-158">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="380ae-159">Általánosságban véve ez azt jelenti, hogy 2 ^ n $ különböző lehetséges bit-sztring van, de a legnagyobb érték, amelyet bármelyikük $1 \cdots 1 = 2 ^ n-1 $ , így ez az összeg felső korlátja.</span><span class="sxs-lookup"><span data-stu-id="380ae-159">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="380ae-160">Ebben a példában nem használjuk a $ \ket { +} ^ {\otimes n } = \ket +} $ értéket a $ { \ket{0 } ^ {\otimes n } = \ket{0 $ értékre, } mivel ez a jelölési konvenció általában a számítási alapállapothoz van fenntartva, és minden qubit nulla értékre van inicializálva.</span><span class="sxs-lookup"><span data-stu-id="380ae-160">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="380ae-161">Habár ebben az esetben ez az egyezmény ésszerű lenne, nem alkalmazható a Quantum Computing-szakirodalom keretében.</span><span class="sxs-lookup"><span data-stu-id="380ae-161">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="380ae-162">Lineárisság kifejező Dirac jelöléssel</span><span class="sxs-lookup"><span data-stu-id="380ae-162">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="380ae-163">A Dirac-jelölés egy másik szép funkciója az a tény, hogy lineáris.</span><span class="sxs-lookup"><span data-stu-id="380ae-163">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="380ae-164">Ha négy kvantum-állapotú vektort szeretne írni,</span><span class="sxs-lookup"><span data-stu-id="380ae-164">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="380ae-165">$ $ (\alpha \ket { \psi } + \beta \ket { \phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \alpha \gamma \ket { \psi } \ket { \chi } + \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } . $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-165">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="380ae-166">Ez azt jelenti, hogy a Dirac-jelöléssel terjesztheti a tízes termék jelölését, így az állapot-vektorok közötti tenser-termékek megtartása ugyanúgy zajlik, mint a hagyományos szorzás.</span><span class="sxs-lookup"><span data-stu-id="380ae-166">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="380ae-167">A melltartó-vektorok hasonló konvenciót követnek a két vektorhoz.</span><span class="sxs-lookup"><span data-stu-id="380ae-167">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="380ae-168">Például az $ \bra { \psi } \bra { \phi } $ vektor felel meg az állapot Vector $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-168">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="380ae-169">Ha a \ket { \psi } $ a $ \alpha \ket{0 } + \beta \ket{1 } $, akkor a vektor melltartó vektoros verziója $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra{0 } \alpha ^ \* + \bra{1 } \beta ^ \*) $.</span><span class="sxs-lookup"><span data-stu-id="380ae-169">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="380ae-170">Tegyük fel például, hogy szeretnénk kiszámítani a valószínűségét, hogy a $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 \ket{0 $ állapotot mérjük a } } Quantum program használatával, hogy az állapotok a $ \ket { +} $ vagy $ \ket-} $ értékűek legyenek { .</span><span class="sxs-lookup"><span data-stu-id="380ae-170">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="380ae-171">Ezt követően a valószínűsége annak, hogy az eszköz kimenete lenne, hogy az állapot $ \ket { -} $</span><span class="sxs-lookup"><span data-stu-id="380ae-171">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="380ae-172">$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-172">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="380ae-173">Az a tény, hogy a negatív előjel jelenik meg a valószínűség kiszámításakor, a kvantum-interferencia megnyilvánulása, amely az egyik olyan mechanizmus, amellyel a Quantum Computing előnyt élvez a klasszikus számítástechnika terén.</span><span class="sxs-lookup"><span data-stu-id="380ae-173">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="380ae-174">ketbra vagy külső termék</span><span class="sxs-lookup"><span data-stu-id="380ae-174">ketbra or outer product</span></span>
<span data-ttu-id="380ae-175">A Dirac jelölésének utolsó eleme a *ketbra* vagy külső termék.</span><span class="sxs-lookup"><span data-stu-id="380ae-175">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="380ae-176">A külső termék a $ \ket { \psi } \bra { \phi } $ Dirac és más néven ketbras, mivel a melltartó és a kulcsfontosságú alaptechnológiák a brakets ellentétes sorrendben történnek.</span><span class="sxs-lookup"><span data-stu-id="380ae-176">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="380ae-177">A külső termék a mátrix szorzásán keresztül van definiálva, mint $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ a Quantum State vectors $ \psi $ és $ \phi $ .</span><span class="sxs-lookup"><span data-stu-id="380ae-177">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="380ae-178">Ennek a jelölésnek a legegyszerűbb és vitathatatlan leggyakoribb példája a következő</span><span class="sxs-lookup"><span data-stu-id="380ae-178">The simplest, and arguably most common example of this notation, is</span></span>

<span data-ttu-id="380ae-179">$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end { bmatrix } \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="380ae-179">$$ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="380ae-180">A Ketbras gyakran nevezik kivetítőknek, mert a kvantum-állapotot egy rögzített értékre tervezik.</span><span class="sxs-lookup"><span data-stu-id="380ae-180">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="380ae-181">Mivel ezek a műveletek nem egységesek (és nem is őrzik meg a vektorok normáját), nem meglepő, hogy a kvantum-számítógép nem tud determinisztikus módon alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="380ae-181">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="380ae-182">A kivetítők azonban szép munkát végeznek, amely leírja, hogy milyen műveletet végeznek a mérések kvantum-állapotban.</span><span class="sxs-lookup"><span data-stu-id="380ae-182">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="380ae-183">Ha például a $ \ket { \psi } $ értéket mérjük a $0-as értékre, $ akkor az azt eredményező átalakítás, hogy az állapot a mérés eredményeképpen megtapasztalható</span><span class="sxs-lookup"><span data-stu-id="380ae-183">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="380ae-184">$ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-184">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="380ae-185">az egyik arra vár, hogy mérjük-e az állapotot, és megtalálhatja a $ \ket{0 } $ értéket.</span><span class="sxs-lookup"><span data-stu-id="380ae-185">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="380ae-186">Az ismételt próbálkozáshoz az ilyen kivetítőket nem lehet a kvantum-számítógép determinisztikus módon állapotában alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="380ae-186">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="380ae-187">Ehelyett a legjobb esetben véletlenszerűen lesznek alkalmazva, ha a $ \ket{0 } $ értéket rögzített valószínűséggel megjelenő eredmény jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="380ae-187">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="380ae-188">Egy ilyen mérték sikeres megírásának valószínűsége az állapotú kvantum-kivetítő várt értéke lehet.</span><span class="sxs-lookup"><span data-stu-id="380ae-188">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

<span data-ttu-id="380ae-189">$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-189">$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="380ae-190">Ez azt szemlélteti, hogy a kivetítők egyszerűen új módot adnak a mérési folyamat kifejezésére.</span><span class="sxs-lookup"><span data-stu-id="380ae-190">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="380ae-191">Ha ehelyett úgy gondoljuk, hogy a qubit-állapot első qubit a $1-as értékre kell mérni, $ ezt a folyamatot a kivetítők és a Dirac-jelölések használatával is kényelmesen le lehet írni:</span><span class="sxs-lookup"><span data-stu-id="380ae-191">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

<span data-ttu-id="380ae-192">$ $ P (\text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right) \ket { \psi } .</span><span class="sxs-lookup"><span data-stu-id="380ae-192">$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="380ae-193">Itt az Identity Matrix is kényelmesen írható Dirac-jelöléssel</span><span class="sxs-lookup"><span data-stu-id="380ae-193">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

<span data-ttu-id="380ae-194">$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="380ae-194">$$ \boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="380ae-195">Abban az esetben, ha két qubits a kivetítő kibontható</span><span class="sxs-lookup"><span data-stu-id="380ae-195">For the case where there are two-qubits the projector can be expanded as</span></span> 

<span data-ttu-id="380ae-196">$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .</span><span class="sxs-lookup"><span data-stu-id="380ae-196">$$ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="380ae-197">Ezt követően láthatjuk, hogy ez összhangban van a multiqubit-állapotok oszlop-vektoros jelöléssel való használatának valószínűségével kapcsolatos megbeszélésekkel:</span><span class="sxs-lookup"><span data-stu-id="380ae-197">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

<span data-ttu-id="380ae-198">$ $ P (\text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="380ae-198">$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="380ae-199">amely megfelel a többszörös qubit mérési vitának.</span><span class="sxs-lookup"><span data-stu-id="380ae-199">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="380ae-200">Ennek az eredménynek az általánosítása a többtényezős qubit esetében azonban valamivel egyszerűbb, ha Dirac-jelölést használ, mint az oszlop-vektoros jelölés, és teljesen egyenértékű a korábbi kezeléssel.</span><span class="sxs-lookup"><span data-stu-id="380ae-200">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="380ae-201">Sűrűségi operátorok</span><span class="sxs-lookup"><span data-stu-id="380ae-201">Density operators</span></span>

<span data-ttu-id="380ae-202">Egy másik hasznos operátor, amely a Dirac jelölést *használja, más*néven *állapot*-kezelőként is ismert.</span><span class="sxs-lookup"><span data-stu-id="380ae-202">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="380ae-203">A Quantum State Vector sűrűségű operátora a következő formát veszi: $ \rho = \ket { \psi } \bra { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="380ae-203">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="380ae-204">Ez a fogalom azt jelenti, hogy az államot mátrixként, nem pedig vektorként jelöli meg, általában azért, mert kényelmes módot biztosít a valószínűségi számítások ábrázolására, valamint lehetővé teszi, hogy az egyik a statisztikai bizonytalanságot is leírja, valamint a kvantum-bizonytalanságot ugyanazon a formalitáson belül.</span><span class="sxs-lookup"><span data-stu-id="380ae-204">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="380ae-205">A kvantum-számítástechnika egyes területein az általános kvantum-operátorok, a vektorok helyett mindenütt elérhetők, de nem szükségesek a mező alapjaihoz.</span><span class="sxs-lookup"><span data-stu-id="380ae-205">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="380ae-206">Az érdekelt olvasó számára javasoljuk, hogy olvassa el a [További tudnivalókat ismertető](xref:microsoft.quantum.more-information)füzetek egyikét.</span><span class="sxs-lookup"><span data-stu-id="380ae-206">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="380ae-207">A Q # Gate a Quantum állapotokkal egyenértékű részei</span><span class="sxs-lookup"><span data-stu-id="380ae-207">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="380ae-208">Az utolsó pont a kvantum-jelöléssel és a Q # programozási nyelvvel ér véget: a dokumentum kezdetén azt is említettük, hogy a kvantum-állapot a kvantum-számítástechnikai adatok alapvető tárgya.</span><span class="sxs-lookup"><span data-stu-id="380ae-208">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="380ae-209">Ekkor meglepőnek tűnhet, hogy a Q #-ban nincs a kvantum állapot fogalma.</span><span class="sxs-lookup"><span data-stu-id="380ae-209">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="380ae-210">Ehelyett az összes állapotot csak az előkészítéséhez használt műveletek írják le.</span><span class="sxs-lookup"><span data-stu-id="380ae-210">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="380ae-211">Az előző példa egy kiváló illusztráció.</span><span class="sxs-lookup"><span data-stu-id="380ae-211">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="380ae-212">Ahelyett, hogy egységes, a regiszterben lévő összes Quantum bites sztringre kifejezzék, az eredményt $H ^ {\otimes n \ket{0 $ értékként is képviseljük } } .</span><span class="sxs-lookup"><span data-stu-id="380ae-212">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="380ae-213">Ennek az állapotnak az exponenciálisan rövidebb leírása nem csupán az előnye, hogy klasszikusan indokolja, de az algoritmus megvalósításához szükséges műveleteket is tömören definiálja.</span><span class="sxs-lookup"><span data-stu-id="380ae-213">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="380ae-214">Emiatt a Q # úgy van kialakítva, hogy a Quantum állapot helyett Gate-sorozatot bocsát ki. elméleti szinten azonban a két perspektíva egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="380ae-214">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
