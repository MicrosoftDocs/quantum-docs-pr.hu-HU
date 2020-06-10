---
title: Quantum Computing – Szószedet
description: A Quantum computingban használt általános feltételek, műveletek és objektumok glosszáriuma.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630094"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="b84c4-103">Quantum Computing – Szószedet</span><span class="sxs-lookup"><span data-stu-id="b84c4-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="b84c4-104">Adjoint</span><span class="sxs-lookup"><span data-stu-id="b84c4-104">Adjoint</span></span>

<span data-ttu-id="b84c4-105">Egy [művelet](xref:microsoft.quantum.glossary#operation)összetett konjugált átültetése.</span><span class="sxs-lookup"><span data-stu-id="b84c4-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="b84c4-106">Az [egységes](xref:microsoft.quantum.glossary#unitary-operator) operátort megvalósító műveletek esetében a adjoint a művelet inverze, és egy tőr szimbólum jelzi.</span><span class="sxs-lookup"><span data-stu-id="b84c4-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="b84c4-107">Ha például a művelet `U` a $U egységes operátort jelöli $ , akkor a `Adjoint U` $U ^ \dagger jelöli $ .</span><span class="sxs-lookup"><span data-stu-id="b84c4-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="b84c4-108">További információ: [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="b84c4-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="b84c4-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="b84c4-109">Ancilla</span></span>

<span data-ttu-id="b84c4-110">Egy [qubit](xref:microsoft.quantum.glossary#qubit) , amely ideiglenes memóriát szolgál a kvantum-számítógép számára, és igény szerint le van foglalva és le van foglalva.</span><span class="sxs-lookup"><span data-stu-id="b84c4-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="b84c4-111">További információ: [több qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="b84c4-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="b84c4-112">Harang állapota</span><span class="sxs-lookup"><span data-stu-id="b84c4-112">Bell state</span></span>

<span data-ttu-id="b84c4-113">Két qubits négy specifikus, maximálisan [összekeverhető](xref:microsoft.quantum.glossary#entanglement) [Quantum állapotának](xref:microsoft.quantum.glossary#quantum-state) egyike.</span><span class="sxs-lookup"><span data-stu-id="b84c4-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="b84c4-114">A négy állapot definiálva van: $ \ket { \ beta_ {ij } } = (\Mathbb{I } \Otimes X ^ iZ ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="b84c4-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="b84c4-115">A Bell-állapotot [EPR-pároknak](xref:microsoft.quantum.glossary#epr-pair)is nevezzük.</span><span class="sxs-lookup"><span data-stu-id="b84c4-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="b84c4-116">Bloch gömb</span><span class="sxs-lookup"><span data-stu-id="b84c4-116">Bloch sphere</span></span>

<span data-ttu-id="b84c4-117">Egy[qubit](xref:microsoft.quantum.glossary#qubit) [kvantum-állapot](xref:microsoft.quantum.glossary#quantum-state) grafikus ábrázolása egy háromdimenziós egység gömb elemeként.</span><span class="sxs-lookup"><span data-stu-id="b84c4-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="b84c4-118">További információ: [qubits és átalakítások megjelenítése a Bloch szférával](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="b84c4-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="b84c4-119">Használata hívható</span><span class="sxs-lookup"><span data-stu-id="b84c4-119">Callable</span></span>

<span data-ttu-id="b84c4-120">Egy [művelet](xref:microsoft.quantum.glossary#operation) vagy [függvény](xref:microsoft.quantum.glossary#function) a Q # nyelven.</span><span class="sxs-lookup"><span data-stu-id="b84c4-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="b84c4-121">További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b84c4-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="b84c4-122">Clifford-csoport</span><span class="sxs-lookup"><span data-stu-id="b84c4-122">Clifford group</span></span>

<span data-ttu-id="b84c4-123">Azok a műveletek [összessége, amelyek](xref:microsoft.quantum.glossary#bloch-sphere) elfoglalják a octants és a [Pauli-operátorok](xref:microsoft.quantum.glossary#pauli-operators)hatását.</span><span class="sxs-lookup"><span data-stu-id="b84c4-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="b84c4-124">Ezek közé tartoznak az Operations [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z), [$H $ ](xref:microsoft.quantum.intrinsic.h) és [$S $ ](xref:microsoft.quantum.intrinsic.s).</span><span class="sxs-lookup"><span data-stu-id="b84c4-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="b84c4-125">Ellenőrzött</span><span class="sxs-lookup"><span data-stu-id="b84c4-125">Controlled</span></span>

<span data-ttu-id="b84c4-126">Olyan Quantum [művelet](xref:microsoft.quantum.glossary#operation) , amely egy vagy több [qubits](xref:microsoft.quantum.glossary#qubit) használ a cél művelethez.</span><span class="sxs-lookup"><span data-stu-id="b84c4-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="b84c4-127">További információ: [ellenőrzött és adjoint műveletek](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="b84c4-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="b84c4-128">Dirac jelölése</span><span class="sxs-lookup"><span data-stu-id="b84c4-128">Dirac Notation</span></span>

<span data-ttu-id="b84c4-129">Egy szimbolikus Gyorsírás, amely leegyszerűsíti a [kvantum-állapotok](xref:microsoft.quantum.glossary#quantum-state), más néven a *Bra-ket* jelölések megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="b84c4-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="b84c4-130">A *melltartó* része egy sor vektort jelöl, például: $ \bra{A } = \begin{ bmatrix } a {_1 } & a {_2 } \end{$, bmatrix } és a *ket* rész egy oszlop vektort jelöl, $ \ket{B } = \begin{ bmatrix } b {_1 } \\ \\ b {_2 } \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="b84c4-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="b84c4-131">További információ: Dirac- [jelölés](xref:microsoft.quantum.concepts.dirac).</span><span class="sxs-lookup"><span data-stu-id="b84c4-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="b84c4-132">Sajátérték</span><span class="sxs-lookup"><span data-stu-id="b84c4-132">Eigenvalue</span></span>

<span data-ttu-id="b84c4-133">Az a tényező, amellyel egy adott átalakítás [eigenvector](xref:microsoft.quantum.glossary#eigenvector) nagysága megváltozik az átalakítás alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="b84c4-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="b84c4-134">Egy négyzetes mátrix $M $ és egy eigenvector $v $ , majd $MV = CV $ , ahol $c $ a sajátérték, és az argumentumok összetett száma lehet.</span><span class="sxs-lookup"><span data-stu-id="b84c4-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="b84c4-135">További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="b84c4-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="b84c4-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="b84c4-136">Eigenvector</span></span>

<span data-ttu-id="b84c4-137">Egy olyan vektor, amelynek irányát egy adott átalakítás nem változtatja meg, és amelynek nagyságrendjét a vektor [sajátérték](xref:microsoft.quantum.glossary#eigenvalue)megfelelő tényező módosítja.</span><span class="sxs-lookup"><span data-stu-id="b84c4-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="b84c4-138">A négyzetes mátrix $M $ és egy sajátérték $c $ , majd $MV = CV $ , ahol $ a $v a mátrix eigenvector, és az argumentumok összetett száma lehet.</span><span class="sxs-lookup"><span data-stu-id="b84c4-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="b84c4-139">További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="b84c4-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="b84c4-140">Összefonódás</span><span class="sxs-lookup"><span data-stu-id="b84c4-140">Entanglement</span></span>

<span data-ttu-id="b84c4-141">A *kvantum-részecskék* (például a [qubits](xref:microsoft.quantum.glossary#qubit)) csatlakoztathatók vagy összekapcsolhatók úgy, hogy ne legyenek egymástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="b84c4-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="b84c4-142">A mérési eredmények akkor is összekapcsolhatók, ha a rendszer végtelenül elválasztja őket.</span><span class="sxs-lookup"><span data-stu-id="b84c4-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="b84c4-143">A felakadás elengedhetetlen a qubit [állapotának](xref:microsoft.quantum.glossary#quantum-state) [méréséhez](xref:microsoft.quantum.glossary#measurement) .</span><span class="sxs-lookup"><span data-stu-id="b84c4-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="b84c4-144">További információ: [speciális mátrix – fogalmak](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="b84c4-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="b84c4-145">EPR pár</span><span class="sxs-lookup"><span data-stu-id="b84c4-145">EPR pair</span></span>

<span data-ttu-id="b84c4-146">Két [qubits](xref:microsoft.quantum.glossary#qubit)négy specifikus, maximálisan összekeverhető [Quantum állapotának](xref:microsoft.quantum.glossary#quantum-state) egyike.</span><span class="sxs-lookup"><span data-stu-id="b84c4-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="b84c4-147">A négy állapot definiálva van: $ \ket { \ beta_ {ij } } = (\Mathbb{1 } \Otimes X ^ iZ ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="b84c4-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="b84c4-148">Egy EPR pár más néven [Bell-állapot](xref:microsoft.quantum.glossary#bell-state)</span><span class="sxs-lookup"><span data-stu-id="b84c4-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="b84c4-149">Evolution</span><span class="sxs-lookup"><span data-stu-id="b84c4-149">Evolution</span></span>

<span data-ttu-id="b84c4-150">A [kvantum-állapot](xref:microsoft.quantum.glossary#quantum-state) időbeli változásának módja.</span><span class="sxs-lookup"><span data-stu-id="b84c4-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="b84c4-151">További információ: [mátrix exponenciálisok](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span><span class="sxs-lookup"><span data-stu-id="b84c4-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="b84c4-152">Függvény</span><span class="sxs-lookup"><span data-stu-id="b84c4-152">Function</span></span>
<span data-ttu-id="b84c4-153">A Q # nyelvben található, tisztán klasszikus (nem Quantum) típusú alrutin.</span><span class="sxs-lookup"><span data-stu-id="b84c4-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="b84c4-154">Míg a függvények a kvantum-algoritmusokon belül vannak használatban, nem működhetnek [qubits](xref:microsoft.quantum.glossary#qubit) vagy hívási [műveleteken](xref:microsoft.quantum.glossary#operation).</span><span class="sxs-lookup"><span data-stu-id="b84c4-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="b84c4-155">További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b84c4-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="b84c4-156">Kapu</span><span class="sxs-lookup"><span data-stu-id="b84c4-156">Gate</span></span>

<span data-ttu-id="b84c4-157">Egy kvantum- [művelet](xref:microsoft.quantum.glossary#operation)örökölt kifejezése a klasszikus logikai kapuk fogalma alapján.</span><span class="sxs-lookup"><span data-stu-id="b84c4-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="b84c4-158">A [kvantum-áramkör](xref:microsoft.quantum.glossary#quantum-circuit-diagram) a klasszikus logikai áramkörök hasonló fogalma alapján kapuk (vagy műveletek) hálózata.</span><span class="sxs-lookup"><span data-stu-id="b84c4-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="b84c4-159">Globális fázis</span><span class="sxs-lookup"><span data-stu-id="b84c4-159">Global phase</span></span>

<span data-ttu-id="b84c4-160">Ha két [állapot](xref:microsoft.quantum.glossary#quantum-state) megegyezik egy összetett szám többszörösével, $e ^ {i \phi } $, azt mondják, hogy eltérnek a globális fázistól.</span><span class="sxs-lookup"><span data-stu-id="b84c4-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="b84c4-161">A helyi fázisokkal ellentétben a globális fázisok nem figyelhetők meg semmilyen [méréssel](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="b84c4-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="b84c4-162">További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="b84c4-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="b84c4-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="b84c4-163">Hadamard</span></span>

<span data-ttu-id="b84c4-164">A Hadamard művelet (más néven Hadamard-kapu vagy átalakító) egyetlen [qubit](xref:microsoft.quantum.glossary#qubit) viselkedik, és a $ \ket{0 $ vagy $ \ket{1 $ páros [pozícióba](xref:microsoft.quantum.glossary#superposition) helyezi, } } Ha a qubit kezdetben $ \ket{0 } $ állapotban van.</span><span class="sxs-lookup"><span data-stu-id="b84c4-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="b84c4-165">A Q # esetében ezt a műveletet az előre definiált művelet alkalmazza [`H`](xref:microsoft.quantum.intrinsic.h) .</span><span class="sxs-lookup"><span data-stu-id="b84c4-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="b84c4-166">Nem módosítható</span><span class="sxs-lookup"><span data-stu-id="b84c4-166">Immutable</span></span>

<span data-ttu-id="b84c4-167">Olyan változó, amelynek értéke nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="b84c4-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="b84c4-168">A Q #-ban egy nem módosítható változó jön létre a `let` kulcsszó használatával.</span><span class="sxs-lookup"><span data-stu-id="b84c4-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="b84c4-169">A *módosítható* változók bejelentéséhez használja a [változékony](xref:microsoft.quantum.glossary#immutable) kulcsszót a bevalláshoz, és a `set` kulcsszót az érték módosításához.</span><span class="sxs-lookup"><span data-stu-id="b84c4-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="b84c4-170">Mérés</span><span class="sxs-lookup"><span data-stu-id="b84c4-170">Measurement</span></span>

<span data-ttu-id="b84c4-171">A megfigyelés eredményét eredményező [qubit](xref:microsoft.quantum.glossary#qubit) (vagy qubits-készlet) manipulációja, amely a klasszikus bitek beszerzését eredményezi.</span><span class="sxs-lookup"><span data-stu-id="b84c4-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="b84c4-172">További információ: [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span><span class="sxs-lookup"><span data-stu-id="b84c4-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="b84c4-173">Változtatható</span><span class="sxs-lookup"><span data-stu-id="b84c4-173">Mutable</span></span>

<span data-ttu-id="b84c4-174">Egy változó, amelynek az értéke a létrehozása után módosítható.</span><span class="sxs-lookup"><span data-stu-id="b84c4-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="b84c4-175">A Q # változóban változtatható változót a kulcsszó használatával kell deklarálni, `mutable` és a kulcsszó használatával kell módosítani `set` .</span><span class="sxs-lookup"><span data-stu-id="b84c4-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="b84c4-176">A `let` kulcsszóval létrehozott változók nem [változtathatók](xref:microsoft.quantum.glossary#immutable) meg, és az értékük nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="b84c4-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="b84c4-177">Névtér</span><span class="sxs-lookup"><span data-stu-id="b84c4-177">Namespace</span></span>

<span data-ttu-id="b84c4-178">A kapcsolódó nevek (például [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function)és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type)) gyűjteményének címkéje.</span><span class="sxs-lookup"><span data-stu-id="b84c4-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="b84c4-179">A [Microsoft. Quantum.](xref:microsoft.quantum.preparation) a névtér például a standard könyvtárban definiált összes szimbólumot felcímkézi a kezdeti állapotok előkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b84c4-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="b84c4-180">Művelet</span><span class="sxs-lookup"><span data-stu-id="b84c4-180">Operation</span></span>

<span data-ttu-id="b84c4-181">A Quantum végrehajtás alapegysége a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="b84c4-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="b84c4-182">Ez nagyjából megfelel a C, C++ vagy Python függvénynek, illetve a C# vagy a Java statikus metódusának.</span><span class="sxs-lookup"><span data-stu-id="b84c4-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="b84c4-183">További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b84c4-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="b84c4-184">Kezelő alkalmazás</span><span class="sxs-lookup"><span data-stu-id="b84c4-184">Operator application</span></span>

<span data-ttu-id="b84c4-185">Quantum művelet végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="b84c4-185">Performing a quantum operation.</span></span> <span data-ttu-id="b84c4-186">Ez általában egy egységes mátrixot alkalmaz az aktuális kvantum-állapot vektorára.</span><span class="sxs-lookup"><span data-stu-id="b84c4-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="b84c4-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="b84c4-187">Oracle</span></span>

<span data-ttu-id="b84c4-188">Egy olyan alrutin, amely Adatfüggő adatokat biztosít a kvantum-algoritmusnak futásidőben.</span><span class="sxs-lookup"><span data-stu-id="b84c4-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="b84c4-189">A cél az, hogy a kimenetek [a](xref:microsoft.quantum.glossary#superposition) helyükön lévő bemeneteknek megfelelő kimenetet adjanak.</span><span class="sxs-lookup"><span data-stu-id="b84c4-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="b84c4-190">További információ: [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span><span class="sxs-lookup"><span data-stu-id="b84c4-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="b84c4-191">Részleges alkalmazás</span><span class="sxs-lookup"><span data-stu-id="b84c4-191">Partial application</span></span>

<span data-ttu-id="b84c4-192">[Függvény](xref:microsoft.quantum.glossary#function) vagy [művelet](xref:microsoft.quantum.glossary#operation) hívása az összes szükséges bemenet nélkül.</span><span class="sxs-lookup"><span data-stu-id="b84c4-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="b84c4-193">Ez egy új [meghívót](xref:microsoft.quantum.glossary#callable) ad vissza, amely csak a hiányzó (aláhúzásjel által jelzett) paramétereket adja meg, amelyeket egy későbbi alkalmazásban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="b84c4-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="b84c4-194">Például a függvény `MyFunc(x : int, y : int) : int {return x + y;}` használatával részben alkalmazhat egy új függvényt `let NewFunc = MyFunc(_, 3)` .</span><span class="sxs-lookup"><span data-stu-id="b84c4-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="b84c4-195">Az új függvényt később is meghívhatja a hiányzó paraméterrel, `NewFunc(2)` amely az *5*értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b84c4-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="b84c4-196">További információ: [részleges alkalmazás](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span><span class="sxs-lookup"><span data-stu-id="b84c4-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="b84c4-197">Pauli-operátorok</span><span class="sxs-lookup"><span data-stu-id="b84c4-197">Pauli operators</span></span>

<span data-ttu-id="b84c4-198">Három 2 x 2 egységes mátrix, azaz a `X` `Y` és a `Z` Quantum művelet.</span><span class="sxs-lookup"><span data-stu-id="b84c4-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="b84c4-199">Az Identity Matrix, $I $ , is gyakran szerepel a készletben is.</span><span class="sxs-lookup"><span data-stu-id="b84c4-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="b84c4-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="b84c4-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="b84c4-201">További információ: [qubit műveletek](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="b84c4-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="b84c4-202">Quantum Circuit diagram</span><span class="sxs-lookup"><span data-stu-id="b84c4-202">Quantum circuit diagram</span></span>

<span data-ttu-id="b84c4-203">Egy módszer, amely grafikusan ábrázolja az egyszerű kvantum-programok [műveleteinek](xref:microsoft.quantum.glossary#operation) (vagy [kapuinak](xref:microsoft.quantum.glossary#gate)) sorozatot, például:</span><span class="sxs-lookup"><span data-stu-id="b84c4-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![Minta áramköri diagram](~/media/qpe.png)<span data-ttu-id="b84c4-205">.</span><span class="sxs-lookup"><span data-stu-id="b84c4-205">.</span></span> 

<span data-ttu-id="b84c4-206">További információ: kvantum- [áramkörök](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="b84c4-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="b84c4-207">Kvantum-kódtárak</span><span class="sxs-lookup"><span data-stu-id="b84c4-207">Quantum libraries</span></span>

<span data-ttu-id="b84c4-208">A Q # programok létrehozásához használható [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) gyűjteményei.</span><span class="sxs-lookup"><span data-stu-id="b84c4-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="b84c4-209">A [standard szintű függvénytár](xref:microsoft.quantum.libraries.standard.intro) alapértelmezés szerint telepítve van.</span><span class="sxs-lookup"><span data-stu-id="b84c4-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="b84c4-210">A rendelkezésre álló további könyvtárak a [kémiai könyvtár](xref:microsoft.quantum.chemistry.concepts.intro), a [numerikus könyvtár](xref:microsoft.quantum.numerics.intro) és a [Machine learning-könyvtár](xref:microsoft.quantum.machine-learning.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="b84c4-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="b84c4-211">Kvantum állapota</span><span class="sxs-lookup"><span data-stu-id="b84c4-211">Quantum state</span></span>

<span data-ttu-id="b84c4-212">Egy elkülönített kvantumrendszer pontos állapota, amelyből kinyerhető a [mérési](xref:microsoft.quantum.glossary#measurement) valószínűség.</span><span class="sxs-lookup"><span data-stu-id="b84c4-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="b84c4-213">A Quantum Computing használatával a Quantum Simulator ezt az információt használja annak szimulálása érdekében, hogy a qubits hogyan válaszolnak a műveletekre.</span><span class="sxs-lookup"><span data-stu-id="b84c4-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="b84c4-214">További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="b84c4-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="b84c4-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="b84c4-215">Qubit</span></span>

<span data-ttu-id="b84c4-216">A kvantum-információk alapszintű egysége, amely *a klasszikus* számítástechnikai funkciókhoz hasonlít.</span><span class="sxs-lookup"><span data-stu-id="b84c4-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="b84c4-217">További információ: [Qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="b84c4-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="b84c4-218">Ismétlés a sikerig</span><span class="sxs-lookup"><span data-stu-id="b84c4-218">Repeat-until-success</span></span>

<span data-ttu-id="b84c4-219">A probabilistically által sikeresnek bizonyuló kvantum-algoritmus.</span><span class="sxs-lookup"><span data-stu-id="b84c4-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="b84c4-220">Hiba esetén a rutin újra próbálkozik, amíg a művelet sikertelen lesz (vagy elérte a korlátot).</span><span class="sxs-lookup"><span data-stu-id="b84c4-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="b84c4-221">További információ: REPEAT to [Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="b84c4-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="b84c4-222">Szabványos kódtárak</span><span class="sxs-lookup"><span data-stu-id="b84c4-222">Standard libraries</span></span>

<span data-ttu-id="b84c4-223">A telepítés során a Q # fordítóprogrammal együtt telepített [műveletek](xref:microsoft.quantum.glossary#operation), [függvények](xref:microsoft.quantum.glossary#function) és [felhasználó által definiált típusok](xref:microsoft.quantum.glossary#user-defined-type) .</span><span class="sxs-lookup"><span data-stu-id="b84c4-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="b84c4-224">A standard szintű függvénytár-implementáció agnosztikus a célszámítógépek tekintetében.</span><span class="sxs-lookup"><span data-stu-id="b84c4-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="b84c4-225">További információ: [standard könyvtárak](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="b84c4-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="b84c4-226">Szuperpozíció</span><span class="sxs-lookup"><span data-stu-id="b84c4-226">Superposition</span></span>

<span data-ttu-id="b84c4-227">A Quantum Computing koncepciója, amely szerint a [qubit](xref:microsoft.quantum.glossary#qubit) két állapot lineáris kombinációja, $ \ket{0 } $ és $ \ket{1 } $, amíg meg nem történik a [mérés](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="b84c4-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="b84c4-228">További információ: a [kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="b84c4-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="b84c4-229">Célszámítógép</span><span class="sxs-lookup"><span data-stu-id="b84c4-229">Target machine</span></span>

<span data-ttu-id="b84c4-230">Fordítási cél, amely egy absztrakt kvantum-programot csökkenti a hardver vagy a szimuláció irányába.</span><span class="sxs-lookup"><span data-stu-id="b84c4-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="b84c4-231">Ez általában számos célra, például a kapu cseréjére, a hibajavítások kódolására, a geometriai elrendezésre és egyebekre vonatkozó újraírásokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b84c4-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="b84c4-232">További információ: [Quantum simulators and Host Applications](xref:microsoft.quantum.machines).</span><span class="sxs-lookup"><span data-stu-id="b84c4-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="b84c4-233">Teleportáció</span><span class="sxs-lookup"><span data-stu-id="b84c4-233">Teleportation</span></span>

<span data-ttu-id="b84c4-234">Az egyik [qubit](xref:microsoft.quantum.glossary#qubit) az adatok vagy a kvantum- [állapotok](xref:microsoft.quantum.glossary#quantum-state)egy helyről a másikra való újragenerálásának módszere a qubit fizikai áthelyezése nélkül a [felakadás](xref:microsoft.quantum.glossary#entanglement) és a [mérés](xref:microsoft.quantum.glossary#measurement)használatával.</span><span class="sxs-lookup"><span data-stu-id="b84c4-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="b84c4-235">További információ: a [kvantum-áramkörök](xref:microsoft.quantum.concepts.circuits) és a megfelelő Kata a [Quantum katas](xref:microsoft.quantum.overview.katas)szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="b84c4-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="b84c4-236">Rekord</span><span class="sxs-lookup"><span data-stu-id="b84c4-236">Tuple</span></span>

<span data-ttu-id="b84c4-237">Vesszővel tagolt értékek gyűjteménye, amely egyetlen értékként viselkedik.</span><span class="sxs-lookup"><span data-stu-id="b84c4-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="b84c4-238">A rekord *típusát* a benne található értékek típusai határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="b84c4-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="b84c4-239">A Q #- [ban a rekordok](xref:microsoft.quantum.glossary#immutable) nem módosítható, és beágyazható, tömböket tartalmazhat, vagy egy tömbben használható.</span><span class="sxs-lookup"><span data-stu-id="b84c4-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="b84c4-240">További információ: a [rekord típusai](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="b84c4-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="b84c4-241">Egységes operátor</span><span class="sxs-lookup"><span data-stu-id="b84c4-241">Unitary operator</span></span>

<span data-ttu-id="b84c4-242">Egy operátor, amelynek inverze egyenlő a [adjoint](xref:microsoft.quantum.glossary#adjoint), azaz $uu ^ {\dagger } = \id $ .</span><span class="sxs-lookup"><span data-stu-id="b84c4-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="b84c4-243">Felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="b84c4-243">User-defined type</span></span>

<span data-ttu-id="b84c4-244">Beépített vagy korábban definiált típusok gyűjteménye, amelyek egyetlen egységként is szerepelhetnek.</span><span class="sxs-lookup"><span data-stu-id="b84c4-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="b84c4-245">További információ: [felhasználó által definiált típusok](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="b84c4-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>