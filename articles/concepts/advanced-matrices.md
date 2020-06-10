---
title: Speciális mátrixfogalmak
description: Ismerje meg a eigenvectors, a eigenvalues és a mátrix exponenciális adatait, a kvantum-algoritmusok leírására és szimulálására szolgáló alapvető eszközöket.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630153"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="857b8-103">Speciális mátrix-fogalmak</span><span class="sxs-lookup"><span data-stu-id="857b8-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="857b8-104">Most kiterjesztjük a mátrixok manipulációját a [*Eigenvalues, a Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) és az [*exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) értékekre, amelyek a kvantum-algoritmusok leírásához és megvalósításához szükséges alapvető eszközkészletet alkotnak.</span><span class="sxs-lookup"><span data-stu-id="857b8-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="857b8-105">Eigenvalues és Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="857b8-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="857b8-106">Legyen $M $ egy négyzetes mátrix, és $v $ olyan vektor, amely nem az összes nulla vektor (azaz a vektor, amely az összes olyan bejegyzést tartalmazza, amely a $0 értékkel egyenlő $ ).</span><span class="sxs-lookup"><span data-stu-id="857b8-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="857b8-107">Tegyük fel $ , hogy $v $M [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) , $ Ha $MV = cv $ bizonyos számú $c $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="857b8-108">Tegyük fel, hogy $c a $ eigenvector $v megfelelő [*sajátérték*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="857b8-109">A mátrixok $M általában egy $ vektort is átalakíthat bármely más vektorba, de egy eigenvector speciális, mert változatlan marad, kivéve, ha egy szám megszorozza.</span><span class="sxs-lookup"><span data-stu-id="857b8-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="857b8-110">Vegye figyelembe, hogy ha $v $ egy eigenvector, amely sajátérték $c $ , akkor $AV $ is egy eigenvector (minden nem nulla $a esetében $ ) ugyanazzal a sajátérték.</span><span class="sxs-lookup"><span data-stu-id="857b8-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="857b8-111">Az Identity Matrix esetében például minden vektor $v $ egy eigenvector, amely sajátérték $1 $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="857b8-112">Egy másik Példaként vegyünk egy olyan [*átlós mátrixot*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D, $ amely csak nullától eltérő bejegyzéseket tartalmaz az átlóban:</span><span class="sxs-lookup"><span data-stu-id="857b8-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="857b8-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="857b8-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="857b8-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="857b8-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="857b8-115">A vektorok</span><span class="sxs-lookup"><span data-stu-id="857b8-115">The vectors</span></span>

<span data-ttu-id="857b8-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } és \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="857b8-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="857b8-117">Ennek a mátrixnak a eigenvectors a eigenvalues $d _1 $ , $d _2 $ és $d _3 $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="857b8-118">Ha $d _1 $ , $d _2 $ , és $d _3 $ különböző számok, akkor ezek a vektorok (és azok többszörösei) a mátrix $D egyetlen eigenvectors $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="857b8-119">Az átlós mátrixok esetében általában könnyen olvasható a eigenvalues és a eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="857b8-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="857b8-120">A eigenvalues az átlóban megjelenő számok, a hozzájuk tartozó eigenvectors pedig az egység vektorok, amelyek egy bejegyzése $1 $ , a fennmaradó bejegyzések pedig $0 $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="857b8-121">Vegye figyelembe a fenti példában, hogy a eigenvectors $D a $ $3 $ dimenziós vektorok alapjait alkotják.</span><span class="sxs-lookup"><span data-stu-id="857b8-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="857b8-122">Az alap olyan vektorok halmaza, amelyekben a vektorok lineáris kombinációként is írhatók.</span><span class="sxs-lookup"><span data-stu-id="857b8-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="857b8-123">Explicit módon $v _1 $ , $v _2 $ , és $v _3, $ ha bármilyen vektor $v $ írható $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ néhány szám $a _1 $ , $a _2 $ és $a _3 $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="857b8-124">Ne felejtse el, hogy egy Hermitian mátrix (más néven önadjoint) egy összetett négyzetes mátrix, amely a saját összetett konjugátumával egyenlő, míg az egységes mátrix egy olyan összetett négyzetes mátrix, amelynek inverze egyenlő a komplex konjugátummal.</span><span class="sxs-lookup"><span data-stu-id="857b8-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="857b8-125">A Hermitian és az egységes mátrixok esetében, amelyek lényegében csak egyetlen, a Quantum Computing-ben észlelt mátrixok, egy általános eredmény a [*spektrális tétel*](https://en.wikipedia.org/wiki/Spectral_theorem), amely a következőket állítja be: bármely Hermitian vagy egységes mátrixú $M esetében $ létezik egy egységes $U, $ hogy $M = U ^ \dagger D u $ egy átlós mátrix $D $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="857b8-126">Emellett a $D átlós bejegyzései $ a $M eigenvalues lesznek $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="857b8-127">Már tudjuk, hogyan kell kiszámítani egy átlós mátrix $D eigenvalues és eigenvectors $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="857b8-128">Ennek a tételnek a használatával tudjuk, hogy ha a $v $ $D $ sajátérték $c $ , például $DV = CV $ , akkor a $U ^ \dagger v $ eigenvector $M $ sajátérték $c $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="857b8-129">Ennek az az oka, hogy</span><span class="sxs-lookup"><span data-stu-id="857b8-129">This is because</span></span>

<span data-ttu-id="857b8-130">$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="857b8-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="857b8-131">Mátrix exponenciális</span><span class="sxs-lookup"><span data-stu-id="857b8-131">Matrix Exponentials</span></span>
<span data-ttu-id="857b8-132">A [*mátrix exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) meghatározása pontosan az exponenciális függvényhez hasonlóan is megadható.</span><span class="sxs-lookup"><span data-stu-id="857b8-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="857b8-133">Mátrix $A mátrixának exponenciális $ kifejezése</span><span class="sxs-lookup"><span data-stu-id="857b8-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="857b8-134">$ $ e ^ A = \boldone + a + \frac{A {2 } !} + \frac{A ^ 3 } {3!} + \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="857b8-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="857b8-135">Ez azért fontos, mert a Quantum Mechanical Time Evolution leírását az űrlap egy egységes mátrixa írja le, $e ^ {iB } $ for Hermitian matrix $B $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="857b8-136">Emiatt a Matrix exponenciálisok végrehajtása a kvantum-számítástechnika alapvető részét képezi, és a Q # olyan belső rutinokat kínál, amelyek ezeknek a műveleteknek a leírására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="857b8-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="857b8-137">A mátrix exponenciális felszámításának számos módja van a klasszikus számítógépeken, és általában számszerűen közelíthető meg egy ilyen exponenciális megoldás.</span><span class="sxs-lookup"><span data-stu-id="857b8-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="857b8-138">Lásd: [*Cleve moleer és Charles van Loan. "Tizenkilenc kétes módszer a mátrix exponenciális kiszámítására." SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) az érintett kihívásokkal kapcsolatos további információkért.</span><span class="sxs-lookup"><span data-stu-id="857b8-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="857b8-139">A mátrix exponenciális kiszámításának legegyszerűbb módja a mátrix eigenvalues és eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="857b8-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="857b8-140">A fent tárgyalt spektrális tétel azt mondja, hogy minden Hermitian vagy egységes mátrixnál $A $ létezik egy egységes mátrix $U $ és egy átlós mátrix $D $ , amely $A = u ^ \dagger D u $ .  A unitarity tulajdonságai miatt $A ^ 2 = U ^ \dagger D ^ 2 U $ és hasonló módon bármely power $p $ $A ^ p = u ^ \dagger D ^ p U $ .  Ha ezt a műveletet behelyettesítjük az operátor definíciójában, a következőt kapjuk:</span><span class="sxs-lookup"><span data-stu-id="857b8-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="857b8-141">$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!}) + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="857b8-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="857b8-142">Más szóval, ha a mátrix eigenbasis alakítja át a $A, $ majd a mátrix exponenciális megszámításával egyenértékű a mátrix eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="857b8-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="857b8-143">A Quantum Computing számos művelete magában foglalja a mátrixok exponenciális használatát, ez a trükk a mátrix eigenbasis való átalakítását mutatja be, amely egyszerűbbé teszi az operátor exponenciális megjelenítését, és számos olyan kvantum-algoritmus mögött található, mint például a Trotter – Suzuki stílusú kvantum-szimulációs módszerek, amelyeket az útmutató későbbi szakaszában ismertetünk.</span><span class="sxs-lookup"><span data-stu-id="857b8-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="857b8-144">Egy másik hasznos tulajdonság az, ha a $B $ egységes és Hermitian, például $B = b ^ {-1 } = B ^ \dagger, $ majd $B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="857b8-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="857b8-145">Ha ezt a szabályt a mátrix exponenciális kiterjesztésére, valamint a $ \boldone $ és a $B feltételek csoportosítására alkalmazza $ , akkor láthatja, hogy a valódi érték $x $ az identitást.</span><span class="sxs-lookup"><span data-stu-id="857b8-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="857b8-146">$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="857b8-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="857b8-147">rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="857b8-147">holds.</span></span> <span data-ttu-id="857b8-148">Ez a trükk különösen hasznos, mivel ez a művelet lehetővé teszi, hogy az egyes műveletek mátrixa exponenciálisan megtörténjen, még akkor is, ha a $B dimenziója $ exponenciálisan nagy, a speciális esetre, ha a $B $ mind az egységes, mind a Hermitian.</span><span class="sxs-lookup"><span data-stu-id="857b8-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
