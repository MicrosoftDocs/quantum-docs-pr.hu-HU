---
<span data-ttu-id="a3459-101">title: vektorok és mátrixok a kvantum-számítástechnikai leírásban: megismerheti a vektorok és mátrixok használatának alapjait.</span><span class="sxs-lookup"><span data-stu-id="a3459-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="a3459-102">Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. vectors MS. Author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuális No-Loc:</span><span class="sxs-lookup"><span data-stu-id="a3459-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="a3459-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="a3459-103">"Q#"</span></span>
- <span data-ttu-id="a3459-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="a3459-104">"$$v"</span></span>
- <span data-ttu-id="a3459-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="a3459-105">"$$"</span></span>
- <span data-ttu-id="a3459-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="a3459-106">"$$"</span></span>
- <span data-ttu-id="a3459-107">"$"</span><span class="sxs-lookup"><span data-stu-id="a3459-107">"$"</span></span>
- <span data-ttu-id="a3459-108">"$"</span><span class="sxs-lookup"><span data-stu-id="a3459-108">"$"</span></span>
- <span data-ttu-id="a3459-109">"$"</span><span class="sxs-lookup"><span data-stu-id="a3459-109">"$"</span></span>
- <span data-ttu-id="a3459-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="a3459-110">"$$"</span></span>
- <span data-ttu-id="a3459-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="a3459-111">"\cdots"</span></span>
- <span data-ttu-id="a3459-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="a3459-112">"bmatrix"</span></span>
- <span data-ttu-id="a3459-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="a3459-113">"\ddots"</span></span>
- <span data-ttu-id="a3459-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="a3459-114">"\equiv"</span></span>
- <span data-ttu-id="a3459-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="a3459-115">"\sum"</span></span>
- <span data-ttu-id="a3459-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="a3459-116">"\begin"</span></span>
- <span data-ttu-id="a3459-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="a3459-117">"\end"</span></span>
- <span data-ttu-id="a3459-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="a3459-118">"\sqrt"</span></span>
- <span data-ttu-id="a3459-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="a3459-119">"\otimes"</span></span>
- <span data-ttu-id="a3459-120">"{"</span><span class="sxs-lookup"><span data-stu-id="a3459-120">"{"</span></span>
- <span data-ttu-id="a3459-121">"}"</span><span class="sxs-lookup"><span data-stu-id="a3459-121">"}"</span></span>
- <span data-ttu-id="a3459-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="a3459-122">"\text"</span></span>
- <span data-ttu-id="a3459-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="a3459-123">"\phi"</span></span>
- <span data-ttu-id="a3459-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="a3459-124">"\kappa"</span></span>
- <span data-ttu-id="a3459-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="a3459-125">"\psi"</span></span>
- <span data-ttu-id="a3459-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="a3459-126">"\alpha"</span></span>
- <span data-ttu-id="a3459-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="a3459-127">"\beta"</span></span>
- <span data-ttu-id="a3459-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="a3459-128">"\gamma"</span></span>
- <span data-ttu-id="a3459-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="a3459-129">"\delta"</span></span>
- <span data-ttu-id="a3459-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="a3459-130">"\omega"</span></span>
- <span data-ttu-id="a3459-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="a3459-131">"\bra"</span></span>
- <span data-ttu-id="a3459-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="a3459-132">"\ket"</span></span>
- <span data-ttu-id="a3459-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="a3459-133">"\boldone"</span></span>
- <span data-ttu-id="a3459-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="a3459-134">"\\\\"</span></span>
- <span data-ttu-id="a3459-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="a3459-135">"\\"</span></span>
- <span data-ttu-id="a3459-136">"="</span><span class="sxs-lookup"><span data-stu-id="a3459-136">"="</span></span>
- <span data-ttu-id="a3459-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="a3459-137">"\frac"</span></span>
- <span data-ttu-id="a3459-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="a3459-138">"\text"</span></span>
- <span data-ttu-id="a3459-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="a3459-139">"\mapsto"</span></span>
- <span data-ttu-id="a3459-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="a3459-140">"\dagger"</span></span>
- <span data-ttu-id="a3459-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="a3459-141">"\to"</span></span>
- <span data-ttu-id="a3459-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="a3459-142">"\begin{cases}"</span></span>
- <span data-ttu-id="a3459-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="a3459-143">"\end{cases}"</span></span>
- <span data-ttu-id="a3459-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="a3459-144">"\operatorname"</span></span>
- <span data-ttu-id="a3459-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="a3459-145">"\braket"</span></span>
- <span data-ttu-id="a3459-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="a3459-146">"\id"</span></span>
- <span data-ttu-id="a3459-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="a3459-147">"\expect"</span></span>
- <span data-ttu-id="a3459-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="a3459-148">"\defeq"</span></span>
- <span data-ttu-id="a3459-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="a3459-149">"\variance"</span></span>
- <span data-ttu-id="a3459-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="a3459-150">"\dd"</span></span>
- <span data-ttu-id="a3459-151">"&"</span><span class="sxs-lookup"><span data-stu-id="a3459-151">"&"</span></span>
- <span data-ttu-id="a3459-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="a3459-152">"\begin{align}"</span></span>
- <span data-ttu-id="a3459-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="a3459-153">"\end{align}"</span></span>
- <span data-ttu-id="a3459-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="a3459-154">"\Lambda"</span></span>
- <span data-ttu-id="a3459-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="a3459-155">"\lambda"</span></span>
- <span data-ttu-id="a3459-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="a3459-156">"\Omega"</span></span>
- <span data-ttu-id="a3459-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="a3459-157">"\mathrm"</span></span>
- <span data-ttu-id="a3459-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="a3459-158">"\left"</span></span>
- <span data-ttu-id="a3459-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="a3459-159">"\right"</span></span>
- <span data-ttu-id="a3459-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="a3459-160">"\qquad"</span></span>
- <span data-ttu-id="a3459-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="a3459-161">"\times"</span></span>
- <span data-ttu-id="a3459-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="a3459-162">"\big"</span></span>
- <span data-ttu-id="a3459-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="a3459-163">"\langle"</span></span>
- <span data-ttu-id="a3459-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="a3459-164">"\rangle"</span></span>
- <span data-ttu-id="a3459-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="a3459-165">"\bigg"</span></span>
- <span data-ttu-id="a3459-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="a3459-166">"\Big"</span></span>
- <span data-ttu-id="a3459-167">"|"</span><span class="sxs-lookup"><span data-stu-id="a3459-167">"|"</span></span>
- <span data-ttu-id="a3459-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="a3459-168">"\mathbb"</span></span>
- <span data-ttu-id="a3459-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="a3459-169">"\vec"</span></span>
- <span data-ttu-id="a3459-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="a3459-170">"\in"</span></span>
- <span data-ttu-id="a3459-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="a3459-171">"\texttt"</span></span>
- <span data-ttu-id="a3459-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="a3459-172">"\ne"</span></span>
- <span data-ttu-id="a3459-173">"<"</span><span class="sxs-lookup"><span data-stu-id="a3459-173">"<"</span></span>
- <span data-ttu-id="a3459-174">">"</span><span class="sxs-lookup"><span data-stu-id="a3459-174">">"</span></span>
- <span data-ttu-id="a3459-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="a3459-175">"\leq"</span></span>
- <span data-ttu-id="a3459-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="a3459-176">"\geq"</span></span>
- <span data-ttu-id="a3459-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="a3459-177">"~~"</span></span>
- <span data-ttu-id="a3459-178">"~"</span><span class="sxs-lookup"><span data-stu-id="a3459-178">"~"</span></span>
- <span data-ttu-id="a3459-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a3459-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="a3459-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a3459-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="a3459-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="a3459-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="a3459-182">Vektorok és mátrixok</span><span class="sxs-lookup"><span data-stu-id="a3459-182">Vectors and Matrices</span></span>

<span data-ttu-id="a3459-183">A kvantum-számítástechnika megismeréséhez elengedhetetlen a vektorok és mátrixok megismerése.</span><span class="sxs-lookup"><span data-stu-id="a3459-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="a3459-184">Egy rövid bevezetést biztosítunk, és az érdekelt olvasóknak javasoljuk, hogy szabványos referenciát olvassanak a lineáris algebra, például a *furcsa, a G (1993) számára. A lineáris algebra bemutatása (Vol. 3). Wellesley, MA: Wellesley-Cambridge megnyomni* vagy online referenciát, például [lineáris algebra](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="a3459-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="a3459-185">A dimenzió (vagy a méret) n egy oszlop vektora (vagy egy egyszerű [*vektora*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ $ $ $ egy $ $ oszlopként rendezett, n komplex szám $ (v_1, v_2, \ldots, v_n) gyűjteménye $ :</span><span class="sxs-lookup"><span data-stu-id="a3459-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="a3459-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="a3459-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-187">v_1\\\\</span></span>
<span data-ttu-id="a3459-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-188">v_2\\\\</span></span>
<span data-ttu-id="a3459-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-189">\vdots\\\\</span></span>
<span data-ttu-id="a3459-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="a3459-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="a3459-191">A Vector v szabványa $ a $ következőképpen van definiálva: $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="a3459-192">A vektorok egység normának számítanak (vagy más néven [*egység vektornak*](https://en.wikipedia.org/wiki/Unit_vector)nevezik), ha a norma értéke $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="a3459-193">A [*vektoros v adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ a $ $ v ^ \dagger $ -t jelöli, és a következő sor-vektorra van beállítva $ \* $ , amely a komplex konjugátumot jelöli.</span><span class="sxs-lookup"><span data-stu-id="a3459-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="a3459-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="a3459-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="a3459-195">A két vektor együttes összeszorzásának leggyakoribb módja a [*belső termék*](https://en.wikipedia.org/wiki/Inner_product_space), más néven a dot termék.</span><span class="sxs-lookup"><span data-stu-id="a3459-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="a3459-196">A belső termék lehetővé teszi egy vektor kivetítését egy másikra, és felbecsülhetetlen értékű, hogy leírja, hogyan lehet egy vektort más egyszerűbb vektorok összegével kifejezni.</span><span class="sxs-lookup"><span data-stu-id="a3459-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="a3459-197">Az $ u $ és $ v közötti $ $ \left \langle \right \rangle $ belső termék az u és v</span><span class="sxs-lookup"><span data-stu-id="a3459-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="a3459-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="a3459-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="a3459-199">Ez a jelölés azt is lehetővé teszi, hogy a Vector v szabványa $ $ $ \sqrt { \langle v, v \rangle } $ formában legyen megírva.</span><span class="sxs-lookup"><span data-stu-id="a3459-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="a3459-200">Egy c számú vektort is használhatunk egy olyan új vektor létrehozásához, $ $ amelynek a bejegyzései a c értékkel vannak megszorozva $ $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="a3459-201">Az u és v két vektort is hozzáadhat $ $ $ $ egy olyan új vektor létrehozásához, amelynek bejegyzései az $ u $ és v bejegyzéseinek összege $ $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="a3459-202">Ezek a műveletek az alábbi ábrán láthatók:</span><span class="sxs-lookup"><span data-stu-id="a3459-202">These operations are depicted below:</span></span>

<span data-ttu-id="a3459-203">$$\mathrm{Ha } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="a3459-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-204">u_1\\\\</span></span>
<span data-ttu-id="a3459-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-205">u_2\\\\</span></span>
<span data-ttu-id="a3459-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-206">\vdots\\\\</span></span>
<span data-ttu-id="a3459-207">u_n \end{bmatrix} ~ \mathrm { és}~</span><span class="sxs-lookup"><span data-stu-id="a3459-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="a3459-208">v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="a3459-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-209">v_1\\\\</span></span>
    <span data-ttu-id="a3459-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-210">v_2\\\\</span></span>
    <span data-ttu-id="a3459-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-211">\vdots\\\\</span></span>
    <span data-ttu-id="a3459-212">v_n \end{bmatrix} , ~ \mathrm { majd}~</span><span class="sxs-lookup"><span data-stu-id="a3459-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="a3459-213">Au + BV =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="a3459-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="a3459-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="a3459-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-216">\vdots\\\\</span></span>
<span data-ttu-id="a3459-217">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="a3459-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="a3459-218">Az [](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $ m n méretű mátrix \times $ egy olyan MN komplex számokból álló gyűjtemény, amelyeknek $ az értéke $ $ m $ és n oszlopban van rendezve $ $ , ahogy az alábbi ábrán látható:</span><span class="sxs-lookup"><span data-stu-id="a3459-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="a3459-219">$$M =</span><span class="sxs-lookup"><span data-stu-id="a3459-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="a3459-220">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="a3459-221">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="a3459-222">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="a3459-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="a3459-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="a3459-224">Vegye figyelembe, hogy az n dimenzió vektora $ $ egyszerűen az $ n 1 méretű mátrix \times $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="a3459-225">Csakúgy, mint a vektorok esetében, egy c számú mátrixot is használhatunk egy olyan $ $ új mátrix beszerzéséhez, ahol minden egyes bejegyzés a c értékkel van megszorozva $ $ , és két mátrixot is hozzáadhat egy olyan új mátrix létrehozásához, amelynek bejegyzései a két mátrix megfelelő bejegyzéseinek összege.</span><span class="sxs-lookup"><span data-stu-id="a3459-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="a3459-226">Mátrix – szorzási és a tenser-termékek</span><span class="sxs-lookup"><span data-stu-id="a3459-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="a3459-227">A n p dimenzióval rendelkező, m n és n dimenziót tartalmazó két mátrixot is szorozzuk $ $ $ \times $ $ $ $ \times $ kell, hogy egy új, m p-es mátrixot kapjon a $ $ $ \times $ következő módon:</span><span class="sxs-lookup"><span data-stu-id="a3459-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="a3459-228">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="a3459-229">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="a3459-230">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}</span><span class="sxs-lookup"><span data-stu-id="a3459-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="a3459-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="a3459-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="a3459-233">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="a3459-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="a3459-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="a3459-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="a3459-236">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}</span><span class="sxs-lookup"><span data-stu-id="a3459-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="a3459-237">ahol a $ P bejegyzéseinek $ $ P_ { ik } = \sum _j M_ { ij } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="a3459-238">Például a $ P_ 11 bejegyzés a { } $ N első sorának belső terméke, $ $ amely az első oszlop $ $ . Vegye figyelembe, hogy mivel a vektor egyszerűen egy mátrix speciális esete, ez a definíció a mátrix-vektoros szorzásra terjed ki.</span><span class="sxs-lookup"><span data-stu-id="a3459-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="a3459-239">A rendszer az összes olyan mátrixot felveszi, amely a sorok és oszlopok száma, illetve a vektorok, amelyek csak $ 1 oszlopnak felelnek meg $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="a3459-240">Egy speciális négyzetes mátrix az [*azonosító mátrix*](https://en.wikipedia.org/wiki/Identity_matrix), $ \boldone $ amely az összes átlós elemmel egyenlő 1 értékkel, $ $ a többi elem pedig $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="a3459-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="a3459-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="a3459-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="a3459-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="a3459-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="a3459-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="a3459-245">Az a négyzetes mátrix esetében $ $ mondjuk, hogy a $ B mátrix a $ saját [*inverze*](https://en.wikipedia.org/wiki/Invertible_matrix) , ha $ AB = ba = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="a3459-246">A mátrix inverzének nem kell léteznie, de ha létezik, egyedi, és $ egy ^-1 jelölést jelölünk { } $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="a3459-247">Az m mátrix $ $ adjoint vagy a konjugátum átültetése $ egy olyan $ mátrix, $ $ amely $ N_ { ij } = M_ { Ji } ^ \* $ -t tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a3459-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="a3459-248">Az m adjoint $ $ általában az m ^ jelöli $ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="a3459-249">Tegyük fel, hogy a mátrix $ u egy $ [*egységes*](https://en.wikipedia.org/wiki/Unitary_matrix) $ , ha uu ^ \dagger = u ^ \dagger u = \boldone $ vagy azzal egyenértékű, $ u ^ { -1 } = u ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="a3459-250">Az egységes mátrixok legfontosabb tulajdonsága az, hogy megőrzik a vektorok normáit.</span><span class="sxs-lookup"><span data-stu-id="a3459-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="a3459-251">Ez azért történik, mert</span><span class="sxs-lookup"><span data-stu-id="a3459-251">This happens because</span></span> 

<span data-ttu-id="a3459-252">$$\langlev, v \rangle = v ^ \dagger v ^ = u ^ \dagger { -1 } u v = v ^ \dagger u ^ \dagger u v = \langle u, u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="a3459-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="a3459-253">Az $ m mátrix $ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , ha $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="a3459-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="a3459-254">Végezetül, a kétféle, m n és n méretű, a p-s mérettel rendelkező két mátrixos [*termék (vagy*](https://en.wikipedia.org/wiki/Tensor_product) Kronecker-termék) $ $ $ \times $ $ $ $ \times $ nagyobb $ = \otimes $ $ , mint az MP NQ, a mérete pedig \times $ $ m $ és $ n $ , amely az alábbiak szerint érhető el:</span><span class="sxs-lookup"><span data-stu-id="a3459-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="a3459-255">M \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="a3459-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="a3459-256">M_ { 11 } ~~ \cdots ~~ M_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="a3459-257">M_ { M1 } ~~ \cdots ~~ M_ { MN  }</span><span class="sxs-lookup"><span data-stu-id="a3459-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="a3459-258">N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ  }\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="a3459-259">N_ { P1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="a3459-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="a3459-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="a3459-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="a3459-261">M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="a3459-262">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="a3459-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="a3459-263">M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1NÉ } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="a3459-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="a3459-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="a3459-265">Ez jobban szemlélteti néhány példát:</span><span class="sxs-lookup"><span data-stu-id="a3459-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="a3459-266">\\\\b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="a3459-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="a3459-267">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="a3459-268">\\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="a3459-269">=\begin{bmatrix}a c \\\\ a d \\\\ a e \\\\ b c \\\\ d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="a3459-270">és</span><span class="sxs-lookup"><span data-stu-id="a3459-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="a3459-271">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="a3459-272">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="a3459-273">egy\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="a3459-274">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a3459-275">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="a3459-276">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a3459-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="a3459-278">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a3459-279">d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="a3459-280">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a3459-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="a3459-281">AK \ AF \ be \ BF \\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="a3459-282">AG \ ah \ BG \ BH \\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="a3459-283">CE \ CF \ de \ DF \\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="a3459-284">CG \ CH \ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="a3459-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="a3459-285">A legtöbbet a következő, a TEN-termékekkel kapcsolatos utolsó hasznos jelölési konvenció az, hogy bármely vektoros $ v $ -vagy mátrix $ $ -m, $ v ^ { \otimes n } $ vagy $ M ^ { \otimes n } $ rövid kéz egy $ n $ -szor ismétlődő tenser termékhez.</span><span class="sxs-lookup"><span data-stu-id="a3459-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="a3459-286">Például:</span><span class="sxs-lookup"><span data-stu-id="a3459-286">For example:</span></span>

\begin{align}
<span data-ttu-id="a3459-287">&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ – 1 \end{bmatrix} ^ { \otimes 2 1 – 1 } = \begin{bmatrix} \\\\ \\\\ – 1 \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="a3459-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="a3459-288">&\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 0 1 0 } = \begin{bmatrix} & \\\\ & \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 2 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & 1 0 0 \\\\ & & 1 0 0 & \\\\ & 1 0 0 1 & & \\\\ & & & \end{bmatrix} 0 0.</span><span class="sxs-lookup"><span data-stu-id="a3459-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
