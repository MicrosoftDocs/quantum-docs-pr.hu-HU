---
title: Q# technikák - Az egész összerakása
description: Végigvezet egy alapvető Q# programon, amely bemutatja a kvantum teleportációt.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030565"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="39554-103">Elhelyezés ez minden együtt: Teleportáció</span><span class="sxs-lookup"><span data-stu-id="39554-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="39554-104">Térjünk vissza a Quantum Circuits-ben meghatározott teleportációs áramkör [példájához.](xref:microsoft.quantum.concepts.circuits)</span><span class="sxs-lookup"><span data-stu-id="39554-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="39554-105">Ezt fogjuk használni, hogy bemutassuk az eddig megtanult fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="39554-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="39554-106">A kvantum teleportáció magyarázata az alábbiakban található azok számára, akik nem ismerik az elméletet, majd a q#-ban a kódimplementáció forgatókönyve.</span><span class="sxs-lookup"><span data-stu-id="39554-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="39554-107">Quantum Teleportáció: Elmélet</span><span class="sxs-lookup"><span data-stu-id="39554-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="39554-108">Quantum teleportáció egy olyan technika küldésére ismeretlen kvantum állapot (amit majd hivatkozni, mint a "__üzenet__") egy qubit az egyik helyen, hogy a qubit egy másik helyen (majd hivatkozni ezeket a qubitek a "__itt__" és "__ott__", illetve).</span><span class="sxs-lookup"><span data-stu-id="39554-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="39554-109">Üzenetünket __message__ vektorként tudjuk ábrázolni dirac jelöléssel:</span><span class="sxs-lookup"><span data-stu-id="39554-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="39554-110">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="39554-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="39554-111">Az __üzenet__ qubit állapota ismeretlen számunkra, mivel nem tudjuk az értékeket $\alpha$ és $\beta$.</span><span class="sxs-lookup"><span data-stu-id="39554-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="39554-112">1. lépés: Kusza állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="39554-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="39554-113">Annak érdekében, hogy küldje el az __üzenetet__ van szükségünk a qubit __itt__ kell kusza a qubit __ott__.</span><span class="sxs-lookup"><span data-stu-id="39554-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="39554-114">Ez egy Hadamard kapu alkalmazásával érhető el, amelyet egy CNOT kapu követ.</span><span class="sxs-lookup"><span data-stu-id="39554-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="39554-115">Nézzük meg a matekmögötti kapuműveleteket.</span><span class="sxs-lookup"><span data-stu-id="39554-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="39554-116">Kezdjük a qubits __itt-ott__ mind a{0}$ ket $ állapotban. __there__</span><span class="sxs-lookup"><span data-stu-id="39554-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="39554-117">Miután entangling ezek a qubits, ezek az állam:</span><span class="sxs-lookup"><span data-stu-id="39554-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="39554-118">$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$</span><span class="sxs-lookup"><span data-stu-id="39554-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="39554-119">2. lépés: Az üzenet elküldése</span><span class="sxs-lookup"><span data-stu-id="39554-119">Step 2: Send the message</span></span>
<span data-ttu-id="39554-120">Az __üzenet__ elküldéséhez először egy CNOT kaput alkalmazunk a qubit __üzenettel__ és __itt__ qubit bemenetként (az __üzenet__ qubit a vezérlő és az __itt__ qubit a cél qubit, ebben az esetben).</span><span class="sxs-lookup"><span data-stu-id="39554-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="39554-121">Ez a bemeneti állapot írható:</span><span class="sxs-lookup"><span data-stu-id="39554-121">This input state can be written:</span></span>

<span data-ttu-id="39554-122">{0} $$ \ket{\psi}\ket{\phi^+} = (\alpha\ket +{1}\beta\ket{1})(\frac {\sqrt{2})(\ket{00} + \ket{11})) $$</span><span class="sxs-lookup"><span data-stu-id="39554-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="39554-123">Ez a következőkre terjed ki:</span><span class="sxs-lookup"><span data-stu-id="39554-123">This expands to:</span></span>

<span data-ttu-id="39554-124">$${2}\ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\sqrt{2}}\ket{011} {2}{100} {2}{111} +\frac{\beta}{\sqrt $!</span><span class="sxs-lookup"><span data-stu-id="39554-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="39554-125">Emlékeztetőül: a CNOT kapu megfordítja a cél qubitet, ha a vezérlő qubit 1.</span><span class="sxs-lookup"><span data-stu-id="39554-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="39554-126">Így például a $\ket{000}$ bemenetnem eredményez változást, mivel az első qubit (a vezérlő) 0.</span><span class="sxs-lookup"><span data-stu-id="39554-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="39554-127">Azonban, hogy egy esetben, ahol az első qubit 1{100}- például egy bemeneti $\ket $.</span><span class="sxs-lookup"><span data-stu-id="39554-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="39554-128">Ebben az esetben a kimenet{110}$\ket $, mivel a második qubit (a cél) a CNOT kapuval van tükrözve.</span><span class="sxs-lookup"><span data-stu-id="39554-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="39554-129">Nézzük most úgy a kimenet, ha a CNOT kapu járt el a mi bemenet felett.</span><span class="sxs-lookup"><span data-stu-id="39554-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="39554-130">Az eredmény:</span><span class="sxs-lookup"><span data-stu-id="39554-130">The result is:</span></span>

<span data-ttu-id="39554-131">{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span><span class="sxs-lookup"><span data-stu-id="39554-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="39554-132">A következő lépés, hogy küldje el az __üzenetet,__ hogy alkalmazza a Hadamard kapu az __üzenet__ qubit (ez az első qubit minden kifejezés).</span><span class="sxs-lookup"><span data-stu-id="39554-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="39554-133">Emlékeztetőül, a Hadamard kapu a következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="39554-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="39554-134">Input (Bemenet)</span><span class="sxs-lookup"><span data-stu-id="39554-134">Input</span></span> | <span data-ttu-id="39554-135">Kimenet</span><span class="sxs-lookup"><span data-stu-id="39554-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="39554-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="39554-136">$\ket{0}$</span></span>  | <span data-ttu-id="39554-137">$\frac{1}{\sqrt{2}}(\ket{0} {1}+ \ket )$</span><span class="sxs-lookup"><span data-stu-id="39554-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="39554-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="39554-138">$\ket{1}$</span></span>  | <span data-ttu-id="39554-139">$\frac{1}{\sqrt{2}}(\ket{0} {1}- \ket )$</span><span class="sxs-lookup"><span data-stu-id="39554-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="39554-140">Ha a Hadamard kaput a fenti kimenetminden egyes ciklusának első qubit-jára alkalmazzuk, a következő eredményt kapjuk:</span><span class="sxs-lookup"><span data-stu-id="39554-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="39554-141">$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}{0} }(\ket + \ket{1})\ket{00} +{2}\frac{\alpha}{\sqrt }(\frac{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {1}{\sqrt{2}}(\ket + \ket )\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket )\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket $$</span><span class="sxs-lookup"><span data-stu-id="39554-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="39554-142">Ne feledje, hogy minden{1}kifejezésnek két{2}$\frac {\sqrt }$ tényezője van.</span><span class="sxs-lookup"><span data-stu-id="39554-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="39554-143">Tudjuk szorozni ezeket ki, amely a következő eredményt:</span><span class="sxs-lookup"><span data-stu-id="39554-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="39554-144">$${2}\frac{\alpha} (\ket{0} {1}+ \ket )\ket{00} +{2}\frac{\alpha} (\ket{0} +{1}\ket )\ket{0} {1}{10} {2}{0} {1}{01} {11} + \frac{\beta}{2}(\ket - \ket )\ket + \frac{\beta} (\ket - \ket )\ket $$</span><span class="sxs-lookup"><span data-stu-id="39554-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="39554-145">A $\frac{1}{2}$ tényező minden egyes kifejezésnél gyakori, így most már a zárójelen kívül rekedhetünk:</span><span class="sxs-lookup"><span data-stu-id="39554-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="39554-146">{1}{2}$$ \frac{0} \big[\alpha(\ket{1}+ \ket )\ket{00} {0} + \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} -{1}\ket )\ket{10} \beta(\ket - \ket -{0} \ket - \ket ) \ket{1}{01}</span><span class="sxs-lookup"><span data-stu-id="39554-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="39554-147">Ezután szorozzuk ki a zárójelben minden kifejezés, amely:</span><span class="sxs-lookup"><span data-stu-id="39554-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="39554-148">$${1}{2}\frac \big[\alfa\ket{000} +{100} \alpha\ket{011} + \alpha\ket +{111} \alpha\ket + \beta\ket{001} {101}{010} - \beta\ket{110} + \beta\ket - \beta\ket - \beta\ket - \beta\ket \beta\ket \beta\ket \big] $$</span><span class="sxs-lookup"><span data-stu-id="39554-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="39554-149">3. lépés: Az eredmény mérése</span><span class="sxs-lookup"><span data-stu-id="39554-149">Step 3: Measure the result</span></span>

<span data-ttu-id="39554-150">Mivel __here__ __itt-ott,__ hogy kusza, minden mérés __itt__ hatással lesz az állam __ott__.</span><span class="sxs-lookup"><span data-stu-id="39554-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="39554-151">Ha mérjük az első és a második qubit __(üzenet__ és __itt)__ meg tudjuk tanulni, milyen állapotban __van,__ mivel ez a tulajdonság a kuszaság.</span><span class="sxs-lookup"><span data-stu-id="39554-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="39554-152">Ha mérjük, és kap egy eredmény 00, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel.</span><span class="sxs-lookup"><span data-stu-id="39554-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="39554-153">Ez $\alpha\ket{000} +\beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="39554-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="39554-154">Ez $\ket{00}(\alpha\ket{0} +\beta\ket{1})$-ra refactorálható.</span><span class="sxs-lookup"><span data-stu-id="39554-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="39554-155">Ezért ha mérjük az első és a második qubit, hogy 00, tudjuk, hogy a harmadik{0} qubit,{1} __ott__van az állam $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="39554-156">Ha mérjük, és kap egy eredmény 01, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel.</span><span class="sxs-lookup"><span data-stu-id="39554-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="39554-157">Ez $\alpha\ket{011} +\beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="39554-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="39554-158">Ez $\ket{01}(\alpha\ket{1} +\beta\ket{0})$-ra refactorálható.</span><span class="sxs-lookup"><span data-stu-id="39554-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="39554-159">Ezért, ha mérjük az első és a második qubit, hogy 01, tudjuk, hogy a{1} harmadik qubit,{0} __ott__van az állam $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="39554-160">Ha mérjük, és kap egy eredményt 10, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel.</span><span class="sxs-lookup"><span data-stu-id="39554-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="39554-161">Ez $\alpha\ket{100} -\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="39554-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="39554-162">Ez $\ket{10}(\alpha\ket{0} -\beta\ket{1})$-ra refactorálható.</span><span class="sxs-lookup"><span data-stu-id="39554-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="39554-163">Ezért ha az első és a második qubit 10-es, akkor tudjuk, hogy a harmadik qubit, __ott__van az állam $(\alpha\ket{0} -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="39554-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="39554-164">Ha mérjük, és kap egy eredményt 11, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel.</span><span class="sxs-lookup"><span data-stu-id="39554-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="39554-165">Ez $\alpha\ket{111} -\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="39554-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="39554-166">Ez $\ket{11}(\alpha\ket{1} -\beta\ket{0})$-ra refactorálható.</span><span class="sxs-lookup"><span data-stu-id="39554-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="39554-167">Ezért ha az első és a második qubit 11-es, akkor tudjuk, hogy a harmadik qubit, __ott__van az állam $(\alpha\ket{1} -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="39554-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="39554-168">4. lépés: Az eredmény értelmezése</span><span class="sxs-lookup"><span data-stu-id="39554-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="39554-169">Emlékeztetőül, az eredeti __üzenetet__ akartunk küldeni volt:</span><span class="sxs-lookup"><span data-stu-id="39554-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="39554-170">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="39554-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="39554-171">Be kell juttatnunk __a__ qubit-et ebbe az állapotba, hogy a kapott állam az, amit szántak.</span><span class="sxs-lookup"><span data-stu-id="39554-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="39554-172">Ha mértük, és kapott egy eredmény 00, __there__akkor a harmadik qubit, ott{0} van az{1}állam $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="39554-173">Mivel ez a kívánt __üzenet,__ nincs szükség változtatásra.</span><span class="sxs-lookup"><span data-stu-id="39554-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="39554-174">Ha mértük, és kapott egy eredmény 01, __there__akkor a harmadik qubit, ott{1} van az{0}állam $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="39554-175">Ez eltér a tervezett __üzenettől,__ azonban a NOT kapu alkalmazása megadja a{0} kívánt állapotot{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="39554-176">Ha mértük, és kapott egy eredmény 10, __there__akkor a harmadik qubit, ott{0} van az{1}állam $(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="39554-177">Ez eltér a tervezett __üzenettől,__ azonban a Z kapu alkalmazása megadja a{0} kívánt állapotot{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="39554-178">Ha mértük, és kapott egy eredmény 11, __there__akkor a harmadik qubit, ott{1} van az{0}állam $(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="39554-179">Ez eltér a tervezett __üzenettől,__ azonban a NOT kapu, majd a Z kapu alkalmazása{0} megadja nekünk{1}a kívánt állapotot $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="39554-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="39554-180">Összefoglalva, ha mérjük, és az első qubit 1, a Z kapu kerül alkalmazásra.</span><span class="sxs-lookup"><span data-stu-id="39554-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="39554-181">Ha mérjük, és a második qubit 1, a NOT kapu kerül alkalmazásra.</span><span class="sxs-lookup"><span data-stu-id="39554-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="39554-182">Összefoglalás</span><span class="sxs-lookup"><span data-stu-id="39554-182">Summary</span></span>
<span data-ttu-id="39554-183">Az alábbiakban egy tankönyv kvantumáramkör látható, amely megvalósítja a teleportálást.</span><span class="sxs-lookup"><span data-stu-id="39554-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="39554-184">Balról jobbra haladva látható:</span><span class="sxs-lookup"><span data-stu-id="39554-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="39554-185">1. lépés: Entangling __itt-ott__ alkalmazásával Hadamard kapu és CNOT kapu. __here__</span><span class="sxs-lookup"><span data-stu-id="39554-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="39554-186">2. lépés: Az __üzenet__ elküldése egy CNOT kapu és egy Hadamard kapu segítségével.</span><span class="sxs-lookup"><span data-stu-id="39554-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="39554-187">3. lépés: Az első és a második qubit, __üzenet__ és __itt__mérése .</span><span class="sxs-lookup"><span data-stu-id="39554-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="39554-188">4. lépés: NOT vagy Z kapu alkalmazása a 3.</span><span class="sxs-lookup"><span data-stu-id="39554-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["Teleport(msg : Qubit, ott: Qubit) : Egység"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="39554-190">Quantum Teleportáció: Kód</span><span class="sxs-lookup"><span data-stu-id="39554-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="39554-191">Megvan a kvantum teleportáció áramköre:</span><span class="sxs-lookup"><span data-stu-id="39554-191">We have our circuit for quantum teleportation:</span></span>

!["Teleport(msg : Qubit, ott: Qubit) : Egység"](~/media/teleportation.svg)

<span data-ttu-id="39554-193">Most már letudjuk fordítani a kvantumáramkör minden egyes lépését Q#-ra.</span><span class="sxs-lookup"><span data-stu-id="39554-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="39554-194">0. lépés: Meghatározás</span><span class="sxs-lookup"><span data-stu-id="39554-194">Step 0: Definition</span></span>
<span data-ttu-id="39554-195">Amikor végzünk teleportáció, tudnunk kell az __üzenetet__ szeretnénk küldeni, és ahol szeretnénk küldeni __(ott__).</span><span class="sxs-lookup"><span data-stu-id="39554-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="39554-196">Ezért kezdjük egy új teleport művelet meghatározásával, amely két qubitet `msg` `there`kap érvként, és:</span><span class="sxs-lookup"><span data-stu-id="39554-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="39554-197">Azt is meg kell `here` kiosztani a `using` qubit, amit elérni egy blokk:</span><span class="sxs-lookup"><span data-stu-id="39554-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="39554-198">1. lépés: Kusza állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="39554-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="39554-199">Ezután létrehozhatjuk a kusza pár @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" között `here` és `there` a műveletek segítségével:</span><span class="sxs-lookup"><span data-stu-id="39554-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="39554-200">2. lépés: Az üzenet elküldése</span><span class="sxs-lookup"><span data-stu-id="39554-200">Step 2: Send the message</span></span>
<span data-ttu-id="39554-201">Ezután a következő $\operatorname{CNOT}$ és $H$ kapukat használjuk az üzenet qubit áthelyezéséhez:</span><span class="sxs-lookup"><span data-stu-id="39554-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="39554-202">3. & 4.</span><span class="sxs-lookup"><span data-stu-id="39554-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="39554-203">Végül, használjuk, @"microsoft.quantum.intrinsic.m" hogy végre a méréseket, és elvégzi a szükséges kapu `if` műveleteket, hogy a kívánt állapot, amint azt a nyilatkozatok:</span><span class="sxs-lookup"><span data-stu-id="39554-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="39554-204">5. lépés: A qubit regiszter újraindítása</span><span class="sxs-lookup"><span data-stu-id="39554-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="39554-205">Végén minden Q # művelet van szükségünk, hogy hagyja, hogy{0}a qubits az állam $\ket $.</span><span class="sxs-lookup"><span data-stu-id="39554-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="39554-206">@"microsoft.quantum.intrinsic.reset" Használhatjuk, hogy indítsa újra az összes qubits a nulla állapot, és ez befejezi a műveletet.</span><span class="sxs-lookup"><span data-stu-id="39554-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


