---
title: Belső műveletek és függvények a QDK
description: Ismerje meg a QDK belső műveleteit és funkcióit, beleértve a klasszikus funkciókat, valamint az egységes, rotációs és mérési műveleteket.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 4d15226fe46be79b7d3e6f414f33f1debd691f40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692117"
---
# <a name="the-prelude"></a><span data-ttu-id="da1c3-103">A bevezetés</span><span class="sxs-lookup"><span data-stu-id="da1c3-103">The Prelude</span></span> #

<span data-ttu-id="da1c3-104">A :::no-loc(Q#)::: Quantum Development Kit részét képező fordítóprogram és a célként megadott gépek olyan belső funkciókat és műveleteket biztosítanak, amelyek a kvantum-programok írásakor használhatók a alkalmazásban :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="da1c3-104">The :::no-loc(Q#)::: compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in :::no-loc(Q#):::.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="da1c3-105">Belső műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="da1c3-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="da1c3-106">A standard könyvtárban definiált belső műveletek nagyjából a különböző kategóriák valamelyikébe tartoznak:</span><span class="sxs-lookup"><span data-stu-id="da1c3-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="da1c3-107">A névtérben összegyűjtött alapvető klasszikus függvények <xref:Microsoft.Quantum.Core> .</span><span class="sxs-lookup"><span data-stu-id="da1c3-107">Essential classical functions, collected in the <xref:Microsoft.Quantum.Core> namespace.</span></span>
- <span data-ttu-id="da1c3-108">[Clifford és $T $ gatesből](xref:microsoft.quantum.concepts.qubit)álló unitaries képviselő műveletek.</span><span class="sxs-lookup"><span data-stu-id="da1c3-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="da1c3-109">A különböző operátorok rotációit képviselő műveletek.</span><span class="sxs-lookup"><span data-stu-id="da1c3-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="da1c3-110">A méréseket végrehajtó műveletek.</span><span class="sxs-lookup"><span data-stu-id="da1c3-110">Operations implementing measurements.</span></span>

<span data-ttu-id="da1c3-111">Mivel a Clifford + $T $ Gate készlet [univerzális](xref:microsoft.quantum.concepts.multiple-qubits) a kvantum-számítástechnika számára, ezek a műveletek elegendőek ahhoz, hogy nagyjából implementálják a elhanyagolható mértékben kis hibán belüli kvantum-algoritmusokat.</span><span class="sxs-lookup"><span data-stu-id="da1c3-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="da1c3-112">A forgatások is :::no-loc(Q#)::: lehetővé teszik, hogy a programozó az egységes qubit-és cnem Gate-könyvtáron belül is működjön.</span><span class="sxs-lookup"><span data-stu-id="da1c3-112">By providing rotations as well, :::no-loc(Q#)::: allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="da1c3-113">Ez a kódtár sokkal könnyebben gondolkodik, mert nem igényli, hogy a programozó közvetlenül fejezzék ki a Clifford + $T $ dekompozíciót, és mivel igen hatékony módszerek léteznek az egyetlen qubit-unitaries a Clifford és a $T $ gatesbe való fordításához (további információt [itt](xref:microsoft.quantum.more-information) talál).</span><span class="sxs-lookup"><span data-stu-id="da1c3-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="da1c3-114">Ha lehetséges, az qubits-ben a bevezetés során meghatározott műveletek lehetővé teszik a Variant alkalmazását `Controlled` , így a célszámítógép a megfelelő dekompozíciót fogja végezni.</span><span class="sxs-lookup"><span data-stu-id="da1c3-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="da1c3-115">Az előzetes verzió ezen részében definiált függvények és műveletek többsége a @"microsoft.quantum.intrinsic" névtérben található, így a legtöbb :::no-loc(Q#)::: forrásfájl a `open Microsoft.Quantum.Intrinsic;` kezdeti névtér deklarációja után azonnal egy direktívával fog rendelkezni.</span><span class="sxs-lookup"><span data-stu-id="da1c3-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most :::no-loc(Q#)::: source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="da1c3-116">A <xref:Microsoft.Quantum.Core> rendszer automatikusan megnyitja a névteret, így a <xref:Microsoft.Quantum.Core.Length> (z) függvény, amely nem tartalmaz `open` utasítást.</span><span class="sxs-lookup"><span data-stu-id="da1c3-116">The <xref:Microsoft.Quantum.Core> namespace is automatically opened, so that functions such as <xref:Microsoft.Quantum.Core.Length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="da1c3-117">Általános Single-Qubit – egységes műveletek</span><span class="sxs-lookup"><span data-stu-id="da1c3-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="da1c3-118">A bevezetés számos gyakori [qubit műveletet](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)is meghatároz.</span><span class="sxs-lookup"><span data-stu-id="da1c3-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="da1c3-119">Az összes művelet lehetővé teszi mind a, mind a következő műveleteket `Controlled` `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="da1c3-120">Pauli-operátorok</span><span class="sxs-lookup"><span data-stu-id="da1c3-120">Pauli Operators</span></span> ####

<span data-ttu-id="da1c3-121">A <xref:Microsoft.Quantum.Intrinsic.X> művelet végrehajtja a Pauli $X $ operátort.</span><span class="sxs-lookup"><span data-stu-id="da1c3-121">The <xref:Microsoft.Quantum.Intrinsic.X> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="da1c3-122">Ez más néven a `NOT` kapu.</span><span class="sxs-lookup"><span data-stu-id="da1c3-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="da1c3-123">Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-124">Az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="da1c3-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="da1c3-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="da1c3-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="da1c3-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="da1c3-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="da1c3-127">A <xref:Microsoft.Quantum.Intrinsic.Y> művelet végrehajtja a Pauli $Y $ operátort.</span><span class="sxs-lookup"><span data-stu-id="da1c3-127">The <xref:Microsoft.Quantum.Intrinsic.Y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="da1c3-128">Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-129">Az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="da1c3-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="da1c3-130">\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="da1c3-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="da1c3-131">& 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="da1c3-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="da1c3-132">A <xref:Microsoft.Quantum.Intrinsic.Z> művelet végrehajtja a Pauli $Z $ operátort.</span><span class="sxs-lookup"><span data-stu-id="da1c3-132">The <xref:Microsoft.Quantum.Intrinsic.Z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="da1c3-133">Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-134">Az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="da1c3-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="da1c3-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="da1c3-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="da1c3-136">0 & – 1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="da1c3-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="da1c3-137">Alább láthatók a [Bloch szférához](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) rendelt átalakítások (az egyes esetekben a rotációs tengely vörös színnel jelenik meg):</span><span class="sxs-lookup"><span data-stu-id="da1c3-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![A Bloch szférára leképezett Pauli-műveletek](~/media/prelude_pauliBloch.png)

<span data-ttu-id="da1c3-139">Fontos megjegyezni, hogy ugyanazt a Pauli-kaput kétszer alkalmazza ugyanarra a qubit, de megszakítja a műveletet (mivel most a 2π (360 °) teljes rotációját hajtotta végre a felszínen a Bloch szférára, így a kiindulási pontra érkezett vissza.</span><span class="sxs-lookup"><span data-stu-id="da1c3-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="da1c3-140">Ez a következő identitáshoz vezet:</span><span class="sxs-lookup"><span data-stu-id="da1c3-140">This brings us to the following identity:</span></span>

<span data-ttu-id="da1c3-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="da1c3-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="da1c3-142">Ez a Bloch szférában látható:</span><span class="sxs-lookup"><span data-stu-id="da1c3-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="da1c3-144">Egyéb Single-Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="da1c3-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="da1c3-145">A <xref:Microsoft.Quantum.Intrinsic.H> művelet megvalósítja a Hadamard kaput.</span><span class="sxs-lookup"><span data-stu-id="da1c3-145">The <xref:Microsoft.Quantum.Intrinsic.H> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="da1c3-146">Ezzel a megoldással a megcélzott qubit Pauli $X $ és $Z $ tengelyét változtatja meg, például $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ és $H \ket{+} = \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="da1c3-147">Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` , és az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="da1c3-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="da1c3-148">\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-et használja.</span><span class="sxs-lookup"><span data-stu-id="da1c3-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="da1c3-149">1 & – 1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="da1c3-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="da1c3-150">A Hadamard Gate különösen fontos, mivel a $ \ket {0} $ és a $ \ket {1} $ állapotú példányok létrehozásához is használható.</span><span class="sxs-lookup"><span data-stu-id="da1c3-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="da1c3-151">A Bloch szféra képviseletében a legkönnyebben úgy gondolja, hogy ez a $ \ket{\psi} $ érték forgása az x tengely körül $ \pi $ radián ($ 180 ^ \circ $), majd az y tengely körüli elforgatása $ \ pi/2 $ radián ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="da1c3-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![A Hadamard művelet a Bloch szférára van leképezve](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="da1c3-153">A <xref:Microsoft.Quantum.Intrinsic.S> művelet végrehajtja a Phase gate $S $ értéket.</span><span class="sxs-lookup"><span data-stu-id="da1c3-153">The <xref:Microsoft.Quantum.Intrinsic.S> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="da1c3-154">Ez a Pauli $Z $ művelet mátrix-négyzetének gyökere.</span><span class="sxs-lookup"><span data-stu-id="da1c3-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="da1c3-155">Vagyis $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="da1c3-156">Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` , és az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="da1c3-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="da1c3-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="da1c3-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="da1c3-158">0 & \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="da1c3-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="da1c3-159">Beosztások</span><span class="sxs-lookup"><span data-stu-id="da1c3-159">Rotations</span></span> ####

<span data-ttu-id="da1c3-160">A fenti, a Pauli és a Clifford műveleteken kívül a :::no-loc(Q#)::: Bevezetés számos módszert kínál a Forgások kifejezésére.</span><span class="sxs-lookup"><span data-stu-id="da1c3-160">In addition to the Pauli and Clifford operations above, the :::no-loc(Q#)::: prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="da1c3-161">Az [qubit műveletekben](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)leírtak szerint az elforgatási képesség kritikus fontosságú a kvantum-algoritmusok számára.</span><span class="sxs-lookup"><span data-stu-id="da1c3-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="da1c3-162">Kezdjük azzal, hogy a $H $ és a $T $ Gates használatával bármilyen egyetlen qubit műveletet kifejezzük, ahol $H $ a Hadamard művelet, és ahol a \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: ez jelenleg a quad back Hack-T használja.</span><span class="sxs-lookup"><span data-stu-id="da1c3-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="da1c3-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} ez a művelet négyzet gyökere <xref:Microsoft.Quantum.Intrinsic.S> , például $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:Microsoft.Quantum.Intrinsic.S> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="da1c3-164">A $T $ kaput a művelet implementálja <xref:Microsoft.Quantum.Intrinsic.T> , és aláírással rendelkezik, amely azt `(Qubit => Unit is Adj + Ctl)` jelzi, hogy egy egységes művelet egy qubit.</span><span class="sxs-lookup"><span data-stu-id="da1c3-164">The $T$ gate is in turn implemented by the <xref:Microsoft.Quantum.Intrinsic.T> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="da1c3-165">Annak ellenére, hogy ez elvileg elegendő ahhoz, hogy bármilyen tetszőleges qubit műveletet le lehessen írni, a különböző célszámítógépek hatékonyabb ábrázolással rendelkezhetnek a Pauli-operátorokkal kapcsolatos rotációs műveletekhez, például a bevezetés számos módszert tartalmaz a convienently kiváltására.</span><span class="sxs-lookup"><span data-stu-id="da1c3-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="da1c3-166">A legalapvetőbb ilyen <xref:Microsoft.Quantum.Intrinsic.r> művelet, amely egy megadott Pauli-tengely, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation}, ahol a $ \sigma $ egy Pauli operátor, a $ \phi $ egy szög, és ahol a $ \exp $ a mátrix exponenciális értéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="da1c3-166">The most basic of these is the <xref:Microsoft.Quantum.Intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="da1c3-167">Aláírással rendelkezik `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , ahol a bemenet első két része a $ \sigma $ és a $ \phi $ klasszikus argumentumokat jelöli, amelyek az egységes operátor megadásához szükségesek $R (\sigma, \phi) $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="da1c3-168">Részben alkalmazhatjuk a $ \sigma $ és a $ \phi $ értéket egy olyan művelet beszerzéséhez, amelynek a típusa egyetlen qubit egységes.</span><span class="sxs-lookup"><span data-stu-id="da1c3-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="da1c3-169">Például a `R(PauliZ, PI() / 4, _)` típusa `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="da1c3-170">A <xref:Microsoft.Quantum.Intrinsic.r> művelet a bemeneti szöget 2 értékre osztja, és a-1 értékkel szorozza meg.</span><span class="sxs-lookup"><span data-stu-id="da1c3-170">The <xref:Microsoft.Quantum.Intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="da1c3-171">$Z $ forgás esetén ez azt jelenti, hogy a $ \ket {0} $ eigenstate a $-\phi/$2, a $ \ket $ eigenstate pedig a $ \phi/$2 által elforgatott érték, hogy a $ \ket $ eigenstate a $ \phi $ \ket {1} {1} képest legyen elforgatva {0} .</span><span class="sxs-lookup"><span data-stu-id="da1c3-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="da1c3-172">Ez különösen azt jelenti, hogy `T` csak a nem `R(PauliZ, PI() / 8, _)` releváns [globális fázisokban](xref:microsoft.quantum.glossary#global-phase)térnek el egymástól.</span><span class="sxs-lookup"><span data-stu-id="da1c3-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="da1c3-173">Emiatt $T $ \frac{\pi} $-Gate néven is ismert {8} .</span><span class="sxs-lookup"><span data-stu-id="da1c3-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="da1c3-174">Vegye figyelembe azt is, hogy az elforgatás körülbelül `PauliI` a $ \phi/$2 globális fázisát alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="da1c3-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="da1c3-175">Habár az ilyen fázisok nem relevánsak, ahogy azt [a koncepcionális dokumentumok](xref:microsoft.quantum.concepts.qubit)is felmutatják, az ellenőrzött rotációk szempontjából fontosak `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="da1c3-176">A kvantum-algoritmusokon belül gyakran hasznos a rotációk dyadic-frakcióként való kimutatása, például a $ \phi = \pi k/2 ^ n $ használata néhány $k \in \mathbb{Z} $ és $n \in \mathbb{N} $ esetében.</span><span class="sxs-lookup"><span data-stu-id="da1c3-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="da1c3-177">A <xref:Microsoft.Quantum.Intrinsic.RFrac> művelet a megadott Pauli-tengely körüli rotációt valósít meg az egyezmény használatával.</span><span class="sxs-lookup"><span data-stu-id="da1c3-177">The <xref:Microsoft.Quantum.Intrinsic.RFrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="da1c3-178">Eltér attól, <xref:Microsoft.Quantum.Intrinsic.R> hogy az elforgatási szög két típusú bemenetként van megadva `Int` , dyadic-frakcióként értelmezve.</span><span class="sxs-lookup"><span data-stu-id="da1c3-178">It differs from <xref:Microsoft.Quantum.Intrinsic.R> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="da1c3-179">Így `RFrac` az aláírással rendelkezik `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-180">Implementálja az qubit egységes $ \exp (i \pi k \sigma/2 ^ n) $ értéket, ahol a $ \sigma $ az első argumentumnak megfelelő Pauli-mátrix, $k $ a második argumentum, és $n $ a harmadik argumentum.</span><span class="sxs-lookup"><span data-stu-id="da1c3-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="da1c3-181">`RFrac(_,k,n,_)` ugyanaz, mint a ( `R(_,-πk/2^n,_)` ). Megjegyzendő, hogy a szög a frakció *negatív* értéke.</span><span class="sxs-lookup"><span data-stu-id="da1c3-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="da1c3-182">A <xref:Microsoft.Quantum.Intrinsic.Rx> művelet egy rotációs műveletet valósít meg a Pauli $X $ tengely körül.</span><span class="sxs-lookup"><span data-stu-id="da1c3-182">The <xref:Microsoft.Quantum.Intrinsic.Rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="da1c3-183">Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-184">`Rx(_, _)` ugyanaz, mint `R(PauliX, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="da1c3-185">A <xref:Microsoft.Quantum.Intrinsic.Ry> művelet egy rotációs műveletet valósít meg a Pauli $Y $ tengely körül.</span><span class="sxs-lookup"><span data-stu-id="da1c3-185">The <xref:Microsoft.Quantum.Intrinsic.Ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="da1c3-186">Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-187">`Ry(_, _)` ugyanaz, mint `R(PauliY,_ , _)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="da1c3-188">A <xref:Microsoft.Quantum.Intrinsic.Rz> művelet egy rotációs műveletet valósít meg a Pauli $Z $ tengely körül.</span><span class="sxs-lookup"><span data-stu-id="da1c3-188">The <xref:Microsoft.Quantum.Intrinsic.Rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="da1c3-189">Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-190">`Rz(_, _)` ugyanaz, mint `R(PauliZ, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="da1c3-191">A <xref:Microsoft.Quantum.Intrinsic.R1> művelet egy rotációt valósít meg a $ \ket {1} $, a $-$1 eigenstate $Z $ érték körüli megadott összeggel.</span><span class="sxs-lookup"><span data-stu-id="da1c3-191">The <xref:Microsoft.Quantum.Intrinsic.R1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="da1c3-192">Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-193">`R1(phi,_)` ugyanaz, mint amit a `R(PauliZ,phi,_)` követ `R(PauliI,-phi,_)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="da1c3-194">A <xref:Microsoft.Quantum.Intrinsic.R1Frac> művelet egy töredékes rotációt valósít meg a Z = 1 eigenstate körüli megadott összeggel.</span><span class="sxs-lookup"><span data-stu-id="da1c3-194">The <xref:Microsoft.Quantum.Intrinsic.R1Frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="da1c3-195">Aláírással rendelkezik `((Int,Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-196">`R1Frac(k,n,_)` ugyanaz, mint amit a `RFrac(PauliZ,-k.n+1,_)` követ `RFrac(PauliI,k,n+1,_)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="da1c3-197">Alább látható egy példa egy rotációs műveletre (az ebben az esetben a Pauli $Z $ tengelyen, ebben a példányban), amely a Bloch szférára van leképezve:</span><span class="sxs-lookup"><span data-stu-id="da1c3-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![A Bloch szférára leképezett rotációs művelet](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="da1c3-199">Több Qubit műveletek</span><span class="sxs-lookup"><span data-stu-id="da1c3-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="da1c3-200">A fenti qubit műveletek mellett a Prelude számos több qubit műveletet is meghatároz.</span><span class="sxs-lookup"><span data-stu-id="da1c3-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="da1c3-201">Először a <xref:Microsoft.Quantum.Intrinsic.CNOT> művelet elvégzi a standard szintű vezérelt- `NOT` Gate, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="da1c3-201">First, the <xref:Microsoft.Quantum.Intrinsic.CNOT> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="da1c3-202">\end{Equation} aláírással rendelkezik `((Qubit, Qubit) => Unit is Adj + Ctl)` , ami azt jelenti, hogy a $ \operatorname{CNOT} $ unitarily két önálló qubits.</span><span class="sxs-lookup"><span data-stu-id="da1c3-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="da1c3-203">`CNOT(q1, q2)` ugyanaz, mint `(Controlled X)([q1], q2)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="da1c3-204">Mivel az elválasztó `Controlled` lehetővé teszi a regisztrációt, a tömb szövegkonstans használatával `[q1]` jelezheti, hogy csak az egyetlen vezérlőt szeretnénk használni.</span><span class="sxs-lookup"><span data-stu-id="da1c3-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="da1c3-205">A <xref:Microsoft.Quantum.Intrinsic.CCNOT> művelet kétszeresen vezérelt nem kaput, más néven a Toffoli kaput hajt végre.</span><span class="sxs-lookup"><span data-stu-id="da1c3-205">The <xref:Microsoft.Quantum.Intrinsic.CCNOT> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="da1c3-206">Aláírással rendelkezik `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-207">`CCNOT(q1, q2, q3)` ugyanaz, mint `(Controlled X)([q1, q2], q3)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="da1c3-208">A <xref:Microsoft.Quantum.Intrinsic.SWAP> művelet felcseréli a két qubits Quantum állapotait.</span><span class="sxs-lookup"><span data-stu-id="da1c3-208">The <xref:Microsoft.Quantum.Intrinsic.SWAP> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="da1c3-209">Ez azt is megvalósítja, hogy implementálja az egységes mátrix \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & \\ 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="da1c3-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="da1c3-210">\end{Equation} aláírása `((Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="da1c3-211">`SWAP(q1,q2)` egyenértékű a következővel, `CNOT(q1, q2)` `CNOT(q2, q1)` és utána `CNOT(q1, q2)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="da1c3-212">A SWAP-kapu *nem* egyezik meg a típussal rendelkező változó elemeinek átrendezésével `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="da1c3-213">A alkalmazás a `SWAP(q1, q2)` és a által hivatkozott qubits állapotának módosítását okozza `q1` `q2` , miközben `let swappedRegister = [q2, q1];` csak azt befolyásolja, hogyan hivatkozunk ezekre a qubits.</span><span class="sxs-lookup"><span data-stu-id="da1c3-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="da1c3-214">Emellett `(Controlled SWAP)([q0], (q1, q2))` lehetővé teszi, `SWAP` hogy a a harmadik qubit állapotára is felkerüljön, amelyet az elemek átrendezése nem jelenthet.</span><span class="sxs-lookup"><span data-stu-id="da1c3-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="da1c3-215">A vezérelt SWAP-kapu, más néven a Fredkin-kapu, elég erős ahhoz, hogy tartalmazza az összes klasszikus számítást.</span><span class="sxs-lookup"><span data-stu-id="da1c3-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="da1c3-216">Végül a Prelude két műveletet biztosít a több qubit Pauli-operátorok exponenciális ábrázolásához.</span><span class="sxs-lookup"><span data-stu-id="da1c3-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="da1c3-217">A <xref:Microsoft.Quantum.Intrinsic.Exp> művelet a Pauli-mátrixok egy tízes szorzatán alapuló rotációs műveletet hajt végre. a többszörös qubit egységes \Begin{Equation} \operatorname{exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), a \end{Equation}, ahol a $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ az egyetlen Qubit Pauli-operátorok sorozata, és ahol a $ \phi $ egy szög.</span><span class="sxs-lookup"><span data-stu-id="da1c3-217">The <xref:Microsoft.Quantum.Intrinsic.Exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="da1c3-218">Az `Exp` elforgatás a $ \vec{\sigma} $ elemet jelenti elemek tömbje `Pauli` , például aláírással `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="da1c3-219">A <xref:Microsoft.Quantum.Intrinsic.ExpFrac> művelet ugyanazt a rotációs műveletet hajtja végre, a fentebb tárgyalt dyadic-frakciós jelölés használatával.</span><span class="sxs-lookup"><span data-stu-id="da1c3-219">The <xref:Microsoft.Quantum.Intrinsic.ExpFrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="da1c3-220">Aláírással rendelkezik `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="da1c3-221">A Pauli-operátorok tenser-termékének exponenciális száma nem egyezik meg a Pauli-operátorok exponenciálisan működő termékeivel.</span><span class="sxs-lookup"><span data-stu-id="da1c3-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="da1c3-222">Vagyis $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="da1c3-223">Mérések</span><span class="sxs-lookup"><span data-stu-id="da1c3-223">Measurements</span></span> ###

<span data-ttu-id="da1c3-224">A méréskor a mért operátor + 1 sajátérték egy `Zero` eredménynek felel meg, és az-1 sajátérték `One` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="da1c3-225">Habár ez az egyezmény páratlannak tűnhet, két nagyon jó előnye van.</span><span class="sxs-lookup"><span data-stu-id="da1c3-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="da1c3-226">Először is, a $ \ket {0} $ értéknek a megfigyelt `Result` értéke az érték `Zero` , míg a $ \ket $ megfigyelése {1} megfelel `One` a következőnek:.</span><span class="sxs-lookup"><span data-stu-id="da1c3-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="da1c3-227">Másodszor, azt is kiírhatjuk, hogy a sajátérték $ \lambda $ megfelel egy eredménynek, $r $ értéke $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="da1c3-228">A mérési műveletek sem a, `Adjoint` sem a nem működőt támogatják `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="da1c3-229">A <xref:Microsoft.Quantum.Intrinsic.Measure> művelet egy vagy több qubits közös mérését végzi a Pauli-operátorok megadott termékében.</span><span class="sxs-lookup"><span data-stu-id="da1c3-229">The <xref:Microsoft.Quantum.Intrinsic.Measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="da1c3-230">Ha a Pauli tömb és a qubit tömb eltérő hosszúságú, akkor a művelet sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="da1c3-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="da1c3-231">`Measure` aláírással rendelkezik `((Pauli[], Qubit[]) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="da1c3-232">Vegye figyelembe, hogy a közös mérések nem egyeznek meg egyenként a qubit mérésével.</span><span class="sxs-lookup"><span data-stu-id="da1c3-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="da1c3-233">Vegyük például a következő állapotot: $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="da1c3-234">A $Z _0 $ és a $Z _1 $ mérése egyenként történik, $r _0 = $1 és $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="da1c3-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="da1c3-235">$Z _0 Z_1 $ mérésével azonban egyetlen eredmény $r _ {\textrm{Joint}} = $0 lesz, ami azt jelenti, hogy a $ \ket $ párosítása {11} pozitív.</span><span class="sxs-lookup"><span data-stu-id="da1c3-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="da1c3-236">Másképpen fogalmazva, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="da1c3-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="da1c3-237">Kritikus fontosságú, mivel a rendszer *csak* az ebből a mérésből származó paritást tanulja meg, a pozitív paritású 2 2 – qubit állapotok közötti, a \ket $ és a $ \ket $ közötti kapcsolatban szereplő kvantum-információk {00} {11} megmaradnak.</span><span class="sxs-lookup"><span data-stu-id="da1c3-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="da1c3-238">Ezt a tulajdonságot később kell megtekinteni, ahogy a hibajavításról van szó.</span><span class="sxs-lookup"><span data-stu-id="da1c3-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="da1c3-239">A kényelem érdekében a bevezetés két további műveletet is biztosít a qubits méréséhez.</span><span class="sxs-lookup"><span data-stu-id="da1c3-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="da1c3-240">Először is, mivel az qubit mérések végrehajtása meglehetősen gyakori, a bevezetés egy gyorsírást határoz meg ebben az esetben.</span><span class="sxs-lookup"><span data-stu-id="da1c3-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="da1c3-241">A <xref:Microsoft.Quantum.Intrinsic.M> művelet a Pauli $Z $ operátort méri egyetlen qubit, és aláírással rendelkezik `(Qubit => Result)` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-241">The <xref:Microsoft.Quantum.Intrinsic.M> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="da1c3-242">A `M(q)` és a `Measure([PauliZ], [q])` kifejezés egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="da1c3-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="da1c3-243">A a <xref:microsoft.quantum.measurement.MultiM> Pauli $Z $ operátort a qubits minden egyes tömbje számára *külön* méri, és az egyes qubit kapott értékek *tömbjét* adja vissza `Result` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-243">The <xref:microsoft.quantum.measurement.MultiM> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="da1c3-244">Bizonyos esetekben ez optimalizálható.</span><span class="sxs-lookup"><span data-stu-id="da1c3-244">In some cases this can be optimized.</span></span> <span data-ttu-id="da1c3-245">Rendelkezik aláírással ( `Qubit[] => Result[])` .</span><span class="sxs-lookup"><span data-stu-id="da1c3-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="da1c3-246">`MultiM(qs)` egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="da1c3-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="da1c3-247">Bővítmény-függvények és-műveletek</span><span class="sxs-lookup"><span data-stu-id="da1c3-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="da1c3-248">Emellett a bevezetés a matematikai és a típusú átalakítási függvények széles választékát határozza meg a .NET-szinten a kódban való használatra :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="da1c3-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within :::no-loc(Q#)::: code.</span></span>
<span data-ttu-id="da1c3-249">A névtér például olyan <xref:Microsoft.Quantum.Math> hasznos műveleteket határoz meg, mint a <xref:Microsoft.Quantum.Math.Sin> és a <xref:Microsoft.Quantum.Math.Log> .</span><span class="sxs-lookup"><span data-stu-id="da1c3-249">For instance, the <xref:Microsoft.Quantum.Math> namespace defines useful operations such as <xref:Microsoft.Quantum.Math.Sin> and <xref:Microsoft.Quantum.Math.Log>.</span></span>
<span data-ttu-id="da1c3-250">A Quantum Development Kit által biztosított implementáció a klasszikus .NET alaposztály-függvénytárat használja, így további kommunikációs kört eredményezhet a kvantum-programok és a klasszikus illesztőprogramjaik között.</span><span class="sxs-lookup"><span data-stu-id="da1c3-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="da1c3-251">Habár ez nem jelent problémát a helyi szimulátor esetében, ez a probléma akkor lehet teljesítményproblémák, ha távoli szimulátort vagy tényleges hardvert használ célként.</span><span class="sxs-lookup"><span data-stu-id="da1c3-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="da1c3-252">Ez azt is okozhatja, hogy az adott rendszer esetében az egyes célszámítógép befolyásolhatja a teljesítményt, ha felülbírálja ezeket a műveleteket az adott rendszeren hatékonyabb verziókkal.</span><span class="sxs-lookup"><span data-stu-id="da1c3-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="da1c3-253">Matematikai</span><span class="sxs-lookup"><span data-stu-id="da1c3-253">Math</span></span> ###

<span data-ttu-id="da1c3-254">A <xref:Microsoft.Quantum.Math> névtér számos hasznos funkciót biztosít a .net alaposztály könyvtárának [ `System.Math` osztályában](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="da1c3-254">The <xref:Microsoft.Quantum.Math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).</span></span>
<span data-ttu-id="da1c3-255">Ezek a függvények ugyanúgy használhatók, mint bármely más :::no-loc(Q#)::: függvény:</span><span class="sxs-lookup"><span data-stu-id="da1c3-255">These functions can be used in the same manner as any other :::no-loc(Q#)::: functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="da1c3-256">Ha a .NET statikus metódus túlterhelt az argumentumok típusa alapján, a megfelelő :::no-loc(Q#)::: függvényt a rendszer a bemenetének típusát jelző utótaggal jelöli meg:</span><span class="sxs-lookup"><span data-stu-id="da1c3-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding :::no-loc(Q#)::: function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="da1c3-257">Bitenkénti-műveletek</span><span class="sxs-lookup"><span data-stu-id="da1c3-257">Bitwise Operations</span></span> ###

<span data-ttu-id="da1c3-258">Végül a <xref:Microsoft.Quantum.Bitwise> névtér számos hasznos függvényt biztosít az egész számok bitenkénti-operátoron keresztüli módosításához.</span><span class="sxs-lookup"><span data-stu-id="da1c3-258">Finally, the <xref:Microsoft.Quantum.Bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="da1c3-259">A például <xref:Microsoft.Quantum.Bitwise.Parity> egy egész szám bitenkénti paritását adja vissza egy másik egész számként.</span><span class="sxs-lookup"><span data-stu-id="da1c3-259">For instance, <xref:Microsoft.Quantum.Bitwise.Parity> returns the bitwise parity of an integer as another integer.</span></span>
