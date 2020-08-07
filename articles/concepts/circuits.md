---
<span data-ttu-id="5a6b3-101">title: kvantum-áramkörök leírása: megtudhatja, hogyan ábrázolhat egyszerű és összetett kvantum-műveleteket a kvantum-diagramok használatával.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="5a6b3-102">Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. áramkörök MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: No-Loc:</span><span class="sxs-lookup"><span data-stu-id="5a6b3-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="5a6b3-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-103">"Q#"</span></span>
- <span data-ttu-id="5a6b3-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-104">"$$v"</span></span>
- <span data-ttu-id="5a6b3-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-105">"$$"</span></span>
- <span data-ttu-id="5a6b3-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-106">"$$"</span></span>
- <span data-ttu-id="5a6b3-107">"$"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-107">"$"</span></span>
- <span data-ttu-id="5a6b3-108">"$"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-108">"$"</span></span>
- <span data-ttu-id="5a6b3-109">"$"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-109">"$"</span></span>
- <span data-ttu-id="5a6b3-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-110">"$$"</span></span>
- <span data-ttu-id="5a6b3-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-111">"\cdots"</span></span>
- <span data-ttu-id="5a6b3-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-112">"bmatrix"</span></span>
- <span data-ttu-id="5a6b3-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-113">"\ddots"</span></span>
- <span data-ttu-id="5a6b3-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-114">"\equiv"</span></span>
- <span data-ttu-id="5a6b3-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-115">"\sum"</span></span>
- <span data-ttu-id="5a6b3-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-116">"\begin"</span></span>
- <span data-ttu-id="5a6b3-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-117">"\end"</span></span>
- <span data-ttu-id="5a6b3-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-118">"\sqrt"</span></span>
- <span data-ttu-id="5a6b3-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-119">"\otimes"</span></span>
- <span data-ttu-id="5a6b3-120">"{"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-120">"{"</span></span>
- <span data-ttu-id="5a6b3-121">"}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-121">"}"</span></span>
- <span data-ttu-id="5a6b3-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-122">"\text"</span></span>
- <span data-ttu-id="5a6b3-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-123">"\phi"</span></span>
- <span data-ttu-id="5a6b3-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-124">"\kappa"</span></span>
- <span data-ttu-id="5a6b3-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-125">"\psi"</span></span>
- <span data-ttu-id="5a6b3-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-126">"\alpha"</span></span>
- <span data-ttu-id="5a6b3-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-127">"\beta"</span></span>
- <span data-ttu-id="5a6b3-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-128">"\gamma"</span></span>
- <span data-ttu-id="5a6b3-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-129">"\delta"</span></span>
- <span data-ttu-id="5a6b3-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-130">"\omega"</span></span>
- <span data-ttu-id="5a6b3-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-131">"\bra"</span></span>
- <span data-ttu-id="5a6b3-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-132">"\ket"</span></span>
- <span data-ttu-id="5a6b3-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-133">"\boldone"</span></span>
- <span data-ttu-id="5a6b3-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-134">"\\\\"</span></span>
- <span data-ttu-id="5a6b3-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-135">"\\"</span></span>
- <span data-ttu-id="5a6b3-136">"="</span><span class="sxs-lookup"><span data-stu-id="5a6b3-136">"="</span></span>
- <span data-ttu-id="5a6b3-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-137">"\frac"</span></span>
- <span data-ttu-id="5a6b3-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-138">"\text"</span></span>
- <span data-ttu-id="5a6b3-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-139">"\mapsto"</span></span>
- <span data-ttu-id="5a6b3-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-140">"\dagger"</span></span>
- <span data-ttu-id="5a6b3-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-141">"\to"</span></span>
- <span data-ttu-id="5a6b3-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-142">"\begin{cases}"</span></span>
- <span data-ttu-id="5a6b3-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-143">"\end{cases}"</span></span>
- <span data-ttu-id="5a6b3-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-144">"\operatorname"</span></span>
- <span data-ttu-id="5a6b3-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-145">"\braket"</span></span>
- <span data-ttu-id="5a6b3-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-146">"\id"</span></span>
- <span data-ttu-id="5a6b3-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-147">"\expect"</span></span>
- <span data-ttu-id="5a6b3-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-148">"\defeq"</span></span>
- <span data-ttu-id="5a6b3-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-149">"\variance"</span></span>
- <span data-ttu-id="5a6b3-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-150">"\dd"</span></span>
- <span data-ttu-id="5a6b3-151">"&"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-151">"&"</span></span>
- <span data-ttu-id="5a6b3-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-152">"\begin{align}"</span></span>
- <span data-ttu-id="5a6b3-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-153">"\end{align}"</span></span>
- <span data-ttu-id="5a6b3-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-154">"\Lambda"</span></span>
- <span data-ttu-id="5a6b3-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-155">"\lambda"</span></span>
- <span data-ttu-id="5a6b3-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-156">"\Omega"</span></span>
- <span data-ttu-id="5a6b3-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-157">"\mathrm"</span></span>
- <span data-ttu-id="5a6b3-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-158">"\left"</span></span>
- <span data-ttu-id="5a6b3-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-159">"\right"</span></span>
- <span data-ttu-id="5a6b3-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-160">"\qquad"</span></span>
- <span data-ttu-id="5a6b3-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-161">"\times"</span></span>
- <span data-ttu-id="5a6b3-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-162">"\big"</span></span>
- <span data-ttu-id="5a6b3-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-163">"\langle"</span></span>
- <span data-ttu-id="5a6b3-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-164">"\rangle"</span></span>
- <span data-ttu-id="5a6b3-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-165">"\bigg"</span></span>
- <span data-ttu-id="5a6b3-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-166">"\Big"</span></span>
- <span data-ttu-id="5a6b3-167">"|"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-167">"|"</span></span>
- <span data-ttu-id="5a6b3-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-168">"\mathbb"</span></span>
- <span data-ttu-id="5a6b3-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-169">"\vec"</span></span>
- <span data-ttu-id="5a6b3-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-170">"\in"</span></span>
- <span data-ttu-id="5a6b3-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-171">"\texttt"</span></span>
- <span data-ttu-id="5a6b3-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-172">"\ne"</span></span>
- <span data-ttu-id="5a6b3-173">"<"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-173">"<"</span></span>
- <span data-ttu-id="5a6b3-174">">"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-174">">"</span></span>
- <span data-ttu-id="5a6b3-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-175">"\leq"</span></span>
- <span data-ttu-id="5a6b3-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-176">"\geq"</span></span>
- <span data-ttu-id="5a6b3-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-177">"~~"</span></span>
- <span data-ttu-id="5a6b3-178">"~"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-178">"~"</span></span>
- <span data-ttu-id="5a6b3-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="5a6b3-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="5a6b3-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="5a6b3-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="5a6b3-182">Kvantum-áramkörök</span><span class="sxs-lookup"><span data-stu-id="5a6b3-182">Quantum Circuits</span></span>
<span data-ttu-id="5a6b3-183">Vegyünk egy pillanatra az egységes átalakítás $ \text { cnem } _ { 01 } (H \otimes 1) $ .</span><span class="sxs-lookup"><span data-stu-id="5a6b3-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="5a6b3-184">Ez a kapui sorozat alapvető jelentőséggel bír a kvantum-számítástechnika szempontjából, mivel a két qubit állapotot hozza létre:</span><span class="sxs-lookup"><span data-stu-id="5a6b3-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="5a6b3-185">$$\mathrm{Cnem } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right ),$$</span><span class="sxs-lookup"><span data-stu-id="5a6b3-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="5a6b3-186">Az ezzel vagy nagyobb bonyolultsággal rendelkező műveletek a kvantum-algoritmusokban és a kvantum-hibák kijavításában mindenütt elérhetők, ezért nagy mértékű feltételnek kell lennie, hogy a vizualizációk *egy egyszerű*metódust használjanak.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="5a6b3-187">A maximálisan kusza kvantum-állapot előkészítésének áramköri diagramja a következő:</span><span class="sxs-lookup"><span data-stu-id="5a6b3-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="5a6b3-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="5a6b3-189"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-190">![Áramköri diagram maximálisan összekeverhető kétqubit állapothoz](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="5a6b3-191">A Quantum Circuit diagram konvenciói</span><span class="sxs-lookup"><span data-stu-id="5a6b3-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="5a6b3-192">A kvantum-műveletek vizuális nyelve könnyebben emészthető, mint a kvantum-kör kifejezésére vonatkozó konvenciók megismerése.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="5a6b3-193">Az alábbi konvenciókat tekintjük át.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-193">We review these conventions below.</span></span>

<span data-ttu-id="5a6b3-194">Egy áramköri diagramon minden egyes folytonos vonal egy qubit vagy általánosabban qubit-regisztrációt ábrázol.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="5a6b3-195">Az egyezmény szerint a felső sor a qubit regiszter $ 0, $ a többi pedig szekvenciálisan van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="5a6b3-196">A fenti példában szereplő áramkör két qubits (vagy egy qubit álló, egymással egyenértékű két regiszterből áll) való működésként van ábrázolva.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="5a6b3-197">Az egy vagy több qubit-regiszteren eljáró kapuk mezőként vannak kijelölve.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="5a6b3-198">Például a szimbólum</span><span class="sxs-lookup"><span data-stu-id="5a6b3-198">For example, the symbol</span></span>

<span data-ttu-id="5a6b3-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="5a6b3-200"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-201">![Egy qubit-regiszteren működő Hadamard művelet szimbóluma](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="5a6b3-202">egy qubit-regisztráción alapuló [Hadamard](xref:microsoft.quantum.intrinsic.h) művelet.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-202">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="5a6b3-203">A Quantum Gates kronológiai sorrendben vannak rendezve a bal szélső kapuval, amelyet a kapu először alkalmaz a qubits.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="5a6b3-204">Más szóval, ha a vezetékeket a kvantum-állapot tárolásával ábrázolja, a vezetékek a diagram minden kapuján balról jobbra helyezik a kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="5a6b3-205">Azaz</span><span class="sxs-lookup"><span data-stu-id="5a6b3-205">That is to say</span></span> 

<span data-ttu-id="5a6b3-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="5a6b3-207"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-208">![A Quantum Gates diagramja balról jobbra van alkalmazva](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="5a6b3-209">az egységes mátrix $ CBA $ .</span><span class="sxs-lookup"><span data-stu-id="5a6b3-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="5a6b3-210">A mátrix szorzása engedelmeskedik a szemközti konvenciónak: a jobb oldali mátrix először van alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="5a6b3-211">A Quantum Circuit-diagramoknál azonban először a bal szélső kaput alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="5a6b3-212">Ez a különbség időnként zavart eredményezhet, ezért fontos megjegyezni, hogy ez a különbség a lineáris algebrai jelölés és a kvantum-áramköri diagramok között jelentős.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="5a6b3-213">A kvantum-áramkörök bemenetei és kimenetei</span><span class="sxs-lookup"><span data-stu-id="5a6b3-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="5a6b3-214">A megadott összes korábbi példa pontosan ugyanazokat a vezetékeket (qubits) adta hozzá a kvantum-kapuhoz, mint a kvantum-kapuból kimenő vezetékek száma.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="5a6b3-215">Előfordulhat, hogy először úgy tűnik, hogy a kvantum-áramkörök több vagy kevesebb kimenettel rendelkeznek, mint általában a bemenetek.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="5a6b3-216">Ez azonban nem lehetséges, mivel az összes kvantum-művelet, a mérték mentése, egységes és ezért reverzibilis.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="5a6b3-217">Ha nem azonos számú kimenet szerepel a bemenetekben, nem vonhatók vissza, és így nem egységesek, ami ellentmond.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="5a6b3-218">Ebben az esetben az áramköri diagramban rajzolt bármely mezőnek pontosan ugyanannyi drótot kell megadnia, mint kilép.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="5a6b3-219">A multi-qubit áramköri diagramok hasonló konvenciókat követnek az qubit is.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="5a6b3-220">Egyértelmű példaként meghatározhatunk egy kétqubites "B" műveletet, $ amely a $ következő lehet: $ (H S \otimes X), $ és az áramkört egyenértékűként kell kifejezni</span><span class="sxs-lookup"><span data-stu-id="5a6b3-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="5a6b3-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="5a6b3-222"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-223">![Kétqubitű egységes művelet áramköri diagramja](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="5a6b3-224">A "B" nézetet úgy is megtekintheti $ $ , hogy egyetlen qubit-regisztráción alapuló művelettel rendelkezik, és nem 2 1-qubit regisztrálja az áramkört használó környezettől függően.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="5a6b3-225">Az absztrakt áramköri diagramok leghasznosabb tulajdonsága az, hogy lehetővé teszik, hogy a bonyolult kvantum-algoritmusokat magas szinten írják le anélkül, hogy le kellene őket állítani az alapvető kapuk számára.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="5a6b3-226">Ez azt jelenti, hogy a nagyméretű kvantum-algoritmusok adatforgalmával kapcsolatban nem kell megismernie az algoritmus működésével kapcsolatos összes alrutin részleteit.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="5a6b3-227">Vezérelt kapuk</span><span class="sxs-lookup"><span data-stu-id="5a6b3-227">Controlled gates</span></span>
<span data-ttu-id="5a6b3-228">A multi-qubit Quantum Circuit-diagramokba beépített másik összeállítás vezérli.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="5a6b3-229">Egy olyan kvantum-vezérelt kapu művelete, $ \Lambda amely (g) $ , ahol egyetlen qubit érték vezérli a g alkalmazást, a $ $ termék állapotának következő példáját tekintheti meg: ( $ \Lambda g) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ . Ez azt jelenti, hogy az ellenőrzött kapu a $ G $ értékre vonatkozik, és csak akkor, ha $ \psi $ a vezérlő qubit az 1 értéket veszi fel $ $ .</span><span class="sxs-lookup"><span data-stu-id="5a6b3-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="5a6b3-230">Általánosságban leírjuk, hogy milyen ellenőrzött műveleteket kell elvégeznie az áramköri diagramokban</span><span class="sxs-lookup"><span data-stu-id="5a6b3-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="5a6b3-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="5a6b3-232"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-233">![Egy megfelelően vezérelt kapu áramköri diagramja](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="5a6b3-234">Itt a fekete kör azt a kvantum-bitet jelöli, amelyen a kapu vezérelhető, és a vertikális huzal azt jelöli, hogy a vezérlő qubit az 1 értéket veszi figyelembe $ $ .</span><span class="sxs-lookup"><span data-stu-id="5a6b3-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="5a6b3-235">Azon speciális esetekben, ahol a $ g = X $ és a $ g Z a = következő jelölést mutatja be a $ kapuk ellenőrzött verziójának leírásához (vegye figyelembe, hogy a vezérelt X kapu a [ $ cnem $ kapu](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="5a6b3-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<span data-ttu-id="5a6b3-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="5a6b3-237"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-238">![Irányított kapuk speciális eseteinek áramköri diagramja](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="5a6b3-239">Q#a lehetővé teszi egy művelet ellenőrzött verziójának automatikus előállítását, amely elmenti a programozótól, hogy ezeket a műveleteket manuálisan kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="5a6b3-240">Alább látható egy példa:</span><span class="sxs-lookup"><span data-stu-id="5a6b3-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="5a6b3-241">Mérési operátor</span><span class="sxs-lookup"><span data-stu-id="5a6b3-241">Measurement operator</span></span>
<span data-ttu-id="5a6b3-242">Az áramköri diagramok megjelenítésének hátralévő művelete a mérés.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="5a6b3-243">A mérés qubit regisztrálja, méri azt, és az eredményt klasszikus információként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="5a6b3-244">Egy mérőszám szimbóluma egy mérési műveletet jelöl, és mindig bemenetként fogadja a qubit-regisztrációt (ezt egy folytonos vonal jelöli), és a klasszikus információ kimeneteit (egy dupla vonallal jelöli).</span><span class="sxs-lookup"><span data-stu-id="5a6b3-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="5a6b3-245">Az ilyen alhálózatok például a következőkre hasonlítanak:</span><span class="sxs-lookup"><span data-stu-id="5a6b3-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="5a6b3-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="5a6b3-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="5a6b3-247"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-248">![Mérési műveletet jelölő szimbólum](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="5a6b3-249">Q#erre a célra implementálja a [mérték kezelőjét](xref:microsoft.quantum.intrinsic.measure) .</span><span class="sxs-lookup"><span data-stu-id="5a6b3-249">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="5a6b3-250">További információt a [mérések című szakaszban](xref:microsoft.quantum.libraries.standard.prelude#measurements) talál.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="5a6b3-251">Hasonlóképpen, az aláramkör</span><span class="sxs-lookup"><span data-stu-id="5a6b3-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="5a6b3-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="5a6b3-253"><A!--nem talál megoldást a középpontba... valószínűleg egy bővítmény szükséges:-></span><span class="sxs-lookup"><span data-stu-id="5a6b3-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="5a6b3-254">![Ellenőrzött műveletet jelképező áramköri diagram](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="5a6b3-255">egy klasszikusan vezérelt kaput biztosít, $ ahol $ a G a klasszikus vezérlési bit értéke $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="5a6b3-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="5a6b3-256">Teleportáló áramköri diagram</span><span class="sxs-lookup"><span data-stu-id="5a6b3-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="5a6b3-257">A kvantum-teleportáció talán a legjobb kvantum-algoritmus ezen összetevők szemléltetésére.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="5a6b3-258">Megtudhatja, hogy a megfelelő [Quantum Kata](xref:microsoft.quantum.overview.katas) -alapú kvantum-teleportáció hogyan helyezheti át az információkat a kvantum-számítógépeken (vagy akár a kvantum-hálózaton lévő távoli Quantum számítógépek között) a felakadás és a mérés használatával.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="5a6b3-259">Érdekes, hogy valójában képes a kvantum állapotának áthelyezésére, azaz egy adott qubit értékének egy qubit a másikra való átállítására, anélkül, hogy a qubit értékének megtudhatja.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="5a6b3-260">Erre azért van szükség, hogy a protokoll a Quantum Mechanics törvényeinek megfelelően működjön.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="5a6b3-261">A kvantum-teleportáció áramkört az alábbi szakasz ismerteti. az áramkör megjegyzésekkel ellátott verzióját is megadja, hogy bemutassa a kvantum-áramkör beolvasásának módját.</span><span class="sxs-lookup"><span data-stu-id="5a6b3-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="5a6b3-262"><!--- ![](.\media\tp2.svg) { szélessége = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="5a6b3-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="5a6b3-263">![Quantum teleportáció-áramkör](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="5a6b3-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
