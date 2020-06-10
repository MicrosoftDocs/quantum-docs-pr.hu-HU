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
# <a name="vectors-and-matrices"></a><span data-ttu-id="f781e-103">Vektorok és mátrixok</span><span class="sxs-lookup"><span data-stu-id="f781e-103">Vectors and Matrices</span></span>

<span data-ttu-id="f781e-104">A kvantum-számítástechnika megismeréséhez elengedhetetlen a vektorok és mátrixok megismerése.</span><span class="sxs-lookup"><span data-stu-id="f781e-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="f781e-105">Egy rövid bevezetést biztosítunk, és az érdekelt olvasóknak javasoljuk, hogy szabványos referenciát olvassanak a lineáris algebra, például a *furcsa, a G (1993) számára. A lineáris algebra bemutatása (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* vagy online referenciák, például [lineáris algebra](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="f781e-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="f781e-106">A dimenzió (vagy a méret) $n egy oszlop vektora (vagy egyszerűen [*vektoros*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v a (z) $ $ $n $ komplex számok (v_1, v_2, \ldots, v_n) száma oszlopként rendezve:</span><span class="sxs-lookup"><span data-stu-id="f781e-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="f781e-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="f781e-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-108">v_1\\\\</span></span>
<span data-ttu-id="f781e-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-109">v_2\\\\</span></span>
<span data-ttu-id="f781e-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-110">\vdots\\\\</span></span>
<span data-ttu-id="f781e-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="f781e-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="f781e-112">A vektoros $v normája $ $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $-ként van definiálva.</span><span class="sxs-lookup"><span data-stu-id="f781e-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="f781e-113">A vektorok egység normának számítanak (vagy más néven [*egység vektoros*](https://en.wikipedia.org/wiki/Unit_vector)), ha a norma értéke $1 $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="f781e-114">A [*vektoros $v adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $v ^ \dagger van megadva, és az $ a következő sor vektorra van meghatározva, ahol a $ \* $ a komplex konjugátumot jelöli,</span><span class="sxs-lookup"><span data-stu-id="f781e-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="f781e-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="f781e-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="f781e-116">A két vektor együttes összeszorzásának leggyakoribb módja a [*belső termék*](https://en.wikipedia.org/wiki/Inner_product_space), más néven a dot termék.</span><span class="sxs-lookup"><span data-stu-id="f781e-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="f781e-117">A belső termék lehetővé teszi egy vektor kivetítését egy másikra, és felbecsülhetetlen értékű, hogy leírja, hogyan lehet egy vektort más egyszerűbb vektorok összegével kifejezni.</span><span class="sxs-lookup"><span data-stu-id="f781e-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="f781e-118">A $u és $v közötti belső termék a $ $ $ \left \langle u, v \right \rangle $ értékkel van definiálva</span><span class="sxs-lookup"><span data-stu-id="f781e-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="f781e-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="f781e-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="f781e-120">Ez a jelölés azt is lehetővé teszi, hogy egy vektor $v a $ $ \sqrt { \langle v, v $ formátumban legyen megírva \rangle } .</span><span class="sxs-lookup"><span data-stu-id="f781e-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="f781e-121">Megszorozhat egy számmal $c vektort $ , amely egy olyan új vektort alkot, amelynek a bejegyzései megszorozzák a $c $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="f781e-122">Két vektort is hozzáadhat $u $ és $v $ egy olyan új vektor létrehozásához, amelynek bejegyzései a $u és $v bejegyzéseinek összege $ $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="f781e-123">Ezek a műveletek az alábbi ábrán láthatók:</span><span class="sxs-lookup"><span data-stu-id="f781e-123">These operations are depicted below:</span></span>

<span data-ttu-id="f781e-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="f781e-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-125">u_1\\\\</span></span>
<span data-ttu-id="f781e-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-126">u_2\\\\</span></span>
<span data-ttu-id="f781e-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-127">\vdots\\\\</span></span>
<span data-ttu-id="f781e-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-129">v_1\\\\</span></span>
    <span data-ttu-id="f781e-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-130">v_2\\\\</span></span>
    <span data-ttu-id="f781e-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-131">\vdots\\\\</span></span>
    <span data-ttu-id="f781e-132">v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="f781e-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="f781e-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="f781e-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-135">\vdots\\\\</span></span>
<span data-ttu-id="f781e-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f781e-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="f781e-137">A $m \times n méretű [*mátrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $ egy $MN komplex számokból álló gyűjtemény, amely $ $m $ sorokban és $n $ oszlopokban van rendezve, ahogy az alábbi ábrán látható:</span><span class="sxs-lookup"><span data-stu-id="f781e-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="f781e-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="f781e-139">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="f781e-140">M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {MN } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="f781e-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="f781e-141">Vegye figyelembe, hogy a Dimension $n vektora $ egyszerűen $n \times 1 méretű mátrix $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="f781e-142">Mint a vektorok esetében, egy számmal $c mátrixot is használhatunk $ egy olyan új mátrix beszerzéséhez, amelyben minden egyes bejegyzést megszoroznak a $cval $ , és két mátrixot is hozzáadhatunk egy olyan új mátrix létrehozásához, amelynek bejegyzései a két mátrix megfelelő bejegyzéseinek összege.</span><span class="sxs-lookup"><span data-stu-id="f781e-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="f781e-143">Mátrix – szorzási és a tenser-termékek</span><span class="sxs-lookup"><span data-stu-id="f781e-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="f781e-144">Két mátrixot is használhatunk $M $ a dimenzió $m \times n $ és az $N $ dimenzió $n a p \times $ , hogy egy új mátrix $P $ a dimenzió $m a \times a $ következő módon:</span><span class="sxs-lookup"><span data-stu-id="f781e-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="f781e-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="f781e-145">\begin{align}</span></span>
<span data-ttu-id="f781e-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-147">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="f781e-148">M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {MN}</span><span class="sxs-lookup"><span data-stu-id="f781e-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="f781e-149">végénbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-149">\end{bmatrix}</span></span>
<span data-ttu-id="f781e-150">megkezdésebmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-150">\begin{bmatrix}</span></span>
<span data-ttu-id="f781e-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="f781e-152">N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {np}</span><span class="sxs-lookup"><span data-stu-id="f781e-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="f781e-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="f781e-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="f781e-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {mp}</span><span class="sxs-lookup"><span data-stu-id="f781e-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="f781e-156">végénbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-156">\end{bmatrix}</span></span>
<span data-ttu-id="f781e-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f781e-157">\end{align}</span></span>

<span data-ttu-id="f781e-158">a $P bejegyzései $ $P _ {ik } = \ sum_j M_ {ij} N_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="f781e-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="f781e-159">A $P _ {11 $ bejegyzés például a } $M első sorának belső terméke a $ $N első oszlopával $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="f781e-160">Vegye figyelembe, hogy mivel a vektor egyszerűen egy mátrix speciális esete, ez a definíció a mátrix-vektoros szorzásra terjed ki.</span><span class="sxs-lookup"><span data-stu-id="f781e-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="f781e-161">A rendszer az összes olyan mátrixot felveszi, amely a sorok és oszlopok száma, illetve a vektorok, amelyek csak $1 oszlopnak felelnek meg $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="f781e-162">Egy speciális négyzetes mátrix az [*Identity Matrix*](https://en.wikipedia.org/wiki/Identity_matrix), a $ \boldone $ , amely az összes átlós elemet $1 értékkel, $ a fennmaradó elemek pedig $0 $ :</span><span class="sxs-lookup"><span data-stu-id="f781e-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="f781e-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="f781e-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="f781e-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="f781e-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="f781e-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="f781e-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="f781e-168">Négyzetes mátrix $A esetén $ a mátrix $B $ az [*inverz*](https://en.wikipedia.org/wiki/Invertible_matrix) , ha $AB = ba = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="f781e-169">A mátrix inverzének nem kell léteznie, de ha létezik, egyedi, és azt $A ^ {-1 $ értékűre jelöljük } .</span><span class="sxs-lookup"><span data-stu-id="f781e-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="f781e-170">Bármely mátrix-$M esetében $ a $M adjoint vagy konjugátum-átültetése $ egy olyan mátrix $N, $ amely $N _ {ij } = M_ {Ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="f781e-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="f781e-171">A $M adjoint $ általában $M ^ \dagger van kijelölve $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="f781e-172">Tegyük fel, hogy a mátrix $U $ [*egységes*](https://en.wikipedia.org/wiki/Unitary_matrix) , ha $uu ^ \dagger = U ^ \dagger U = \boldone $ vagy azzal egyenértékű, $U ^ {-1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="f781e-173">Az egységes mátrixok legfontosabb tulajdonsága az, hogy megőrzik a vektorok normáit.</span><span class="sxs-lookup"><span data-stu-id="f781e-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="f781e-174">Ez azért történik, mert</span><span class="sxs-lookup"><span data-stu-id="f781e-174">This happens because</span></span> 

<span data-ttu-id="f781e-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="f781e-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="f781e-176">A mátrix $M $ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , ha $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="f781e-177">Végül a két [*mátrix (vagy*](https://en.wikipedia.org/wiki/Tensor_product) Kronecker termék) $M $ $m \times n $ és $N mérete $ $p \Times q $ nagyobb mátrix $P = M \otimes n $ méretű $mp \times nq $ , és a következő módon szerezhető be $ : $M és $N $ .</span><span class="sxs-lookup"><span data-stu-id="f781e-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="f781e-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="f781e-178">\begin{align}</span></span>
    <span data-ttu-id="f781e-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-180">M_ {11 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="f781e-181">M_ {M1 } ~ ~ \cdots ~ ~ M_ {MN}</span><span class="sxs-lookup"><span data-stu-id="f781e-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="f781e-182">végénbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-182">\end{bmatrix}</span></span>
    <span data-ttu-id="f781e-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-184">N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="f781e-185">N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq}</span><span class="sxs-lookup"><span data-stu-id="f781e-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="f781e-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1N } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f781e-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="f781e-188">M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {MN } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1NÉ } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="f781e-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f781e-189">\end{bmatrix}.</span></span>
<span data-ttu-id="f781e-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f781e-190">\end{align}</span></span>

<span data-ttu-id="f781e-191">Ez jobban szemlélteti néhány példát:</span><span class="sxs-lookup"><span data-stu-id="f781e-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="f781e-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="f781e-195">\\\\[1,5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="f781e-196">végénbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-196">\end{bmatrix}</span></span>
    <span data-ttu-id="f781e-197">= \begin{ bmatrix } a c a \\ \\ d a \\ \\ e \\ \\ b c \\ \\ b d \\ \\ \endbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="f781e-198">és</span><span class="sxs-lookup"><span data-stu-id="f781e-198">and</span></span>

<span data-ttu-id="f781e-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="f781e-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="f781e-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="f781e-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-204">a \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f781e-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f781e-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f781e-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f781e-212">végénbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-212">\end{bmatrix}</span></span>
    <span data-ttu-id="f781e-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f781e-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="f781e-214">AE \ AF \ be \ BF \\ \\ AG \ ah \ BG \ bh \\ \\ CE \ CF \ de \ DF \\ \\ CG \ CH \ DG \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f781e-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="f781e-215">A legtöbbször hasznos, a TEN-termékekkel kapcsolatos jelölési konvenció az, hogy bármely vektoros $v $ vagy mátrix $M $ , $v ^ {\otimes n } $ vagy $M ^ {\otimes n } $ rövid Hand egy $n $ -szor ismétlődő tízes termékhez.</span><span class="sxs-lookup"><span data-stu-id="f781e-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="f781e-216">Például:</span><span class="sxs-lookup"><span data-stu-id="f781e-216">For example:</span></span>

<span data-ttu-id="f781e-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="f781e-217">\begin{align}</span></span>
<span data-ttu-id="f781e-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 0 0 0 \\ \\ \\ \\ \\ \\ \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f781e-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="f781e-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f781e-219">\end{align}</span></span>
