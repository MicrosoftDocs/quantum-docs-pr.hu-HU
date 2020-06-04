---
title: 'Műveletek és függvények a Q-ban #'
description: Műveletek és függvények definiálása és hívása, valamint az ellenőrzött és adjoint műveletekre vonatkozó specializációk.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 9e924b973c4f22a59dd862df3f4f0d70278a1b4e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327798"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="68876-103">Műveletek és függvények a Q-ban #</span><span class="sxs-lookup"><span data-stu-id="68876-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="68876-104">Új műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="68876-104">Defining New Operations</span></span>

<span data-ttu-id="68876-105">A műveletek a Q # legfontosabbak.</span><span class="sxs-lookup"><span data-stu-id="68876-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="68876-106">A deklarációt követően meghívhatók a klasszikus .NET-alkalmazásokból, például szimulátor használatával vagy a Q #-on belüli egyéb műveletekkel.</span><span class="sxs-lookup"><span data-stu-id="68876-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="68876-107">A Q # által meghatározott minden művelet hívhat meg tetszőleges számú egyéb műveletet, beleértve a nyelv által meghatározott beépített belső műveleteket is.</span><span class="sxs-lookup"><span data-stu-id="68876-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="68876-108">A belső műveletek meghatározásának konkrét módja a célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="68876-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="68876-109">A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.</span><span class="sxs-lookup"><span data-stu-id="68876-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="68876-110">A Q # forrásfájl tetszőleges számú műveletet meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="68876-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="68876-111">A művelet nevének a névtéren belül egyedinek kell lennie, és nem ütközhet típus-vagy függvénynév-névvel.</span><span class="sxs-lookup"><span data-stu-id="68876-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="68876-112">A műveleti deklaráció a kulcsszóból áll, amelyet a művelet nevét, a művelethez tartozó `operation` argumentumokat definiáló típust, egy kettőspontot, egy Type jegyzetet ad meg, amely a művelet `:` eredményének típusát írja le, opcionálisan a művelet jellemzőit, a nyitó kapcsos zárójelet `{` , a műveleti deklaráció törzsét és egy záró záró zárójelet `}` .</span><span class="sxs-lookup"><span data-stu-id="68876-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="68876-113">Mindegyik művelet egy bemenetet hoz létre, kimenetet állít elő, és meghatározza egy vagy több műveleti specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="68876-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="68876-114">A lehetséges szakosodások, valamint a definiálása/meghívása alább részletesebben olvashatók.</span><span class="sxs-lookup"><span data-stu-id="68876-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="68876-115">Egyelőre a következő műveletnek kell megfontolnia, amely csak az alapértelmezett szövegtörzset határozza meg, és egyetlen qubit használ a bemenetként, majd meghívja a beépített <xref:microsoft.quantum.intrinsic.x> műveletet a bemeneten:</span><span class="sxs-lookup"><span data-stu-id="68876-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="68876-116">A kulcsszó `operation` megkezdi a művelet definícióját, és ezt a nevet követi; itt: `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="68876-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="68876-117">Ezután a bemenet típusa a következőként van definiálva `Qubit` :, valamint egy név, amely az `target` új műveleten belüli bemenetre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="68876-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="68876-118">Hasonlóképpen, az `Unit` határozza meg, hogy a művelet kimenete üres.</span><span class="sxs-lookup"><span data-stu-id="68876-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="68876-119">Ezt hasonlóan a `void` C#-ban és más kötelező nyelvekhez használják, és ez egyenértékű az `unit` F # és más funkcionális nyelvek esetében.</span><span class="sxs-lookup"><span data-stu-id="68876-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="68876-120">A műveletek több érdekes típust is visszaadhatnak, mint a `Unit` .</span><span class="sxs-lookup"><span data-stu-id="68876-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="68876-121">A <xref:microsoft.quantum.intrinsic.m> művelet például egy típusú kimenetet ad vissza `Result` , amely a mérés végrehajtását jelöli.</span><span class="sxs-lookup"><span data-stu-id="68876-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="68876-122">Egy művelet kimenetét átadhatja egy másik műveletnek, vagy használhatja azt a `let` kulcsszóval egy új változó definiálásához.</span><span class="sxs-lookup"><span data-stu-id="68876-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="68876-123">Ez lehetővé teszi a klasszikus számításokat, amelyek alacsony szinten működnek a kvantum-műveletekkel, például a [sűrűbb kódolásban](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="68876-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="68876-124">A Q # minden művelete pontosan egy bemenetet vesz igénybe, és pontosan egy kimenetet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="68876-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="68876-125">Ezután több bemenet és kimenet is képviselteti magát a *rekordok*használatával, amely egyszerre több értéket gyűjt össze egyetlen értékkel.</span><span class="sxs-lookup"><span data-stu-id="68876-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="68876-126">Informálisan azt mondjuk, hogy a Q # egy "rekordos kijelentkezés" nyelv.</span><span class="sxs-lookup"><span data-stu-id="68876-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="68876-127">Ezt a fogalmat követve `()` az "üres" rekordnak kell szerepelnie, amelynek típusa a következő: `Unit` .</span><span class="sxs-lookup"><span data-stu-id="68876-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="68876-128">Vezérelt és Adjoint műveletek</span><span class="sxs-lookup"><span data-stu-id="68876-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="68876-129">Ha egy művelet egy egységes átalakítást valósít meg, a Q # számos műveletének esetében, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen.</span><span class="sxs-lookup"><span data-stu-id="68876-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="68876-130">Egy művelet *adjoint* -specializálása meghatározza, hogy a művelet milyen hatással van az "inverz" értékre, míg a *szabályozott* specializáció meghatározza, hogy a művelet hogyan működik, ha az alkalmazás egy adott kvantum-regiszter állapotára van feltétele.</span><span class="sxs-lookup"><span data-stu-id="68876-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="68876-131">A Adjoints elengedhetetlen a kvantum-számítási feladatok számos aspektusa szempontjából.</span><span class="sxs-lookup"><span data-stu-id="68876-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="68876-132">Az alábbiakban a [conjugations](#conjugations) szakaszban talál egy ilyen helyzetet, amely egy hasznos Q # programozási technikával együtt tárgyalt.</span><span class="sxs-lookup"><span data-stu-id="68876-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="68876-133">Egy művelet ellenőrzött verziója olyan új művelet, amely hatékonyan alkalmazza az alapműveletet, ha az összes vezérlő qubits megadott állapotban van.</span><span class="sxs-lookup"><span data-stu-id="68876-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="68876-134">Ha a vezérlő qubits van, akkor az alapszintű műveletet a rendszer következetesen alkalmazza a Felfekvés megfelelő részére.</span><span class="sxs-lookup"><span data-stu-id="68876-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="68876-135">Így a rendszer gyakran használja az ellenőrzött műveleteket a felakadás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="68876-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="68876-136">Természetesen egy *vezérelt adjoint* specializáció is létezhet, amely meghatározza egy művelet adjoint vezérelt alkalmazását.</span><span class="sxs-lookup"><span data-stu-id="68876-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="68876-137">Ha $U $ egy művelet által megvalósított egységes átalakítás `U` , akkor `Adjoint U` az egységes átalakítást jelöli $U ^ \dagger $, amely a komplex konjugátum átültetése.</span><span class="sxs-lookup"><span data-stu-id="68876-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="68876-138">Egy művelet egymást követő alkalmazása után a adjoint állapota változatlan marad, ahogy azt az a tény mutatja, hogy $UU ^ \dagger = U ^ \dagger U = \id $, az Identity Matrix.</span><span class="sxs-lookup"><span data-stu-id="68876-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="68876-139">Egy vezérelt művelet egységes ábrázolása valamivel árnyaltabb, de további részleteket a [Quantum Computing-fogalmak: több qubits](xref:microsoft.quantum.concepts.multiple-qubits)is talál.</span><span class="sxs-lookup"><span data-stu-id="68876-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="68876-140">A következő szakasz azt ismerteti, hogyan hívhatja meg ezeket a különböző szakterületeket a Q # kódjában.</span><span class="sxs-lookup"><span data-stu-id="68876-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="68876-141">Az alábbiakban részletesen ismertetjük, hogyan definiálhat műveleteket a támogatáshoz.</span><span class="sxs-lookup"><span data-stu-id="68876-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="68876-142">Hívási művelet specializációi</span><span class="sxs-lookup"><span data-stu-id="68876-142">Calling operation specializations</span></span>

<span data-ttu-id="68876-143">A *Q # egy olyan* gyár, amely új műveletet határoz meg egy másik műveletből.</span><span class="sxs-lookup"><span data-stu-id="68876-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="68876-144">A Q # két standard, a és a `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="68876-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="68876-145">Az új művelet megvalósításának meghatározásakor az üzemben lévők az alapművelet megvalósításához férnek hozzá.</span><span class="sxs-lookup"><span data-stu-id="68876-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="68876-146">Így a fellépők összetettebb funkciókkal rendelkezhetnek, mint a hagyományos magasabb szintű függvények.</span><span class="sxs-lookup"><span data-stu-id="68876-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="68876-147">A Q # Type rendszer nem rendelkezik képviselettel a következőben:.</span><span class="sxs-lookup"><span data-stu-id="68876-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="68876-148">Ezért jelenleg nem lehet őket egy változóhoz kötni, vagy argumentumként átadni őket.</span><span class="sxs-lookup"><span data-stu-id="68876-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="68876-149">A rendszer egy, a műveletre való alkalmazásával egy új műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="68876-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="68876-150">Például az a művelet, amely abból ered, hogy a rendszer a `Adjoint` `Y` műveletet a művelettel a műveletre alkalmazza `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="68876-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="68876-151">Előfordulhat, hogy az új művelet a többi művelethez hasonlóan hívható meg.</span><span class="sxs-lookup"><span data-stu-id="68876-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="68876-152">Ahhoz, hogy egy művelet támogassa a és/vagy az elhasználók alkalmazását `Adjoint` `Controlled` , a visszatérési típusának szükségszerűen kell lennie `Unit` .</span><span class="sxs-lookup"><span data-stu-id="68876-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="68876-153">`Adjoint`nem aktív</span><span class="sxs-lookup"><span data-stu-id="68876-153">`Adjoint` functor</span></span>

<span data-ttu-id="68876-154">Így `Adjoint Y(q1)` a Adjoint a `Y` művelethez alkalmazza az új művelet létrehozását, és az új műveletet alkalmazza a következőre: `q1` .</span><span class="sxs-lookup"><span data-stu-id="68876-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="68876-155">Az új művelet ugyanazzal az aláírással és típussal rendelkezik, mint az alapművelet `Y` .</span><span class="sxs-lookup"><span data-stu-id="68876-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="68876-156">Az új művelet azt is lehetővé teszi, hogy a `Adjoint` , és csak akkor engedélyezze, `Controlled` Ha az alapművelet volt.</span><span class="sxs-lookup"><span data-stu-id="68876-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="68876-157">A Adjoint-tulajdonos a saját inverze. vagyis `Adjoint Adjoint Op` mindig ugyanaz, mint a `Op` .</span><span class="sxs-lookup"><span data-stu-id="68876-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="68876-158">`Controlled`nem aktív</span><span class="sxs-lookup"><span data-stu-id="68876-158">`Controlled` functor</span></span>

<span data-ttu-id="68876-159">Hasonlóképpen `Controlled X(controls, target)` alkalmazza az ellenőrzött futtatót a `X` műveletre új művelet létrehozásához, és az új műveletet a és a értékre alkalmazza `controls` `target` .</span><span class="sxs-lookup"><span data-stu-id="68876-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="68876-160">A Q #-ban az ellenőrzött verziók mindig a vezérlési qubits egy tömbjét foglalják magukban, és a megadott állapot mindig az összes vezérlési qubits a számítási ( `PauliZ` ) `One` állapotban, a $ \ket $ értékben {1} .</span><span class="sxs-lookup"><span data-stu-id="68876-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="68876-161">A más állapotokon alapuló vezérlést úgy érheti el, ha a megfelelő egységes műveletet alkalmazza a vezérlő qubits az ellenőrzött művelet előtt, majd az egységes művelet inverzét alkalmazza az ellenőrzött művelet után.</span><span class="sxs-lookup"><span data-stu-id="68876-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="68876-162">Ha például egy `X` műveletet egy vezérlő qubit egy vezérelt művelet előtt és után alkalmaz, akkor a művelet az `Zero` adott qubit állapotára ($ \ket $) irányítja a műveletet {0} , és a művelet `H` előtt és után is szabályozni fogja az állapotot `PauliX` `One` , azaz az-1 sajátérték a Pauli X, a $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt $ helyett, nem pedig {2} az `PauliZ` `One` állapotot.</span><span class="sxs-lookup"><span data-stu-id="68876-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="68876-163">A művelet kifejezése miatt új műveleti kifejezés is létrehozható az elhasználó használatával `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="68876-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="68876-164">Az új művelet aláírása az eredeti művelet aláírásán alapul.</span><span class="sxs-lookup"><span data-stu-id="68876-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="68876-165">Az eredmény típusa azonos, de a bemeneti típus egy kétrekordos qubit tömb, amely a vezérlő qubit (ka) t az első elemként, az eredeti művelet argumentumait pedig második elemként tárolja.</span><span class="sxs-lookup"><span data-stu-id="68876-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="68876-166">Az új művelet támogatja a- `Controlled` t, és csak akkor támogatja, `Adjoint` Ha az eredeti művelet megtörtént.</span><span class="sxs-lookup"><span data-stu-id="68876-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="68876-167">Ha az eredeti művelet csak egyetlen argumentumot vett igénybe, akkor a rendszer az önálló rekordos egyenértékűséget fogja itt lejátszani.</span><span class="sxs-lookup"><span data-stu-id="68876-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="68876-168">Például a a `Controlled X` művelet ellenőrzött verziója `X` .</span><span class="sxs-lookup"><span data-stu-id="68876-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="68876-169">`X`típusa van `(Qubit => Unit is Adj + Ctl)` , ezért `Controlled X` a Type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; egypéldányos egyenértékűség miatt ez megegyezik a következővel: `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="68876-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="68876-170">Ha az alapművelet több argumentumot is vett igénybe, ne felejtse el zárójelek közé helyezni a művelet ellenőrzött verziójának megfelelő argumentumait, hogy azok egy rekordba legyenek konvertálva.</span><span class="sxs-lookup"><span data-stu-id="68876-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="68876-171">Például a a `Controlled Rz` művelet ellenőrzött verziója `Rz` .</span><span class="sxs-lookup"><span data-stu-id="68876-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="68876-172">`Rz`típusa van `((Double, Qubit) => Unit is Adj + Ctl)` , ezért `Controlled Rz` típusa van `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="68876-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="68876-173">Tehát `Controlled Rz(controls, (0.1, target))` érvényes hívás lenne `Controlled Rz` (jegyezze fel a zárójeleket `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="68876-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="68876-174">Egy másik példaként `CNOT(control, target)` a is megvalósítható `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="68876-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="68876-175">Ha egy célt 2 vezérlő qubits (CCNOT) kell vezérelni, használhatunk `Controlled X([control1, control2], target)` utasítást.</span><span class="sxs-lookup"><span data-stu-id="68876-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="68876-176">A és a-elválasztók `Controlled` `Adjoint` ingázás, így nincs különbség a alkalmazása `Controlled Adjoint Op` vagy a `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="68876-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="68876-177">Vezérelt és Adjoint implementációk meghatározása</span><span class="sxs-lookup"><span data-stu-id="68876-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="68876-178">Az első művelet deklarációjában a fenti példákban a műveletek és az aláírásokkal, illetve a-ben `BitFlip` `DecodeSuperdense` lettek definiálva `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="68876-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="68876-179">A `DecodeSuperdense` mértékek beleszámítása nem egy egységes művelet, ezért nem léteznek szabályozott, nem adjoint specializációk (az ilyen művelet visszaadására vonatkozó követelmény visszahívása `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="68876-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="68876-180">Mivel azonban `BitFlip` egyszerűen végrehajtja az egységes <xref:microsoft.quantum.intrinsic.x> műveletet, azt is megtehette, hogy mindkét specializációt meghatározta.</span><span class="sxs-lookup"><span data-stu-id="68876-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="68876-181">Itt részletesen ismertetjük, hogy miként lehet megtekinteni a szakosodások létezését a Q # művelet deklarációjában, így lehetővé teszi számukra, hogy a és/vagy az ellátottak együttes használatával is meghívják őket `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="68876-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="68876-182">Az [alábbiakban](#circumstances-for-validly-defining-specializations)néhány olyan helyzetet ismertetünk, amelyekben érvényes vagy érvénytelen, hogy deklaráljon bizonyos specializációkat.</span><span class="sxs-lookup"><span data-stu-id="68876-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="68876-183">A művelet jellemzői határozzák meg, hogy milyen típusú elválasztók alkalmazhatók a deklarált műveletre, és milyen hatással vannak rájuk.</span><span class="sxs-lookup"><span data-stu-id="68876-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="68876-184">Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható, pontosabban a következő műveletekkel kapcsolatos megjegyzésekkel: vagy `is Adj` , `is Ctl` vagy `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="68876-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="68876-185">Az egyes specializációk tényleges implementációja *implicit módon* vagy *explicit módon* definiálva lehet.</span><span class="sxs-lookup"><span data-stu-id="68876-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="68876-186">Implementációk implicit meghatározása</span><span class="sxs-lookup"><span data-stu-id="68876-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="68876-187">Ebben az esetben a műveleti deklaráció törzse kizárólag az alapértelmezett implementációból áll.</span><span class="sxs-lookup"><span data-stu-id="68876-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="68876-188">Például:</span><span class="sxs-lookup"><span data-stu-id="68876-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="68876-189">Itt az egyes implicit módon deklarált specializációhoz tartozó implementációt automatikusan generálja a fordító, amelyet a vagy a rendszer `Adjoint` használatakor kell végrehajtani `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="68876-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="68876-190">Így a hívása `Adjoint PrepareEntangledPair` azt eredményezi, hogy a fordító végrehajtja a adjoint, `CNOT` majd a adjoint `H` .</span><span class="sxs-lookup"><span data-stu-id="68876-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="68876-191">Ezek az egyéni műveletek önmagukban is adjoint, így az eredményül kapott `Adjoint PrepareEntangledPair` művelet csupán a alkalmazásból, majd a rendszerből áll `CNOT(here, there)` `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="68876-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="68876-192">Ezért ezt a példát úgy tudjuk megírni `DecodeSuperdense` , hogy a fenti példában tömörebb módon, a adjoint segítségével `PrepareEntangledPair` átalakítja a kusza állapotot egy nem összeillesztett qubits:</span><span class="sxs-lookup"><span data-stu-id="68876-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="68876-193">A deklarációban szereplő műveleti jellemzőkkel rendelkező Megjegyzés hasznos annak biztosításához, hogy a fordító automatikusan generáljon más specializációkat az alapértelmezett implementáció alapján.</span><span class="sxs-lookup"><span data-stu-id="68876-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="68876-194">Számos fontos korlátozást kell figyelembe venni, amikor a rendszer megtervezi, hogy milyen műveleteket végeznek az üzemben.</span><span class="sxs-lookup"><span data-stu-id="68876-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="68876-195">A legtöbb kritikus jelentőséggel bír, ha egy olyan műveletre specializálódott, amely bármely más művelet kimeneti értékét használja, *nem* lehet automatikusan generálni a fordítótól, mert nem egyértelmű, hogy az ilyen műveletekben szereplő utasítások hogyan rendezhetők át ugyanezen hatás megszerzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="68876-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="68876-196">Ezért gyakran érdemes explicit módon megadnia a különböző implementációkat.</span><span class="sxs-lookup"><span data-stu-id="68876-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="68876-197">Implementációk explicit meghatározása</span><span class="sxs-lookup"><span data-stu-id="68876-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="68876-198">Abban az esetben, ha a fordító nem tudja létrehozni a megvalósítást, explicit módon megadható.</span><span class="sxs-lookup"><span data-stu-id="68876-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="68876-199">Az ilyen explicit specializációs nyilatkozatok megfelelő *generációs irányelvből* vagy felhasználó által definiált implementációból állhatnak.</span><span class="sxs-lookup"><span data-stu-id="68876-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="68876-200">Itt biztosítjuk a lehetőségek teljes körét, az alábbi példákkal.</span><span class="sxs-lookup"><span data-stu-id="68876-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="68876-201">Explicit specializációs deklarációk</span><span class="sxs-lookup"><span data-stu-id="68876-201">Explicit specialization declarations</span></span>

<span data-ttu-id="68876-202">A Q # műveletei a következő explicit specializációs deklarációkat tartalmazhatják:</span><span class="sxs-lookup"><span data-stu-id="68876-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="68876-203">A `body` specializáció meghatározza a művelet végrehajtását, és nem alkalmazta a műveletet.</span><span class="sxs-lookup"><span data-stu-id="68876-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="68876-204">A `adjoint` specializáció meghatározza a művelet megvalósítását az `Adjoint` alkalmazottal.</span><span class="sxs-lookup"><span data-stu-id="68876-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="68876-205">A `controlled` specializáció meghatározza a művelet megvalósítását az `Controlled` alkalmazottal.</span><span class="sxs-lookup"><span data-stu-id="68876-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="68876-206">A `controlled adjoint` specializáció meghatározza a művelet megvalósítását mind a, mind a által alkalmazott operációs rendszersel `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="68876-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="68876-207">Ez a specializáció is elnevezhető `adjoint controlled` , mivel a két elválasztó.</span><span class="sxs-lookup"><span data-stu-id="68876-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="68876-208">A művelet specializáció a specializációs címkéből (például `body` vagy `adjoint` stb.) áll, amelyet az alábbiak egyike követ:</span><span class="sxs-lookup"><span data-stu-id="68876-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="68876-209">Az alább leírtak szerint kifejezett nyilatkozat.</span><span class="sxs-lookup"><span data-stu-id="68876-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="68876-210">Egy *irányelv* , amely közli a fordítóval, *Hogyan* hozhatja ki a specializációt, az egyik:</span><span class="sxs-lookup"><span data-stu-id="68876-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="68876-211">`intrinsic`, ami azt jelzi, hogy a specializációt a célszámítógép kapja meg.</span><span class="sxs-lookup"><span data-stu-id="68876-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="68876-212">`distribute`, amely a `controlled` és a `controlled adjoint` specializációkkal használható.</span><span class="sxs-lookup"><span data-stu-id="68876-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="68876-213">A használatakor `controlled` azt jelzi, hogy a fordítónak ki kell számítania a specializációt úgy, hogy az `Controlled` összes műveletére alkalmazza a-t `body` .</span><span class="sxs-lookup"><span data-stu-id="68876-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="68876-214">A használatakor `controlled adjoint` azt jelzi, hogy a fordítónak a `Controlled` specializáció összes műveletére alkalmazva kell kiszámítani a specializációt `adjoint` .</span><span class="sxs-lookup"><span data-stu-id="68876-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="68876-215">`invert`, ami azt jelzi, hogy a fordítónak ki kell számítania a `adjoint` specializációt a következő lépésekkel `body` , például a műveletek sorrendjének megfordításával és a adjoint alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="68876-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="68876-216">A használatakor `adjoint controlled` Ez azt jelzi, hogy a fordítónak a specializáció megfordításával kell kiszámítani a specializációt `controlled` .</span><span class="sxs-lookup"><span data-stu-id="68876-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="68876-217">`self`, amely azt jelzi, hogy a adjoint specializáció megegyezik a `body` specializációval.</span><span class="sxs-lookup"><span data-stu-id="68876-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="68876-218">Ez a `adjoint` és a `adjoint controlled` specializációra érvényes.</span><span class="sxs-lookup"><span data-stu-id="68876-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="68876-219">A `adjoint controlled` esetében `self` azt jelenti, hogy a `adjoint controlled` specializáció ugyanaz, mint a `controlled` specializáció.</span><span class="sxs-lookup"><span data-stu-id="68876-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="68876-220">`auto`, jelezve, hogy a fordítónak ki kell választania egy megfelelő irányelvet az alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="68876-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="68876-221">`auto`nem használható a `body` specializációhoz.</span><span class="sxs-lookup"><span data-stu-id="68876-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="68876-222">Az irányelvek és `auto` mind a záró pontosvesszőt igénylik `;` .</span><span class="sxs-lookup"><span data-stu-id="68876-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="68876-223">Az `auto` irányelv a következő generációs irányelvre lesz feloldva, ha a megadott explicit nyilatkozattal `body` rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="68876-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="68876-224">A `adjoint` specializáció a direktíva alapján jön létre `invert` .</span><span class="sxs-lookup"><span data-stu-id="68876-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="68876-225">A `controlled` specializáció a direktíva alapján jön létre `distribute` .</span><span class="sxs-lookup"><span data-stu-id="68876-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="68876-226">A `adjoint controlled` specializáció a direktíva alapján jön létre `invert` , ha explicit deklaráció `controlled` van megadva, de nem egyet `adjoint` , és `distribute` egyéb módon.</span><span class="sxs-lookup"><span data-stu-id="68876-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="68876-227">Ha egy művelet önadjoint, explicit módon megadhatja a adjoint vagy az irányított adjoint specializációt az `self` előállítási irányelv alapján, hogy a fordító felhasználhassa ezeket az információkat optimalizálási célokra.</span><span class="sxs-lookup"><span data-stu-id="68876-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="68876-228">A felhasználó által definiált implementációt tartalmazó specializációs nyilatkozat egy argumentummal, majd egy, a specializációt megvalósító Q # kóddal rendelkező utasítási blokkot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="68876-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="68876-229">A argumentumok listájában `...` a rendszer a művelet egészére vonatkozóan deklarált argumentumokat jelöli.</span><span class="sxs-lookup"><span data-stu-id="68876-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="68876-230">`body`És esetében `adjoint` az argumentumok listájának mindig a `(...)` következőnek kell lennie: és esetében `controlled` `adjoint controlled` az argumentumok listájának olyan szimbólumnak kell lennie, amely a vezérlési qubits tömbjét jelöli, majd a jelet `...` zárójelek közé kell tenni, például: `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="68876-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="68876-231">Példák</span><span class="sxs-lookup"><span data-stu-id="68876-231">Examples</span></span>

<span data-ttu-id="68876-232">A művelet deklarációja olyan egyszerű lehet, mint a következő, amely meghatározza a primitív Pauli X műveletet:</span><span class="sxs-lookup"><span data-stu-id="68876-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="68876-233">Vegye figyelembe, hogy a Pauli X művelet adjoint a direktíva határozza meg, `self` mert a definíció szerint a `X` saját inverze.</span><span class="sxs-lookup"><span data-stu-id="68876-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="68876-234">A fenti kód `PrepareEntangledPair` például egyenértékű az alábbi kóddal, amely explicit specializációs deklarációkat tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="68876-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="68876-235">A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan kell előállítani a specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="68876-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="68876-236">Felhasználó által definiált specializációs implementáció</span><span class="sxs-lookup"><span data-stu-id="68876-236">User-defined specialization implementation</span></span>

<span data-ttu-id="68876-237">Ha a fordító nem tud automatikusan előállítani egy bizonyos specializáció megvalósítását, vagy ha hatékonyabb megvalósításra van lehetőség, akkor a megvalósítás manuálisan is megadható.</span><span class="sxs-lookup"><span data-stu-id="68876-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="68876-238">A fenti példában `adjoint invert;` azt jelzi, hogy a adjoint specializációt úgy kell létrehozni, hogy visszaállítja a törzs megvalósítását, és `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint specializációt úgy kell létrehozni, hogy visszaállítja a szabályozott specializáció adott implementációját.</span><span class="sxs-lookup"><span data-stu-id="68876-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="68876-239">Ha az alapértelmezett törzsön kívül egy vagy több specializációt is explicit módon kell deklarálni, akkor az alapértelmezett törzs megvalósítását megfelelő specializációs nyilatkozatba is kell becsomagolni:</span><span class="sxs-lookup"><span data-stu-id="68876-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="68876-240">A specializációk érvényes meghatározásának körülményei</span><span class="sxs-lookup"><span data-stu-id="68876-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="68876-241">Adjoint/vezérelt üzemeltetési nyilatkozatok</span><span class="sxs-lookup"><span data-stu-id="68876-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="68876-242">A adjoint vagy az ellenőrzött verziók nélküli műveletet kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="68876-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="68876-243">Például a mérési műveletek egyike sem, mert nem invertálható vagy ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="68876-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="68876-244">Egy művelet támogatja a `Adjoint` és/vagy a-t, `Controlled` Ha a nyilatkozata tartalmazza a megfelelő specializációk implicit vagy explicit nyilatkozatát.</span><span class="sxs-lookup"><span data-stu-id="68876-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="68876-245">Az explicit módon bejelentett adjoint/vezérelt specializáció egy adjoint/vezérelt specializáció létezését feltételezi.</span><span class="sxs-lookup"><span data-stu-id="68876-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="68876-246">Egy olyan művelet esetében, amelynek a törzse ismétlődik, amíg-sikeres hurkokat tartalmaz, állítson be utasítások, mérések, visszaküldési utasítások vagy más olyan műveletekre irányuló hívásokat, amelyek nem támogatják az `Adjoint` adjoint-specializációt, és nem lehetséges, hogy automatikusan generáljon egy, az `invert` vagy az `auto` irányelvet követő specializáció</span><span class="sxs-lookup"><span data-stu-id="68876-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="68876-247">Egy olyan művelet esetében, amelynek a törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem támogatják az üzemen kívüli tevékenységet `Controlled` , nem lehetséges, hogy automatikusan generál egy szabályozott specializációt a `distribute` vagy a `auto` direktíva után.</span><span class="sxs-lookup"><span data-stu-id="68876-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="68876-248">Vezérelt Adjoint</span><span class="sxs-lookup"><span data-stu-id="68876-248">Controlled Adjoint</span></span>

<span data-ttu-id="68876-249">Egy művelet ellenőrzött adjoint-verziója határozza meg, hogy a rendszer milyen módon implementálja a adjoint a művelethez.</span><span class="sxs-lookup"><span data-stu-id="68876-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="68876-250">Az adjoint-verzióval nem rendelkező műveletet kell megadnia. például a mérési műveletek nem rendelkeznek szabályozott adjoint-verzióval, mert nem ellenőrizhetők és nem invertálható.</span><span class="sxs-lookup"><span data-stu-id="68876-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="68876-251">Egy művelet vezérelt adjoint-specializációjának léteznie kell, ha a adjoint és a szabályozott specializáció is létezik.</span><span class="sxs-lookup"><span data-stu-id="68876-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="68876-252">Ebben az esetben a vezérelt adjoint specializáció létezését következtetik ki, és a fordító a megfelelő specializációt hozza létre, ha nincs explicit módon definiált implementáció.</span><span class="sxs-lookup"><span data-stu-id="68876-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="68876-253">Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem rendelkeznek szabályozott adjoint-verzióval, a adjoint-specializáció automatikus generálása a `invert` `distribute` vagy az `auto` direktíva nem lehetséges.</span><span class="sxs-lookup"><span data-stu-id="68876-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="68876-254">Típus kompatibilitása</span><span class="sxs-lookup"><span data-stu-id="68876-254">Type Compatibility</span></span>

<span data-ttu-id="68876-255">Egy olyan művelet, amelynél további felhasználók támogatottak, a rendszer bárhol használható egy kevesebb ellátott művelettel, de ugyanez az aláírás várható.</span><span class="sxs-lookup"><span data-stu-id="68876-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="68876-256">Előfordulhat például, hogy egy típusú műveletet `(Qubit => Unit is Adj)` kell használni, ahol egy típusú művelet `(Qubit => Unit)` várható.</span><span class="sxs-lookup"><span data-stu-id="68876-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="68876-257">A Q # *a* hívható visszatérési típusok tekintetében a következő: egy típust visszaadó meghívható, amely `'A` kompatibilis az ugyanazzal a bemeneti típussal és a (z `'A` ) rendszerrel kompatibilis eredményhalmaz típussal.</span><span class="sxs-lookup"><span data-stu-id="68876-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="68876-258">A Q # *contravariant típusparamétert* a bemeneti típusok tekintetében: egy olyan meghívót, amely bemenetként fogadja a típust, `'A` és kompatibilis az ugyanazzal az eredménnyel, és egy olyan bemeneti típussal, amely kompatibilis a szolgáltatással `'A` .</span><span class="sxs-lookup"><span data-stu-id="68876-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="68876-259">Ez a következő definíciók miatt:</span><span class="sxs-lookup"><span data-stu-id="68876-259">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="68876-260">a következők teljesülnek:</span><span class="sxs-lookup"><span data-stu-id="68876-260">the following are true:</span></span>

- <span data-ttu-id="68876-261">Előfordulhat, hogy a függvény a `ConjugateInvertWith` vagy a `inner` argumentumával hívható meg `Invert` `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="68876-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="68876-262">Előfordulhat, hogy a függvényt `ConjugateUnitaryWith` egy argumentummal kell meghívni `inner` `ApplyUnitary` , de nem `Invert` .</span><span class="sxs-lookup"><span data-stu-id="68876-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="68876-263">Lehet, hogy egy típusú érték `(Qubit[] => Unit is Adj + Ctl)` adható vissza `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="68876-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68876-264">A Q # 0,3 jelentős változást vezetett be a felhasználó által definiált típusok viselkedésében.</span><span class="sxs-lookup"><span data-stu-id="68876-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="68876-265">A felhasználó által definiált típusokat az alapul szolgáló típus burkolt verziójaként, nem pedig altípusként kezeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="68876-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="68876-266">Ez azt jelenti, hogy a felhasználó által definiált típus értéke nem használható, ha a rendszer az alapul szolgáló típus értékét várta.</span><span class="sxs-lookup"><span data-stu-id="68876-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="68876-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="68876-267">Conjugations</span></span>

<span data-ttu-id="68876-268">A klasszikus BITS-vel szemben a kvantum-memória felszabadítása valamivel nagyobb mértékben történik, mivel a qubits vakon alaphelyzetbe állítása nem kívánt hatással lehet a fennmaradó számításra, ha a qubits továbbra is összefonódik.</span><span class="sxs-lookup"><span data-stu-id="68876-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="68876-269">Ezt elkerülheti, ha a memóriát a memória felszabadítása előtt megfelelően elvégezte.</span><span class="sxs-lookup"><span data-stu-id="68876-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="68876-270">A kvantum-számítástechnika általános mintája a következő:</span><span class="sxs-lookup"><span data-stu-id="68876-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="68876-271">A 0,9-es verziótól kezdődően a fenti transzformációt megvalósító ragozás-utasítást támogatunk.</span><span class="sxs-lookup"><span data-stu-id="68876-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="68876-272">Az utasítás használatával a művelet a `ApplyWith` következő módon valósítható meg:</span><span class="sxs-lookup"><span data-stu-id="68876-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="68876-273">Egy ilyen ragozó utasítás nyilvánvalóan sokkal hasznosabb lehet, ha a külső és belső átalakítás nem érhető el azonnal, hanem több utasításból álló blokk alapján.</span><span class="sxs-lookup"><span data-stu-id="68876-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="68876-274">A blokkon belül definiált utasítások inverz átalakítását a fordító automatikusan hozza létre, és az Apply-Block befejeződése után hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="68876-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="68876-275">Mivel a blokk részeként használt változó változók nem használhatók fel az alkalmazás-blokkban, a generált transzformáció garantált, hogy a adjoint a blokkon belül.</span><span class="sxs-lookup"><span data-stu-id="68876-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="68876-276">Új függvények definiálása</span><span class="sxs-lookup"><span data-stu-id="68876-276">Defining New Functions</span></span>

<span data-ttu-id="68876-277">A functions kizárólag determinisztikus, a klasszikus rutinok a Q #-ban, amelyek különböznek a műveletektől, és nem megengedett, hogy a kimeneti érték kiszámításán kívül más effektusok is legyenek.</span><span class="sxs-lookup"><span data-stu-id="68876-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="68876-278">Különösen a függvények nem hívhatnak meg műveleteket; qubits bevonása, lefoglalása vagy kölcsönzése; véletlenszerű számok mintavételezése; Ellenkező esetben a bemeneti értéken kívüli állapot függ egy függvénynek.</span><span class="sxs-lookup"><span data-stu-id="68876-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="68876-279">Ennek következményeként a Q # függvények *tisztán*vannak rendelve, hogy mindig ugyanazokat a bemeneti értékeket rendelik ugyanahhoz a kimeneti értékekhez.</span><span class="sxs-lookup"><span data-stu-id="68876-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="68876-280">Így a Q # fordító biztonságosan átrendezheti, hogyan és mikor hívja meg a függvényeket a műveleti specializációk létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="68876-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="68876-281">A Q # forrásfájl tetszőleges számú funkciót meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="68876-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="68876-282">A függvények nevének egyedinek kell lennie a névtéren belül, és nem ütközhet a művelet vagy a típus nevével.</span><span class="sxs-lookup"><span data-stu-id="68876-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="68876-283">A függvények definiálása hasonlóan működik a művelet definiálásához, azzal a kivétellel, hogy egy függvényhez nem lehet adjoint vagy vezérelt specializációt meghatározni.</span><span class="sxs-lookup"><span data-stu-id="68876-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="68876-284">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="68876-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="68876-285">vagy</span><span class="sxs-lookup"><span data-stu-id="68876-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="68876-286">Klasszikus Logic in functions = = jó</span><span class="sxs-lookup"><span data-stu-id="68876-286">Classical logic in functions == good</span></span>

<span data-ttu-id="68876-287">Ha ezt megteheti, hasznos lehet a klasszikus logikát kiírni a függvények helyett, hogy azok a műveletek során könnyebben használhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="68876-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="68876-288">Ha például a `Square` fenti deklarációt egy *műveletként*írta volna, akkor a fordító nem tudta garantálni, hogy ugyanazt a bemenetet ugyanazzal a kimenettel fogja létrehozni.</span><span class="sxs-lookup"><span data-stu-id="68876-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="68876-289">A függvények és a műveletek közötti különbség kihangsúlyozása érdekében vegye figyelembe, hogy egy véletlenszerűen kiválasztott számnak a Q #-műveletből való klasszikus mintavételezési problémája:</span><span class="sxs-lookup"><span data-stu-id="68876-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="68876-290">Minden egyes `U` híváskor egy másik művelet fog megjelenni `target` .</span><span class="sxs-lookup"><span data-stu-id="68876-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="68876-291">A fordító nem tudja garantálni, hogy ha felvettünk egy `adjoint auto` specializációs nyilatkozatot a alkalmazásba `U` , akkor az `U(target); Adjoint U(target);` identitásként viselkednek (azaz No-op).</span><span class="sxs-lookup"><span data-stu-id="68876-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="68876-292">Ez sérti a [vektorokban és mátrixokban](xref:microsoft.quantum.concepts.vectors)megjelenő adjoint definícióját, amely lehetővé teszi, hogy egy adjoint-specializációt egy olyan műveletben engedélyezzen, ahol a művelet meghívása <xref:microsoft.quantum.math.randomreal> megszegi a fordító által biztosított garanciákat; <xref:microsoft.quantum.math.randomreal> egy olyan művelet, amely esetében nem létezik adjoint vagy vezérelt verzió.</span><span class="sxs-lookup"><span data-stu-id="68876-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="68876-293">Másrészről, ami lehetővé teszi, hogy a függvényhívás, például a `Square` biztonságos, a fordító biztos lehet abban, hogy csak a bemenetet kell megőriznie ahhoz, hogy a `Square` kimenet stabil legyen.</span><span class="sxs-lookup"><span data-stu-id="68876-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="68876-294">Így a lehető legtöbb klasszikus logikát elkülönítheti a functions szolgáltatásban, így a logika más funkciókban és műveletekben is felhasználható.</span><span class="sxs-lookup"><span data-stu-id="68876-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="68876-295">Általános (típus-paraméteres) Callables</span><span class="sxs-lookup"><span data-stu-id="68876-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="68876-296">Számos olyan függvény és művelet, amelyet érdemes lehet meghatározni, valójában nem támaszkodik a bemenetek típusaira, hanem csak egy másik függvény vagy művelet segítségével implicit módon használják a saját típusait.</span><span class="sxs-lookup"><span data-stu-id="68876-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="68876-297">Tegyük fel például, hogy a *Térkép* fogalma számos funkcionális nyelvhez közös. a függvény $f (x) $ és Values $ \{ x_1, x_2, \dots, x_n \} $, Map egy új gyűjteményt ad vissza: $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="68876-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="68876-298">Ha ezt a Q #-ban szeretné megvalósítani, kihasználhatjuk, hogy a függvények első osztályúak legyenek.</span><span class="sxs-lookup"><span data-stu-id="68876-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="68876-299">Tegyük fel, hogy egy rövid példa a `Map` ★ helyőrzőként való használatára, miközben kitaláljuk, hogy milyen típusokra van szükségünk.</span><span class="sxs-lookup"><span data-stu-id="68876-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="68876-300">Vegye figyelembe, hogy ez a függvény ugyanúgy néz ki, mint amit a tényleges típusok helyettesítenek.</span><span class="sxs-lookup"><span data-stu-id="68876-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="68876-301">Az egész számokból a Paulis-ra történő leképezések például a lebegőpontos számok és a karakterláncok közötti térképre hasonlítanak.</span><span class="sxs-lookup"><span data-stu-id="68876-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="68876-302">Elvileg írhatunk egy verziót `Map` minden olyan típushoz, amelyben találkozhatunk, de ez számos problémát jelent.</span><span class="sxs-lookup"><span data-stu-id="68876-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="68876-303">Ha például hibát talál a alkalmazásban `Map` , akkor biztosítani kell, hogy a javítás a összes verziójában egységesen legyen alkalmazva `Map` .</span><span class="sxs-lookup"><span data-stu-id="68876-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="68876-304">Emellett, ha új rekordot vagy UDT hozunk létre, most új típust is létre kell állítania `Map` .</span><span class="sxs-lookup"><span data-stu-id="68876-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="68876-305">Ez egy kis mennyiségű ilyen funkció esetében is megtartható, mivel az `Map` új típusok bevezetésének díja aránytalanul nagy, meglehetősen rövid sorrendbe kerül.</span><span class="sxs-lookup"><span data-stu-id="68876-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="68876-306">A nehézségek nagy része azonban azt eredményezi, hogy a fordító nem kapott olyan információt, amely a különböző verzióival kapcsolatos információk felismeréséhez szükséges `Map` .</span><span class="sxs-lookup"><span data-stu-id="68876-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="68876-307">Gyakorlatilag azt szeretnénk, hogy a fordító a `Map` q # *típusaitól* a q # függvényekig valamilyen matematikai függvényt kezelje.</span><span class="sxs-lookup"><span data-stu-id="68876-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="68876-308">Ezt a fogalmat úgy kell megfogalmazni, hogy a functions és a Operations függvények *Type paramétereket*, valamint a szokásos rekord paramétereit is használják.</span><span class="sxs-lookup"><span data-stu-id="68876-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="68876-309">A fenti példákban szeretnénk úgy gondolni, hogy `Map` `Int, Pauli` az első esetben és a második esetben a típus paramétereit kell beírni `Double, String` .</span><span class="sxs-lookup"><span data-stu-id="68876-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="68876-310">A legtöbb esetben ezek a típusú paraméterek a szokásos típusokként használhatók: paraméterek típusú értékeket használunk a tömbök és rekordok, a függvények és a műveletek hívásához, valamint a szokásos vagy változtatható változókhoz való hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="68876-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="68876-311">A közvetett függőség legszélsőségesebb esete a qubits, ahol a Q # program nem hivatkozhat közvetlenül a típus struktúrájára `Qubit` , de ezeket a típusokat más műveletekre és funkciókra **kell** átadnia.</span><span class="sxs-lookup"><span data-stu-id="68876-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="68876-312">A fenti példához visszatérve láthatjuk, hogy a `Map` Type paraméterrel kell rendelkeznie, az egyiket pedig a bemenetnek, a `fn` másikat pedig a kimenetének kell képviselnie `fn` .</span><span class="sxs-lookup"><span data-stu-id="68876-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="68876-313">A Q #-ban ez a szög zárójelek (azaz `<>` nem brakets $ \braket $!) hozzáadásával történik, {} a deklarációban szereplő függvény vagy művelet neve után, valamint az egyes típusparaméter-paraméterek listázásával.</span><span class="sxs-lookup"><span data-stu-id="68876-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="68876-314">Az egyes típusparaméter-paraméterek nevének egy kullancstal kell kezdődnie `'` , amely azt jelzi, hogy ez egy típusparaméter, nem pedig egy egyszerű típus (más néven *konkrét* típus).</span><span class="sxs-lookup"><span data-stu-id="68876-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="68876-315">Ezért a következőt `Map` írjuk:</span><span class="sxs-lookup"><span data-stu-id="68876-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="68876-316">Vegye figyelembe, hogy a definíciója `Map<'Input, 'Output>` nagyon hasonlít a korábban megírt verziókhoz.</span><span class="sxs-lookup"><span data-stu-id="68876-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="68876-317">Az egyetlen különbség az, hogy kifejezetten tájékoztatjuk a fordítót, amely `Map` nem függ közvetlenül attól, hogy mi `'Input` és milyen `'Output` , de két típust is használ, ha közvetve használja őket `fn` .</span><span class="sxs-lookup"><span data-stu-id="68876-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="68876-318">Az ilyen módon történő Definiálás után meghívjuk, mintha `Map<'Input, 'Output>` egy szokványos függvény lenne:</span><span class="sxs-lookup"><span data-stu-id="68876-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="68876-319">Az általános függvények és műveletek írása egy olyan hely, ahol a "rekord-in rekord kijelentkezése" nagyon hasznos módszer a Q # függvények és műveletek gondolkodására.</span><span class="sxs-lookup"><span data-stu-id="68876-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="68876-320">Mivel minden függvény pontosan egy bemenetet vesz át, és pontosan egy kimenetet ad vissza, a típus bemenete `'T -> 'U` *bármilyen* Q # függvénynek felel meg.</span><span class="sxs-lookup"><span data-stu-id="68876-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="68876-321">Hasonlóképpen, minden művelet átadható egy típusú bemenetnek `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="68876-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="68876-322">Második példaként vegye figyelembe, hogy milyen kihívással kell elírnia egy olyan függvényt, amely két másik függvény összeállítását adja vissza:</span><span class="sxs-lookup"><span data-stu-id="68876-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="68876-323">Itt pontosan meg kell határoznia, hogy mi, és milyen mértékben `A` `B` `C` korlátozza az új függvény hasznosságát `Compose` .</span><span class="sxs-lookup"><span data-stu-id="68876-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="68876-324">Az összes után `Compose` csak a, a és a, a `A` `B` és a `C` *használatával* függ `innerFn` `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="68876-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="68876-325">Alternatív megoldásként hozzáadhatunk olyan típusú paramétereket, amelyek `Compose` azt jelzik, hogy a (z *any* ) és a (z) és a (z) a következő `A` `B` `C` paraméterekkel egyezik `innerFn` `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="68876-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="68876-326">A Q # standard kódtárak számos ilyen típusú paraméterrel rendelkező műveletet és funkciót biztosítanak, hogy a magasabb rendű vezérlési folyamat könnyebben kifejezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="68876-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="68876-327">Ezeket a [Q # standard Library útmutatóban](xref:microsoft.quantum.libraries.standard.intro)tovább tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="68876-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="68876-328">Callables első osztályú értékként</span><span class="sxs-lookup"><span data-stu-id="68876-328">Callables as First-Class Values</span></span>

<span data-ttu-id="68876-329">Az egyik kritikus módszer, amellyel a vezérlési folyamat és a klasszikus logika a függvények helyett functions használatával történik, hogy a Q # *első osztályú*műveleteit és funkcióit használják.</span><span class="sxs-lookup"><span data-stu-id="68876-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="68876-330">Ez azt eredményezi, hogy a nyelv minden értéke a saját jobb oldalán van.</span><span class="sxs-lookup"><span data-stu-id="68876-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="68876-331">Például a következőkben teljesen érvényes Q # kód van, ha egy kicsit indirekt:</span><span class="sxs-lookup"><span data-stu-id="68876-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="68876-332">A `ourH` fenti kódrészletben szereplő változó értéke ezután a művelet <xref:microsoft.quantum.intrinsic.h> , például az, hogy meghívjuk ezt az értéket, mint bármely más művelet.</span><span class="sxs-lookup"><span data-stu-id="68876-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="68876-333">Ez lehetővé teszi olyan műveletek írását, amelyek a bemenetük részeként végzik a műveleteket, és a magasabb rendű vezérlési folyamatokra vonatkozó fogalmakat képeznek.</span><span class="sxs-lookup"><span data-stu-id="68876-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="68876-334">Tegyük fel például, hogy a "Square" műveletet úgy képzeli el, hogy kétszer ugyanazt a cél qubit alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="68876-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="68876-335">Műveletek visszaküldése egy függvényből</span><span class="sxs-lookup"><span data-stu-id="68876-335">Returning operations from a function</span></span>

<span data-ttu-id="68876-336">Kiemeljük, hogy a kimenetek részeként is visszaadhatjuk a műveleteket, így a klasszikus feltételes logika valamilyen módon izolálható klasszikus függvényként, amely egy művelet formájában egy kvantum-program leírását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="68876-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="68876-337">Egyszerű példaként tekintse meg a teleportálás példáját, amelyben a kétbites klasszikus üzenetet fogadó fél az üzenetet arra használja, hogy dekódolja a qubit a megfelelő teleportált állapotba.</span><span class="sxs-lookup"><span data-stu-id="68876-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="68876-338">Ezt egy olyan függvényben írhatjuk, amely a két klasszikus bitet veszi át, és visszaadja a megfelelő dekódolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="68876-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="68876-339">Ez az új függvény valóban egy függvény, abban az esetben, ha a és az azonos értékeit `hereBit` hívjuk `thereBit` , mindig ugyanezt a műveletet fogjuk visszakapni.</span><span class="sxs-lookup"><span data-stu-id="68876-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="68876-340">Így a dekóder biztonságosan futtatható a műveletekben anélkül, hogy meg kellene indokolnia, hogy a dekódolási logika hogyan működjön együtt a különböző műveleti szakosodások definícióinak használatával.</span><span class="sxs-lookup"><span data-stu-id="68876-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="68876-341">Ez azt is megteheti, hogy elszigetelte a klasszikus logikát egy függvényen belül, garantálva azt a fordítót, hogy a függvény hívása büntetlenül rendezhető, feltéve, hogy a bevitel megmarad.</span><span class="sxs-lookup"><span data-stu-id="68876-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="68876-342">Részleges alkalmazás</span><span class="sxs-lookup"><span data-stu-id="68876-342">Partial Application</span></span>

<span data-ttu-id="68876-343">A műveleteknek a *részleges alkalmazás*használatával történő visszaadását lehetővé tehetjük, amelyekben a bemenet egy vagy több részének megadásával egy függvénynek vagy műveletnek a tényleges hívása nélkül is megadható.</span><span class="sxs-lookup"><span data-stu-id="68876-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="68876-344">Például a fenti példa visszahívásával `ApplyTwice` jelezheti, hogy nem szeretnénk megadni, azonnal, hogy a bemeneti művelet melyik qubit vonatkozzon:</span><span class="sxs-lookup"><span data-stu-id="68876-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="68876-345">Ebben az esetben a helyi változó `twiceOp` a részlegesen alkalmazott műveletet tartalmazza `ApplyTwice(op, _)` , ahol a bemenetben még nem megadott részek szerepelnek `_` .</span><span class="sxs-lookup"><span data-stu-id="68876-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="68876-346">Ha a következő sorban hívja meg a hívást, a rendszer a `twiceOp` részlegesen alkalmazott művelethez továbbítja a bemenetet az eredeti művelethez.</span><span class="sxs-lookup"><span data-stu-id="68876-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="68876-347">Így a fenti kódrészlet gyakorlatilag azonos azzal, hogy közvetlenül meghívja őket, és a `ApplyTwice(op, target)` Mentés után egy új helyi változót vezettünk be, amely lehetővé teszi a hívás késleltetését, miközben a bemenet egyes részeit biztosítjuk.</span><span class="sxs-lookup"><span data-stu-id="68876-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="68876-348">Mivel egy részlegesen alkalmazott művelet valójában nem lett meghívva, amíg a teljes adatbevitel meg nem történt, akkor a függvényekből is biztonságosan részben alkalmazhatjuk a műveleteket.</span><span class="sxs-lookup"><span data-stu-id="68876-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="68876-349">Elméletileg a klasszikus logika `SquareOperation` sokkal jobban érintett, de továbbra is el van különítve a többi művelettől, mert az garantálja, hogy a fordító a functions szolgáltatással kapcsolatban tud nyújtani.</span><span class="sxs-lookup"><span data-stu-id="68876-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="68876-350">Ezt a megközelítést fogja használni a Q # standard könyvtárban a klasszikus vezérlési folyamat kifejezésére, amely a kvantum-programokban könnyen használható.</span><span class="sxs-lookup"><span data-stu-id="68876-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="68876-351">Rekurzió</span><span class="sxs-lookup"><span data-stu-id="68876-351">Recursion</span></span>

<span data-ttu-id="68876-352">A Q # callables közvetlenül vagy közvetve rekurzívak.</span><span class="sxs-lookup"><span data-stu-id="68876-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="68876-353">Ez azt is megteheti, hogy egy művelet vagy funkció meghívhatja magát, vagy meghívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.</span><span class="sxs-lookup"><span data-stu-id="68876-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="68876-354">A rekurzió használatának két fontos megjegyzése van, azonban:</span><span class="sxs-lookup"><span data-stu-id="68876-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="68876-355">A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.</span><span class="sxs-lookup"><span data-stu-id="68876-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="68876-356">Ez jelentős hatással lehet az algoritmus végrehajtási idejére.</span><span class="sxs-lookup"><span data-stu-id="68876-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="68876-357">Ha tényleges kvantum-eszközön végez végrehajtást, előfordulhat, hogy a halmozott terület korlátozva van, ezért a mélyebb rekurzió hibát okozhat.</span><span class="sxs-lookup"><span data-stu-id="68876-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="68876-358">A Q # Compiler és a Runtime nem azonosítja és optimalizálja a farok rekurzióját.</span><span class="sxs-lookup"><span data-stu-id="68876-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68876-359">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="68876-359">Next steps</span></span>

<span data-ttu-id="68876-360">További tudnivalók a Q #-ban található [változókról](xref:microsoft.quantum.guide.variables) .</span><span class="sxs-lookup"><span data-stu-id="68876-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>