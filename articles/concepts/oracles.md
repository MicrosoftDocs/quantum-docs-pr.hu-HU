---
<span data-ttu-id="a047d-101">title: Quantum Oracles Description: megtudhatja, hogyan dolgozhat és határozhat meg a Quantum Oracles, Black Box műveleteit, amelyeket egy másik algoritmus bemenetként használ.</span><span class="sxs-lookup"><span data-stu-id="a047d-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="a047d-102">Szerző: cgranade UID: Microsoft. Quantum. Concepts. Oracles MS. Author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 MS. topic: No-Loc:</span><span class="sxs-lookup"><span data-stu-id="a047d-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="a047d-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="a047d-103">"$$"</span></span>
- <span data-ttu-id="a047d-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="a047d-104">"$$"</span></span>
- <span data-ttu-id="a047d-105">"$"</span><span class="sxs-lookup"><span data-stu-id="a047d-105">"$"</span></span>
- <span data-ttu-id="a047d-106">"$"</span><span class="sxs-lookup"><span data-stu-id="a047d-106">"$"</span></span>
- <span data-ttu-id="a047d-107">"$"</span><span class="sxs-lookup"><span data-stu-id="a047d-107">"$"</span></span>
- <span data-ttu-id="a047d-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="a047d-108">"$$"</span></span>
- <span data-ttu-id="a047d-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="a047d-109">"\cdots"</span></span>
- <span data-ttu-id="a047d-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="a047d-110">"bmatrix"</span></span>
- <span data-ttu-id="a047d-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="a047d-111">"\ddots"</span></span>
- <span data-ttu-id="a047d-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="a047d-112">"\equiv"</span></span>
- <span data-ttu-id="a047d-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="a047d-113">"\sum"</span></span>
- <span data-ttu-id="a047d-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="a047d-114">"\begin"</span></span>
- <span data-ttu-id="a047d-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="a047d-115">"\end"</span></span>
- <span data-ttu-id="a047d-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="a047d-116">"\sqrt"</span></span>
- <span data-ttu-id="a047d-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="a047d-117">"\otimes"</span></span>
- <span data-ttu-id="a047d-118">"{"</span><span class="sxs-lookup"><span data-stu-id="a047d-118">"{"</span></span>
- <span data-ttu-id="a047d-119">"}"</span><span class="sxs-lookup"><span data-stu-id="a047d-119">"}"</span></span>
- <span data-ttu-id="a047d-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="a047d-120">"\text"</span></span>
- <span data-ttu-id="a047d-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="a047d-121">"\phi"</span></span>
- <span data-ttu-id="a047d-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="a047d-122">"\kappa"</span></span>
- <span data-ttu-id="a047d-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="a047d-123">"\psi"</span></span>
- <span data-ttu-id="a047d-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="a047d-124">"\alpha"</span></span>
- <span data-ttu-id="a047d-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="a047d-125">"\beta"</span></span>
- <span data-ttu-id="a047d-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="a047d-126">"\gamma"</span></span>
- <span data-ttu-id="a047d-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="a047d-127">"\delta"</span></span>
- <span data-ttu-id="a047d-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="a047d-128">"\omega"</span></span>
- <span data-ttu-id="a047d-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="a047d-129">"\bra"</span></span>
- <span data-ttu-id="a047d-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="a047d-130">"\ket"</span></span>
- <span data-ttu-id="a047d-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="a047d-131">"\boldone"</span></span>
- <span data-ttu-id="a047d-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="a047d-132">"\\\\"</span></span>
- <span data-ttu-id="a047d-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="a047d-133">"\\"</span></span>
- <span data-ttu-id="a047d-134">"="</span><span class="sxs-lookup"><span data-stu-id="a047d-134">"="</span></span>
- <span data-ttu-id="a047d-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="a047d-135">"\frac"</span></span>
- <span data-ttu-id="a047d-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="a047d-136">"\text"</span></span>
- <span data-ttu-id="a047d-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="a047d-137">"\mapsto"</span></span>
- <span data-ttu-id="a047d-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="a047d-138">"\dagger"</span></span>
- <span data-ttu-id="a047d-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="a047d-139">"\to"</span></span>
- <span data-ttu-id="a047d-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="a047d-140">"\begin{cases}"</span></span>
- <span data-ttu-id="a047d-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="a047d-141">"\end{cases}"</span></span>
- <span data-ttu-id="a047d-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="a047d-142">"\operatorname"</span></span>
- <span data-ttu-id="a047d-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="a047d-143">"\braket"</span></span>
- <span data-ttu-id="a047d-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="a047d-144">"\id"</span></span>
- <span data-ttu-id="a047d-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="a047d-145">"\expect"</span></span>
- <span data-ttu-id="a047d-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="a047d-146">"\defeq"</span></span>
- <span data-ttu-id="a047d-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="a047d-147">"\variance"</span></span>
- <span data-ttu-id="a047d-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="a047d-148">"\dd"</span></span>
- <span data-ttu-id="a047d-149">"&"</span><span class="sxs-lookup"><span data-stu-id="a047d-149">"&"</span></span>
- <span data-ttu-id="a047d-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="a047d-150">"\begin{align}"</span></span>
- <span data-ttu-id="a047d-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="a047d-151">"\end{align}"</span></span>
- <span data-ttu-id="a047d-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="a047d-152">"\Lambda"</span></span>
- <span data-ttu-id="a047d-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="a047d-153">"\lambda"</span></span>
- <span data-ttu-id="a047d-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="a047d-154">"\Omega"</span></span>
- <span data-ttu-id="a047d-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="a047d-155">"\mathrm"</span></span>
- <span data-ttu-id="a047d-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="a047d-156">"\left"</span></span>
- <span data-ttu-id="a047d-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="a047d-157">"\right"</span></span>
- <span data-ttu-id="a047d-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="a047d-158">"\qquad"</span></span>
- <span data-ttu-id="a047d-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="a047d-159">"\times"</span></span>
- <span data-ttu-id="a047d-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="a047d-160">"\big"</span></span>
- <span data-ttu-id="a047d-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="a047d-161">"\langle"</span></span>
- <span data-ttu-id="a047d-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="a047d-162">"\rangle"</span></span>
- <span data-ttu-id="a047d-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="a047d-163">"\bigg"</span></span>
- <span data-ttu-id="a047d-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="a047d-164">"\Big"</span></span>
- <span data-ttu-id="a047d-165">"|"</span><span class="sxs-lookup"><span data-stu-id="a047d-165">"|"</span></span>
- <span data-ttu-id="a047d-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="a047d-166">"\mathbb"</span></span>
- <span data-ttu-id="a047d-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="a047d-167">"\vec"</span></span>
- <span data-ttu-id="a047d-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="a047d-168">"\in"</span></span>
- <span data-ttu-id="a047d-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="a047d-169">"\texttt"</span></span>
- <span data-ttu-id="a047d-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="a047d-170">"\ne"</span></span>
- <span data-ttu-id="a047d-171">"<"</span><span class="sxs-lookup"><span data-stu-id="a047d-171">"<"</span></span>
- <span data-ttu-id="a047d-172">">"</span><span class="sxs-lookup"><span data-stu-id="a047d-172">">"</span></span>
- <span data-ttu-id="a047d-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="a047d-173">"\leq"</span></span>
- <span data-ttu-id="a047d-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="a047d-174">"\geq"</span></span>
- <span data-ttu-id="a047d-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="a047d-175">"~~"</span></span>
- <span data-ttu-id="a047d-176">"~"</span><span class="sxs-lookup"><span data-stu-id="a047d-176">"~"</span></span>
- <span data-ttu-id="a047d-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a047d-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="a047d-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a047d-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="a047d-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="a047d-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="a047d-180">Quantum jóslatok</span><span class="sxs-lookup"><span data-stu-id="a047d-180">Quantum Oracles</span></span>

<span data-ttu-id="a047d-181">Az Oracle $ O $ egy "fekete doboz" művelet, amelyet bemenetként használ egy másik algoritmushoz.</span><span class="sxs-lookup"><span data-stu-id="a047d-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="a047d-182">Az ilyen műveletek gyakran az $ f: \\ { 0, 1 \\ } ^ n 0, 1 ^ m klasszikus függvénnyel vannak definiálva, \to \\ { \\ } $ amely egy $ n $ bites bináris bemenetet vesz igénybe, és egy $ m $ bites bináris kimenetet hoz létre.</span><span class="sxs-lookup"><span data-stu-id="a047d-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="a047d-183">Ehhez vegye fontolóra egy adott bináris bemeneti $ x-t = (X_ { 0 } , X_ { 1 } , \dots, X_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="a047d-184">Az qubit-állapotokat $ \ket { \vec { x } } = \ket { X_ { 0 } } \otimes \ket { X_ { 1 } } \otimes \cdots \otimes \ket { X_ { n-1 } } $ értékre lehet felcímkézni.</span><span class="sxs-lookup"><span data-stu-id="a047d-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="a047d-185">Először megpróbáljuk meghatározni az o-t $ $ , hogy az $ o \ket { x } = \ket { f (x) } $ , de ez néhány problémával is rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="a047d-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="a047d-186">Először $ $ is lehet, hogy a bemeneti és kimeneti (n m) értéknek eltérő a mérete $ \ne $ , így az $ O alkalmazása $ megváltoztathatja a regisztrációban lévő qubits számát.</span><span class="sxs-lookup"><span data-stu-id="a047d-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="a047d-187">Másodszor, még ha $ n = m is $ , a függvény nem lehet invertálható: Ha $ f (x) = f (y) $ egy $ x \ne y $ , akkor az $ o \ket { x } = o \ket { y, } $ de $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="a047d-188">Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $ O ^ \dagger $ , és az Oracles-nek hozzá kell adni egy adjoint.</span><span class="sxs-lookup"><span data-stu-id="a047d-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="a047d-189">Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján</span><span class="sxs-lookup"><span data-stu-id="a047d-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="a047d-190">Mindkét problémát felhasználhatjuk egy második m qubits-regisztráció bevezetésével $ $ , hogy megtartsa a választ.</span><span class="sxs-lookup"><span data-stu-id="a047d-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="a047d-191">Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $ x \in \\ { 0, 1 \\ } ^ n $ és $ y \in \\ { 0, 1 \\ } ^ m $ értéknél.</span><span class="sxs-lookup"><span data-stu-id="a047d-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="a047d-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="a047d-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="a047d-193">Most $ o = o ^ \dagger $ by Construction, így mindkét korábbi problémát megoldottuk.</span><span class="sxs-lookup"><span data-stu-id="a047d-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="a047d-194">Ha szeretné látni, hogy o $ = o ^ { \dagger } $ , vegye figyelembe, hogy $ o ^ 2, = \boldone $ mivel $ a \oplus b \oplus b a a = $ $ , b \in \[ ! OP. NO-LOC ({)] 0, 1 \[ ! OP. NEM-LOC (})] $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="a047d-195">Ennek eredményeképpen az $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="a047d-196">Fontos, hogy az Oracle ily módon történő meghatározása az egyes számítási állapotok esetében $ \ket { x } \ket { y azt } $ is meghatározza, hogy az $ O hogyan $ viselkedik bármely más államban.</span><span class="sxs-lookup"><span data-stu-id="a047d-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="a047d-197">Ez azonnal az a tény, hogy az $ O $ , mint az összes kvantum-művelet, lineáris abban az állapotban, amelyben működik.</span><span class="sxs-lookup"><span data-stu-id="a047d-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="a047d-198">Vegye figyelembe a Hadamard műveletet, például: $ h \ket { 0 } = \ket { + } $ és $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="a047d-199">Ha tudni szeretné, hogyan viselkedik $ a h, akkor a $ $ \ket { + } $ $ h $ lineáris,</span><span class="sxs-lookup"><span data-stu-id="a047d-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="a047d-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="a047d-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="a047d-201">= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="a047d-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="a047d-202">Az Oracle O meghatározása esetén $ $ hasonlóképpen használhatjuk azt is, hogy az $ \ket { \psi } $ $ n + m qubits lévő állapotok a $ következőképpen írhatók:</span><span class="sxs-lookup"><span data-stu-id="a047d-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="a047d-203">{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="a047d-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="a047d-204">ahol $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ az állapot együtthatóit jelöli $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="a047d-205">Így</span><span class="sxs-lookup"><span data-stu-id="a047d-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="a047d-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="a047d-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="a047d-207">= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="a047d-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="a047d-208">Jóslatok fázisa</span><span class="sxs-lookup"><span data-stu-id="a047d-208">Phase oracles</span></span>
<span data-ttu-id="a047d-209">Azt is megteheti, $ hogy egy Oracle o-ra kódolja az f- $ t egy $ $ , a bemeneten alapuló _fázis_ alkalmazásával $ $ . Például meghatározhatjuk az O-t, $ $ hogy$$</span><span class="sxs-lookup"><span data-stu-id="a047d-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="a047d-210">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="a047d-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="a047d-211">Ha az Oracle egy fázisban először egy számítási állapotú x-ben működik $ \ket { } $ , akkor ez a fázis globális fázis, ezért nem észlelhető.</span><span class="sxs-lookup"><span data-stu-id="a047d-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="a047d-212">Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="a047d-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="a047d-213">Tegyük fel például, hogy egy fázis Oracle $ $ -O_f az f qubit függvényhez $ $ .</span><span class="sxs-lookup"><span data-stu-id="a047d-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="a047d-214">Majd$$</span><span class="sxs-lookup"><span data-stu-id="a047d-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="a047d-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="a047d-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="a047d-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="a047d-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="a047d-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="a047d-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="a047d-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="a047d-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="a047d-219">=(-1) ^ { f (0) } Z ^ { f (0) – f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="a047d-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="a047d-220">Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.</span><span class="sxs-lookup"><span data-stu-id="a047d-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="a047d-221">Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="a047d-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="a047d-222">A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="a047d-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="a047d-223">További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.</span><span class="sxs-lookup"><span data-stu-id="a047d-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
