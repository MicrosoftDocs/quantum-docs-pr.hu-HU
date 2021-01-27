---
<span data-ttu-id="82f4c-101">title: Pauli-mérések leírása: megtudhatja, hogyan dolgozhat az egy-és több qubit Pauli-mérési műveletekkel.</span><span class="sxs-lookup"><span data-stu-id="82f4c-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="82f4c-102">Szerző: bradben UID: Microsoft. Quantum. Concepts. Pauli MS. Author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuális No-Loc:</span><span class="sxs-lookup"><span data-stu-id="82f4c-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="82f4c-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="82f4c-103">"Q#"</span></span>
- <span data-ttu-id="82f4c-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="82f4c-104">"$$v"</span></span>
- <span data-ttu-id="82f4c-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="82f4c-105">"$$"</span></span>
- <span data-ttu-id="82f4c-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="82f4c-106">"$$"</span></span>
- <span data-ttu-id="82f4c-107">"$"</span><span class="sxs-lookup"><span data-stu-id="82f4c-107">"$"</span></span>
- <span data-ttu-id="82f4c-108">"$"</span><span class="sxs-lookup"><span data-stu-id="82f4c-108">"$"</span></span>
- <span data-ttu-id="82f4c-109">"$"</span><span class="sxs-lookup"><span data-stu-id="82f4c-109">"$"</span></span>
- <span data-ttu-id="82f4c-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="82f4c-110">"$$"</span></span>
- <span data-ttu-id="82f4c-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="82f4c-111">"\cdots"</span></span>
- <span data-ttu-id="82f4c-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="82f4c-112">"bmatrix"</span></span>
- <span data-ttu-id="82f4c-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="82f4c-113">"\ddots"</span></span>
- <span data-ttu-id="82f4c-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="82f4c-114">"\equiv"</span></span>
- <span data-ttu-id="82f4c-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="82f4c-115">"\sum"</span></span>
- <span data-ttu-id="82f4c-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="82f4c-116">"\begin"</span></span>
- <span data-ttu-id="82f4c-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="82f4c-117">"\end"</span></span>
- <span data-ttu-id="82f4c-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="82f4c-118">"\sqrt"</span></span>
- <span data-ttu-id="82f4c-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="82f4c-119">"\otimes"</span></span>
- <span data-ttu-id="82f4c-120">"{"</span><span class="sxs-lookup"><span data-stu-id="82f4c-120">"{"</span></span>
- <span data-ttu-id="82f4c-121">"}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-121">"}"</span></span>
- <span data-ttu-id="82f4c-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="82f4c-122">"\text"</span></span>
- <span data-ttu-id="82f4c-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="82f4c-123">"\phi"</span></span>
- <span data-ttu-id="82f4c-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="82f4c-124">"\kappa"</span></span>
- <span data-ttu-id="82f4c-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="82f4c-125">"\psi"</span></span>
- <span data-ttu-id="82f4c-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="82f4c-126">"\alpha"</span></span>
- <span data-ttu-id="82f4c-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="82f4c-127">"\beta"</span></span>
- <span data-ttu-id="82f4c-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="82f4c-128">"\gamma"</span></span>
- <span data-ttu-id="82f4c-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="82f4c-129">"\delta"</span></span>
- <span data-ttu-id="82f4c-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="82f4c-130">"\omega"</span></span>
- <span data-ttu-id="82f4c-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="82f4c-131">"\bra"</span></span>
- <span data-ttu-id="82f4c-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="82f4c-132">"\ket"</span></span>
- <span data-ttu-id="82f4c-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="82f4c-133">"\boldone"</span></span>
- <span data-ttu-id="82f4c-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="82f4c-134">"\\\\"</span></span>
- <span data-ttu-id="82f4c-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="82f4c-135">"\\"</span></span>
- <span data-ttu-id="82f4c-136">"="</span><span class="sxs-lookup"><span data-stu-id="82f4c-136">"="</span></span>
- <span data-ttu-id="82f4c-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="82f4c-137">"\frac"</span></span>
- <span data-ttu-id="82f4c-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="82f4c-138">"\text"</span></span>
- <span data-ttu-id="82f4c-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="82f4c-139">"\mapsto"</span></span>
- <span data-ttu-id="82f4c-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="82f4c-140">"\dagger"</span></span>
- <span data-ttu-id="82f4c-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="82f4c-141">"\to"</span></span>
- <span data-ttu-id="82f4c-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-142">"\begin{cases}"</span></span>
- <span data-ttu-id="82f4c-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-143">"\end{cases}"</span></span>
- <span data-ttu-id="82f4c-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="82f4c-144">"\operatorname"</span></span>
- <span data-ttu-id="82f4c-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="82f4c-145">"\braket"</span></span>
- <span data-ttu-id="82f4c-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="82f4c-146">"\id"</span></span>
- <span data-ttu-id="82f4c-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="82f4c-147">"\expect"</span></span>
- <span data-ttu-id="82f4c-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="82f4c-148">"\defeq"</span></span>
- <span data-ttu-id="82f4c-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="82f4c-149">"\variance"</span></span>
- <span data-ttu-id="82f4c-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="82f4c-150">"\dd"</span></span>
- <span data-ttu-id="82f4c-151">"&"</span><span class="sxs-lookup"><span data-stu-id="82f4c-151">"&"</span></span>
- <span data-ttu-id="82f4c-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-152">"\begin{align}"</span></span>
- <span data-ttu-id="82f4c-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-153">"\end{align}"</span></span>
- <span data-ttu-id="82f4c-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="82f4c-154">"\Lambda"</span></span>
- <span data-ttu-id="82f4c-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="82f4c-155">"\lambda"</span></span>
- <span data-ttu-id="82f4c-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="82f4c-156">"\Omega"</span></span>
- <span data-ttu-id="82f4c-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="82f4c-157">"\mathrm"</span></span>
- <span data-ttu-id="82f4c-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="82f4c-158">"\left"</span></span>
- <span data-ttu-id="82f4c-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="82f4c-159">"\right"</span></span>
- <span data-ttu-id="82f4c-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="82f4c-160">"\qquad"</span></span>
- <span data-ttu-id="82f4c-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="82f4c-161">"\times"</span></span>
- <span data-ttu-id="82f4c-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="82f4c-162">"\big"</span></span>
- <span data-ttu-id="82f4c-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="82f4c-163">"\langle"</span></span>
- <span data-ttu-id="82f4c-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="82f4c-164">"\rangle"</span></span>
- <span data-ttu-id="82f4c-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="82f4c-165">"\bigg"</span></span>
- <span data-ttu-id="82f4c-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="82f4c-166">"\Big"</span></span>
- <span data-ttu-id="82f4c-167">"|"</span><span class="sxs-lookup"><span data-stu-id="82f4c-167">"|"</span></span>
- <span data-ttu-id="82f4c-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="82f4c-168">"\mathbb"</span></span>
- <span data-ttu-id="82f4c-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="82f4c-169">"\vec"</span></span>
- <span data-ttu-id="82f4c-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="82f4c-170">"\in"</span></span>
- <span data-ttu-id="82f4c-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="82f4c-171">"\texttt"</span></span>
- <span data-ttu-id="82f4c-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="82f4c-172">"\ne"</span></span>
- <span data-ttu-id="82f4c-173">"<"</span><span class="sxs-lookup"><span data-stu-id="82f4c-173">"<"</span></span>
- <span data-ttu-id="82f4c-174">">"</span><span class="sxs-lookup"><span data-stu-id="82f4c-174">">"</span></span>
- <span data-ttu-id="82f4c-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="82f4c-175">"\leq"</span></span>
- <span data-ttu-id="82f4c-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="82f4c-176">"\geq"</span></span>
- <span data-ttu-id="82f4c-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="82f4c-177">"~~"</span></span>
- <span data-ttu-id="82f4c-178">"~"</span><span class="sxs-lookup"><span data-stu-id="82f4c-178">"~"</span></span>
- <span data-ttu-id="82f4c-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="82f4c-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="82f4c-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="82f4c-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="82f4c-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="82f4c-182">Pauli-mérések</span><span class="sxs-lookup"><span data-stu-id="82f4c-182">Pauli Measurements</span></span>

<span data-ttu-id="82f4c-183">Az előző megbeszélésekben a számítási szempontok alapján történik a mérés.</span><span class="sxs-lookup"><span data-stu-id="82f4c-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="82f4c-184">Valójában más gyakori mérések történnek a kvantum-számítástechnikaban, amelyek egy adott szempontból megfelelőek a számítási szempontok alapján.</span><span class="sxs-lookup"><span data-stu-id="82f4c-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="82f4c-185">A használata során Q# a leggyakrabban a legelterjedtebb típusú mérések lesznek a *Pauli-mérések*, amelyek általánosítják a számítási alapjait, hogy más alapértékekre, valamint a különböző qubits közötti paritásos méréseket is tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82f4c-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="82f4c-186">Ilyen esetekben gyakori, hogy megbeszéljük a Pauli-operátorok mérését, általában egy operátort, például az $ x, Y, z $ vagy $ z \otimes z, x \otimes x, x \otimes Y $ és így tovább.</span><span class="sxs-lookup"><span data-stu-id="82f4c-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span> 

> [!TIP]
<span data-ttu-id="82f4c-187">> A-ben a Q# multi-Qubit Pauli-operátorokat általában típusú tömbök jelölik `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="82f4c-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="82f4c-188">> Például az $ X \otimes Z Y jelöléséhez \otimes $ használhatja a tömböt `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="82f4c-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="82f4c-189">A kiértékelése a Pauli-operátorok esetében különösen gyakori a kvantum-hibák helyesbítésének almezőjében.</span><span class="sxs-lookup"><span data-stu-id="82f4c-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="82f4c-190">A-ben Q# egy hasonló konvenciót követünk, amely a mérések alternatív nézetét ismerteti.</span><span class="sxs-lookup"><span data-stu-id="82f4c-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="82f4c-191">A Pauli-mérések részleteinek megismerése előtt érdemes meggondolni, hogy a kvantum-számítógépeken belüli egyetlen qubit hogyan mérhető a kvantum állapot.</span><span class="sxs-lookup"><span data-stu-id="82f4c-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="82f4c-192">Képzelje el, hogy egy $ n $ -qubit kvantum-állapottal rendelkezik, majd az egyik qubit azonnal kiszámítja a $ 2 ^ n lehetőség felét, $ amelyet az állapot tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="82f4c-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="82f4c-193">Ez azt jelenti, hogy a mérték a kvantum-állapotot a két fél szóköz egyikére vetíti.</span><span class="sxs-lookup"><span data-stu-id="82f4c-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="82f4c-194">Általánosíthatja a mérést úgy gondoljuk, hogy ezt az adatelemzést is figyelembe vesszük.</span><span class="sxs-lookup"><span data-stu-id="82f4c-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="82f4c-195">Az alterületek tömör azonosításához szükség van egy nyelvre a leírásához.</span><span class="sxs-lookup"><span data-stu-id="82f4c-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="82f4c-196">A két alterület leírásának egyik módja, ha egy olyan mátrixon keresztül adja meg őket, amely csak két egyedi eigenvalues rendelkezik, az egyezmény szerint $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="82f4c-197">Az alterületek ily módon történő leírásának egyszerű példáját a $ Z $ :</span><span class="sxs-lookup"><span data-stu-id="82f4c-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="82f4c-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & – 1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="82f4c-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="82f4c-199">A Pauli-Z mátrix átlós elemeinek olvasásával $ $ láthatjuk, hogy a $ Z $ két eigenvectors, $ \ket { 0 } $ és $ \ket { 1 } $ , a megfelelő eigenvalues $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="82f4c-200">Így ha mérjük a qubit és a beszerzést `Zero` (amely a 0. állapotnak felel meg $ \ket { } $ ), tudjuk, hogy a qubit állapota a $ $ Z operátor + 1 $ eigenstate $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="82f4c-201">Hasonlóképpen, ha beszerezhetjük `One` , tudjuk, hogy a qubit állapota a $ -1 $ eigenstate $ $ . Ezt a folyamatot a Pauli-mérések nyelvén kell megtekinteni, amely a "Pauli Z" mérési módszernek $ $ felel meg, és teljes mértékben megfelel a számítási alapokra vonatkozó mérések elvégzésének.</span><span class="sxs-lookup"><span data-stu-id="82f4c-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="82f4c-202">A $ \times $ Z egységes átalakítását biztosító 2 2 mátrix $ $ is megfelel ennek a feltételnek.</span><span class="sxs-lookup"><span data-stu-id="82f4c-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="82f4c-203">Ez azt is megteheti, hogy egy $ = u ^ \dagger Z u-es mátrixot is használhat $ , ahol az $ u $ bármely más egységes mátrix, amely egy olyan mátrixot biztosít, amely meghatározza egy mérték két eredményét a $ \pm 1 $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="82f4c-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="82f4c-204">A Pauli-mérések jelölése erre az egységes egyenértékűségre hivatkozik, $ Ha az X, Y, Z $ méréseket egyenértékű mértékegységként azonosítja, amelyet az egyik a qubit származó információk megszerzésére használhat.</span><span class="sxs-lookup"><span data-stu-id="82f4c-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="82f4c-205">Ezek a mérések az alábbiakban láthatók a kényelem érdekében.</span><span class="sxs-lookup"><span data-stu-id="82f4c-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="82f4c-206">|Pauli-mérés –  | egységes átalakítás  |</span><span class="sxs-lookup"><span data-stu-id="82f4c-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="82f4c-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="82f4c-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="82f4c-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="82f4c-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="82f4c-209">|$ $ Y | $HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="82f4c-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="82f4c-210">Ez a nyelv használata esetén a "Y mérték $ $ " egyenértékű a $ HS ^ alkalmazásával, \dagger $ majd a számítási folyamat alapján történő méréssel, ahol a [`S`](xref:Microsoft.Quantum.Intrinsic.S) belső kvantum-művelet néha "Phase Gate" néven is ismert, és az egységes mátrix szimulálható.</span><span class="sxs-lookup"><span data-stu-id="82f4c-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:Microsoft.Quantum.Intrinsic.S) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="82f4c-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="82f4c-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="82f4c-212">1 & 0 \\\\ 0 & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="82f4c-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="82f4c-213">Emellett a $ HS ^ \dagger $ a Quantum State Vector-re való alkalmazása, majd a Z mérése is megegyezik azzal $ $ , hogy a következő művelet egyenértékű `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="82f4c-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```qsharp
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="82f4c-214">A megfelelő állapotot a rendszer úgy fogja megtalálni, hogy visszaalakítja a számítási alapot, amely az $ sh- $ t a kvantum-állapot vektorára alkalmazza; a fenti kódrészletben a blokk használatával automatikusan kezeli az átalakítást a számítási alapra `within … apply` .</span><span class="sxs-lookup"><span data-stu-id="82f4c-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="82f4c-215">A-ben Q# azt mondjuk, hogy az eredmény---az, hogy az---állapottal való interakcióból kinyert klasszikus információ "j" értékkel van megadva, amely azt jelzi, hogy `Result` $ \in \\ { \texttt { } \texttt { } \\ } $ az eredmény az $ (-1) ^ j eigenspace, amely a $ Pauli operátort méri.</span><span class="sxs-lookup"><span data-stu-id="82f4c-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="82f4c-216">Többszörös qubit mérések</span><span class="sxs-lookup"><span data-stu-id="82f4c-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="82f4c-217">A több-qubit Pauli-operátorok mérései hasonló módon vannak definiálva, ahogy a következőkben is látható:</span><span class="sxs-lookup"><span data-stu-id="82f4c-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="82f4c-218">Z: 1 0 0 0 0 \otimes = \begin{bmatrix} & & – 1 0 0 0 0 & \\\\ & & & \\\\ & & – 1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1.</span><span class="sxs-lookup"><span data-stu-id="82f4c-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="82f4c-219">Így a két Pauli- $ Z operátorok kétféle $ $ $ , 1 és $ -1 eigenvalues álló mátrixot alkotnak $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="82f4c-220">Az qubit esethez hasonlóan mindkettő fél helyet jelent, ami azt jelenti, hogy az elérhető vektor területének fele a $ + 1 $ eigenspace és a fennmaradó fele az $ -1 $ eigenspace tartozik.</span><span class="sxs-lookup"><span data-stu-id="82f4c-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="82f4c-221">Általánosságban elmondható, hogy a kéttengelyes termék definíciója alapján a Pauli- $ Z operátorok és az identitás bármely tenser terméke is betartja $ ezt.</span><span class="sxs-lookup"><span data-stu-id="82f4c-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="82f4c-222">Példa:</span><span class="sxs-lookup"><span data-stu-id="82f4c-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="82f4c-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="82f4c-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="82f4c-224">1 &  0 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="82f4c-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="82f4c-226">0 &  0 & – 1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="82f4c-227">0 &  0 & & – 1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="82f4c-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="82f4c-228">Ahogy korábban is, az ilyen mátrixok egységes átalakítása a \pm 1 eigenvalues által megcímkézett két fél szóközt is ismerteti $ $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="82f4c-229">Például: $ X \otimes x h = h \otimes (z \otimes z) h h \otimes , $  az identitástól, amely a $ z = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="82f4c-230">Az qubit esethez hasonlóan mind a kétqubit Pauli-mérések $ u ^ (Z) u-vel írhatók \dagger \otimes \id $ $ 4 \times 4 $ egységes mátrixhoz $ u $ . A következő táblázatban szereplő transzformációk enumerálása.</span><span class="sxs-lookup"><span data-stu-id="82f4c-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="82f4c-231">>Az alábbi táblázatban a $ \operatorname { swap használatával } $ jelezheti a mátrixot >$$</span><span class="sxs-lookup"><span data-stu-id="82f4c-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="82f4c-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="82f4c-232">> \begin{align}</span></span>
<span data-ttu-id="82f4c-233">>     \operatorname{SWAP } &=</span><span class="sxs-lookup"><span data-stu-id="82f4c-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="82f4c-234">>     \left( \begin { mátrix}</span><span class="sxs-lookup"><span data-stu-id="82f4c-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="82f4c-235">>         1 & 0 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="82f4c-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="82f4c-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="82f4c-238">>0 & 0 & 0 & 1 > \end { mátrix } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="82f4c-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="82f4c-239">> $$</span><span class="sxs-lookup"><span data-stu-id="82f4c-239">> $$</span></span>
<span data-ttu-id="82f4c-240">> a belső művelet szimulálására szolgál [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="82f4c-240">> used to simulate the intrinsic operation [`SWAP`](xref:Microsoft.Quantum.Intrinsic).</span></span>

<span data-ttu-id="82f4c-241">|Pauli-mérés –     | egységes átalakítás  |</span><span class="sxs-lookup"><span data-stu-id="82f4c-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="82f4c-242">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="82f4c-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="82f4c-243">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="82f4c-244">|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="82f4c-245">|$\boldone \otimes Z $ | $ \operatorname { swap } $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="82f4c-246">|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { swap } $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="82f4c-247">|$\boldone \otimes Y $ | $ (hs ^ \dagger \otimes \boldone ) \operatorname { swap } $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="82f4c-248">|$Z \otimes Z $ | $ \operatorname { cnem } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="82f4c-249">|$X \otimes Z $ | $ \operatorname { cnem } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="82f4c-250">|$Y \otimes Z $ | $ \operatorname { cnem } \_ { 10 } (hs ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="82f4c-251">|$Z \otimes X $ | $ \operatorname { cnem } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="82f4c-252">|$X \otimes X $ | $ \operatorname { cnem } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="82f4c-253">|$Y \otimes X $ | $ \operatorname { cnem } \_ { 10 } (hs ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="82f4c-254">|$Z \otimes Y $ | $ \operatorname { cnem } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="82f4c-255">|$X \otimes Y $ | $ \operatorname { cnem } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="82f4c-256">|$Y \otimes Y $ | $ \operatorname { cnem } \_ { 10 } (hs ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="82f4c-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="82f4c-257">Itt a [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) művelet a következő okból jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="82f4c-257">Here, the [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operation appears for the following reason.</span></span>
<span data-ttu-id="82f4c-258">A fenti indoklásnak megfelelően minden olyan Pauli-mérés, amely nem tartalmazza a $ \boldone $ mátrixot, egy egységes, z z-ig egyenlő $ \otimes $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="82f4c-259">A z z $ eigenvalues \otimes csak az $ egyes számítási alapú vektorokból álló qubits paritása függ, és a vezérelt nem műveletek szolgálnak a paritás kiszámításához és az első bites tároláshoz.</span><span class="sxs-lookup"><span data-stu-id="82f4c-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="82f4c-260">Ezután az első bit mérése után helyreállítjuk az eredményül kapott fél terület identitását, amely egyenértékű a Pauli-operátor mérésével.</span><span class="sxs-lookup"><span data-stu-id="82f4c-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="82f4c-261">Egy további Megjegyzés: Ha úgy gondolja, hogy $ a z z 1. és 1. számú mérési érték \otimes $ megegyeznek $ \otimes \mathbb { } $ $ \mathbb { , akkor ez a } \otimes $ feltételezés hamis lenne.</span><span class="sxs-lookup"><span data-stu-id="82f4c-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="82f4c-262">Ennek az az oka, hogy a $ z \otimes z-ig a eigenstate a $ kvantum-állapotot a $ $ $ fenti operátorok + 1 vagy-1 $ értékére méri.</span><span class="sxs-lookup"><span data-stu-id="82f4c-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="82f4c-263">$ \otimes \mathbb { } $ $ \mathbb { Az 1. és 1 } \otimes . szám mérésével $ a Quantum State Vector először az $ 1. fele, \otimes \mathbb { } $ majd egy $ \mathbb { 1 } \otimes $ . fél szóközre van húzva. Mivel négy számítási alap vektor létezik, mindkét mérés végrehajtása csökkenti az állapotot egy negyedéves területre, és így csökkenti azt egyetlen számítási célú vektorban.</span><span class="sxs-lookup"><span data-stu-id="82f4c-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="82f4c-264">Qubitek közötti korreláció</span><span class="sxs-lookup"><span data-stu-id="82f4c-264">Correlations between qubits</span></span>
<span data-ttu-id="82f4c-265">A Pauli-mátrixok, például az x x vagy a z z. a tízesebb termékek mérésének egy másik módja, $ \otimes $ $ \otimes $ hogy ezek a méretek lehetővé teszik a két qubits közötti összefüggésekben tárolt információk megtekintését.</span><span class="sxs-lookup"><span data-stu-id="82f4c-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="82f4c-266">$Az X mérésével \otimes \id $ megtekintheti az első qubit helyileg tárolt adatokat.</span><span class="sxs-lookup"><span data-stu-id="82f4c-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="82f4c-267">Habár a kvantum-számítástechnika mindkét típusú mérése egyenlően értékes, a korábbi megvilágítja a kvantum-számítástechnika erejét.</span><span class="sxs-lookup"><span data-stu-id="82f4c-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="82f4c-268">Ez azt mutatja, hogy a kvantum-számítástechnikaban gyakran a tanulni kívánt információ nem egyetlen qubit van tárolva, hanem nem helyileg, hanem az összes qubits, és ezért csak egy közös mérésen (például z z) keresztül történik $ \otimes $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="82f4c-269">A hibajavítás során például gyakran szeretnénk megismerni, hogy milyen hibák történtek, miközben a rendszer nem a védelemmel ellátott állapotról tanul.</span><span class="sxs-lookup"><span data-stu-id="82f4c-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="82f4c-270">A [bit-flip code minta](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) példa arra, hogyan végezhető el a mérések használata, például z z és z z $ \otimes \otimes \id $ $ \id \otimes \otimes $ . < --TODO: változtassa meg a minta böngészőre mutató hivatkozást, amint a bit-flip code minta be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="82f4c-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="82f4c-271">Az önkényes Pauli-operátorok, például az $ X \otimes Y \otimes Z \otimes \boldone $ is mérhetők.</span><span class="sxs-lookup"><span data-stu-id="82f4c-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="82f4c-272">A Pauli-operátorok összes ilyen tenser-terméke csak két eigenvalues $ \pm 1 $ , és mindkét eigenspaces a teljes vektoros terület felét képezi.</span><span class="sxs-lookup"><span data-stu-id="82f4c-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="82f4c-273">Így a fent említett követelmények egybeesnek.</span><span class="sxs-lookup"><span data-stu-id="82f4c-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="82f4c-274">A-ben az Q# ilyen mérések a j értéket adják vissza, $ $ Ha a mérés eredménye a $ következő: eigenspace (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="82f4c-275">Mivel a Pauli-mérések beépített funkciója hasznos, Q# mert az ilyen operátorok méréséhez hosszú láncú vezérelt, nem kapuk és átalakítások szükségesek, hogy leírják a diagonalizing U Gate, amely a művelet kiépítéséhez $ $ szükséges a $ Z és a $ $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="82f4c-276">Az előre definiált mérések egyikének megadásához nem kell aggódnia, hogy hogyan alakíthatja át az adatokat, hogy a számítási alap a szükséges információkat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="82f4c-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="82f4c-277">Q# automatikusan kezeli az összes szükséges átalakítást.</span><span class="sxs-lookup"><span data-stu-id="82f4c-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="82f4c-278">További információ: [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) és [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) műveletek.</span><span class="sxs-lookup"><span data-stu-id="82f4c-278">For more information, see the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) and [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="82f4c-279">A No-Cloning tétel</span><span class="sxs-lookup"><span data-stu-id="82f4c-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="82f4c-280">A Quantum információi hatékonyak.</span><span class="sxs-lookup"><span data-stu-id="82f4c-280">Quantum information is powerful.</span></span>
<span data-ttu-id="82f4c-281">Lehetővé teszi, hogy elképesztően olyan dolgokat végezzenek, mint a faktorok száma exponenciálisan, mint a legismertebb klasszikus algoritmusok, vagy hatékonyan szimulálja a korrelált elektron-rendszereket, amelyekkel a klasszikusan exponenciálisan kell szimulálni a pontos műveleteket.</span><span class="sxs-lookup"><span data-stu-id="82f4c-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="82f4c-282">A kvantum-számítástechnika hatékonysága azonban korlátozott.</span><span class="sxs-lookup"><span data-stu-id="82f4c-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="82f4c-283">Az egyik ilyen korlátozást a *nem klónozási tétel* adja meg.</span><span class="sxs-lookup"><span data-stu-id="82f4c-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="82f4c-284">A No-Cloning tétel találó nevű.</span><span class="sxs-lookup"><span data-stu-id="82f4c-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="82f4c-285">Az általános kvantum-állapotok egy kvantum-számítógép általi klónozását nem teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="82f4c-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="82f4c-286">A tétel bizonyítása rendkívül egyszerű.</span><span class="sxs-lookup"><span data-stu-id="82f4c-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="82f4c-287">Habár a nem klónozási tétel teljes bizonyítéka egy kicsit túl sok technikai megoldás a vitához, a további kiegészítő qubits nem a hatókörén belül.</span><span class="sxs-lookup"><span data-stu-id="82f4c-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope.</span></span>

<span data-ttu-id="82f4c-288">Egy ilyen kvantum-számítógép esetében a klónozási műveletet egy egységes mátrixtal kell ismertetni.</span><span class="sxs-lookup"><span data-stu-id="82f4c-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="82f4c-289">Megtiltjuk a mérést, mivel az sérült a klónozott állapotot.</span><span class="sxs-lookup"><span data-stu-id="82f4c-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="82f4c-290">A klónozási művelet szimulálása érdekében azt szeretnénk, hogy az egységes mátrix a következő tulajdonságot használja. $$</span><span class="sxs-lookup"><span data-stu-id="82f4c-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="82f4c-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="82f4c-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="82f4c-292">bármilyen állapothoz $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="82f4c-293">A mátrixok szorzásának lineáris tulajdonsága azt jelenti, hogy bármely második kvantum $ \ket { \phi } $ -állapotnál</span><span class="sxs-lookup"><span data-stu-id="82f4c-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="82f4c-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="82f4c-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="82f4c-295">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="82f4c-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="82f4c-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="82f4c-297">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="82f4c-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="82f4c-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="82f4c-298">\right) \\\\</span></span>
    <span data-ttu-id="82f4c-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right )) \right .</span><span class="sxs-lookup"><span data-stu-id="82f4c-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="82f4c-300">Ez biztosítja a No-Cloningi tétel mögötti alapvető intuíciót: minden olyan eszközön, amely ismeretlen kvantum-állapotot másol, hibákat kell kimutatnia legalább néhány, az általa másolt államban.</span><span class="sxs-lookup"><span data-stu-id="82f4c-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="82f4c-301">Míg a legfontosabb feltételezés, hogy a Cloner lineárisan működik a bemeneti állapoton, megsértheti a kiegészítő qubits hozzáadását és mérését, az ilyen interakciók pedig a mérési statisztikán keresztül a rendszerre vonatkozó információkat is felhasználhatják, és meggátolják az ilyen esetekben történő pontos klónozást is.</span><span class="sxs-lookup"><span data-stu-id="82f4c-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="82f4c-302">A No-Cloning tétel részletesebb igazolását lásd: [További információ](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="82f4c-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="82f4c-303">A No-Cloningi tétel fontos a kvantum-számítástechnika minőségi megismerése érdekében, mert ha a kvantum-állapotok költséges klónozását is lehetővé teszi, akkor közel varázslatos képességet kap a kvantum-állapotok megismeréséhez.</span><span class="sxs-lookup"><span data-stu-id="82f4c-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="82f4c-304">Valójában megsértheti a Heisenberg hencegő bizonytalansági elvét.</span><span class="sxs-lookup"><span data-stu-id="82f4c-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="82f4c-305">Azt is megteheti, hogy az optimális Cloner használatával egyetlen mintát vesz igénybe egy összetett kvantum-eloszlásból, és megtudhatja, hogy az adott disztribúcióról csak egyetlen mintából lehet tájékozódni.</span><span class="sxs-lookup"><span data-stu-id="82f4c-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="82f4c-306">Ez olyan lenne, mint egy érme tükrözése és a fejek betartása, majd egy barátomnak szól az eredményről, amelynek a válaszát "Ah az érme eloszlásának Bernoulli kell lennie a $ p = 0.512643 \ ldots $ !"</span><span class="sxs-lookup"><span data-stu-id="82f4c-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="82f4c-307">Egy ilyen utasítás nem sensical, mert egy kis információ (a fejek végeredménye) egyszerűen nem tudja biztosítani az elosztás kódolásához szükséges több bitet a jelentős előzetes információk nélkül.</span><span class="sxs-lookup"><span data-stu-id="82f4c-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="82f4c-308">Hasonlóképpen, az előzetes információk nélkül nem tudjuk tökéletesen klónozott állapotba állítani a kvantum-állapotot $ $ .</span><span class="sxs-lookup"><span data-stu-id="82f4c-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="82f4c-309">Az információk nem ingyenesek a Quantum Computing szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="82f4c-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="82f4c-310">A mért qubit egyetlen kis mennyiségű információt biztosítanak, és a No-Cloning-tétel azt mutatja, hogy nincs olyan hátsó ajtó, amely kihasználható a rendszeren szerzett információk és a meghívott zavarok közötti alapvető kompromisszum körül.</span><span class="sxs-lookup"><span data-stu-id="82f4c-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
