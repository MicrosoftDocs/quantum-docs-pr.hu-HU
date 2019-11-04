---
title: Kvantum-áramkörök | Microsoft Docs
description: Kvantum-áramkörök
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210643"
---
# <a name="quantum-circuits"></a><span data-ttu-id="04860-103">Kvantum-áramkörök</span><span class="sxs-lookup"><span data-stu-id="04860-103">Quantum Circuits</span></span>
<span data-ttu-id="04860-104">Vegyünk egy pillanatra az egységes átalakítás $ \text{CNEM} _{01}(H\otimes 1) $ értéket.</span><span class="sxs-lookup"><span data-stu-id="04860-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="04860-105">Ez a kapui sorozat alapvető jelentőséggel bír a kvantum-számítástechnika szempontjából, mivel a két qubit állapotot hozza létre:</span><span class="sxs-lookup"><span data-stu-id="04860-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="04860-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="04860-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="04860-107">Az ezzel vagy nagyobb bonyolultsággal rendelkező műveletek a kvantum-algoritmusokban és a kvantum-hibák kijavításában mindenütt elérhetők, ezért nagy mértékű feltételnek kell lennie, hogy a vizualizációk *egy egyszerű*metódust használjanak.</span><span class="sxs-lookup"><span data-stu-id="04860-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="04860-108">A maximálisan kusza kvantum-állapot előkészítésének áramköri diagramja a következő:</span><span class="sxs-lookup"><span data-stu-id="04860-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="04860-109">A Quantum Circuit diagram konvenciói</span><span class="sxs-lookup"><span data-stu-id="04860-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="04860-110">A kvantum-műveletek vizuális nyelve könnyebben emészthető, mint a kvantum-kör kifejezésére vonatkozó konvenciók megismerése.</span><span class="sxs-lookup"><span data-stu-id="04860-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="04860-111">Az alábbi konvenciókat tekintjük át.</span><span class="sxs-lookup"><span data-stu-id="04860-111">We review these conventions below.</span></span>

<span data-ttu-id="04860-112">Egy áramköri diagramon minden egyes folytonos vonal egy qubit vagy általánosabban qubit-regisztrációt ábrázol.</span><span class="sxs-lookup"><span data-stu-id="04860-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="04860-113">Az egyezmény szerint a legfelső sor a $0 $ qubit-regisztráció, a maradék pedig szekvenciálisan van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="04860-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="04860-114">A fenti példában szereplő áramkör két qubits (vagy egy qubit álló, egymással egyenértékű két regiszterből áll) való működésként van ábrázolva.</span><span class="sxs-lookup"><span data-stu-id="04860-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="04860-115">Az egy vagy több qubit-regiszteren eljáró kapuk mezőként vannak kijelölve.</span><span class="sxs-lookup"><span data-stu-id="04860-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="04860-116">Például a szimbólum</span><span class="sxs-lookup"><span data-stu-id="04860-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="04860-117">a [Hadamard](xref:microsoft.quantum.primitive.h) -kapu egy qubit-regiszteren működik.</span><span class="sxs-lookup"><span data-stu-id="04860-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="04860-118">A Quantum Gates kronológiai sorrendben vannak rendezve a bal szélső kapuval, amelyet a kapu először alkalmaz a qubits.</span><span class="sxs-lookup"><span data-stu-id="04860-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="04860-119">Más szóval, ha a vezetékeket a kvantum-állapot tárolásával ábrázolja, a vezetékek a diagram minden kapuján balról jobbra helyezik a kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="04860-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="04860-120">Azaz</span><span class="sxs-lookup"><span data-stu-id="04860-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="04860-121">az egységes mátrix $CBA $.</span><span class="sxs-lookup"><span data-stu-id="04860-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="04860-122">A mátrix szorzása engedelmeskedik a szemközti konvenciónak: a jobb oldali mátrix először van alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="04860-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="04860-123">A Quantum Circuit-diagramoknál azonban először a bal szélső kaput alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="04860-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="04860-124">Ez a különbség időnként zavart eredményezhet, ezért fontos megjegyezni, hogy ez a különbség a lineáris algebrai jelölés és a kvantum-áramköri diagramok között jelentős.</span><span class="sxs-lookup"><span data-stu-id="04860-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="04860-125">A kvantum-áramkörök bemenetei és kimenetei</span><span class="sxs-lookup"><span data-stu-id="04860-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="04860-126">A megadott összes korábbi példa pontosan ugyanazokat a vezetékeket (qubits) adta hozzá a kvantum-kapuhoz, mint a kvantum-kapuból kimenő vezetékek száma.</span><span class="sxs-lookup"><span data-stu-id="04860-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="04860-127">Előfordulhat, hogy először úgy tűnik, hogy a kvantum-áramkörök több vagy kevesebb kimenettel rendelkeznek, mint általában a bemenetek.</span><span class="sxs-lookup"><span data-stu-id="04860-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="04860-128">Ez azonban nem lehetséges, mivel az összes kvantum-művelet, a mérték mentése, egységes és ezért reverzibilis.</span><span class="sxs-lookup"><span data-stu-id="04860-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="04860-129">Ha nem azonos számú kimenet szerepel a bemenetekben, nem vonhatók vissza, és így nem egységesek, ami ellentmond.</span><span class="sxs-lookup"><span data-stu-id="04860-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="04860-130">Ebben az esetben az áramköri diagramban rajzolt bármely mezőnek pontosan ugyanannyi drótot kell megadnia, mint kilép.</span><span class="sxs-lookup"><span data-stu-id="04860-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="04860-131">A multi-qubit áramköri diagramok hasonló konvenciókat követnek az qubit is.</span><span class="sxs-lookup"><span data-stu-id="04860-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="04860-132">Példaként meghatározhatunk egy kétqubites, egységes műveletet $B $-t a $ (H S\otimes X) $ értékre, és az áramkört egyenértékűként kell kifejezni</span><span class="sxs-lookup"><span data-stu-id="04860-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="04860-133">$B $-t úgy is megtekintheti, mintha egy qubit-regisztráción alapuló művelettel rendelkezik, és nem 2 1-qubit regisztrálja az áramkört használó környezettől függően.</span><span class="sxs-lookup"><span data-stu-id="04860-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="04860-134">Az absztrakt áramköri diagramok leghasznosabb tulajdonsága az, hogy lehetővé teszik, hogy a bonyolult kvantum-algoritmusokat magas szinten írják le anélkül, hogy le kellene őket állítani az alapvető kapuk számára.</span><span class="sxs-lookup"><span data-stu-id="04860-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="04860-135">Ez azt jelenti, hogy a nagyméretű kvantum-algoritmusok adatforgalmával kapcsolatban nem kell megismernie az algoritmus működésével kapcsolatos összes alrutin részleteit.</span><span class="sxs-lookup"><span data-stu-id="04860-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="04860-136">Vezérelt kapuk</span><span class="sxs-lookup"><span data-stu-id="04860-136">Controlled gates</span></span>
<span data-ttu-id="04860-137">A multi-qubit Quantum Circuit-diagramokba beépített másik összeállítás vezérli.</span><span class="sxs-lookup"><span data-stu-id="04860-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="04860-138">Egy olyan kvantum-vezérelt kapu művelete, amely a $ \Lambda (G) $ értéket jelöli, ahol egyetlen qubit érték vezérli $G $-t, a termék állapotára vonatkozó input $ \Lambda (G) következő példáját tekintheti meg (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="04860-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="04860-139">Ez azt jelenti, hogy az ellenőrzött kapu $G $ értéket alkalmaz a $ \psi $-t tartalmazó regisztrációra, és csak akkor, ha a vezérlő qubit $1 $ értékű.</span><span class="sxs-lookup"><span data-stu-id="04860-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="04860-140">Általánosságban leírjuk, hogy milyen ellenőrzött műveleteket kell elvégeznie az áramköri diagramokban</span><span class="sxs-lookup"><span data-stu-id="04860-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="04860-141">Itt a fekete kör azt a kvantum-bitet jelöli, amelyen a kapu vezérelhető, és a vertikális huzal azt jelöli, hogy a vezérlő qubit a $1 $ értéket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="04860-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="04860-142">Azon speciális esetekben, ahol $G = X $ és $G = Z $ bevezetjük a következő jelölést a kapuk ellenőrzött verziójának leírásához (vegye figyelembe, hogy a vezérelt X Gate a [$CNOT $ Gate](xref:microsoft.quantum.primitive.cnot)):</span><span class="sxs-lookup"><span data-stu-id="04860-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="04860-143">A Q # olyan metódusokat biztosít, amelyek automatikusan előállítják egy művelet ellenőrzött verzióját, amely elmenti a programozótól, hogy ezeket a műveleteket manuálisan kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="04860-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="04860-144">Alább látható egy példa:</span><span class="sxs-lookup"><span data-stu-id="04860-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="04860-145">Mérési operátor</span><span class="sxs-lookup"><span data-stu-id="04860-145">Measurement operator</span></span>
<span data-ttu-id="04860-146">Az áramköri diagramok megjelenítésének hátralévő művelete a mérés.</span><span class="sxs-lookup"><span data-stu-id="04860-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="04860-147">A mérés qubit regisztrálja, méri azt, és az eredményt klasszikus információként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="04860-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="04860-148">Egy mérőszám szimbóluma egy mérési műveletet jelöl, és mindig bemenetként fogadja a qubit-regisztrációt (ezt egy folytonos vonal jelöli), és a klasszikus információ kimeneteit (egy dupla vonallal jelöli).</span><span class="sxs-lookup"><span data-stu-id="04860-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="04860-149">Az ilyen alhálózatok például a következőkre hasonlítanak:</span><span class="sxs-lookup"><span data-stu-id="04860-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="04860-150">![mérési áramkör](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="04860-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="04860-151">A Q # erre a célra alkalmazza a [mérték kezelőjét](xref:microsoft.quantum.primitive.measure) .</span><span class="sxs-lookup"><span data-stu-id="04860-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="04860-152">További információt a [mérések című szakaszban](xref:microsoft.quantum.libraries.standard.prelude#measurements) talál.</span><span class="sxs-lookup"><span data-stu-id="04860-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="04860-153">Hasonlóképpen, az aláramkör</span><span class="sxs-lookup"><span data-stu-id="04860-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="04860-154">egy klasszikusan vezérelt kaput biztosít, ahol a $G $ a klasszikus vezérlési bit értéke $1 $.</span><span class="sxs-lookup"><span data-stu-id="04860-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="04860-155">Teleportáló áramköri diagram</span><span class="sxs-lookup"><span data-stu-id="04860-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="04860-156">A [kvantum-teleportáció](xref:microsoft.quantum.techniques.puttingittogether) talán a legjobb kvantum-algoritmus ezen összetevők szemléltetésére.</span><span class="sxs-lookup"><span data-stu-id="04860-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="04860-157">A kvantum-teleportáció az a módszer, amellyel a kvantum-számítógépeken (vagy akár a kvantum-hálózaton lévő távoli kvantum-számítógépek között) is áthelyezheti az adatátvitelt a felakadás és a mérés használatával.</span><span class="sxs-lookup"><span data-stu-id="04860-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="04860-158">Érdekes, hogy valójában képes a kvantum állapotának áthelyezésére, azaz egy adott qubit értékének egy qubit a másikra való átállítására, anélkül, hogy a qubit értékének megtudhatja.</span><span class="sxs-lookup"><span data-stu-id="04860-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="04860-159">Erre azért van szükség, hogy a protokoll a Quantum Mechanics törvényeinek megfelelően működjön.</span><span class="sxs-lookup"><span data-stu-id="04860-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="04860-160">A kvantum-teleportáció áramkört az alábbi szakasz ismerteti. az áramkör megjegyzésekkel ellátott verzióját is megadja, hogy bemutassa a kvantum-áramkör beolvasásának módját.</span><span class="sxs-lookup"><span data-stu-id="04860-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
