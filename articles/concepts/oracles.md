---
<span data-ttu-id="8aded-101">title: Quantum Oracles Description: megtudhatja, hogyan dolgozhat és határozhat meg a Quantum Oracles, Black Box műveleteit, amelyeket egy másik algoritmus bemenetként használ.</span><span class="sxs-lookup"><span data-stu-id="8aded-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="8aded-102">Szerző: cgranade UID: Microsoft. Quantum. Concepts. Oracles MS. Author: chgranad MS. Date: 07/11/2018 MS. topic: No-Loc:</span><span class="sxs-lookup"><span data-stu-id="8aded-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="8aded-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="8aded-103">"Q#"</span></span>
- <span data-ttu-id="8aded-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="8aded-104">"$$v"</span></span>
- <span data-ttu-id="8aded-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="8aded-105">"$$"</span></span>
- <span data-ttu-id="8aded-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="8aded-106">"$$"</span></span>
- <span data-ttu-id="8aded-107">"$"</span><span class="sxs-lookup"><span data-stu-id="8aded-107">"$"</span></span>
- <span data-ttu-id="8aded-108">"$"</span><span class="sxs-lookup"><span data-stu-id="8aded-108">"$"</span></span>
- <span data-ttu-id="8aded-109">"$"</span><span class="sxs-lookup"><span data-stu-id="8aded-109">"$"</span></span>
- <span data-ttu-id="8aded-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="8aded-110">"$$"</span></span>
- <span data-ttu-id="8aded-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="8aded-111">"\cdots"</span></span>
- <span data-ttu-id="8aded-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="8aded-112">"bmatrix"</span></span>
- <span data-ttu-id="8aded-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="8aded-113">"\ddots"</span></span>
- <span data-ttu-id="8aded-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="8aded-114">"\equiv"</span></span>
- <span data-ttu-id="8aded-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="8aded-115">"\sum"</span></span>
- <span data-ttu-id="8aded-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="8aded-116">"\begin"</span></span>
- <span data-ttu-id="8aded-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="8aded-117">"\end"</span></span>
- <span data-ttu-id="8aded-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="8aded-118">"\sqrt"</span></span>
- <span data-ttu-id="8aded-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="8aded-119">"\otimes"</span></span>
- <span data-ttu-id="8aded-120">"{"</span><span class="sxs-lookup"><span data-stu-id="8aded-120">"{"</span></span>
- <span data-ttu-id="8aded-121">"}"</span><span class="sxs-lookup"><span data-stu-id="8aded-121">"}"</span></span>
- <span data-ttu-id="8aded-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="8aded-122">"\text"</span></span>
- <span data-ttu-id="8aded-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="8aded-123">"\phi"</span></span>
- <span data-ttu-id="8aded-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="8aded-124">"\kappa"</span></span>
- <span data-ttu-id="8aded-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="8aded-125">"\psi"</span></span>
- <span data-ttu-id="8aded-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="8aded-126">"\alpha"</span></span>
- <span data-ttu-id="8aded-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="8aded-127">"\beta"</span></span>
- <span data-ttu-id="8aded-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="8aded-128">"\gamma"</span></span>
- <span data-ttu-id="8aded-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="8aded-129">"\delta"</span></span>
- <span data-ttu-id="8aded-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="8aded-130">"\omega"</span></span>
- <span data-ttu-id="8aded-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="8aded-131">"\bra"</span></span>
- <span data-ttu-id="8aded-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="8aded-132">"\ket"</span></span>
- <span data-ttu-id="8aded-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="8aded-133">"\boldone"</span></span>
- <span data-ttu-id="8aded-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="8aded-134">"\\\\"</span></span>
- <span data-ttu-id="8aded-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="8aded-135">"\\"</span></span>
- <span data-ttu-id="8aded-136">"="</span><span class="sxs-lookup"><span data-stu-id="8aded-136">"="</span></span>
- <span data-ttu-id="8aded-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="8aded-137">"\frac"</span></span>
- <span data-ttu-id="8aded-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="8aded-138">"\text"</span></span>
- <span data-ttu-id="8aded-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="8aded-139">"\mapsto"</span></span>
- <span data-ttu-id="8aded-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="8aded-140">"\dagger"</span></span>
- <span data-ttu-id="8aded-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="8aded-141">"\to"</span></span>
- <span data-ttu-id="8aded-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="8aded-142">"\begin{cases}"</span></span>
- <span data-ttu-id="8aded-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="8aded-143">"\end{cases}"</span></span>
- <span data-ttu-id="8aded-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="8aded-144">"\operatorname"</span></span>
- <span data-ttu-id="8aded-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="8aded-145">"\braket"</span></span>
- <span data-ttu-id="8aded-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="8aded-146">"\id"</span></span>
- <span data-ttu-id="8aded-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="8aded-147">"\expect"</span></span>
- <span data-ttu-id="8aded-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="8aded-148">"\defeq"</span></span>
- <span data-ttu-id="8aded-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="8aded-149">"\variance"</span></span>
- <span data-ttu-id="8aded-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="8aded-150">"\dd"</span></span>
- <span data-ttu-id="8aded-151">"&"</span><span class="sxs-lookup"><span data-stu-id="8aded-151">"&"</span></span>
- <span data-ttu-id="8aded-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="8aded-152">"\begin{align}"</span></span>
- <span data-ttu-id="8aded-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="8aded-153">"\end{align}"</span></span>
- <span data-ttu-id="8aded-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="8aded-154">"\Lambda"</span></span>
- <span data-ttu-id="8aded-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="8aded-155">"\lambda"</span></span>
- <span data-ttu-id="8aded-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="8aded-156">"\Omega"</span></span>
- <span data-ttu-id="8aded-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="8aded-157">"\mathrm"</span></span>
- <span data-ttu-id="8aded-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="8aded-158">"\left"</span></span>
- <span data-ttu-id="8aded-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="8aded-159">"\right"</span></span>
- <span data-ttu-id="8aded-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="8aded-160">"\qquad"</span></span>
- <span data-ttu-id="8aded-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="8aded-161">"\times"</span></span>
- <span data-ttu-id="8aded-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="8aded-162">"\big"</span></span>
- <span data-ttu-id="8aded-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="8aded-163">"\langle"</span></span>
- <span data-ttu-id="8aded-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="8aded-164">"\rangle"</span></span>
- <span data-ttu-id="8aded-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="8aded-165">"\bigg"</span></span>
- <span data-ttu-id="8aded-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="8aded-166">"\Big"</span></span>
- <span data-ttu-id="8aded-167">"|"</span><span class="sxs-lookup"><span data-stu-id="8aded-167">"|"</span></span>
- <span data-ttu-id="8aded-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="8aded-168">"\mathbb"</span></span>
- <span data-ttu-id="8aded-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="8aded-169">"\vec"</span></span>
- <span data-ttu-id="8aded-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="8aded-170">"\in"</span></span>
- <span data-ttu-id="8aded-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="8aded-171">"\texttt"</span></span>
- <span data-ttu-id="8aded-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="8aded-172">"\ne"</span></span>
- <span data-ttu-id="8aded-173">"<"</span><span class="sxs-lookup"><span data-stu-id="8aded-173">"<"</span></span>
- <span data-ttu-id="8aded-174">">"</span><span class="sxs-lookup"><span data-stu-id="8aded-174">">"</span></span>
- <span data-ttu-id="8aded-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="8aded-175">"\leq"</span></span>
- <span data-ttu-id="8aded-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="8aded-176">"\geq"</span></span>
- <span data-ttu-id="8aded-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="8aded-177">"~~"</span></span>
- <span data-ttu-id="8aded-178">"~"</span><span class="sxs-lookup"><span data-stu-id="8aded-178">"~"</span></span>
- <span data-ttu-id="8aded-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="8aded-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="8aded-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="8aded-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="8aded-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="8aded-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="8aded-182">Quantum jóslatok</span><span class="sxs-lookup"><span data-stu-id="8aded-182">Quantum Oracles</span></span>

<span data-ttu-id="8aded-183">Az Oracle $ O $ egy "fekete doboz" művelet, amelyet bemenetként használ egy másik algoritmushoz.</span><span class="sxs-lookup"><span data-stu-id="8aded-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="8aded-184">Az ilyen műveletek gyakran az $ f: \\ { 0, 1 \\ } ^ n 0, 1 ^ m klasszikus függvénnyel vannak definiálva, \to \\ { \\ } $ amely egy $ n $ bites bináris bemenetet vesz igénybe, és egy $ m $ bites bináris kimenetet hoz létre.</span><span class="sxs-lookup"><span data-stu-id="8aded-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="8aded-185">Ehhez vegye fontolóra egy adott bináris bemeneti $ x-t = (X_ { 0 } , X_ { 1 } , \dots, X_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="8aded-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="8aded-186">Az qubit-állapotokat $ \ket { \vec { x } } = \ket { X_ { 0 } } \otimes \ket { X_ { 1 } } \otimes \cdots \otimes \ket { X_ { n-1 } } $ értékre lehet felcímkézni.</span><span class="sxs-lookup"><span data-stu-id="8aded-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="8aded-187">Először megpróbáljuk meghatározni az o-t $ $ , hogy az $ o \ket { x } = \ket { f (x) } $ , de ez néhány problémával is rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="8aded-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="8aded-188">Először $ $ is lehet, hogy a bemeneti és kimeneti (n m) értéknek eltérő a mérete $ \ne $ , így az $ O alkalmazása $ megváltoztathatja a regisztrációban lévő qubits számát.</span><span class="sxs-lookup"><span data-stu-id="8aded-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="8aded-189">Másodszor, még ha $ n = m is $ , a függvény nem lehet invertálható: Ha $ f (x) = f (y) $ egy $ x \ne y $ , akkor az $ o \ket { x } = o \ket { y, } $ de $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="8aded-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="8aded-190">Ez azt jelenti, hogy nem tudjuk kialakítani a adjoint műveletet $ O ^ \dagger $ , és az Oracles-nek hozzá kell adni egy adjoint.</span><span class="sxs-lookup"><span data-stu-id="8aded-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="8aded-191">Az Oracle meghatározása a számítási alapú állapotokra gyakorolt hatásuk alapján</span><span class="sxs-lookup"><span data-stu-id="8aded-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="8aded-192">Mindkét problémát felhasználhatjuk egy második m qubits-regisztráció bevezetésével $ $ , hogy megtartsa a választ.</span><span class="sxs-lookup"><span data-stu-id="8aded-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="8aded-193">Ezután definiáljuk az Oracle hatását az összes számítási állapotra: az összes $ x \in \\ { 0, 1 \\ } ^ n $ és $ y \in \\ { 0, 1 \\ } ^ m $ értéknél.</span><span class="sxs-lookup"><span data-stu-id="8aded-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="8aded-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="8aded-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="8aded-195">Most $ o = o ^ \dagger $ by Construction, így mindkét korábbi problémát megoldottuk.</span><span class="sxs-lookup"><span data-stu-id="8aded-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="8aded-196">>Ha szeretné megtekinteni, hogy az o $ = { \dagger } $ $ ^ 2 = \boldone $ $ egy \oplus b \oplus = , b:: $ $ \in \: No-Loc ({)::: 0, 1 \: :: No-Loc (}) $ :::.</span><span class="sxs-lookup"><span data-stu-id="8aded-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="8aded-197">>Ennek eredményeképpen az $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="8aded-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="8aded-198">Fontos, hogy az Oracle ily módon történő meghatározása az egyes számítási állapotok esetében $ \ket { x } \ket { y azt } $ is meghatározza, hogy az $ O hogyan $ viselkedik bármely más államban.</span><span class="sxs-lookup"><span data-stu-id="8aded-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="8aded-199">Ez azonnal az a tény, hogy az $ O $ , mint az összes kvantum-művelet, lineáris abban az állapotban, amelyben működik.</span><span class="sxs-lookup"><span data-stu-id="8aded-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="8aded-200">Vegye figyelembe a Hadamard műveletet, például: $ h \ket { 0 } = \ket { + } $ és $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="8aded-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="8aded-201">Ha tudni szeretné, hogyan viselkedik $ a h, akkor a $ $ \ket { + } $ $ h $ lineáris,</span><span class="sxs-lookup"><span data-stu-id="8aded-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="8aded-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="8aded-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="8aded-203">&= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="8aded-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="8aded-204">Az Oracle O meghatározása esetén $ $ hasonlóképpen használhatjuk azt is, hogy az $ \ket { \psi } $ $ n + m qubits lévő állapotok a $ következőképpen írhatók:</span><span class="sxs-lookup"><span data-stu-id="8aded-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="8aded-205">\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="8aded-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="8aded-206">ahol $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ az állapot együtthatóit jelöli $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="8aded-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="8aded-207">Így</span><span class="sxs-lookup"><span data-stu-id="8aded-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="8aded-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="8aded-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="8aded-209">&= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="8aded-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="8aded-210">Jóslatok fázisa</span><span class="sxs-lookup"><span data-stu-id="8aded-210">Phase oracles</span></span>
<span data-ttu-id="8aded-211">Azt is megteheti, $ hogy egy Oracle o-ra kódolja az f- $ t egy $ $ , a bemeneten alapuló _fázis_ alkalmazásával $ $ . Például meghatározhatjuk az O-t, $ $ hogy $$</span><span class="sxs-lookup"><span data-stu-id="8aded-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="8aded-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="8aded-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="8aded-213">Ha az Oracle egy fázisban először egy számítási állapotú x-ben működik $ \ket { } $ , akkor ez a fázis globális fázis, ezért nem észlelhető.</span><span class="sxs-lookup"><span data-stu-id="8aded-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="8aded-214">Az Oracle azonban nagyon nagy teljesítményű erőforrás lehet, ha egy vagy több helyre, vagy ellenőrzött műveletre alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="8aded-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="8aded-215">Tegyük fel például, hogy egy fázis Oracle $ $ -O_f az f qubit függvényhez $ $ .</span><span class="sxs-lookup"><span data-stu-id="8aded-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="8aded-216">Majd $$</span><span class="sxs-lookup"><span data-stu-id="8aded-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="8aded-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="8aded-217">O_f \ket{+}</span></span>
        <span data-ttu-id="8aded-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="8aded-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="8aded-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="8aded-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="8aded-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="8aded-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="8aded-221">&=(-1) ^ { f (0) } Z ^ { f (0) – f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="8aded-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="8aded-222">Általánosságban az Oracle-nézetek mindkét nézete kibővíthető úgy, hogy olyan klasszikus függvényeket képviselje, amelyek valódi számokat adnak vissza csak egyetlen bit helyett.</span><span class="sxs-lookup"><span data-stu-id="8aded-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="8aded-223">Az Oracle megvalósításának legjobb módja, ha az Oracle-t egy adott algoritmuson belül szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="8aded-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="8aded-224">A [Deutsch-Józsa algoritmus](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) például az első módon megvalósított Oracle-re támaszkodik, míg a a (z) a következő módon az Oracle által megvalósított [algoritmusra](https://en.wikipedia.org/wiki/Grover's_algorithm) támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="8aded-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="8aded-225">További részletekért ajánljuk a [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)-ben folytatott vitát.</span><span class="sxs-lookup"><span data-stu-id="8aded-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
