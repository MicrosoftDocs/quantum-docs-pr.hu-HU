---
<span data-ttu-id="bcbff-101">title: részletes mátrix – fogalmak leírása: Ismerje meg a eigenvectors, a eigenvalues és a mátrix exponenciálisait, a kvantum-algoritmusok leírásához és szimulálásához használt alapvető eszközöket.</span><span class="sxs-lookup"><span data-stu-id="bcbff-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="bcbff-102">Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. Matrix – speciális MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: No-Loc:</span><span class="sxs-lookup"><span data-stu-id="bcbff-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="bcbff-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-103">"$$"</span></span>
- <span data-ttu-id="bcbff-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-104">"$$"</span></span>
- <span data-ttu-id="bcbff-105">"$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-105">"$"</span></span>
- <span data-ttu-id="bcbff-106">"$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-106">"$"</span></span>
- <span data-ttu-id="bcbff-107">"$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-107">"$"</span></span>
- <span data-ttu-id="bcbff-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-108">"$$"</span></span>
- <span data-ttu-id="bcbff-109">"$$$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-109">"$$$"</span></span>
- <span data-ttu-id="bcbff-110">"$$$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-110">"$$$"</span></span>
- <span data-ttu-id="bcbff-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="bcbff-111">"$$$"</span></span>
- <span data-ttu-id="bcbff-112">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="bcbff-112">"\cdots"</span></span>
- <span data-ttu-id="bcbff-113">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="bcbff-113">"bmatrix"</span></span>
- <span data-ttu-id="bcbff-114">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="bcbff-114">"\ddots"</span></span>
- <span data-ttu-id="bcbff-115">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="bcbff-115">"\equiv"</span></span>
- <span data-ttu-id="bcbff-116">"\sum"</span><span class="sxs-lookup"><span data-stu-id="bcbff-116">"\sum"</span></span>
- <span data-ttu-id="bcbff-117">"\begin"</span><span class="sxs-lookup"><span data-stu-id="bcbff-117">"\begin"</span></span>
- <span data-ttu-id="bcbff-118">"\end"</span><span class="sxs-lookup"><span data-stu-id="bcbff-118">"\end"</span></span>
- <span data-ttu-id="bcbff-119">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="bcbff-119">"\sqrt"</span></span>
- <span data-ttu-id="bcbff-120">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="bcbff-120">"\otimes"</span></span>
- <span data-ttu-id="bcbff-121">"{"</span><span class="sxs-lookup"><span data-stu-id="bcbff-121">"{"</span></span>
- <span data-ttu-id="bcbff-122">"}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-122">"}"</span></span>
- <span data-ttu-id="bcbff-123">"\text"</span><span class="sxs-lookup"><span data-stu-id="bcbff-123">"\text"</span></span>
- <span data-ttu-id="bcbff-124">"\phi"</span><span class="sxs-lookup"><span data-stu-id="bcbff-124">"\phi"</span></span>
- <span data-ttu-id="bcbff-125">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="bcbff-125">"\kappa"</span></span>
- <span data-ttu-id="bcbff-126">"\psi"</span><span class="sxs-lookup"><span data-stu-id="bcbff-126">"\psi"</span></span>
- <span data-ttu-id="bcbff-127">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="bcbff-127">"\alpha"</span></span>
- <span data-ttu-id="bcbff-128">"\beta"</span><span class="sxs-lookup"><span data-stu-id="bcbff-128">"\beta"</span></span>
- <span data-ttu-id="bcbff-129">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="bcbff-129">"\gamma"</span></span>
- <span data-ttu-id="bcbff-130">"\delta"</span><span class="sxs-lookup"><span data-stu-id="bcbff-130">"\delta"</span></span>
- <span data-ttu-id="bcbff-131">"\omega"</span><span class="sxs-lookup"><span data-stu-id="bcbff-131">"\omega"</span></span>
- <span data-ttu-id="bcbff-132">"\bra"</span><span class="sxs-lookup"><span data-stu-id="bcbff-132">"\bra"</span></span>
- <span data-ttu-id="bcbff-133">"\ket"</span><span class="sxs-lookup"><span data-stu-id="bcbff-133">"\ket"</span></span>
- <span data-ttu-id="bcbff-134">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="bcbff-134">"\boldone"</span></span>
- <span data-ttu-id="bcbff-135">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="bcbff-135">"\\\\"</span></span>
- <span data-ttu-id="bcbff-136">"\\"</span><span class="sxs-lookup"><span data-stu-id="bcbff-136">"\\"</span></span>
- <span data-ttu-id="bcbff-137">"="</span><span class="sxs-lookup"><span data-stu-id="bcbff-137">"="</span></span>
- <span data-ttu-id="bcbff-138">"\frac"</span><span class="sxs-lookup"><span data-stu-id="bcbff-138">"\frac"</span></span>
- <span data-ttu-id="bcbff-139">"\text"</span><span class="sxs-lookup"><span data-stu-id="bcbff-139">"\text"</span></span>
- <span data-ttu-id="bcbff-140">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="bcbff-140">"\mapsto"</span></span>
- <span data-ttu-id="bcbff-141">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="bcbff-141">"\dagger"</span></span>
- <span data-ttu-id="bcbff-142">"\to"</span><span class="sxs-lookup"><span data-stu-id="bcbff-142">"\to"</span></span>
- <span data-ttu-id="bcbff-143">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-143">"\begin{cases}"</span></span>
- <span data-ttu-id="bcbff-144">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-144">"\end{cases}"</span></span>
- <span data-ttu-id="bcbff-145">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="bcbff-145">"\operatorname"</span></span>
- <span data-ttu-id="bcbff-146">"\braket"</span><span class="sxs-lookup"><span data-stu-id="bcbff-146">"\braket"</span></span>
- <span data-ttu-id="bcbff-147">"\id"</span><span class="sxs-lookup"><span data-stu-id="bcbff-147">"\id"</span></span>
- <span data-ttu-id="bcbff-148">"\expect"</span><span class="sxs-lookup"><span data-stu-id="bcbff-148">"\expect"</span></span>
- <span data-ttu-id="bcbff-149">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="bcbff-149">"\defeq"</span></span>
- <span data-ttu-id="bcbff-150">"\variance"</span><span class="sxs-lookup"><span data-stu-id="bcbff-150">"\variance"</span></span>
- <span data-ttu-id="bcbff-151">"\dd"</span><span class="sxs-lookup"><span data-stu-id="bcbff-151">"\dd"</span></span>
- <span data-ttu-id="bcbff-152">"&"</span><span class="sxs-lookup"><span data-stu-id="bcbff-152">"&"</span></span>
- <span data-ttu-id="bcbff-153">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-153">"\begin{align}"</span></span>
- <span data-ttu-id="bcbff-154">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-154">"\end{align}"</span></span>
- <span data-ttu-id="bcbff-155">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="bcbff-155">"\Lambda"</span></span>
- <span data-ttu-id="bcbff-156">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="bcbff-156">"\lambda"</span></span>
- <span data-ttu-id="bcbff-157">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="bcbff-157">"\Omega"</span></span>
- <span data-ttu-id="bcbff-158">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="bcbff-158">"\mathrm"</span></span>
- <span data-ttu-id="bcbff-159">"\left"</span><span class="sxs-lookup"><span data-stu-id="bcbff-159">"\left"</span></span>
- <span data-ttu-id="bcbff-160">"\right"</span><span class="sxs-lookup"><span data-stu-id="bcbff-160">"\right"</span></span>
- <span data-ttu-id="bcbff-161">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="bcbff-161">"\qquad"</span></span>
- <span data-ttu-id="bcbff-162">"\times"</span><span class="sxs-lookup"><span data-stu-id="bcbff-162">"\times"</span></span>
- <span data-ttu-id="bcbff-163">"\big"</span><span class="sxs-lookup"><span data-stu-id="bcbff-163">"\big"</span></span>
- <span data-ttu-id="bcbff-164">"\langle"</span><span class="sxs-lookup"><span data-stu-id="bcbff-164">"\langle"</span></span>
- <span data-ttu-id="bcbff-165">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="bcbff-165">"\rangle"</span></span>
- <span data-ttu-id="bcbff-166">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="bcbff-166">"\bigg"</span></span>
- <span data-ttu-id="bcbff-167">"\Big"</span><span class="sxs-lookup"><span data-stu-id="bcbff-167">"\Big"</span></span>
- <span data-ttu-id="bcbff-168">"|"</span><span class="sxs-lookup"><span data-stu-id="bcbff-168">"|"</span></span>
- <span data-ttu-id="bcbff-169">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="bcbff-169">"\mathbb"</span></span>
- <span data-ttu-id="bcbff-170">"\vec"</span><span class="sxs-lookup"><span data-stu-id="bcbff-170">"\vec"</span></span>
- <span data-ttu-id="bcbff-171">"\in"</span><span class="sxs-lookup"><span data-stu-id="bcbff-171">"\in"</span></span>
- <span data-ttu-id="bcbff-172">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="bcbff-172">"\texttt"</span></span>
- <span data-ttu-id="bcbff-173">"\ne"</span><span class="sxs-lookup"><span data-stu-id="bcbff-173">"\ne"</span></span>
- <span data-ttu-id="bcbff-174">"<"</span><span class="sxs-lookup"><span data-stu-id="bcbff-174">"<"</span></span>
- <span data-ttu-id="bcbff-175">">"</span><span class="sxs-lookup"><span data-stu-id="bcbff-175">">"</span></span>
- <span data-ttu-id="bcbff-176">"\leq"</span><span class="sxs-lookup"><span data-stu-id="bcbff-176">"\leq"</span></span>
- <span data-ttu-id="bcbff-177">"\geq"</span><span class="sxs-lookup"><span data-stu-id="bcbff-177">"\geq"</span></span>
- <span data-ttu-id="bcbff-178">"~~"</span><span class="sxs-lookup"><span data-stu-id="bcbff-178">"~~"</span></span>
- <span data-ttu-id="bcbff-179">"~"</span><span class="sxs-lookup"><span data-stu-id="bcbff-179">"~"</span></span>
- <span data-ttu-id="bcbff-180">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-180">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="bcbff-181">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="bcbff-181">"\end{bmatrix}"</span></span>
- <span data-ttu-id="bcbff-182">"\_"</span><span class="sxs-lookup"><span data-stu-id="bcbff-182">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="bcbff-183">Speciális mátrix-fogalmak</span><span class="sxs-lookup"><span data-stu-id="bcbff-183">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="bcbff-184">Most kiterjesztjük a mátrixok manipulációját a [*Eigenvalues, a Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) és az [*exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) értékekre, amelyek a kvantum-algoritmusok leírásához és megvalósításához szükséges alapvető eszközkészletet alkotnak.</span><span class="sxs-lookup"><span data-stu-id="bcbff-184">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="bcbff-185">Eigenvalues és Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="bcbff-185">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="bcbff-186">Legyen $ $ egy négyzetes mátrix, a $ v pedig $ egy olyan vektor, amely nem az összes nulla vektor (azaz a vektor és az összes bejegyzés értéke $ 0 $ ).</span><span class="sxs-lookup"><span data-stu-id="bcbff-186">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="bcbff-187">Tegyük fel, hogy a $ v $ egy [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) , $ Ha az $ $ MV = CV $ néhány c számú $ $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-187">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="bcbff-188">A $ c érték azt jelenti $ , hogy a [*sajátérték*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) megfelelő a eigenvector $ v $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-188">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="bcbff-189">Az M mátrix általában $ egy $ vektort alakíthat át bármilyen más vektorba, de egy eigenvector speciális, mert változatlan marad, kivéve, ha egy szám megszorozza.</span><span class="sxs-lookup"><span data-stu-id="bcbff-189">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="bcbff-190">Vegye figyelembe, hogy ha $ $ a v egy eigenvector a sajátérték $ c $ -vel, akkor $ $ az AV is egy eigenvector (bármilyen nullától $ $ eltérő), ugyanazzal a sajátérték.</span><span class="sxs-lookup"><span data-stu-id="bcbff-190">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="bcbff-191">Az Identity Matrix esetében például minden vektor $ v $ egy eigenvector, amely sajátérték $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-191">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="bcbff-192">Egy másik Példaként vegyünk egy olyan, a D típusú [*átlós mátrixot*](https://en.wikipedia.org/wiki/Diagonal_matrix) , $ $ amely csak nullától eltérő bejegyzéseket tartalmaz az átlóban:</span><span class="sxs-lookup"><span data-stu-id="bcbff-192">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="bcbff-193">d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="bcbff-193">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="bcbff-194">A vektorok</span><span class="sxs-lookup"><span data-stu-id="bcbff-194">The vectors</span></span>

$$<span data-ttu-id="bcbff-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} és \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="bcbff-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="bcbff-196">Ennek a mátrixnak a eigenvectors a eigenvalues $ d_1 $ , $ d_2 $ és $ d_3 $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-196">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="bcbff-197">Ha $ d_1 $ , $ d_2 $ és $ d_3 $ különböző számok, akkor ezek a vektorok (és azok többszörösei) a d mátrix egyetlen eigenvectors $ $ . Az átlós mátrixok esetében általában könnyen olvasható a eigenvalues és a eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="bcbff-197">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="bcbff-198">A eigenvalues az átlóban megjelenő számok, a hozzájuk tartozó eigenvectors pedig az egység vektorok, amelyek egy bejegyzése $ 1 $ , a fennmaradó bejegyzések pedig 0 értékűek $ $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-198">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="bcbff-199">Vegye figyelembe a fenti példában, hogy a D eigenvectors a $ $ $ 3 $ dimenziós vektorok alapját képezi.</span><span class="sxs-lookup"><span data-stu-id="bcbff-199">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="bcbff-200">Az alap olyan vektorok halmaza, amelyekben a vektorok lineáris kombinációként is írhatók.</span><span class="sxs-lookup"><span data-stu-id="bcbff-200">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="bcbff-201">Explicit módon, $ v_1 $ , $ v_2 $ és $ v_3 formában, $ Ha bármelyik Vector $ v $ $ = a_1 v_1 + a_2 v_2 + a_3 v_3 $ néhány szám $ a_1 $ , $ a_2 $ és a_3 számára $ $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-201">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="bcbff-202">Ne felejtse el, hogy egy Hermitian mátrix (más néven adjoint) egy összetett négyzet alakú mátrix, amely a saját összetett konjugált átültetésével egyenlő, míg az egységes mátrix egy olyan összetett négyzetes mátrix, amelynek az inverze megegyezik a adjoint vagy összetett konjugátum-átültetéssel.</span><span class="sxs-lookup"><span data-stu-id="bcbff-202">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="bcbff-203">A Hermitian és az egységes mátrixok esetében, amelyek lényegében csak egyetlen, a Quantum Computing-ben észlelt mátrixok, egy általános eredmény a [*spektrális tétel*](https://en.wikipedia.org/wiki/Spectral_theorem), amely a következőket állítja be: bármely Hermitian vagy egységes mátrixú $ m esetében $ létezik egy egységes $ U, $ például $ m = u ^ \dagger D u egy $ átlós mátrix d-hez $ $ . Továbbá a D átlós bejegyzései $ $ az M eigenvalues lesznek $ $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-203">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="bcbff-204">Már tudjuk, hogyan számítjuk ki a eigenvalues és a eigenvectors egy átlós mátrix D-ben $ $ . A tétel használatával tudjuk, hogy ha a $ v $ egy eigenvector, $ a $ sajátérték $ c $ , azaz a $ DV = CV, az $ $ U ^ \dagger v $ $ $ a sajátérték c eigenvector lesz $ $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-204">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="bcbff-205">Ennek az az oka, hogy</span><span class="sxs-lookup"><span data-stu-id="bcbff-205">This is because</span></span>

$$<span data-ttu-id="bcbff-206">M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="bcbff-206">M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="bcbff-207">Mátrix exponenciális</span><span class="sxs-lookup"><span data-stu-id="bcbff-207">Matrix Exponentials</span></span>
<span data-ttu-id="bcbff-208">A [*mátrix exponenciális*](https://en.wikipedia.org/wiki/Matrix_exponential) meghatározása pontosan az exponenciális függvényhez hasonlóan is megadható.</span><span class="sxs-lookup"><span data-stu-id="bcbff-208">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="bcbff-209">Az a mátrix exponenciálisa lehet $ a $ következőképpen kifejezve</span><span class="sxs-lookup"><span data-stu-id="bcbff-209">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="bcbff-210">e ^ A = \boldone + a + a \frac { ^ 2 } { 2! } + \frac { ^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="bcbff-210">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="bcbff-211">Ez azért fontos, mert a Quantum Mechanical Time Evolution leírását az $ e ^ { } $ Hermitian Matrix $ B $ .  Emiatt a Matrix exponenciálisok végrehajtása a kvantum-számítástechnika alapvető részét képezi, és a Q # olyan belső rutinokat kínál, amelyek ezeknek a műveleteknek a leírására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="bcbff-211">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="bcbff-212">A mátrix exponenciális felszámításának számos módja van a klasszikus számítógépeken, és általában számszerűen közelíthető meg egy ilyen exponenciális megoldás.</span><span class="sxs-lookup"><span data-stu-id="bcbff-212">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="bcbff-213">Lásd: [*Cleve moleer és Charles van Loan. "Tizenkilenc kétes módszer a mátrix exponenciális kiszámítására." SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) az érintett kihívásokkal kapcsolatos további információkért.</span><span class="sxs-lookup"><span data-stu-id="bcbff-213">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="bcbff-214">A mátrix exponenciális kiszámításának legegyszerűbb módja a mátrix eigenvalues és eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="bcbff-214">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="bcbff-215">Pontosabban, a fentiekben tárgyalt spektrális tétel azt mondja, hogy minden Hermitian vagy egységes mátrixnál $ $ létezik egy egységes mátrix $ U $ és egy átlós mátrix $ d, $ például $ egy = u ^ \dagger D u $ .  A unitarity tulajdonságai miatt $ egy ^ 2 = u ^ d ^ \dagger 2 u $ , és hasonlóképpen bármely Power $ p a $ $ ^ = \dagger $ p u ^ p ^ p u.  Ha ezt a műveletet behelyettesítjük az operátor definíciójában, a következőt kapjuk:</span><span class="sxs-lookup"><span data-stu-id="bcbff-215">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="bcbff-216">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { ! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 0 & \cdots & \\\\ 0 & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="bcbff-216">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="bcbff-217">Más szóval, ha az a mátrix eigenbasis alakítja át a mátrixot, $ $ akkor a mátrix exponenciális értéke a mátrix eigenvalues szokásos exponenciális számításával egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="bcbff-217">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="bcbff-218">A Quantum Computing számos művelete magában foglalja a mátrixok exponenciális használatát, ez a trükk a mátrix eigenbasis való átalakítását mutatja be, amely egyszerűbbé teszi az operátor exponenciális megjelenítését, és számos olyan kvantum-algoritmus mögött található, mint például a Trotter – Suzuki stílusú kvantum-szimulációs módszerek, amelyeket az útmutató későbbi szakaszában ismertetünk.</span><span class="sxs-lookup"><span data-stu-id="bcbff-218">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="bcbff-219">Egy másik hasznos tulajdonság az, ha a $ B $ mind az egységes, mind a Hermitian, azaz $ b = b ^ { -1 } = b ^, \dagger $ majd $ b ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="bcbff-219">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="bcbff-220">Ha ezt a szabályt a mátrix exponenciális kiterjesztésére, valamint a $ \boldone $ és a B kifejezés csoportosítására $ alkalmazza $ , akkor láthatja, hogy bármely valós érték $ x $ az identitás</span><span class="sxs-lookup"><span data-stu-id="bcbff-220">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

$$<span data-ttu-id="bcbff-221">e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="bcbff-221">e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="bcbff-222">rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="bcbff-222">holds.</span></span> <span data-ttu-id="bcbff-223">Ez a trükk különösen hasznos, mivel ez a művelet lehetővé teszi, hogy a mátrix exponenciális értékekkel rendelkezzen, még akkor is, ha a $ b dimenzió $ exponenciálisan nagy méretű, a speciális esetben, ha a $ b az $ egységes és a Hermitian.</span><span class="sxs-lookup"><span data-stu-id="bcbff-223">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
