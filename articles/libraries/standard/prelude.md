---
title: Belső műveletek és függvények a QDK
description: Ismerje meg a QDK belső műveleteit és funkcióit, beleértve a klasszikus funkciókat, valamint az egységes, rotációs és mérési műveleteket.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907205"
---
# <a name="the-prelude"></a><span data-ttu-id="4b556-103">A bevezetés</span><span class="sxs-lookup"><span data-stu-id="4b556-103">The Prelude</span></span> #

<span data-ttu-id="4b556-104">A Q # fordítóprogram és a Quantum Development Kit részét képező cél gépek olyan belső funkciókat és műveleteket biztosítanak, amelyek a Quantum-programok a Q #-ban való írásakor használhatók.</span><span class="sxs-lookup"><span data-stu-id="4b556-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="4b556-105">Belső műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="4b556-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="4b556-106">A standard könyvtárban definiált belső műveletek nagyjából a különböző kategóriák valamelyikébe tartoznak:</span><span class="sxs-lookup"><span data-stu-id="4b556-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="4b556-107">A <xref:microsoft.quantum.core> névtérben összegyűjtött alapvető klasszikus függvények.</span><span class="sxs-lookup"><span data-stu-id="4b556-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="4b556-108">[Clifford és $T $ gatesből](xref:microsoft.quantum.concepts.qubit)álló unitaries képviselő műveletek.</span><span class="sxs-lookup"><span data-stu-id="4b556-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="4b556-109">A különböző operátorok rotációit képviselő műveletek.</span><span class="sxs-lookup"><span data-stu-id="4b556-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="4b556-110">A méréseket végrehajtó műveletek.</span><span class="sxs-lookup"><span data-stu-id="4b556-110">Operations implementing measurements.</span></span>

<span data-ttu-id="4b556-111">Mivel a Clifford + $T $ Gate készlet [univerzális](xref:microsoft.quantum.concepts.multiple-qubits) a kvantum-számítástechnika számára, ezek a műveletek elegendőek ahhoz, hogy nagyjából implementálják a elhanyagolható mértékben kis hibán belüli kvantum-algoritmusokat.</span><span class="sxs-lookup"><span data-stu-id="4b556-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="4b556-112">A Q # lehetővé teszi, hogy a programozók a single qubit egységes és CNEM Gate könyvtárán belül is működjenek.</span><span class="sxs-lookup"><span data-stu-id="4b556-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="4b556-113">Ez a kódtár sokkal könnyebben gondolkodik, mert nem igényli, hogy a programozó közvetlenül fejezzék ki a Clifford + $T $ dekompozíciót, és mivel igen hatékony módszerek léteznek az egyetlen qubit-unitaries a Clifford és a $T $ gatesbe való fordításához (további információt [itt](xref:microsoft.quantum.more-information) talál).</span><span class="sxs-lookup"><span data-stu-id="4b556-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="4b556-114">Ha lehetséges, a qubits-ben a bevezetés során meghatározott műveletek lehetővé teszik a `Controlled` változat alkalmazását, például hogy a célszámítógép végrehajtja a megfelelő dekompozíciót.</span><span class="sxs-lookup"><span data-stu-id="4b556-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="4b556-115">A bevezetés ezen részében meghatározott függvények és műveletek közül sok a @"microsoft.quantum.intrinsic" névtérben van, így a legtöbb Q # forrásfájlokat tartalmazó `open Microsoft.Quantum.Intrinsic;` direktíva közvetlenül a kezdeti névtér deklarációja után fog rendelkezni.</span><span class="sxs-lookup"><span data-stu-id="4b556-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="4b556-116">A rendszer automatikusan megnyit <xref:microsoft.quantum.core> névteret, így a függvények, például a <xref:microsoft.quantum.core.length> `open` utasítás nélkül is használhatók.</span><span class="sxs-lookup"><span data-stu-id="4b556-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="4b556-117">Közös Qubit – egységes műveletek</span><span class="sxs-lookup"><span data-stu-id="4b556-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="4b556-118">A bevezetés számos gyakori [qubit műveletet](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)is meghatároz.</span><span class="sxs-lookup"><span data-stu-id="4b556-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="4b556-119">Az összes művelet lehetővé teszi mind a `Controlled`, mind a `Adjoint`-belit.</span><span class="sxs-lookup"><span data-stu-id="4b556-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="4b556-120">Pauli-operátorok</span><span class="sxs-lookup"><span data-stu-id="4b556-120">Pauli Operators</span></span> ####

<span data-ttu-id="4b556-121">A <xref:microsoft.quantum.intrinsic.x> művelet végrehajtja a Pauli $X $ operátort.</span><span class="sxs-lookup"><span data-stu-id="4b556-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="4b556-122">Ez más néven a `NOT` kapu.</span><span class="sxs-lookup"><span data-stu-id="4b556-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="4b556-123">Aláírása `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-124">Az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="4b556-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4b556-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="4b556-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4b556-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4b556-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4b556-127">A <xref:microsoft.quantum.intrinsic.y> művelet végrehajtja a Pauli $Y $ operátort.</span><span class="sxs-lookup"><span data-stu-id="4b556-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="4b556-128">Aláírása `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-129">Az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="4b556-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4b556-130">\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="4b556-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4b556-131">& 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4b556-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4b556-132">A <xref:microsoft.quantum.intrinsic.z> művelet végrehajtja a Pauli $Z $ operátort.</span><span class="sxs-lookup"><span data-stu-id="4b556-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="4b556-133">Aláírása `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-134">Az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="4b556-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4b556-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="4b556-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4b556-136">0 & – 1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4b556-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4b556-137">Alább láthatók a [Bloch szférához](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) rendelt átalakítások (az egyes esetekben a rotációs tengely vörös színnel jelenik meg):</span><span class="sxs-lookup"><span data-stu-id="4b556-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![A Bloch szférára leképezett Pauli-műveletek](~/media/prelude_pauliBloch.png)

<span data-ttu-id="4b556-139">Fontos megjegyezni, hogy ugyanazt a Pauli-kaput kétszer alkalmazza ugyanarra a qubit, de megszakítja a műveletet (mivel most a 2π (360 °) teljes rotációját hajtotta végre a felszínen a Bloch szférára, így a kiindulási pontra érkezett vissza.</span><span class="sxs-lookup"><span data-stu-id="4b556-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="4b556-140">Ez a következő identitáshoz vezet:</span><span class="sxs-lookup"><span data-stu-id="4b556-140">This brings us to the following identity:</span></span>

<span data-ttu-id="4b556-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="4b556-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="4b556-142">Ez a Bloch szférában látható:</span><span class="sxs-lookup"><span data-stu-id="4b556-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="4b556-144">Más, egyetlen Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="4b556-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="4b556-145">A <xref:microsoft.quantum.intrinsic.h> művelet megvalósítja a Hadamard kaput.</span><span class="sxs-lookup"><span data-stu-id="4b556-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="4b556-146">Ezzel a megoldással a megcélzott qubit Pauli $X $ és $Z $ tengelyét változtatja meg, például $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ és $H \ket{+} = \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="4b556-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="4b556-147">Aláírási `(Qubit => Unit is Adj + Ctl)`rendelkezik, és az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="4b556-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4b556-148">\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="4b556-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4b556-149">1 & – 1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4b556-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4b556-150">A Hadamard Gate különösen fontos, mivel a $ \ket{0}$ és $ \ket{1}$ állapotú példányok létrehozásához is használható.</span><span class="sxs-lookup"><span data-stu-id="4b556-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="4b556-151">A Bloch szféra képviseletében a legkönnyebben úgy gondolja, hogy ez a $ \ket{\psi} $ érték forgása az x tengely körül $ \pi $ radián ($ 180 ^ \circ $), majd az y tengely körüli elforgatása $ \ pi/2 $ radián ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="4b556-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![A Hadamard művelet a Bloch szférára van leképezve](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="4b556-153">A <xref:microsoft.quantum.intrinsic.s> művelet megvalósítja a Phase Gate $S $ értéket.</span><span class="sxs-lookup"><span data-stu-id="4b556-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="4b556-154">Ez a Pauli $Z $ művelet mátrix-négyzetének gyökere.</span><span class="sxs-lookup"><span data-stu-id="4b556-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="4b556-155">Vagyis $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="4b556-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="4b556-156">Aláírási `(Qubit => Unit is Adj + Ctl)`rendelkezik, és az egységes qubit felel meg:</span><span class="sxs-lookup"><span data-stu-id="4b556-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4b556-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.</span><span class="sxs-lookup"><span data-stu-id="4b556-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4b556-158">0 & \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4b556-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="4b556-159">Cserélgetésére</span><span class="sxs-lookup"><span data-stu-id="4b556-159">Rotations</span></span> ####

<span data-ttu-id="4b556-160">A fenti Pauli és Clifford műveleteken kívül a Q # Prelude számos módszert kínál a Forgások kifejezésére.</span><span class="sxs-lookup"><span data-stu-id="4b556-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="4b556-161">Az [qubit műveletekben](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)leírtak szerint az elforgatási képesség kritikus fontosságú a kvantum-algoritmusok számára.</span><span class="sxs-lookup"><span data-stu-id="4b556-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="4b556-162">Kezdjük azzal, hogy a $H $ és a $T $ Gates használatával bármilyen egyetlen qubit műveletet kifejezzük, ahol a $H $ a Hadamard művelet, és ahol a \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: ez jelenleg a quad back Hack-T használja.</span><span class="sxs-lookup"><span data-stu-id="4b556-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="4b556-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} ez a <xref:microsoft.quantum.intrinsic.s> művelet négyzet gyökere, például $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="4b556-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="4b556-164">A $T $ Gate a <xref:microsoft.quantum.intrinsic.t> művelettel van megvalósítva, és aláírási `(Qubit => Unit is Adj + Ctl)`rendelkezik, amely azt jelzi, hogy ez egy egységes művelet egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="4b556-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="4b556-165">Annak ellenére, hogy ez elvileg elegendő ahhoz, hogy bármilyen tetszőleges qubit műveletet le lehessen írni, a különböző célszámítógépek hatékonyabb ábrázolással rendelkezhetnek a Pauli-operátorokkal kapcsolatos rotációs műveletekhez, például a bevezetés számos különféle módszert tartalmaz a convienently ilyen elfordulások kifejezése.</span><span class="sxs-lookup"><span data-stu-id="4b556-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="4b556-166">A legalapvetőbb ilyen a <xref:microsoft.quantum.intrinsic.r> művelet, amely egy megadott Pauli-tengely, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation}, ahol a $ \sigma $ egy Pauli operátor, $ \phi $ egy szög, és ahol $ \exp $ a mátrix exponenciális értéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="4b556-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="4b556-167">Aláírási `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`rendelkezik, ahol a bemenet első két része a $ \sigma $ és a $ \phi $ klasszikus argumentumokat jelöli, amelyek az egységes operátor $R (\sigma, \phi) $ értékének megadásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="4b556-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="4b556-168">Részben alkalmazhatjuk a $ \sigma $ és a $ \phi $ értéket egy olyan művelet beszerzéséhez, amelynek a típusa egyetlen qubit egységes.</span><span class="sxs-lookup"><span data-stu-id="4b556-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="4b556-169">Például `R(PauliZ, PI() / 4, _)` típusa `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="4b556-170">A <xref:microsoft.quantum.intrinsic.r> művelet a bemeneti szöget 2 értékre osztja, és szorozza meg a-1 értékkel.</span><span class="sxs-lookup"><span data-stu-id="4b556-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="4b556-171">$Z $ forgás esetén ez azt jelenti, hogy a $ \ket{0}$ eigenstate a $-\phi/$2, a $ \ket{1}$ eigenstate pedig a $ \phi/$2 által elforgatva, így a $ \ket{1}$ eigenstate a $ \phi $ értékkel, a $ \ket{0}$ eigenstate-hez képest forog.</span><span class="sxs-lookup"><span data-stu-id="4b556-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="4b556-172">Ez különösen azt jelenti, hogy a `T` és a `R(PauliZ, PI() / 8, _)` csak a irreleváns [globális fázisban](xref:microsoft.quantum.glossary#global-phase)térnek el egymástól.</span><span class="sxs-lookup"><span data-stu-id="4b556-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="4b556-173">Emiatt a $T $ \frac{\pi}{8}$-Gate néven is ismert.</span><span class="sxs-lookup"><span data-stu-id="4b556-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="4b556-174">Vegye figyelembe azt is, hogy a `PauliI` körüli forgatás egyszerűen a $ \phi/$2 globális fázisát alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="4b556-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="4b556-175">Habár az ilyen fázisok nem relevánsak, ahogy azt [a fogalmi dokumentumok](xref:microsoft.quantum.concepts.qubit)is felmutatják, az ellenőrzött `PauliI` rotációk szempontjából fontosak.</span><span class="sxs-lookup"><span data-stu-id="4b556-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="4b556-176">A kvantum-algoritmusokon belül gyakran hasznos a rotációk dyadic-frakcióként való kimutatása, például a $ \phi = \pi k/2 ^ n $ használata néhány $k \in \mathbb{Z} $ és $n \in \mathbb{N} $ esetében.</span><span class="sxs-lookup"><span data-stu-id="4b556-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="4b556-177">A <xref:microsoft.quantum.intrinsic.rfrac> művelet egy megadott Pauli-tengely körüli rotációt valósít meg az egyezmény használatával.</span><span class="sxs-lookup"><span data-stu-id="4b556-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="4b556-178">Eltér a <xref:microsoft.quantum.intrinsic.r>tól, hogy az elforgatási szög két `Int`típusú bemenetként van megadva, dyadic-frakcióként értelmezve.</span><span class="sxs-lookup"><span data-stu-id="4b556-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="4b556-179">Így a `RFrac` aláírása `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-180">Implementálja az qubit egységes $ \exp (i \pi k \sigma/2 ^ n) $ értéket, ahol a $ \sigma $ az első argumentumnak megfelelő Pauli-mátrix, $k $ a második argumentum, és $n $ a harmadik argumentum.</span><span class="sxs-lookup"><span data-stu-id="4b556-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="4b556-181">`RFrac(_,k,n,_)` ugyanaz, mint `R(_,-πk/2^n,_)`; vegye figyelembe, hogy a szög a frakció *negatív* értéke.</span><span class="sxs-lookup"><span data-stu-id="4b556-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="4b556-182">A <xref:microsoft.quantum.intrinsic.rx> művelet egy rotációs műveletet valósít meg a Pauli $X $ tengely körül.</span><span class="sxs-lookup"><span data-stu-id="4b556-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="4b556-183">Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-184">`Rx(_, _)` ugyanaz, mint `R(PauliX, _, _)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="4b556-185">A <xref:microsoft.quantum.intrinsic.ry> művelet egy rotációs műveletet valósít meg a Pauli $Y $ tengely körül.</span><span class="sxs-lookup"><span data-stu-id="4b556-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="4b556-186">Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-187">`Ry(_, _)` ugyanaz, mint `R(PauliY,_ , _)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="4b556-188">A <xref:microsoft.quantum.intrinsic.rz> művelet egy rotációs műveletet valósít meg a Pauli $Z $ tengely körül.</span><span class="sxs-lookup"><span data-stu-id="4b556-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="4b556-189">Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-190">`Rz(_, _)` ugyanaz, mint `R(PauliZ, _, _)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="4b556-191">A <xref:microsoft.quantum.intrinsic.r1> művelet elforgatást hajt végre a megadott összeggel a $ \ket{1}$, a $-$1 eigenstate $Z $ értéknél.</span><span class="sxs-lookup"><span data-stu-id="4b556-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="4b556-192">Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-193">`R1(phi,_)` ugyanaz, mint `R(PauliZ,phi,_)`, majd `R(PauliI,-phi,_)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="4b556-194">A <xref:microsoft.quantum.intrinsic.r1frac> művelet egy tört forgást valósít meg a Z = 1 eigenstate körüli megadott összeggel.</span><span class="sxs-lookup"><span data-stu-id="4b556-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="4b556-195">Aláírása `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-196">`R1Frac(k,n,_)` ugyanaz, mint `RFrac(PauliZ,-k.n+1,_)`, majd `RFrac(PauliI,k,n+1,_)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="4b556-197">Alább látható egy példa egy rotációs műveletre (az ebben az esetben a Pauli $Z $ tengelyen, ebben a példányban), amely a Bloch szférára van leképezve:</span><span class="sxs-lookup"><span data-stu-id="4b556-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![A Bloch szférára leképezett rotációs művelet](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="4b556-199">Több Qubit műveletek</span><span class="sxs-lookup"><span data-stu-id="4b556-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="4b556-200">A fenti qubit műveletek mellett a Prelude számos több qubit műveletet is meghatároz.</span><span class="sxs-lookup"><span data-stu-id="4b556-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="4b556-201">Először is a <xref:microsoft.quantum.intrinsic.cnot> művelet elvégzi a szabványos vezérelt`NOT` kaput, a \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4b556-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="4b556-202">\end{Equation} aláírási `((Qubit, Qubit) => Unit is Adj + Ctl)`, ami azt jelenti, hogy a $ \operatorname{CNOT} $ unitarily két önálló qubits.</span><span class="sxs-lookup"><span data-stu-id="4b556-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="4b556-203">`CNOT(q1, q2)` ugyanaz, mint `(Controlled X)([q1], q2)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="4b556-204">Mivel a `Controlled`-kezelő lehetővé teszi a regisztrációt, a tömb literál `[q1]` használatával jelezheti, hogy csak az egyetlen vezérlőt szeretnénk használni.</span><span class="sxs-lookup"><span data-stu-id="4b556-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="4b556-205">A <xref:microsoft.quantum.intrinsic.ccnot> művelet kétszeresen vezérelt nem kaput hajt végre, néha Toffoli kapuként is ismert.</span><span class="sxs-lookup"><span data-stu-id="4b556-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="4b556-206">Aláírása `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-207">`CCNOT(q1, q2, q3)` ugyanaz, mint `(Controlled X)([q1, q2], q3)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="4b556-208">A <xref:microsoft.quantum.intrinsic.swap> művelet felcseréli két qubits Quantum állapotait.</span><span class="sxs-lookup"><span data-stu-id="4b556-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="4b556-209">Ez azt is megvalósítja, hogy implementálja az egységes mátrix \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4b556-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="4b556-210">\end{Equation} aláírása `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4b556-211">`SWAP(q1,q2)` egyenértékű a `CNOT(q1, q2)`, majd a `CNOT(q2, q1)` után `CNOT(q1, q2)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="4b556-212">A SWAP-kapu *nem* azonos a `Qubit[]`típusú változók elemeinek átrendezésével.</span><span class="sxs-lookup"><span data-stu-id="4b556-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="4b556-213">A `SWAP(q1, q2)` alkalmazása a `q1` és a `q2`által hivatkozott qubits állapotának módosítását eredményezi, míg `let swappedRegister = [q2, q1];` csak azt befolyásolja, hogyan hivatkozunk ezekre a qubits.</span><span class="sxs-lookup"><span data-stu-id="4b556-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="4b556-214">Emellett `(Controlled SWAP)([q0], (q1, q2))` lehetővé teszi, hogy a `SWAP` egy harmadik qubit állapotára lehessen felvenni, amelyet az elemek átrendezése nem jelenthet.</span><span class="sxs-lookup"><span data-stu-id="4b556-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="4b556-215">A vezérelt SWAP-kapu, más néven a Fredkin-kapu, elég erős ahhoz, hogy tartalmazza az összes klasszikus számítást.</span><span class="sxs-lookup"><span data-stu-id="4b556-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="4b556-216">Végül a Prelude két műveletet biztosít a több qubit Pauli-operátorok exponenciális ábrázolásához.</span><span class="sxs-lookup"><span data-stu-id="4b556-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="4b556-217">A <xref:microsoft.quantum.intrinsic.exp> művelet elforgatást hajt végre a Pauli-mátrixok egy tízes szorzata alapján. a többszörös qubit egységes \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), a \end{Equation}, ahol a $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ az egyetlen qubit Pauli-operátorok sorozata, és ahol a $ \phi $ egy szög.</span><span class="sxs-lookup"><span data-stu-id="4b556-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="4b556-218">A `Exp` forgás a $ \vec{\sigma} $ értéket jelöli `Pauli` elemek tömbje, például aláírási `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="4b556-219">A <xref:microsoft.quantum.intrinsic.expfrac> művelet ugyanazt a rotációs műveletet hajtja végre, a fentebb tárgyalt dyadic-frakciós jelölés használatával.</span><span class="sxs-lookup"><span data-stu-id="4b556-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="4b556-220">Aláírása `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="4b556-221">A Pauli-operátorok tenser-termékének exponenciális száma nem egyezik meg a Pauli-operátorok exponenciálisan működő termékeivel.</span><span class="sxs-lookup"><span data-stu-id="4b556-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="4b556-222">Vagyis $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="4b556-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="4b556-223">Mérések</span><span class="sxs-lookup"><span data-stu-id="4b556-223">Measurements</span></span> ###

<span data-ttu-id="4b556-224">A méréskor a mért operátor + 1 sajátérték `Zero` eredménynek felel meg, és az-1 sajátérték `One` eredmény.</span><span class="sxs-lookup"><span data-stu-id="4b556-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="4b556-225">Habár ez az egyezmény páratlannak tűnhet, két nagyon jó előnye van.</span><span class="sxs-lookup"><span data-stu-id="4b556-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="4b556-226">Először is, ha a $ \ket{0}$ értéket jelöli a `Result` érték `Zero`, a $ \ket{1}$ megfigyelve pedig `One`nak felel meg.</span><span class="sxs-lookup"><span data-stu-id="4b556-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="4b556-227">Másodszor, azt is kiírhatjuk, hogy a sajátérték $ \lambda $ megfelel egy eredménynek, $r $ értéke $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="4b556-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="4b556-228">A mérési műveletek sem a `Adjoint`, sem a `Controlled`-belit nem támogatják.</span><span class="sxs-lookup"><span data-stu-id="4b556-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="4b556-229">A <xref:microsoft.quantum.intrinsic.measure> művelet egy vagy több qubits együttes mérését hajtja végre a Pauli-operátorok megadott termékében.</span><span class="sxs-lookup"><span data-stu-id="4b556-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="4b556-230">Ha a Pauli tömb és a qubit tömb eltérő hosszúságú, akkor a művelet sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="4b556-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="4b556-231">`Measure` aláírása `((Pauli[], Qubit[]) => Result)`.</span><span class="sxs-lookup"><span data-stu-id="4b556-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="4b556-232">Vegye figyelembe, hogy a közös mérések nem egyeznek meg egyenként a qubit mérésével.</span><span class="sxs-lookup"><span data-stu-id="4b556-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="4b556-233">Tegyük fel például, hogy a $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$ értéket adja meg.</span><span class="sxs-lookup"><span data-stu-id="4b556-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="4b556-234">A $Z _0 $ és a $Z _1 $ mérése egyenként történik, $r _0 = $1 és $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="4b556-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="4b556-235">$Z _0 Z_1 $ mérésével azonban egyetlen eredmény $r _ {\textrm{Joint}} = $0, amely azt jelenti, hogy a $ \ket{11}$ párosítása pozitív.</span><span class="sxs-lookup"><span data-stu-id="4b556-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="4b556-236">Másképpen fogalmazva, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="4b556-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="4b556-237">Kritikus fontosságú, mivel *csak* a mértékből Tanuljuk meg a paritást, a 2 2 – qubit állapotú pozitív paritás, a $ \ket{00}$ és a $ \ket{11}$ közötti kapcsolatban szereplő kvantum-információk megmaradnak.</span><span class="sxs-lookup"><span data-stu-id="4b556-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="4b556-238">Ezt a tulajdonságot később kell megtekinteni, ahogy a hibajavításról van szó.</span><span class="sxs-lookup"><span data-stu-id="4b556-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="4b556-239">A kényelem érdekében a bevezetés két további műveletet is biztosít a qubits méréséhez.</span><span class="sxs-lookup"><span data-stu-id="4b556-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="4b556-240">Először is, mivel az qubit mérések végrehajtása meglehetősen gyakori, a bevezetés egy gyorsírást határoz meg ebben az esetben.</span><span class="sxs-lookup"><span data-stu-id="4b556-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="4b556-241">A <xref:microsoft.quantum.intrinsic.m> művelet a Pauli $Z $ operátort méri egyetlen qubit, és aláírási `(Qubit => Result)`rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="4b556-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="4b556-242">`M(q)` egyenértékű a `Measure([PauliZ], [q])`.</span><span class="sxs-lookup"><span data-stu-id="4b556-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="4b556-243">A <xref:microsoft.quantum.measurement.multim> a Pauli $Z $ operátort a qubits minden egyes tömbje számára *külön* méri, így az egyes qubit kapott `Result` értékek *tömbjét* adja vissza.</span><span class="sxs-lookup"><span data-stu-id="4b556-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="4b556-244">Bizonyos esetekben ez optimalizálható.</span><span class="sxs-lookup"><span data-stu-id="4b556-244">In some cases this can be optimized.</span></span> <span data-ttu-id="4b556-245">Aláírása (`Qubit[] => Result[])`.</span><span class="sxs-lookup"><span data-stu-id="4b556-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="4b556-246">`MultiM(qs)` egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="4b556-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="4b556-247">Bővítmény-függvények és-műveletek</span><span class="sxs-lookup"><span data-stu-id="4b556-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="4b556-248">Emellett a bevezetés a matematikai és a típusú átalakítási függvények gazdag készletét határozza meg a .NET-szinten a Q # kódban való használatra.</span><span class="sxs-lookup"><span data-stu-id="4b556-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="4b556-249">Például a <xref:microsoft.quantum.extensions.math> névtér olyan hasznos műveleteket határoz meg, mint például a <xref:microsoft.quantum.extensions.math.sin> és a <xref:microsoft.quantum.extensions.math.log>.</span><span class="sxs-lookup"><span data-stu-id="4b556-249">For instance, the <xref:microsoft.quantum.extensions.math> namespace defines useful operations such as <xref:microsoft.quantum.extensions.math.sin> and <xref:microsoft.quantum.extensions.math.log>.</span></span>
<span data-ttu-id="4b556-250">A Quantum Development Kit által biztosított implementáció a klasszikus .NET alaposztály-függvénytárat használja, így további kommunikációs kört eredményezhet a kvantum-programok és a klasszikus illesztőprogramjaik között.</span><span class="sxs-lookup"><span data-stu-id="4b556-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="4b556-251">Habár ez nem jelent problémát a helyi szimulátor esetében, ez a probléma akkor lehet teljesítményproblémák, ha távoli szimulátort vagy tényleges hardvert használ célként.</span><span class="sxs-lookup"><span data-stu-id="4b556-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="4b556-252">Ez azt is okozhatja, hogy az adott rendszer esetében az egyes célszámítógép befolyásolhatja a teljesítményt, ha felülbírálja ezeket a műveleteket az adott rendszeren hatékonyabb verziókkal.</span><span class="sxs-lookup"><span data-stu-id="4b556-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="4b556-253">Matematikai</span><span class="sxs-lookup"><span data-stu-id="4b556-253">Math</span></span> ###

<span data-ttu-id="4b556-254">A <xref:microsoft.quantum.extensions.math> névtér számos hasznos funkciót biztosít a .NET alaposztály könyvtárának [`System.Math` osztályában](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span><span class="sxs-lookup"><span data-stu-id="4b556-254">The <xref:microsoft.quantum.extensions.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="4b556-255">Ezek a függvények ugyanúgy használhatók, mint bármely más Q # függvény:</span><span class="sxs-lookup"><span data-stu-id="4b556-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="4b556-256">Ha a .NET statikus metódus túlterhelt az argumentumok típusa alapján, a megfelelő Q # függvényt a rendszer a bemenetének típusát jelző utótaggal jelöli meg:</span><span class="sxs-lookup"><span data-stu-id="4b556-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="4b556-257">Bitenkénti-műveletek</span><span class="sxs-lookup"><span data-stu-id="4b556-257">Bitwise Operations</span></span> ###

<span data-ttu-id="4b556-258">Végül a <xref:microsoft.quantum.extensions.bitwise> névtér számos hasznos függvényt biztosít az egész számok bitenkénti-operátoron keresztüli módosításához.</span><span class="sxs-lookup"><span data-stu-id="4b556-258">Finally, the <xref:microsoft.quantum.extensions.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="4b556-259">A <xref:microsoft.quantum.extensions.bitwise.parity> például egy egész szám bitenkénti paritását adja vissza egy másik egész számként.</span><span class="sxs-lookup"><span data-stu-id="4b556-259">For instance, <xref:microsoft.quantum.extensions.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
