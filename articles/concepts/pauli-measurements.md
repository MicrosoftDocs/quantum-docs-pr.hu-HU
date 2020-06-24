---
title: Pauli-mérések
description: Ismerje meg, hogyan dolgozhat egyetlen és több qubit Pauli-mérési művelettel.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269473"
---
# <a name="pauli-measurements"></a><span data-ttu-id="e527b-103">Pauli-mérések</span><span class="sxs-lookup"><span data-stu-id="e527b-103">Pauli Measurements</span></span>

<span data-ttu-id="e527b-104">Az előző megbeszélésekben a számítási szempontok alapján történik a mérés.</span><span class="sxs-lookup"><span data-stu-id="e527b-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="e527b-105">Valójában más gyakori mérések történnek a kvantum-számítástechnikaban, amelyek egy adott szempontból megfelelőek a számítási szempontok alapján.</span><span class="sxs-lookup"><span data-stu-id="e527b-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="e527b-106">Ahogy dolgozik a Q #-ban, a leggyakoribb mérések valószínűleg *Pauli-mérések*lesznek, ami általánosítja a számítási alapjait, hogy más alapértékekre, valamint a különböző qubits közötti paritásos méréseket is tartalmazzon.</span><span class="sxs-lookup"><span data-stu-id="e527b-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="e527b-107">Ilyen esetekben gyakori, hogy megbeszéljük a Pauli-operátorok mérését, általában egy operátort (például $X, Y, Z $ vagy $Z \otimes Z, x \otimes x, x \otimes Y stb $ .).</span><span class="sxs-lookup"><span data-stu-id="e527b-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="e527b-108">A Q #-ban a többszörös qubit Pauli-operátorokat általában típusú tömbök jelölik `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="e527b-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="e527b-109">Ha például az $X \otimes Z \otimes Y jelölését szeretné $ használni, használhatja a tömböt `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="e527b-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="e527b-110">A kiértékelése a Pauli-operátorok esetében különösen gyakori a kvantum-hibák helyesbítésének almezőjében.</span><span class="sxs-lookup"><span data-stu-id="e527b-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="e527b-111">A Q #-ban egy hasonló konvenciót követünk. most a mérések alternatív nézetét magyarázjuk.</span><span class="sxs-lookup"><span data-stu-id="e527b-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="e527b-112">A Pauli-mérések részleteinek megismerése előtt érdemes meggondolni, hogy a kvantum-számítógépeken belüli egyetlen qubit hogyan mérhető a kvantum állapot.</span><span class="sxs-lookup"><span data-stu-id="e527b-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="e527b-113">Képzelje el, hogy $n $ qubit Quantum állapottal rendelkezik, majd az egyik qubit azonnal kiszámítja a $2 ^ n $ lehetőség felét, amelyet az állapot tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="e527b-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="e527b-114">Ez azt jelenti, hogy a mérték a kvantum-állapotot a két fél szóköz egyikére vetíti.</span><span class="sxs-lookup"><span data-stu-id="e527b-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="e527b-115">Általánosíthatja a mérést úgy gondoljuk, hogy ezt az adatelemzést is figyelembe vesszük.</span><span class="sxs-lookup"><span data-stu-id="e527b-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="e527b-116">Az alterületek tömör azonosításához szükség van egy nyelvre a leírásához.</span><span class="sxs-lookup"><span data-stu-id="e527b-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="e527b-117">A két alterület leírásának egyik módja, ha egy olyan mátrixon keresztül adja meg őket, amely csak két egyedi eigenvalues rendelkezik, az egyezmény szerint pedig $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="e527b-118">Az alterületek ily módon történő leírásának egyszerű példája $Z $ :</span><span class="sxs-lookup"><span data-stu-id="e527b-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="e527b-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-119">$$ \begin{align}</span></span>
  <span data-ttu-id="e527b-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e527b-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="e527b-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-121">\end{align}</span></span>
$$

<span data-ttu-id="e527b-122">A Pauli-$Z mátrix átlós elemeinek beolvasásával $ láthatjuk, hogy $Z $ két eigenvectors, $ \ket{0 } $ és $ \ket{1 } $ értékű, a megfelelő eigenvalues $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="e527b-123">Így ha mérjük a qubit és a beszerzést `Zero` (amely a $ \ket{0 $ értéknek felel meg } ), tudjuk, hogy a qubit állapota a $Z operátor $ + 1 $ eigenstate $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="e527b-124">Hasonlóképpen, ha beszerezhetjük `One` , tudjuk, hogy a qubit állapota a $Z $-1 $ eigenstate $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="e527b-125">Ezt a folyamatot a Pauli-mérések nyelvén nevezzük a "Pauli $Z mérésének" kifejezésnek $ , és teljes mértékben egyenértékűek a számítási alapokra vonatkozó mérések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="e527b-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="e527b-126">A \times $ $Z egységes átalakítására alkalmas bármely $2 2 mátrix $ megfelel ennek a feltételnek is.</span><span class="sxs-lookup"><span data-stu-id="e527b-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="e527b-127">Ez azt is megteheti, hogy használhatunk egy Matrix $A = U ^ \dagger Z U $ -t, ahol a $U $ bármely más egységes mátrix, amely egy olyan mátrixot biztosít, amely meghatározza egy mérték két eredményét a $ \pm 1 $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="e527b-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="e527b-128">A Pauli-mérések jelölése erre az egységes egyenértékűségre hivatkozik, ha a $X, Y, Z $ méréseket egyenértékű mértékegységként azonosítja, amelyet egy qubit származó információk megszerzéséhez lehet tenni.</span><span class="sxs-lookup"><span data-stu-id="e527b-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="e527b-129">Ezek a mérések az alábbiakban láthatók a kényelem érdekében.</span><span class="sxs-lookup"><span data-stu-id="e527b-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="e527b-130">Pauli-mérés</span><span class="sxs-lookup"><span data-stu-id="e527b-130">Pauli Measurement</span></span>  |<span data-ttu-id="e527b-131">Egységes átalakítás</span><span class="sxs-lookup"><span data-stu-id="e527b-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="e527b-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="e527b-132">$Z$</span></span>               | <span data-ttu-id="e527b-133">\boldone USD$</span><span class="sxs-lookup"><span data-stu-id="e527b-133">$\boldone$</span></span>             |
| <span data-ttu-id="e527b-134">$X$</span><span class="sxs-lookup"><span data-stu-id="e527b-134">$X$</span></span>               | <span data-ttu-id="e527b-135">$H$</span><span class="sxs-lookup"><span data-stu-id="e527b-135">$H$</span></span>                    |
| <span data-ttu-id="e527b-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="e527b-136">$Y$</span></span>               | <span data-ttu-id="e527b-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="e527b-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="e527b-138">Ez a nyelv használata esetén a "mérték $Y $ " egyenértékű a $HS ^ \dagger alkalmazásával, $ majd a számítási alap mérésével, ahol a [`S`](xref:microsoft.quantum.intrinsic.s) belső kvantum-művelet néha "Phase Gate", és az egységes mátrix szimulálható.</span><span class="sxs-lookup"><span data-stu-id="e527b-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="e527b-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-139">$$ \begin{align}</span></span>
    <span data-ttu-id="e527b-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e527b-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="e527b-141">1 & 0 \\ \\ 0 & \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e527b-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="e527b-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-142">\end{align}</span></span>
$$

<span data-ttu-id="e527b-143">Ezzel egyenértékű a $HS ^ \dagger $ a kvantum-állapot vektorára való alkalmazásával, majd a $Z mérésével is $ , hogy a következő művelet egyenértékű legyen `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="e527b-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="e527b-144">A megfelelő állapotot a rendszer úgy fogja megtalálni, hogy visszaalakítja a számítási alapot, amely a Quantum State Vector $SH alkalmazására vonatkozik $ ; a fenti kódrészletben a blokk használatával automatikusan kezeli az átalakítást a számítási alapra `within … apply` .</span><span class="sxs-lookup"><span data-stu-id="e527b-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="e527b-145">A Q #-ban azt mondjuk, hogy az eredmény---az a klasszikus információ, amelyet a rendszer az állapottal való interakcióból kinyert--- `Result` $j \in \\ {\Texttt{Zero } , \texttt{One} $, amely azt jelzi, hogy az eredmény szerepel-e a } \\ Pauli operátor által mért $ (-1) ^ j $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="e527b-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="e527b-146">Többszörös qubit mérések</span><span class="sxs-lookup"><span data-stu-id="e527b-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="e527b-147">A több-qubit Pauli-operátorok mérései hasonló módon vannak definiálva, ahogy a következőkben is látható:</span><span class="sxs-lookup"><span data-stu-id="e527b-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="e527b-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e527b-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="e527b-149">Így a kétféle Pauli-$Z-kezelők kétféle, a $ $ + 1 $ és a $-1 eigenvalues tartalmazó mátrixot alkotnak $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="e527b-150">Az qubit esethez hasonlóan mindkettő fél helyet jelent, ami azt jelenti, hogy az elérhető vektor területének fele a $ + 1 $ eigenspace és a fennmaradó fele a $-1 eigenspace-hez tartozik $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="e527b-151">Általánosságban elmondható, hogy a kéttényezős termék definíciója alapján a Pauli-$Z $ operátorok és az identitások bármely tenser terméke is engedelmeskedik.</span><span class="sxs-lookup"><span data-stu-id="e527b-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="e527b-152">Példa:</span><span class="sxs-lookup"><span data-stu-id="e527b-152">For example,</span></span>

<span data-ttu-id="e527b-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-153">$$ \begin{align}</span></span>
    <span data-ttu-id="e527b-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e527b-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="e527b-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 0 \\ \\ & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e527b-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="e527b-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-156">\end{align}</span></span>
$$

<span data-ttu-id="e527b-157">Ahogy korábban is, az ilyen mátrixok egységes átalakítása a $ \pm 1 eigenvalues címkével ellátott két fél szóközt is ismerteti $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="e527b-158">Például $X \otimes X = h \otimes h (z \otimes z) h h \otimes $ az identitásból, amely $Z = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="e527b-159">Az qubit esethez hasonlóan mind a két qubit (Pauli) mérések írhatók, mint $U ^ \dagger (Z \otimes \id) U $ $4 \times 4 $ egységes mátrixokhoz $U $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="e527b-160">A következő táblázatban szereplő transzformációk enumerálása.</span><span class="sxs-lookup"><span data-stu-id="e527b-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="e527b-161">Az alábbi táblázatban a $ \operatorname{SWAP $ értéket használjuk } a Matrix $ $ \begin{align jelzésére}</span><span class="sxs-lookup"><span data-stu-id="e527b-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="e527b-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="e527b-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="e527b-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="e527b-164">a $ $ a belső művelet szimulálása céljából használatos [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="e527b-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="e527b-165">Pauli-mérés</span><span class="sxs-lookup"><span data-stu-id="e527b-165">Pauli Measurement</span></span>     |<span data-ttu-id="e527b-166">Egységes átalakítás</span><span class="sxs-lookup"><span data-stu-id="e527b-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="e527b-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="e527b-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="e527b-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="e527b-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="e527b-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="e527b-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="e527b-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="e527b-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e527b-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="e527b-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e527b-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="e527b-176">\operatorname{SWAP USD}$</span><span class="sxs-lookup"><span data-stu-id="e527b-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="e527b-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e527b-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="e527b-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="e527b-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="e527b-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e527b-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="e527b-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="e527b-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="e527b-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e527b-181">$Z\otimes Z$</span></span> | <span data-ttu-id="e527b-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="e527b-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="e527b-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e527b-183">$X\otimes Z$</span></span> | <span data-ttu-id="e527b-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="e527b-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="e527b-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e527b-185">$Y\otimes Z$</span></span> | <span data-ttu-id="e527b-186">$ \operatorname{CNOT } \_ {10 } (hs ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="e527b-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="e527b-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e527b-187">$Z\otimes X$</span></span> | <span data-ttu-id="e527b-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="e527b-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="e527b-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e527b-189">$X\otimes X$</span></span> | <span data-ttu-id="e527b-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="e527b-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="e527b-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e527b-191">$Y\otimes X$</span></span> | <span data-ttu-id="e527b-192">$ \operatorname{CNOT } \_ {10 } (hs ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="e527b-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="e527b-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e527b-193">$Z\otimes Y$</span></span> | <span data-ttu-id="e527b-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="e527b-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="e527b-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e527b-195">$X\otimes Y$</span></span> | <span data-ttu-id="e527b-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="e527b-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="e527b-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e527b-197">$Y\otimes Y$</span></span> | <span data-ttu-id="e527b-198">$ \operatorname{CNOT } \_ {10 } (hs ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="e527b-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="e527b-199">Itt a [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) művelet a következő okból jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="e527b-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="e527b-200">Minden olyan Pauli-mérés, amely nem tartalmazza a $ \boldone $ mátrixot, egyenértékű a \otimes $ fenti indoklással $Z Z értékkel.</span><span class="sxs-lookup"><span data-stu-id="e527b-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="e527b-201">A ( \otimes Z) $Z Z eigenvalues $ csak az egyes számítási alapú vektorokat alkotó qubits paritása függ, és a vezérelt nem műveletek szolgálnak a paritás kiszámításához és az első bites tároláshoz.</span><span class="sxs-lookup"><span data-stu-id="e527b-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="e527b-202">Ezután az első bit mérése után helyreállítjuk az eredményül kapott fél terület identitását, amely egyenértékű a Pauli-operátor mérésével.</span><span class="sxs-lookup"><span data-stu-id="e527b-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="e527b-203">Egy további Megjegyzés: Ha úgy gondolja, hogy a $Z Z mérése \otimes $ megegyeznek a $Z \otimes \mathbb{1 } $, majd a $ \mathbb{1 \otimes Z értékkel } , akkor $ Ez a feltételezés hamis lenne.</span><span class="sxs-lookup"><span data-stu-id="e527b-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="e527b-204">Ennek az az oka, hogy az $Z \otimes Z $ -projekteket a kvantum-állapottal mérjük a $ fenti operátorok $ + 1 vagy $-1 $ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="e527b-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="e527b-205">$Z \otimes \mathbb{1 } $, majd a $ \Mathbb{1 } \otimes Z $ projekt mérésével a quantum State Vector először $Z \otimes \mathbb{1 $, majd a } $ \mathbb{1 } \otimes Z egy fél $ területére kerül. Mivel négy számítási alap vektor létezik, mindkét mérés végrehajtása csökkenti az állapotot egy negyedéves területre, és így csökkenti azt egyetlen számítási célú vektorban.</span><span class="sxs-lookup"><span data-stu-id="e527b-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="e527b-206">Qubits közötti korrelációk</span><span class="sxs-lookup"><span data-stu-id="e527b-206">Correlations between qubits</span></span>
<span data-ttu-id="e527b-207">A Pauli-mátrixok (például $X X vagy $Z Z) tízesebb termékeinek mérésének egy másik módja, \otimes $ \otimes $ hogy ezek a mérések lehetővé teszik a két qubits közötti összefüggésekben tárolt információk megkeresését.</span><span class="sxs-lookup"><span data-stu-id="e527b-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="e527b-208">$X \id mérésével \otimes $ megtekintheti az első qubit helyileg tárolt adatokat.</span><span class="sxs-lookup"><span data-stu-id="e527b-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="e527b-209">Habár a kvantum-számítástechnika mindkét típusú mérése egyenlően értékes, a korábbi megvilágítja a kvantum-számítástechnika erejét.</span><span class="sxs-lookup"><span data-stu-id="e527b-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="e527b-210">Ez azt mutatja, hogy a kvantum-számítástechnikaban gyakran a tanulni kívánt információ nem egyetlen qubit van tárolva, hanem nem helyileg, hanem az összes qubits, és ezért csak egy közös mérésen (pl. $Z \otimes Z) keresztül történik $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="e527b-211">A hibajavítás során például gyakran szeretnénk megismerni, hogy milyen hibák történtek, miközben a rendszer nem a védelemmel ellátott állapotról tanul.</span><span class="sxs-lookup"><span data-stu-id="e527b-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="e527b-212">A [bit-flip Code](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) példa azt szemlélteti, hogyan teheti meg a méréseket, például a $Z \otimes Z \otimes \id $ és a $ \id \Otimes z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="e527b-213">Tetszőleges Pauli-operátorok, például $X \otimes Y \Otimes Z \otimes \boldone $ is mérhetők.</span><span class="sxs-lookup"><span data-stu-id="e527b-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="e527b-214">A Pauli-operátorok összes ilyen tenser-terméke csak két eigenvalues $ \pm 1 $ , míg mindkét eigenspaces a teljes vektoros terület felét képezi.</span><span class="sxs-lookup"><span data-stu-id="e527b-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="e527b-215">Így a fent említett követelmények egybeesnek.</span><span class="sxs-lookup"><span data-stu-id="e527b-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="e527b-216">A Q #-ban az ilyen mérések $j, $ Ha a mérés eredménye a eigenspace (-1) ^ j jel eredményét eredményezi $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="e527b-217">A Q # beépített funkciójaként a Pauli-mérések használata hasznos lehet, mivel az ilyen operátorok mérése hosszú láncú, nem kapukat és átalakításokat igényel, hogy leírja a diagonalizing $U kaput, amely a $ műveletnek a $Z $ és a $ \id tenser-termékként való kifejezéséhez szükséges $ . Az előre definiált mérések egyikének megadásához nem kell aggódnia, hogy hogyan alakíthatja át az adatokat, hogy a számítási alap a szükséges információkat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e527b-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="e527b-218">A Q # az összes szükséges átalakítást automatikusan kezeli.</span><span class="sxs-lookup"><span data-stu-id="e527b-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="e527b-219">További információ: [`Measure`](xref:microsoft.quantum.intrinsic.measure) és [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) műveletek.</span><span class="sxs-lookup"><span data-stu-id="e527b-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="e527b-220">A klónozás nélküli tétel</span><span class="sxs-lookup"><span data-stu-id="e527b-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="e527b-221">A Quantum információi hatékonyak.</span><span class="sxs-lookup"><span data-stu-id="e527b-221">Quantum information is powerful.</span></span>
<span data-ttu-id="e527b-222">Lehetővé teszi, hogy elképesztően olyan dolgokat végezzenek, mint a faktorok száma exponenciálisan, mint a legismertebb klasszikus algoritmusok, vagy hatékonyan szimulálja a korrelált elektron-rendszereket, amelyekkel a klasszikusan exponenciálisan kell szimulálni a pontos műveleteket.</span><span class="sxs-lookup"><span data-stu-id="e527b-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="e527b-223">A kvantum-számítástechnika hatékonysága azonban korlátozott.</span><span class="sxs-lookup"><span data-stu-id="e527b-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="e527b-224">Az egyik ilyen korlátozást a *nem klónozási tétel*adja meg.</span><span class="sxs-lookup"><span data-stu-id="e527b-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="e527b-225">A nem klónozási tétel találó elnevezésű.</span><span class="sxs-lookup"><span data-stu-id="e527b-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="e527b-226">Az általános kvantum-állapotok egy kvantum-számítógép általi klónozását nem teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="e527b-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="e527b-227">A tétel bizonyítása rendkívül egyszerű.</span><span class="sxs-lookup"><span data-stu-id="e527b-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="e527b-228">Habár a nem klónozási tétel teljes bizonyítéka egy kicsit túl technikai a vitánk számára, a további kiegészítő qubits hiánya nem a hatókörön belül van (a kiegészítő qubits a számítás során qubits használják, és könnyen használhatók és kezelhetők a Q #-ban, lásd a [kölcsönzött qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="e527b-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="e527b-229">Egy ilyen kvantum-számítógép esetében a klónozási műveletet egy egységes mátrixtal kell ismertetni.</span><span class="sxs-lookup"><span data-stu-id="e527b-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="e527b-230">Megtiltjuk a mérést, mivel az sérült a klónozott állapotot.</span><span class="sxs-lookup"><span data-stu-id="e527b-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="e527b-231">A klónozási művelet szimulálása érdekében azt szeretnénk, hogy az egységes mátrix a $ $ U \ket { \psi } \ket{0 } = \ket { \psi } { \ket \psi}</span><span class="sxs-lookup"><span data-stu-id="e527b-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="e527b-232">$ $ minden állapothoz $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="e527b-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="e527b-233">A mátrix szorzásának lineáris tulajdonsága azt jelenti, hogy bármely második kvantum-állapothoz $ \ket { \phi } $,</span><span class="sxs-lookup"><span data-stu-id="e527b-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="e527b-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-234">$$ \begin{align}</span></span>
    <span data-ttu-id="e527b-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="e527b-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="e527b-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="e527b-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="e527b-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="e527b-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="e527b-238">\right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).</span><span class="sxs-lookup"><span data-stu-id="e527b-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="e527b-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e527b-239">\end{align}</span></span>
$$

<span data-ttu-id="e527b-240">Ez biztosítja az alapvető intuíciót a nem klónozási tétel mögött: minden olyan eszközön, amely egy ismeretlen kvantum-állapotot másol, a hibákat legalább néhány, az általa használt állapotból kell kiváltani.</span><span class="sxs-lookup"><span data-stu-id="e527b-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="e527b-241">Míg a legfontosabb feltételezés, hogy a Cloner lineárisan működik a bemeneti állapoton, megsértheti a kiegészítő qubits hozzáadását és mérését, az ilyen interakciók pedig a mérési statisztikán keresztül a rendszerre vonatkozó információkat is felhasználhatják, és meggátolják az ilyen esetekben történő pontos klónozást is.</span><span class="sxs-lookup"><span data-stu-id="e527b-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="e527b-242">A nem klónozási tétel részletesebb igazolását a [További tudnivalókat](xref:microsoft.quantum.more-information)ismertető témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="e527b-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="e527b-243">A nem klónozási tétel fontos a kvantum-számítástechnika minőségi megismerése érdekében, mert ha a kvantum-állapotok költséges klónozását, akkor közel varázslatos képességet kap a kvantum-állapotok megismeréséhez.</span><span class="sxs-lookup"><span data-stu-id="e527b-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="e527b-244">Valójában megsértheti a Heisenberg hencegő bizonytalansági elvét.</span><span class="sxs-lookup"><span data-stu-id="e527b-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="e527b-245">Azt is megteheti, hogy az optimális Cloner használatával egyetlen mintát vesz igénybe egy összetett kvantum-eloszlásból, és megtudhatja, hogy az adott disztribúcióról csak egyetlen mintából lehet tájékozódni.</span><span class="sxs-lookup"><span data-stu-id="e527b-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="e527b-246">Ez olyan lenne, mint egy érme tükrözése és a fejek betartása, majd egy barátomnak szól az eredményről, amelyeknek válaszoltak "Ah az érme eloszlásának Bernoulli kell lennie $p = 0.512643 \ ldots $ !"</span><span class="sxs-lookup"><span data-stu-id="e527b-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="e527b-247">Egy ilyen utasítás nem sensical, mert egy kis információ (a fejek végeredménye) egyszerűen nem tudja biztosítani az elosztás kódolásához szükséges több bitet a jelentős előzetes információk nélkül.</span><span class="sxs-lookup"><span data-stu-id="e527b-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="e527b-248">Hasonlóképpen, az előzetes információk nélkül nem tudjuk tökéletesen klónozott állapotba állítani a kvantum-állapotot, mivel nem tudjuk felkészíteni az ilyen érmék együttesét anélkül, hogy $p tudnánk $ .</span><span class="sxs-lookup"><span data-stu-id="e527b-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="e527b-249">Az információk nem ingyenesek a Quantum Computing szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="e527b-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="e527b-250">A mért qubit egyetlen kis mennyiségű információt biztosítanak, a nem klónozási tétel pedig azt mutatja, hogy nincs olyan hátsó ajtó, amely felhasználható a rendszerről szerzett információk és a meghívott zavarok közötti alapvető kompromisszum megszerzéséhez.</span><span class="sxs-lookup"><span data-stu-id="e527b-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
