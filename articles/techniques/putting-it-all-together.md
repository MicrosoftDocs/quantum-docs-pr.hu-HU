---
title: 'Az összes együttes üzembe helyezése – Q # technikák | Microsoft Docs'
description: 'Az összes egyesítése – Q # technikák'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820164"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="dc065-103">Az összes egyesítése: teleportáció</span><span class="sxs-lookup"><span data-stu-id="dc065-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="dc065-104">Térjen vissza a [kvantum-áramkörökben](xref:microsoft.quantum.concepts.circuits)definiált teleportáció-kör példára.</span><span class="sxs-lookup"><span data-stu-id="dc065-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="dc065-105">Ezt az eddig megtanult fogalmak szemléltetésére fogjuk használni.</span><span class="sxs-lookup"><span data-stu-id="dc065-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="dc065-106">A Quantum teleportáció magyarázatát alább találja azok számára, akik nem ismerik az elméletet, majd a kód megvalósításának bemutatóját a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="dc065-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="dc065-107">Quantum teleportáció: elmélet</span><span class="sxs-lookup"><span data-stu-id="dc065-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="dc065-108">A kvantum-teleportáció olyan technika, amely egy ismeretlen kvantum-állapot küldését teszi elérhetővé (amit "__üzenetnek__" nevezünk) egy adott helyen lévő qubit egy másik helyen lévő qubit (ezt a qubits a "Here" és a "__here__"kifejezéssel tekintjük meg).</span><span class="sxs-lookup"><span data-stu-id="dc065-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="dc065-109">Az Dirac-jelölést használó vektorként az __üzenetet__ is képviseljük:</span><span class="sxs-lookup"><span data-stu-id="dc065-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="dc065-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="dc065-111">Az __üzenet__ qubit ismeretlen a számunkra, mert nem tudjuk a $ \alpha $ és a $ \beta $ értékeit.</span><span class="sxs-lookup"><span data-stu-id="dc065-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="dc065-112">1\. lépés: kusza állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="dc065-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="dc065-113">Ahhoz, hogy el lehessen küldeni az __üzenetet__ , a qubit __itt__ kell összekeverni __a qubit.__</span><span class="sxs-lookup"><span data-stu-id="dc065-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="dc065-114">Ez egy Hadamard-kapu, majd egy CNEM-kapu után érhető el.</span><span class="sxs-lookup"><span data-stu-id="dc065-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="dc065-115">Nézzük meg a kapu műveletei mögötti matematikai műveleteket.</span><span class="sxs-lookup"><span data-stu-id="dc065-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="dc065-116">A qubits __itt__ és a $ \ket{0}$ __állapotban is__ megkezdődik.</span><span class="sxs-lookup"><span data-stu-id="dc065-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="dc065-117">A qubits összekeverve a következő állapotban vannak:</span><span class="sxs-lookup"><span data-stu-id="dc065-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="dc065-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="dc065-119">2\. lépés: az üzenet elküldése</span><span class="sxs-lookup"><span data-stu-id="dc065-119">Step 2: Send the message</span></span>
<span data-ttu-id="dc065-120">Az __üzenet__ elküldéséhez először alkalmazzon egy cnem-kaput az __üzenet__ qubit, és __itt__ qubit bemenetként (az __üzenet__ qubit, amely a vezérlő __, a qubit pedig a cél__ qubit, ebben a példányban).</span><span class="sxs-lookup"><span data-stu-id="dc065-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="dc065-121">Ezt a bemeneti állapotot lehet írni:</span><span class="sxs-lookup"><span data-stu-id="dc065-121">This input state can be written:</span></span>

<span data-ttu-id="dc065-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="dc065-123">Ez a következőre bővül:</span><span class="sxs-lookup"><span data-stu-id="dc065-123">This expands to:</span></span>

<span data-ttu-id="dc065-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="dc065-125">Emlékeztetőként a CNEM-kapu megfordítja a cél qubit, amikor a vezérlő qubit értéke 1.</span><span class="sxs-lookup"><span data-stu-id="dc065-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="dc065-126">Így például a $ \ket{000}$ bemenet nem változik, mert az első qubit (a vezérlő) 0.</span><span class="sxs-lookup"><span data-stu-id="dc065-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="dc065-127">Azonban tegyük fel, hogy az első qubit 1 – például a $ \ket{100}$ bemenet.</span><span class="sxs-lookup"><span data-stu-id="dc065-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="dc065-128">Ebben az esetben a kimenet a $ \ket{110}$, mivel a második qubit (a cél) a CNEM-kapu tükrözött.</span><span class="sxs-lookup"><span data-stu-id="dc065-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="dc065-129">Most nézzük meg a kimenetet, ha a CNEM kapu a fenti bemeneten működött.</span><span class="sxs-lookup"><span data-stu-id="dc065-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="dc065-130">Az eredmény a következőket eredményezi:</span><span class="sxs-lookup"><span data-stu-id="dc065-130">The result is:</span></span>

<span data-ttu-id="dc065-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="dc065-132">Az __üzenet__ elküldésének következő lépése egy Hadamard-kapu alkalmazása az __üzenet__ qubit (ez az egyes kifejezések első qubit).</span><span class="sxs-lookup"><span data-stu-id="dc065-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="dc065-133">Emlékeztetőként a Hadamard Gate a következő műveleteket végzi el:</span><span class="sxs-lookup"><span data-stu-id="dc065-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="dc065-134">Input (Bemenet)</span><span class="sxs-lookup"><span data-stu-id="dc065-134">Input</span></span> | <span data-ttu-id="dc065-135">Kimenet</span><span class="sxs-lookup"><span data-stu-id="dc065-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="dc065-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="dc065-136">$\ket{0}$</span></span>  | <span data-ttu-id="dc065-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="dc065-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="dc065-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="dc065-138">$\ket{1}$</span></span>  | <span data-ttu-id="dc065-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="dc065-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="dc065-140">Ha a Hadamard kaput a fenti kimenet minden egyes időszakának első qubit alkalmazza, a következő eredményt értjük:</span><span class="sxs-lookup"><span data-stu-id="dc065-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="dc065-141">$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="dc065-142">Vegye figyelembe, hogy az egyes feltételek $2 \frac{1}{\sqrt{2}} $ tényezővel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="dc065-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="dc065-143">Ezeket az eredményeket a következő eredmény megadásával tudjuk megszorozni:</span><span class="sxs-lookup"><span data-stu-id="dc065-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="dc065-144">$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="dc065-145">A $ \frac{1}{2}$ Factor az egyes kifejezések esetében közös, így most már a zárójeleken kívül is elhelyezhetők:</span><span class="sxs-lookup"><span data-stu-id="dc065-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="dc065-146">$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="dc065-147">Ezután a zárójeleket a következő kifejezésekkel szorozva adhatja meg:</span><span class="sxs-lookup"><span data-stu-id="dc065-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="dc065-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="dc065-149">3\. lépés: az eredmény mérése</span><span class="sxs-lookup"><span data-stu-id="dc065-149">Step 3: Measure the result</span></span>

<span data-ttu-id="dc065-150">Mivel __itt__ van, és __nincs__ összekeverve, a mérések __itt__ is hatással __lesznek.__</span><span class="sxs-lookup"><span data-stu-id="dc065-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="dc065-151">Ha mérjük az első és a második qubit (__üzenet__ és __itt__), megtudhatjuk, __milyen állapotban van a-__ ben, a felakadás ezen tulajdonsága miatt.</span><span class="sxs-lookup"><span data-stu-id="dc065-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="dc065-152">Ha méri és lekéri a 00 értéket, a rendszer összecsukja az eredményt, így csak a feltételek konzisztensek.</span><span class="sxs-lookup"><span data-stu-id="dc065-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="dc065-153">Ez a $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="dc065-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="dc065-154">Ez a $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $ értékre állítható át.</span><span class="sxs-lookup"><span data-stu-id="dc065-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="dc065-155">Ezért ha az első és második qubit 00-ra mérjük, __tudjuk, hogy__a harmadik qubit a következő állapotban van: $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="dc065-156">Ha a rendszer kiértékeli és beolvassa az eredmény 01 értéket, a rendszer összecsukja az eredményt, így csak a feltételek konzisztensek.</span><span class="sxs-lookup"><span data-stu-id="dc065-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="dc065-157">Ez a $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="dc065-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="dc065-158">Ez a $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $ értékre állítható át.</span><span class="sxs-lookup"><span data-stu-id="dc065-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="dc065-159">Ezért ha az első és második qubit 01-re mérjük, __tudjuk, hogy__a harmadik qubit a következő állapotban van: $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="dc065-160">Ha mérjük és megkapjuk a 10. eredményt, a rendszer összeomlik, és csak az ezzel az eredménnyel konzisztens kifejezéseket hagyja.</span><span class="sxs-lookup"><span data-stu-id="dc065-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="dc065-161">Ez a $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="dc065-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="dc065-162">Ezt a $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $ értékre lehet átvenni.</span><span class="sxs-lookup"><span data-stu-id="dc065-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="dc065-163">Ezért __, ha__az első és második qubit 10 értékre mérjük, tudjuk, hogy a harmadik qubit a következő állapotban van: $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="dc065-164">Ha mérjük és beolvasjuk a 11. eredményt, a rendszer Összecsukja a feltételt, és csak az ezzel az eredménnyel konzisztens kifejezéseket hagyja.</span><span class="sxs-lookup"><span data-stu-id="dc065-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="dc065-165">Ez a $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="dc065-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="dc065-166">Ezt a $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $ értékre lehet átvenni.</span><span class="sxs-lookup"><span data-stu-id="dc065-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="dc065-167">Ezért ha az első és második qubit 11-re mérjük, __tudjuk, hogy__a harmadik qubit a következő állapotban van: $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="dc065-168">4\. lépés: az eredmény értelmezése</span><span class="sxs-lookup"><span data-stu-id="dc065-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="dc065-169">Emlékeztetőként az eredetileg elküldeni kívánt __üzenet__ a következő volt:</span><span class="sxs-lookup"><span data-stu-id="dc065-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="dc065-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="dc065-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="dc065-171">Be kell szereznie a __qubit ebbe az__ állapotba, hogy a kapott állapot legyen a kívánt érték.</span><span class="sxs-lookup"><span data-stu-id="dc065-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="dc065-172">Ha a mért érték a 00, a harmadik qubit pedig a következő __állapotban van:__ $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="dc065-173">Mivel ez a kívánt __üzenet__, nincs szükség módosításra.</span><span class="sxs-lookup"><span data-stu-id="dc065-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="dc065-174">Ha a mért érték a 01, akkor a harmadik qubit a (\alpha\ket{1} + \beta\ket{0}) $ __állapotban van.__</span><span class="sxs-lookup"><span data-stu-id="dc065-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="dc065-175">Ez eltér a kívánt __üzenettől__, de a nem kapu alkalmazása a kívánt állapotot adja meg (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="dc065-176">Ha a mért érték 10, akkor a harmadik qubit a (\alpha\ket{0}-\beta\ket{1}) $ __állapotban van.__</span><span class="sxs-lookup"><span data-stu-id="dc065-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="dc065-177">Ez eltér a kívánt __üzenettől__, azonban a Z-kapu alkalmazása a kívánt állapotot adja meg (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="dc065-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="dc065-178">Ha a mért érték 11, akkor a harmadik qubit a (\alpha\ket{1}-\beta\ket{0}) $ __állapotban van.__</span><span class="sxs-lookup"><span data-stu-id="dc065-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="dc065-179">Ez különbözik a kívánt __üzenettől__, de a nem kaput, majd egy Z kapun a kívánt állapotot ($ (\alpha\ket{0} + \beta\ket{1}) $ értéket adja meg nekünk.</span><span class="sxs-lookup"><span data-stu-id="dc065-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="dc065-180">Ha a mérés és az első qubit értéke 1, a rendszer a Z kaput alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="dc065-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="dc065-181">Ha mérjük, és a második qubit értéke 1, a rendszer nem alkalmaz egy kaput.</span><span class="sxs-lookup"><span data-stu-id="dc065-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="dc065-182">Összefoglalás</span><span class="sxs-lookup"><span data-stu-id="dc065-182">Summary</span></span>
<span data-ttu-id="dc065-183">Alább látható egy szöveges könyvből álló kvantum-kör, amely megvalósítja a teleportáció.</span><span class="sxs-lookup"><span data-stu-id="dc065-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="dc065-184">Balról jobbra haladva a következőt láthatja:</span><span class="sxs-lookup"><span data-stu-id="dc065-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="dc065-185">1\. lépés: a __Hadamard-kapu__ és a cnem-kapu alkalmazásával összekeverhető __itt__ .</span><span class="sxs-lookup"><span data-stu-id="dc065-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="dc065-186">2\. lépés: az __üzenet__ elküldése egy cnem-kapuval és egy Hadamard-kapuval.</span><span class="sxs-lookup"><span data-stu-id="dc065-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="dc065-187">3\. lépés: az első és a második qubits, az __üzenet__ és az __itt__mért érték mérése.</span><span class="sxs-lookup"><span data-stu-id="dc065-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="dc065-188">4\. lépés: nem kapu vagy Z kapu alkalmazása a 3. lépésben mért mértéktől függően.</span><span class="sxs-lookup"><span data-stu-id="dc065-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["Teleport (msg: Qubit, ott: Qubit): egység"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="dc065-190">Quantum teleportáció: kód</span><span class="sxs-lookup"><span data-stu-id="dc065-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="dc065-191">A Quantum teleportáció:</span><span class="sxs-lookup"><span data-stu-id="dc065-191">We have our circuit for quantum teleportation:</span></span>

!["Teleport (msg: Qubit, ott: Qubit): egység"](~/media/teleportation.svg)

<span data-ttu-id="dc065-193">Most már lefordíthatja az ebben a kvantum-áramkörben lévő lépéseket Q #-ra.</span><span class="sxs-lookup"><span data-stu-id="dc065-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="dc065-194">0\. lépés: definíció</span><span class="sxs-lookup"><span data-stu-id="dc065-194">Step 0: Definition</span></span>
<span data-ttu-id="dc065-195">A teleportálás elvégzése után tudnunk kell, hogy milyen __üzenetet__ szeretnénk elküldeni, és hová szeretnénk elküldeni (__ott__).</span><span class="sxs-lookup"><span data-stu-id="dc065-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="dc065-196">Éppen ezért egy új, az argumentumként megadott teleport-művelet definiálásával kezdjük, `msg` és `there`:</span><span class="sxs-lookup"><span data-stu-id="dc065-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="dc065-197">Szükség van egy qubit-`here` kiosztására is, amelyet egy `using` blokkmal érhetünk el:</span><span class="sxs-lookup"><span data-stu-id="dc065-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="dc065-198">1\. lépés: kusza állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="dc065-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="dc065-199">Ezután az @"microsoft.quantum.intrinsic.h" és a @"microsoft.quantum.intrinsic.cnot" műveletekkel hozhatjuk létre a kusza párokat `here` és `there` között:</span><span class="sxs-lookup"><span data-stu-id="dc065-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="dc065-200">2\. lépés: az üzenet elküldése</span><span class="sxs-lookup"><span data-stu-id="dc065-200">Step 2: Send the message</span></span>
<span data-ttu-id="dc065-201">Ezt követően a következő $ \operatorname{CNOT} $ és $H $ Gates használatával helyezheti át az üzenet qubit:</span><span class="sxs-lookup"><span data-stu-id="dc065-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="dc065-202">3\. lépés & 4: az eredmény mérése és értelmezése</span><span class="sxs-lookup"><span data-stu-id="dc065-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="dc065-203">Végül a @"microsoft.quantum.intrinsic.m" használatával hajtjuk végre a méréseket, és végrehajtjuk a szükséges kiindulási műveleteket a kívánt állapot eléréséhez, `if` utasítások szerint:</span><span class="sxs-lookup"><span data-stu-id="dc065-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="dc065-204">Ez befejezi a teleportáló operátor definícióját, így felszabadítjuk `here`, befejezve a törzset, és befejezjük a műveletet.</span><span class="sxs-lookup"><span data-stu-id="dc065-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
