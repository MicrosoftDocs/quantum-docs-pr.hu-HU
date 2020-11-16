---
title: 'Műveletek és függvények a-ben Q#'
description: Műveletek és függvények definiálása és hívása, valamint az ellenőrzött és adjoint műveletekre vonatkozó specializációk.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 55e6d3e1a242386c46213083692377520df83a80
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692138"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="d086b-103">Műveletek és függvények a-ben Q#</span><span class="sxs-lookup"><span data-stu-id="d086b-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="d086b-104">Új műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="d086b-104">Defining New Operations</span></span>

<span data-ttu-id="d086b-105">A műveletek a legfontosabbak Q# .</span><span class="sxs-lookup"><span data-stu-id="d086b-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="d086b-106">A bejelentést követően meghívhatók a klasszikus .NET-alkalmazásokból, például szimulátor vagy más, a alkalmazáson belüli műveletekkel Q# .</span><span class="sxs-lookup"><span data-stu-id="d086b-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="d086b-107">A ben definiált minden művelet Q# tetszőleges számú egyéb műveletet hívhat meg, beleértve a nyelv által meghatározott beépített belső műveleteket is.</span><span class="sxs-lookup"><span data-stu-id="d086b-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="d086b-108">A belső műveletek meghatározásának konkrét módja a Q# célszámítógéptől függ.</span><span class="sxs-lookup"><span data-stu-id="d086b-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="d086b-109">A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.</span><span class="sxs-lookup"><span data-stu-id="d086b-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="d086b-110">Minden Q# forrásfájl tetszőleges számú műveletet meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="d086b-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="d086b-111">A művelet nevének a névtéren belül egyedinek kell lennie, és nem ütközhet a típus vagy a függvény nevével.</span><span class="sxs-lookup"><span data-stu-id="d086b-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="d086b-112">A műveleti deklaráció a kulcsszóból áll, amelyet a művelet nevét, a művelethez tartozó `operation` argumentumokat definiáló típust, egy kettőspontot, egy Type jegyzetet ad meg, amely a művelet `:` eredményének típusát írja le, opcionálisan megadhatja a műveleti jellemzőket, egy nyitó kapcsos zárójelet, majd a műveleti deklaráció törzsét kapcsos zárójelek közé `{ }` .</span><span class="sxs-lookup"><span data-stu-id="d086b-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="d086b-113">Mindegyik művelet egy bemenetet hoz létre, kimenetet állít elő, és meghatározza egy vagy több műveleti specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="d086b-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="d086b-114">A lehetséges szakosodások, valamint az ezek meghatározása és meghívása a cikk különböző fejezeteiben olvasható.</span><span class="sxs-lookup"><span data-stu-id="d086b-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="d086b-115">Egyelőre a következő műveletnek kell megfontolnia, amely csak az alapértelmezett szövegtörzset határozza meg, és egyetlen qubit használ a bemenetként, majd meghívja a beépített <xref:Microsoft.Quantum.Intrinsic.X> műveletet a bemeneten:</span><span class="sxs-lookup"><span data-stu-id="d086b-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:Microsoft.Quantum.Intrinsic.X> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="d086b-116">A kulcsszó `operation` megkezdi a művelet definícióját, amelyet a név követ, itt: `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="d086b-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="d086b-117">A következő lépés a bemenet típusa ( `Qubit` ), valamint egy név, amely az `target` új műveleten belüli bemenetre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="d086b-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="d086b-118">Végül `Unit` azt is meghatározza, hogy a művelet kimenete üres.</span><span class="sxs-lookup"><span data-stu-id="d086b-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="d086b-119">`Unit` a használata hasonlóan a `void` C#-ban és más, felszólító nyelvekhez, és az `unit` F # és más funkcionális nyelvekkel egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="d086b-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="d086b-120">A műveletek több érdekes típust is visszaadhatnak, mint a `Unit` .</span><span class="sxs-lookup"><span data-stu-id="d086b-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="d086b-121">A <xref:Microsoft.Quantum.Intrinsic.m> művelet például egy típusú kimenetet ad vissza `Result` , amely a mérés végrehajtását jelöli.</span><span class="sxs-lookup"><span data-stu-id="d086b-121">For instance, the <xref:Microsoft.Quantum.Intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="d086b-122">Átadhatja egy műveletből egy másik műveletnek, vagy felhasználhatja azt a `let` kulcsszóval egy új változó definiálásához.</span><span class="sxs-lookup"><span data-stu-id="d086b-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="d086b-123">Ez a megközelítés lehetővé teszi a klasszikus számítások használatát, amelyek alacsony szinten működnek a kvantum-műveletekkel, például a [sűrűbb kódolásban](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="d086b-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="d086b-124">A minden művelete Q# pontosan egy bemenetet vesz fel, és pontosan egy kimenetet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="d086b-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="d086b-125">Több bemenet és kimenet is szerepel a *rekordok* használatával, amely egyszerre több értéket gyűjt össze egyetlen értékkel.</span><span class="sxs-lookup"><span data-stu-id="d086b-125">Multiple inputs and outputs are represented using *tuples* , which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="d086b-126">Ebben a tekintetben Q# a egy "rekordos kijelentkezés" nyelv.</span><span class="sxs-lookup"><span data-stu-id="d086b-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="d086b-127">Ezt a fogalmat követve az üres zárójelek egy halmaza, `()` amelynek a típusa "Empty" (üres `Unit` ) rekord.</span><span class="sxs-lookup"><span data-stu-id="d086b-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="d086b-128">Vezérelt és Adjoint műveletek</span><span class="sxs-lookup"><span data-stu-id="d086b-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="d086b-129">Ha egy művelet egy egységes átalakítást valósít meg, mint a számos művelet esetében, Q# akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve* legyen.</span><span class="sxs-lookup"><span data-stu-id="d086b-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled* .</span></span> <span data-ttu-id="d086b-130">Egy művelet *adjoint* -specializálása meghatározza, hogy a művelet milyen hatással van az "inverz" értékre, míg a *szabályozott* specializáció meghatározza, hogy a művelet hogyan működik, ha az alkalmazás egy adott kvantum-regiszter állapotára van feltétele.</span><span class="sxs-lookup"><span data-stu-id="d086b-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="d086b-131">A Adjoints elengedhetetlen a kvantum-számítási feladatok számos aspektusa szempontjából.</span><span class="sxs-lookup"><span data-stu-id="d086b-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="d086b-132">A hasznos programozási technikák mellett egy ilyen helyzetre például a Q# következő témakörben olvashat [: Control flow: conjugations](xref:microsoft.quantum.guide.controlflow#conjugations).</span><span class="sxs-lookup"><span data-stu-id="d086b-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Control Flow: Conjugations](xref:microsoft.quantum.guide.controlflow#conjugations).</span></span> <span data-ttu-id="d086b-133">Egy művelet ellenőrzött verziója olyan új művelet, amely hatékonyan alkalmazza az alapműveletet, ha az összes vezérlő qubits megadott állapotban van.</span><span class="sxs-lookup"><span data-stu-id="d086b-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="d086b-134">Ha a vezérlő qubits van, akkor az alapszintű műveletet a rendszer következetesen alkalmazza a Felfekvés megfelelő részére.</span><span class="sxs-lookup"><span data-stu-id="d086b-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="d086b-135">Így a rendszer gyakran használja az ellenőrzött műveleteket a felakadás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d086b-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="d086b-136">Természetesen egy *vezérelt adjoint* specializáció is létezhet, amely meghatározza egy művelet adjoint vezérelt alkalmazását.</span><span class="sxs-lookup"><span data-stu-id="d086b-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="d086b-137">Ha $U $ egy művelet által megvalósított egységes átalakítás `U` , akkor `Adjoint U` az egységes átalakítást jelöli $U ^ \dagger $, amely a komplex konjugátum átültetése.</span><span class="sxs-lookup"><span data-stu-id="d086b-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="d086b-138">Egy művelet egymást követő alkalmazása után a adjoint állapota változatlan marad, ahogy azt az a tény mutatja, hogy $UU ^ \dagger = U ^ \dagger U = \id $, az Identity Matrix.</span><span class="sxs-lookup"><span data-stu-id="d086b-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="d086b-139">Egy vezérelt művelet egységes ábrázolása valamivel árnyaltabb, de további részleteket a [Quantum Computing-fogalmak: több qubits](xref:microsoft.quantum.concepts.multiple-qubits)is talál.</span><span class="sxs-lookup"><span data-stu-id="d086b-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="d086b-140">A következő szakasz ismerteti, hogyan hívhatja meg ezeket a különféle szakkifejezéseket a Q# kódban, és hogyan határozhat meg műveleteket a támogatásához.</span><span class="sxs-lookup"><span data-stu-id="d086b-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="d086b-141">Hívási művelet specializációi</span><span class="sxs-lookup"><span data-stu-id="d086b-141">Calling operation specializations</span></span>

<span data-ttu-id="d086b-142">A *-ben egy olyan* Q# gyár, amely új műveletet határoz meg egy másik műveletből.</span><span class="sxs-lookup"><span data-stu-id="d086b-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="d086b-143">A két szabványos, a Q# és a `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="d086b-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="d086b-144">Az új művelet megvalósításának meghatározásakor az üzemben lévők az alapművelet megvalósításához férnek hozzá.</span><span class="sxs-lookup"><span data-stu-id="d086b-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="d086b-145">Így a fellépők összetettebb funkciókkal rendelkezhetnek, mint a hagyományos magasabb szintű függvények.</span><span class="sxs-lookup"><span data-stu-id="d086b-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="d086b-146">A rendszer nem rendelkezik képviselettel a Q# típusban.</span><span class="sxs-lookup"><span data-stu-id="d086b-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="d086b-147">Ezért jelenleg nem lehet őket egy változóhoz kötni, vagy argumentumként átadni őket.</span><span class="sxs-lookup"><span data-stu-id="d086b-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="d086b-148">Használjon egy olyan műveletet, amely egy olyan műveletre alkalmazza, amely egy új műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="d086b-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="d086b-149">Ha például a műveletet a `Adjoint` művelettel alkalmazza, az `Y` új műveletet adja vissza `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="d086b-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="d086b-150">Az új műveletet más műveletekhez hasonlóan hívhatja meg.</span><span class="sxs-lookup"><span data-stu-id="d086b-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="d086b-151">Ahhoz, hogy egy művelet támogassa a vagy a nem működő példányok alkalmazását `Adjoint` `Controlled` , szükségszerűen a visszatérési típusának kell lennie `Unit` .</span><span class="sxs-lookup"><span data-stu-id="d086b-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="d086b-152">`Adjoint` nem aktív</span><span class="sxs-lookup"><span data-stu-id="d086b-152">`Adjoint` functor</span></span>

<span data-ttu-id="d086b-153">Ennek megfelelően a `Adjoint Y(q1)` `Adjoint` rendszer a műveletre alkalmazza az `Y` új művelet létrehozását, és az új műveletet a következőre alkalmazza: `q1` .</span><span class="sxs-lookup"><span data-stu-id="d086b-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="d086b-154">Az új művelet ugyanazzal az aláírással és típussal rendelkezik, mint az alapművelet `Y` .</span><span class="sxs-lookup"><span data-stu-id="d086b-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="d086b-155">Ebben az esetben az új művelet is támogatja `Adjoint` , és csak akkor támogatja, `Controlled` Ha az alapművelet nem volt.</span><span class="sxs-lookup"><span data-stu-id="d086b-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="d086b-156">A kihasználó a `Adjoint` saját inverze, azaz `Adjoint Adjoint Op` mindig ugyanaz, mint `Op` .</span><span class="sxs-lookup"><span data-stu-id="d086b-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="d086b-157">`Controlled` nem aktív</span><span class="sxs-lookup"><span data-stu-id="d086b-157">`Controlled` functor</span></span>

<span data-ttu-id="d086b-158">Hasonlóképpen `Controlled X(controls, target)` alkalmazza a `Controlled` műveletet a `X` műveletre egy új művelet létrehozásához, és az új műveletet a és a rendszerre alkalmazza `controls` `target` .</span><span class="sxs-lookup"><span data-stu-id="d086b-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="d086b-159">A-ben az Q# ellenőrzött verziók mindig a vezérlési qubits egy tömbjét használják, és az ellenőrzés mindig a számítási ( `PauliZ` ) `One` állapot, a $ \ket $ qubits összes vezérlője alapján zajlik {1} .</span><span class="sxs-lookup"><span data-stu-id="d086b-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="d086b-160">A más állapotokon alapuló vezérlést úgy érheti el, hogy a megfelelő egységes műveletet alkalmazza a vezérlési qubits az ellenőrzött művelet előtt, majd alkalmazza az egységes művelet inverzét az ellenőrzött művelet után.</span><span class="sxs-lookup"><span data-stu-id="d086b-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="d086b-161">Ha például egy `X` műveletet egy vezérlő qubit egy vezérelt művelet előtt és után alkalmaz, akkor a művelet az `Zero` adott qubit állapotára ($ \ket $) irányítja a műveletet, és az állapotra vonatkozó {0} `H` vezérlők előtt és után alkalmaz egy műveletet `PauliX` `One` , azaz az-1 sajátérték a Pauli X, a $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt $ helyett, nem pedig {2} az `PauliZ` `One` állapotot.</span><span class="sxs-lookup"><span data-stu-id="d086b-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="d086b-162">Egy műveleti kifejezés miatt új műveleti kifejezés is létrehozható az elválasztó használatával `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="d086b-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="d086b-163">Az új művelet aláírása az eredeti művelet aláírásán alapul.</span><span class="sxs-lookup"><span data-stu-id="d086b-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="d086b-164">Az eredmény típusa azonos, de a bemeneti típus egy kétrekordos qubit tömb, amely a vezérlő qubit (ka) t az első elemként, az eredeti művelet argumentumait pedig második elemként tárolja.</span><span class="sxs-lookup"><span data-stu-id="d086b-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="d086b-165">Az új művelet támogatja a- `Controlled` t, és csak akkor támogatja, `Adjoint` Ha az eredeti művelet megtörtént.</span><span class="sxs-lookup"><span data-stu-id="d086b-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="d086b-166">Ha az eredeti művelet csak egyetlen argumentumot vett igénybe, akkor az önálló [rekordos egyenértékűség](xref:microsoft.quantum.guide.types) a játékba kerül.</span><span class="sxs-lookup"><span data-stu-id="d086b-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="d086b-167">Például a a `Controlled X` művelet ellenőrzött verziója `X` .</span><span class="sxs-lookup"><span data-stu-id="d086b-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="d086b-168">`X` típusa van `(Qubit => Unit is Adj + Ctl)` , ezért `Controlled X` a Type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; egypéldányos egyenértékűség miatt ez megegyezik a következővel: `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d086b-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="d086b-169">Ha az alapművelet több argumentumot is vett igénybe, ne felejtse el zárójelek közé helyezni a művelet ellenőrzött verziójának megfelelő argumentumait, hogy azok egy rekordba legyenek konvertálva.</span><span class="sxs-lookup"><span data-stu-id="d086b-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="d086b-170">Például a a `Controlled Rz` művelet ellenőrzött verziója `Rz` .</span><span class="sxs-lookup"><span data-stu-id="d086b-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="d086b-171">`Rz` típusa van `((Double, Qubit) => Unit is Adj + Ctl)` , ezért `Controlled Rz` típusa van `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d086b-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d086b-172">Tehát `Controlled Rz(controls, (0.1, target))` érvényes hívás lenne `Controlled Rz` (jegyezze fel a zárójeleket `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="d086b-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="d086b-173">Egy másik példaként `CNOT(control, target)` a is megvalósítható `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="d086b-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="d086b-174">Ha egy célt két vezérlő qubits (CCNOT) vezérel, használjon egy `Controlled X([control1, control2], target)` utasítást.</span><span class="sxs-lookup"><span data-stu-id="d086b-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="d086b-175">A és a-elválasztók `Controlled` `Adjoint` ingázás, így nincs különbség a alkalmazása `Controlled Adjoint Op` vagy a `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="d086b-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="d086b-176">Vezérelt és Adjoint implementációk meghatározása</span><span class="sxs-lookup"><span data-stu-id="d086b-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="d086b-177">Az előző példákban szereplő első művelet deklarációjában a műveletek és az aláírásokkal, illetve a műveletekkel `BitFlip` `DecodeSuperdense` lettek definiálva `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="d086b-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="d086b-178">A `DecodeSuperdense` mértékek beleszámítása nem egy egységes művelet, ezért nem léteznek szabályozott, nem adjoint specializációk (az ilyen művelet visszaadására vonatkozó követelmény visszahívása `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="d086b-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="d086b-179">Mivel azonban `BitFlip` egyszerűen végrehajtja az egységes <xref:Microsoft.Quantum.Intrinsic.X> műveletet, megadhatja azt mindkét specializációval.</span><span class="sxs-lookup"><span data-stu-id="d086b-179">However, as `BitFlip` simply performs the unitary <xref:Microsoft.Quantum.Intrinsic.X> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="d086b-180">Ez a szakasz részletesen ismerteti, hogyan lehet felvenni a specializációkat a Q# műveleti deklarációkban, így lehetővé teszi számukra, hogy meghívják őket a vagy a-rel együtt `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="d086b-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="d086b-181">Ha további információt szeretne arról, hogy milyen helyzetek érvényesek, vagy nem érvényesek bizonyos specializációk bejelentésére, tekintse meg a jelen cikkben szereplő, [a specializációk érvényességét meghatározó körülményeket](#circumstances-for-validly-defining-specializations) .</span><span class="sxs-lookup"><span data-stu-id="d086b-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="d086b-182">A művelet jellemzői határozzák meg, hogy milyen típusú elválasztók alkalmazhatók a deklarált műveletre, és milyen hatással vannak rájuk.</span><span class="sxs-lookup"><span data-stu-id="d086b-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="d086b-183">Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható, pontosabban a következő műveletekkel kapcsolatos megjegyzésekkel: vagy `is Adj` , `is Ctl` vagy `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="d086b-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="d086b-184">Az egyes specializációk tényleges implementációja *implicit módon* vagy *explicit módon* definiálva lehet.</span><span class="sxs-lookup"><span data-stu-id="d086b-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="d086b-185">Implementációk implicit meghatározása</span><span class="sxs-lookup"><span data-stu-id="d086b-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="d086b-186">Ebben az esetben a műveleti deklaráció törzse kizárólag az alapértelmezett implementációból áll.</span><span class="sxs-lookup"><span data-stu-id="d086b-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="d086b-187">Például:</span><span class="sxs-lookup"><span data-stu-id="d086b-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="d086b-188">Itt az egyes implicit módon deklarált specializációhoz tartozó implementációt automatikusan generálja a fordító, amelyet a vagy a rendszer `Adjoint` használatakor kell végrehajtani `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="d086b-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="d086b-189">Így a hívása `Adjoint PrepareEntangledPair` azt eredményezi, hogy a fordító végrehajtja a adjoint, `CNOT` majd a adjoint `H` .</span><span class="sxs-lookup"><span data-stu-id="d086b-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="d086b-190">Ezek az egyéni műveletek önmagukban is adjoint, így az eredményül kapott `Adjoint PrepareEntangledPair` művelet csupán a alkalmazásból, majd a rendszerből áll `CNOT(here, there)` `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="d086b-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="d086b-191">Ebből kifolyólag ezt az `DecodeSuperdense` előző példában több tömörítéssel is megírhatja, ha a adjoint segítségével `PrepareEntangledPair` átalakítja a kusza állapotot egy nem összeillesztett qubits:</span><span class="sxs-lookup"><span data-stu-id="d086b-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="d086b-192">A deklarációban szereplő műveleti jellemzőkkel rendelkező Megjegyzés hasznos annak biztosításához, hogy a fordító automatikusan generáljon más specializációkat az alapértelmezett implementáció alapján.</span><span class="sxs-lookup"><span data-stu-id="d086b-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="d086b-193">Számos fontos korlátozást kell figyelembe venni, amikor a rendszer megtervezi, hogy milyen műveleteket kell megterveznie.</span><span class="sxs-lookup"><span data-stu-id="d086b-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="d086b-194">A legtöbb kritikus jelentőséggel bír, ha egy olyan műveletre specializálódott, amely bármely más művelet kimeneti értékét használja, *nem* lehet automatikusan generálni a fordítótól, mert nem egyértelmű, hogy az ilyen műveletekben szereplő utasítások hogyan rendezhetők át ugyanezen hatás megszerzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="d086b-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="d086b-195">Ezért gyakran érdemes explicit módon megadnia a különböző implementációkat.</span><span class="sxs-lookup"><span data-stu-id="d086b-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="d086b-196">Implementációk explicit meghatározása</span><span class="sxs-lookup"><span data-stu-id="d086b-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="d086b-197">Abban az esetben, ha a fordító nem tudja előállítani a megvalósítást, explicit módon megadhatja.</span><span class="sxs-lookup"><span data-stu-id="d086b-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="d086b-198">Az ilyen explicit specializációs nyilatkozatok megfelelő *generációs irányelvből* vagy felhasználó által definiált implementációból állhatnak.</span><span class="sxs-lookup"><span data-stu-id="d086b-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="d086b-199">A következőkben a lehetőségek teljes köre látható, néhány példa a explicit specializációra.</span><span class="sxs-lookup"><span data-stu-id="d086b-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="d086b-200">Explicit specializációs deklarációk</span><span class="sxs-lookup"><span data-stu-id="d086b-200">Explicit specialization declarations</span></span>

<span data-ttu-id="d086b-201">Q# a műveletek a következő explicit specializációs deklarációkat tartalmazhatják:</span><span class="sxs-lookup"><span data-stu-id="d086b-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="d086b-202">A `body` specializáció meghatározza a művelet végrehajtását, és nem alkalmazta a műveletet.</span><span class="sxs-lookup"><span data-stu-id="d086b-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="d086b-203">A `adjoint` specializáció meghatározza a művelet megvalósítását az `Adjoint` alkalmazottal.</span><span class="sxs-lookup"><span data-stu-id="d086b-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="d086b-204">A `controlled` specializáció meghatározza a művelet megvalósítását az `Controlled` alkalmazottal.</span><span class="sxs-lookup"><span data-stu-id="d086b-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="d086b-205">A `controlled adjoint` specializáció meghatározza a művelet megvalósítását mind a, mind a által alkalmazott operációs rendszersel `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="d086b-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="d086b-206">Ez a specializáció is elnevezhető `adjoint controlled` , mivel a két elválasztó.</span><span class="sxs-lookup"><span data-stu-id="d086b-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="d086b-207">A műveletek specializációja a specializációs címkéből (például vagy) áll, amelyet az alábbiak `body` `adjoint` egyike követ:</span><span class="sxs-lookup"><span data-stu-id="d086b-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="d086b-208">Az alábbi módon leírt explicit deklaráció.</span><span class="sxs-lookup"><span data-stu-id="d086b-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="d086b-209">Egy *irányelv* , amely közli a fordítóval, *Hogyan* hozhatja ki a specializációt, az egyik:</span><span class="sxs-lookup"><span data-stu-id="d086b-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="d086b-210">`intrinsic`, amely azt jelzi, hogy a célszámítógép biztosítja a specializációt.</span><span class="sxs-lookup"><span data-stu-id="d086b-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="d086b-211">`distribute`, a és a `controlled` `controlled adjoint` specializációk használatával.</span><span class="sxs-lookup"><span data-stu-id="d086b-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="d086b-212">A használatakor `controlled` azt jelzi, hogy a fordítónak ki kell számítania a specializációt úgy, hogy az `Controlled` összes műveletére alkalmazza a-t `body` .</span><span class="sxs-lookup"><span data-stu-id="d086b-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="d086b-213">A használatakor `controlled adjoint` azt jelzi, hogy a fordítónak a `Controlled` specializáció összes műveletére alkalmazva kell kiszámítani a specializációt `adjoint` .</span><span class="sxs-lookup"><span data-stu-id="d086b-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="d086b-214">`invert`, ami azt jelzi, hogy a fordítónak ki kell számítania a `adjoint` specializációt úgy, hogy visszaállítja a `body` műveletet, például megfordítja a műveletek sorrendjét, és alkalmazza a adjoint.</span><span class="sxs-lookup"><span data-stu-id="d086b-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="d086b-215">A használatakor `adjoint controlled` Ez azt jelzi, hogy a fordítónak a specializáció megfordításával kell kiszámítani a specializációt `controlled` .</span><span class="sxs-lookup"><span data-stu-id="d086b-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="d086b-216">`self`, amely azt jelzi, hogy a adjoint specializáció megegyezik a `body` specializációval.</span><span class="sxs-lookup"><span data-stu-id="d086b-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="d086b-217">`self`A használata jogi a `adjoint` és a `adjoint controlled` specializációhoz.</span><span class="sxs-lookup"><span data-stu-id="d086b-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="d086b-218">A `adjoint controlled` esetében `self` azt jelenti, hogy a `adjoint controlled` specializáció ugyanaz, mint a `controlled` specializáció.</span><span class="sxs-lookup"><span data-stu-id="d086b-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="d086b-219">`auto`, jelezve, hogy a fordítónak ki kell választania egy megfelelő irányelvet az alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="d086b-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="d086b-220">`auto`A specializációhoz nem használható `body` .</span><span class="sxs-lookup"><span data-stu-id="d086b-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="d086b-221">Az irányelvek és `auto` mind a záró pontosvesszőt igénylik `;` .</span><span class="sxs-lookup"><span data-stu-id="d086b-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="d086b-222">Az `auto` irányelv a következő létrehozott irányelvre lesz feloldva, ha a megadott explicit nyilatkozattal `body` rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="d086b-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="d086b-223">A `adjoint` specializáció a direktíva alapján jön létre `invert` .</span><span class="sxs-lookup"><span data-stu-id="d086b-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="d086b-224">A `controlled` specializáció a direktíva alapján jön létre `distribute` .</span><span class="sxs-lookup"><span data-stu-id="d086b-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="d086b-225">A `adjoint controlled` specializáció a direktíva alapján jön létre `invert` , ha explicit deklaráció `controlled` van megadva, de nem egyet `adjoint` , és `distribute` egyéb módon.</span><span class="sxs-lookup"><span data-stu-id="d086b-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="d086b-226">Ha egy művelet önadjoint, explicit módon megadhatja a adjoint vagy az irányított adjoint specializációt az `self` előállítási irányelv alapján, hogy a fordító felhasználhassa ezeket az információkat optimalizálási célokra.</span><span class="sxs-lookup"><span data-stu-id="d086b-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="d086b-227">A felhasználó által definiált implementációt tartalmazó specializációs nyilatkozat egy olyan argumentumot tartalmaz, amelyet a Q# specializációt megvalósító kóddal rendelkező utasítás követ.</span><span class="sxs-lookup"><span data-stu-id="d086b-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="d086b-228">A argumentumok listájában `...` a rendszer a művelet egészére vonatkozóan deklarált argumentumokat jelöli.</span><span class="sxs-lookup"><span data-stu-id="d086b-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="d086b-229">`body`És esetében `adjoint` az argumentumok listájának mindig a `(...)` következőnek kell lennie: és esetében `controlled` `adjoint controlled` az argumentumok listájának olyan szimbólumnak kell lennie, amely a vezérlési qubits tömbjét jelöli, majd a jelet `...` zárójelek közé kell tenni, például: `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="d086b-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="d086b-230">Példák</span><span class="sxs-lookup"><span data-stu-id="d086b-230">Examples</span></span>

<span data-ttu-id="d086b-231">A művelet deklarációja olyan egyszerű lehet, mint a következő, amely meghatározza a primitív Pauli X műveletet:</span><span class="sxs-lookup"><span data-stu-id="d086b-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="d086b-232">Vegye figyelembe, hogy a Pauli X művelet adjoint a direktíva határozza meg, `self` mert a definíció szerint a `X` saját inverze.</span><span class="sxs-lookup"><span data-stu-id="d086b-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="d086b-233">A korábbi `PrepareEntangledPair` példában a kód egyenértékű a következő kóddal, amely explicit specializációs deklarációkat tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="d086b-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="d086b-234">A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan kell előállítani a specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="d086b-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="d086b-235">Felhasználó által definiált specializációs implementáció</span><span class="sxs-lookup"><span data-stu-id="d086b-235">User-defined specialization implementation</span></span>

<span data-ttu-id="d086b-236">Ha a fordító nem tud automatikusan létrehozni egy bizonyos specializáció megvalósítását, vagy ha hatékonyabb megvalósítást lehet megadni, manuálisan is meghatározhatja a megvalósítást.</span><span class="sxs-lookup"><span data-stu-id="d086b-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="d086b-237">Az előző példában `adjoint invert;` azt jelzi, hogy a adjoint specializációt úgy kell létrehozni, hogy visszaállítja a törzs megvalósítását, és `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint specializációt úgy kell létrehozni, hogy visszaállítja a szabályozott specializáció adott implementációját.</span><span class="sxs-lookup"><span data-stu-id="d086b-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="d086b-238">Ha az alapértelmezett törzsön kívül egy vagy több specializációt is explicit módon kell deklarálni, akkor az alapértelmezett törzs megvalósítását megfelelő specializációs nyilatkozatba is kell becsomagolni:</span><span class="sxs-lookup"><span data-stu-id="d086b-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="d086b-239">A specializációk érvényes meghatározásának körülményei</span><span class="sxs-lookup"><span data-stu-id="d086b-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="d086b-240">Adjoint/vezérelt üzemeltetési nyilatkozatok</span><span class="sxs-lookup"><span data-stu-id="d086b-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="d086b-241">A adjoint vagy az ellenőrzött verziók nélküli műveletet kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="d086b-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="d086b-242">Például a mérési műveletek egyike sem invertálható, sem ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="d086b-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="d086b-243">Egy művelet támogatja a `Adjoint` és a-kezelőket, `Controlled` Ha a nyilatkozata tartalmazza a megfelelő specializációk implicit vagy explicit nyilatkozatát.</span><span class="sxs-lookup"><span data-stu-id="d086b-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="d086b-244">Az explicit módon bejelentett adjoint/vezérelt specializáció egy adjoint/vezérelt specializáció létezését feltételezi.</span><span class="sxs-lookup"><span data-stu-id="d086b-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="d086b-245">Egy olyan művelet esetében, amelynek a törzse ismétlődik, amíg-sikeres hurkokat tartalmaz, állítson be utasítások, mérések, visszaküldési utasítások vagy más olyan műveletekre irányuló hívásokat, amelyek nem támogatják az `Adjoint` adjoint-specializációt, és nem lehetséges, hogy automatikusan generáljon egy, az `invert` vagy az `auto` irányelvet követő specializáció</span><span class="sxs-lookup"><span data-stu-id="d086b-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="d086b-246">Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat is tartalmaz, amelyek nem támogatják az üzemen kívüli tevékenységet `Controlled` , nem lehetséges, hogy automatikusan generál egy szabályozott specializációt a `distribute` vagy a `auto` direktíva után.</span><span class="sxs-lookup"><span data-stu-id="d086b-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="d086b-247">Vezérelt Adjoint</span><span class="sxs-lookup"><span data-stu-id="d086b-247">Controlled Adjoint</span></span>

<span data-ttu-id="d086b-248">Egy művelet ellenőrzött adjoint-verziója határozza meg, hogyan kell megvalósítani a művelet adjoint egy kvantum által vezérelt verzióját.</span><span class="sxs-lookup"><span data-stu-id="d086b-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="d086b-249">Az adjoint-verzióval nem rendelkező műveletet kell megadnia. például a mérési műveletek nem rendelkeznek szabályozott adjoint-verzióval, mert nem ellenőrizhetők és nem invertálható.</span><span class="sxs-lookup"><span data-stu-id="d086b-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="d086b-250">Egy művelet vezérelt adjoint-specializációjának léteznie kell, ha a adjoint és a szabályozott specializáció is létezik.</span><span class="sxs-lookup"><span data-stu-id="d086b-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="d086b-251">Ebben az esetben az irányított adjoint specializáció létezését következtetik ki.</span><span class="sxs-lookup"><span data-stu-id="d086b-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="d086b-252">Ha nincs explicit módon definiált implementáció, a fordítás a megfelelő specializációt hozza létre.</span><span class="sxs-lookup"><span data-stu-id="d086b-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="d086b-253">Egy olyan művelet esetében, amelynek a törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem rendelkeznek szabályozott adjoint-verzióval, a adjoint-specializációt automatikusan generálja a `invert` , `distribute` vagy az `auto` direktíva nem lehetséges.</span><span class="sxs-lookup"><span data-stu-id="d086b-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="d086b-254">Típus kompatibilitása</span><span class="sxs-lookup"><span data-stu-id="d086b-254">Type Compatibility</span></span>

<span data-ttu-id="d086b-255">Használjon olyan műveletet, amelyben további, a rendszer által támogatott, de az aláírással rendelkező művelet is használható.</span><span class="sxs-lookup"><span data-stu-id="d086b-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="d086b-256">Ha például egy típusú műveletet használ, bárhol használhatja a `(Qubit => Unit is Adj)` típusú műveletet `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="d086b-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="d086b-257">Q#a *covariant* meghívásos visszatérési típusok esetében: egy típust visszaadó meghívót, amely `'A` azonos típusú bemeneti típussal és az azzal kompatibilis eredményhalmaz típussal kompatibilis `'A` .</span><span class="sxs-lookup"><span data-stu-id="d086b-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="d086b-258">Q# a *contravariant típusparamétert* a bemeneti típusokra vonatkozik: egy olyan típusú hívás, amely bemenetként fogadja az adott típust, és kompatibilis a alkalmazással `'A` kompatibilis bemeneti típussal `'A` .</span><span class="sxs-lookup"><span data-stu-id="d086b-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="d086b-259">Ez a következő definíciók miatt történik.</span><span class="sxs-lookup"><span data-stu-id="d086b-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="d086b-260">képes vagy</span><span class="sxs-lookup"><span data-stu-id="d086b-260">you can</span></span>

- <span data-ttu-id="d086b-261">Hívja meg a függvényt az `ConjugateInvertWith` `inner` egyik vagy a argumentumával `Invert` `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="d086b-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="d086b-262">Hívja meg a függvényt `ConjugateUnitaryWith` egy `inner` argumentummal `ApplyUnitary` , de nem `Invert` .</span><span class="sxs-lookup"><span data-stu-id="d086b-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="d086b-263">Egy típus értékének visszaadása a következőből: `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="d086b-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d086b-264">Q# 0,3 jelentős különbség mutatkozott a felhasználó által definiált típusok viselkedésében.</span><span class="sxs-lookup"><span data-stu-id="d086b-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="d086b-265">A felhasználó által definiált típusokat az alapul szolgáló típus burkolt verziójaként, nem pedig altípusként kezeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="d086b-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="d086b-266">Ez azt jelenti, hogy a felhasználó által definiált típus értéke nem használható, ha a mögöttes típus értéke a várt érték.</span><span class="sxs-lookup"><span data-stu-id="d086b-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="d086b-267">Új függvények definiálása</span><span class="sxs-lookup"><span data-stu-id="d086b-267">Defining New Functions</span></span>

<span data-ttu-id="d086b-268">A függvények tisztán determinisztikus, klasszikus rutinok, amelyek a-ben Q# különböznek, és nem megengedett, hogy a kimeneti érték kiszámításán kívül más effektusok is legyenek.</span><span class="sxs-lookup"><span data-stu-id="d086b-268">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="d086b-269">Különösen a függvények nem hívhatnak meg műveleteket; qubits bevonása, lefoglalása vagy kölcsönzése; véletlenszerű számok mintavételezése; Ellenkező esetben a bemeneti értéken kívüli állapot függ egy függvénynek.</span><span class="sxs-lookup"><span data-stu-id="d086b-269">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="d086b-270">Ennek következményeként a Q# függvények *tisztán* vannak rendelve, hogy mindig ugyanazokat a bemeneti értékeket rendelik ugyanahhoz a kimeneti értékekhez.</span><span class="sxs-lookup"><span data-stu-id="d086b-270">As a consequence, Q# functions are *pure* , in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="d086b-271">Ez a viselkedés lehetővé teszi Q# , hogy a fordító biztonságosan átrendezje a függvények meghívását a műveleti szakosodások létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="d086b-271">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="d086b-272">Minden Q# forrásfájl tetszőleges számú funkciót meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="d086b-272">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="d086b-273">A függvények nevének egyedinek kell lennie a névtéren belül, és nem ütközhet a művelet vagy a típus nevével.</span><span class="sxs-lookup"><span data-stu-id="d086b-273">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="d086b-274">A függvények definiálása hasonlóan működik a művelet definiálásához, azzal a kivétellel, hogy egy függvényhez nem lehet adjoint vagy vezérelt specializációt meghatározni.</span><span class="sxs-lookup"><span data-stu-id="d086b-274">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="d086b-275">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="d086b-275">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="d086b-276">vagy</span><span class="sxs-lookup"><span data-stu-id="d086b-276">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="d086b-277">Klasszikus Logic in functions = = jó</span><span class="sxs-lookup"><span data-stu-id="d086b-277">Classical logic in functions == good</span></span>

<span data-ttu-id="d086b-278">Ha ez lehetséges, hasznos lehet a klasszikus logikát kiírni a függvények helyett, hogy a műveletek könnyebben használhassák azt.</span><span class="sxs-lookup"><span data-stu-id="d086b-278">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="d086b-279">Ha például a korábbi `Square` deklarációt *műveletként* írta volna, akkor a fordító nem tudta garantálni, hogy ugyanazt a bemenetet ugyanazzal a kimenettel fogja létrehozni.</span><span class="sxs-lookup"><span data-stu-id="d086b-279">For example, if you had written the earlier `Square` declaration as an *operation* , then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="d086b-280">A függvények és a műveletek közötti különbség kihangsúlyozása érdekében vegye figyelembe, hogy az adott műveletből klasszikusan mintavételezésre kerül egy véletlenszerű szám Q# .</span><span class="sxs-lookup"><span data-stu-id="d086b-280">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="d086b-281">Minden alkalommal `U` , amikor meghívja a szolgáltatást, egy másik művelettel rendelkezik `target` .</span><span class="sxs-lookup"><span data-stu-id="d086b-281">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="d086b-282">Különösen a fordító nem tudja garantálni, hogy ha egy `adjoint auto` specializációs nyilatkozatot ad hozzá a alkalmazáshoz `U` , akkor az `U(target); Adjoint U(target);` identitásként viselkedik (azaz No-op).</span><span class="sxs-lookup"><span data-stu-id="d086b-282">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="d086b-283">Ez sérti a [vektorokban és mátrixokban](xref:microsoft.quantum.concepts.vectors)definiált adjoint definícióját, amely lehetővé teszi, hogy a fordító automatikusan létrehozzon egy adjoint specializációt egy olyan műveletben, amelyben a művelet meghívása <xref:Microsoft.Quantum.Math.RandomReal> megszakítja a fordító által biztosított garanciákat; <xref:Microsoft.Quantum.Math.RandomReal> egy olyan művelet, amelynek nem létezik adjoint vagy vezérelt verziója.</span><span class="sxs-lookup"><span data-stu-id="d086b-283">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:Microsoft.Quantum.Math.RandomReal> would break the guarantees provided by the compiler; <xref:Microsoft.Quantum.Math.RandomReal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="d086b-284">Másfelől pedig lehetővé teszi, hogy a függvények olyan hívásokat engedélyezzenek, mint például `Square` a biztonságos, és biztosítja a fordító számára, hogy a kimenet stabilitásának megőrzése érdekében csak a bemenetet kell megőriznie `Square` .</span><span class="sxs-lookup"><span data-stu-id="d086b-284">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="d086b-285">Így a lehető legtöbb klasszikus logikát elkülönítheti a functions szolgáltatásban, így a logika más funkciókban és műveletekben is felhasználható.</span><span class="sxs-lookup"><span data-stu-id="d086b-285">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="d086b-286">Általános (típus-paraméteres) Callables</span><span class="sxs-lookup"><span data-stu-id="d086b-286">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="d086b-287">Számos, a definiálni kívánt függvény és művelet ténylegesen nem támaszkodik a bemenetek típusaira, hanem csak egy másik függvényen vagy műveleten keresztül implicit módon használják a saját típusait.</span><span class="sxs-lookup"><span data-stu-id="d086b-287">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="d086b-288">Tegyük fel például, hogy a *Térkép* fogalma számos funkcionális nyelvhez közös. a függvény $f (x) $ és Values $ \{ x_1, x_2, \dots, x_n \} $, Map egy új gyűjteményt ad vissza: $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="d086b-288">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="d086b-289">Ennek megvalósításához Q# használja ki azt a tényt, hogy a functions első osztályú.</span><span class="sxs-lookup"><span data-stu-id="d086b-289">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="d086b-290">Íme egy gyors példa, amely `Map` `T` helyőrzőként használja a szükséges típusokat.</span><span class="sxs-lookup"><span data-stu-id="d086b-290">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="d086b-291">Vegye figyelembe, hogy ez a függvény ugyanúgy néz ki, mint amit a ténylegesen helyettesít.</span><span class="sxs-lookup"><span data-stu-id="d086b-291">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="d086b-292">Az egész számokból a Paulis-ra történő leképezések például a lebegőpontos számok és a karakterláncok közötti térképre hasonlítanak.</span><span class="sxs-lookup"><span data-stu-id="d086b-292">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="d086b-293">Elvileg írhat egy verziót `Map` minden olyan típushoz, amely találkozik, de ez számos nehézséget jelent.</span><span class="sxs-lookup"><span data-stu-id="d086b-293">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="d086b-294">Ha például hibát talál a alkalmazásban `Map` , akkor győződjön meg arról, hogy a javítást a összes verziójában egységesen alkalmazza `Map` .</span><span class="sxs-lookup"><span data-stu-id="d086b-294">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="d086b-295">Emellett, ha új rekordot vagy UDT hoz létre, akkor az új típussal együtt létre kell majd állítania egy újat is `Map` .</span><span class="sxs-lookup"><span data-stu-id="d086b-295">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="d086b-296">Ez egy kis mennyiségű ilyen funkció esetében is eltartható, mivel a több és több funkciója is ugyanolyan formában van, mint az `Map` , hogy az új típusok bevezetésének díja aránytalanul nagy lesz a meglehetősen rövid sorrendben.</span><span class="sxs-lookup"><span data-stu-id="d086b-296">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="d086b-297">A probléma nagy része azonban abból ered, hogy nem adta meg a fordítónak a különböző verzióinak felismeréséhez szükséges információkat `Map` .</span><span class="sxs-lookup"><span data-stu-id="d086b-297">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="d086b-298">Gyakorlatilag azt szeretné, hogy a fordító a `Map` Q# függvények *típusaként* valamilyen matematikai függvényt kezelje Q# .</span><span class="sxs-lookup"><span data-stu-id="d086b-298">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="d086b-299">Q# ezt a fogalmat úgy formalizes meg, hogy a functions és a Operations függvények *típus paraméterekkel* , valamint a szokásos rekordos paraméterekkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="d086b-299">Q# formalizes this notion by allowing functions and operations to have *type parameters* , as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="d086b-300">Az előző példákban úgy gondolja, hogy `Map` `Int, Pauli` az első esetben, a második esetben pedig a type paramétert adja meg `Double, String` .</span><span class="sxs-lookup"><span data-stu-id="d086b-300">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="d086b-301">A legtöbb esetben használja ezeket a típusú paramétereket, mintha a szokásos típusok lennének.</span><span class="sxs-lookup"><span data-stu-id="d086b-301">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="d086b-302">Paraméterek típusú értékek használata tömbök és rekordok, a függvények és a műveletek hívásához, valamint a szokásos vagy változtatható változókhoz való hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="d086b-302">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="d086b-303">A közvetett függőség legszélsőségesebb esete a qubits, ahol a Q# program nem hivatkozhat közvetlenül a típus struktúrájára, `Qubit` azonban ezeket a típusokat más műveletekre és funkciókra **kell** átadnia.</span><span class="sxs-lookup"><span data-stu-id="d086b-303">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="d086b-304">Ha visszatér a korábbi példához, akkor láthatja, hogy a `Map` Type paraméterrel kell rendelkeznie, az egyik pedig a bemenet, a másik pedig a `fn` kimenetét jelöli `fn` .</span><span class="sxs-lookup"><span data-stu-id="d086b-304">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="d086b-305">A alkalmazásban Q# Ez a szögletes zárójelek (azaz `<>` nem brakets $ \braket $!) hozzáadásával történik, {} a deklarációban szereplő függvény vagy művelet neve után, valamint az egyes Típusparaméterek listázásával.</span><span class="sxs-lookup"><span data-stu-id="d086b-305">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="d086b-306">Az egyes típusparaméter-paraméterek nevének egy kullancstal kell kezdődnie `'` , amely azt jelzi, hogy ez egy típusparaméter, nem pedig egy egyszerű típus (más néven *konkrét* típus).</span><span class="sxs-lookup"><span data-stu-id="d086b-306">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="d086b-307">Így `Map` van írva:</span><span class="sxs-lookup"><span data-stu-id="d086b-307">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="d086b-308">Vegye figyelembe, hogy a definíciója `Map<'Input, 'Output>` nagyon hasonlít a previoius-verziókhoz.</span><span class="sxs-lookup"><span data-stu-id="d086b-308">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="d086b-309">Az egyetlen különbség, hogy explicit módon tájékoztatta a fordítót, amely `Map` nem függ közvetlenül attól, hogy mi `'Input` és milyen `'Output` , de két típust használ, ha közvetve használja őket `fn` .</span><span class="sxs-lookup"><span data-stu-id="d086b-309">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="d086b-310">Ha így lett meghatározva, akkor úgy `Map<'Input, 'Output>` hívhatja meg, mintha egy szokványos függvény lenne:</span><span class="sxs-lookup"><span data-stu-id="d086b-310">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="d086b-311">Az általános függvények és műveletek írása egy olyan hely, ahol a "rekord-in rekord kijelentkezése" nagyon hasznos módszer a Q# függvények és műveletek gondolkodására.</span><span class="sxs-lookup"><span data-stu-id="d086b-311">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="d086b-312">Mivel minden függvény pontosan egy bemenetet vesz át, és pontosan egy kimenetet ad vissza, a típus bemenete `'T -> 'U` *bármilyen* Q# függvénynek megfelel.</span><span class="sxs-lookup"><span data-stu-id="d086b-312">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="d086b-313">Hasonlóképpen bármilyen műveletet átadhat egy típusú bemenetnek `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="d086b-313">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="d086b-314">Második példaként vegye figyelembe, hogy milyen kihívással kell elírnia egy olyan függvényt, amely két másik függvény összeállítását adja vissza:</span><span class="sxs-lookup"><span data-stu-id="d086b-314">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="d086b-315">Itt pontosan meg kell adnia `A` `B` `C` a következőt:, és így szigorúan korlátozza az új függvény segédprogramját `Compose` .</span><span class="sxs-lookup"><span data-stu-id="d086b-315">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="d086b-316">Az összes után `Compose` csak a, a és a, a `A` `B` és a `C` *használatával* függ `innerFn` `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="d086b-316">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="d086b-317">Alternatív megoldásként hozzáadhat olyan típusú paramétereket, amelyek `Compose` azt jelzik, hogy a (z) *any* és a (z) és a (z) a következő `A` `B` `C` paraméterekkel `innerFn` egyezik `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="d086b-317">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="d086b-318">A Q# standard szintű kódtárak számos ilyen típusú paraméteres műveletet és függvényt biztosítanak, így könnyebben kipróbálható a magasabb rendű vezérlési folyamat.</span><span class="sxs-lookup"><span data-stu-id="d086b-318">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="d086b-319">Ezeket a [ Q# standard szintű könyvtár útmutatója ismerteti](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="d086b-319">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="d086b-320">Callables First-Class értékként</span><span class="sxs-lookup"><span data-stu-id="d086b-320">Callables as First-Class Values</span></span>

<span data-ttu-id="d086b-321">Az egyik kritikus módszer, amellyel a vezérlési folyamat és a klasszikus logika a függvények helyett functions használatával történik, így a műveletek és a függvények az Q# *első osztályúak* .</span><span class="sxs-lookup"><span data-stu-id="d086b-321">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class* .</span></span>
<span data-ttu-id="d086b-322">Ez azt eredményezi, hogy a nyelv minden értéke a saját jobb oldalán van.</span><span class="sxs-lookup"><span data-stu-id="d086b-322">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="d086b-323">A következők például tökéletesen érvényes Q# kód, ha kicsit közvetett:</span><span class="sxs-lookup"><span data-stu-id="d086b-323">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="d086b-324">Az `ourH` előző kódrészletben szereplő változó értéke ezután a művelet <xref:Microsoft.Quantum.Intrinsic.H> , például a többi művelethez hasonló érték hívható meg.</span><span class="sxs-lookup"><span data-stu-id="d086b-324">The value of the variable `ourH` in the previous snippet is then the operation <xref:Microsoft.Quantum.Intrinsic.H>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="d086b-325">Ezzel a képességgel olyan műveleteket írhat, amelyek a bemenetük részeként műveleteket hajtanak végre, és a magasabb rendű vezérlési folyamatokra vonatkozó fogalmakat alkotnak.</span><span class="sxs-lookup"><span data-stu-id="d086b-325">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="d086b-326">Képzelje el például, hogy a "Square" műveletet úgy szeretné használni, hogy kétszer alkalmazza azt ugyanarra a cél qubit.</span><span class="sxs-lookup"><span data-stu-id="d086b-326">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="d086b-327">Műveletek visszaküldése egy függvényből</span><span class="sxs-lookup"><span data-stu-id="d086b-327">Returning operations from a function</span></span>

<span data-ttu-id="d086b-328">Fontos kiemelni, hogy a kimenetek részeként is visszatérhetnek a műveletekhez, így a klasszikus feltételes logika valamilyen módon elkülöníthető klasszikus függvényként, amely egy művelet formájában egy kvantum-program leírását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="d086b-328">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="d086b-329">Egyszerű példaként tekintse meg a teleportálás példáját, amelyben a kétbites klasszikus üzenetet fogadó fél az üzenetet arra használja, hogy dekódolja a qubit a megfelelő teleportált állapotba.</span><span class="sxs-lookup"><span data-stu-id="d086b-329">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="d086b-330">Ezt megírhatja egy függvényben, amely a két klasszikus bitet veszi át, és visszaadja a megfelelő dekódolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="d086b-330">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="d086b-331">Ez az új függvény valóban egy függvény, abban az esetben, ha a és az azonos értékeit hívja meg `hereBit` `thereBit` , mindig ugyanazt a műveletet kapja vissza.</span><span class="sxs-lookup"><span data-stu-id="d086b-331">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="d086b-332">Így a dekóder biztonságosan futhat a műveletekben anélkül, hogy meg kellene indokolnia, hogy a dekódolási logika hogyan működjön együtt a különböző műveleti szakosodások definíciói alapján.</span><span class="sxs-lookup"><span data-stu-id="d086b-332">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="d086b-333">Ez azt jelenti, hogy a függvényben található klasszikus logika el van különítve, és garantálva van, hogy a függvény hívása legyen büntetlenül, amíg a bevitel megmarad.</span><span class="sxs-lookup"><span data-stu-id="d086b-333">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="d086b-334">Részleges alkalmazás</span><span class="sxs-lookup"><span data-stu-id="d086b-334">Partial Application</span></span>

<span data-ttu-id="d086b-335">A műveleteknek a *részleges alkalmazás* használatával történő visszaadására szolgáló függvények sokkal nagyobb mértékben is megadhatók, amelyekben a bemenet egy vagy több részét egy függvénynek vagy műveletnek kell megadnia anélkül, hogy ténylegesen meghívja azt.</span><span class="sxs-lookup"><span data-stu-id="d086b-335">You can do significantly more with functions that return operations by using *partial application* , in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="d086b-336">A `ApplyTwice` fenti példában azt jelezheti, hogy nem kívánja megadni, azonnal, hogy a bemeneti művelet melyik qubit vonatkozzon:</span><span class="sxs-lookup"><span data-stu-id="d086b-336">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="d086b-337">Ebben az esetben a helyi változó `twiceOp` a részben alkalmazott műveletet tartalmazza `ApplyTwice(op, _)` , ahol `_` a a bemenet azon részeit jelzi, amelyek még nincsenek megadva.</span><span class="sxs-lookup"><span data-stu-id="d086b-337">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="d086b-338">Ha a következő sorban hívja meg a hívást, a rendszer a `twiceOp` részben alkalmazott művelethez továbbítja a bemenetet az eredeti művelethez.</span><span class="sxs-lookup"><span data-stu-id="d086b-338">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="d086b-339">Így az előző kódrészlet gyakorlatilag azonos ahhoz, hogy közvetlenül meghívja őket `ApplyTwice(op, target)` , mentse az új helyi változót, így késleltetheti a hívást, miközben a bemenet egyes részeit is megadja.</span><span class="sxs-lookup"><span data-stu-id="d086b-339">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="d086b-340">Mivel egy részlegesen alkalmazott művelet valójában nem lett meghívva, amíg a teljes bemenet meg nem lett biztosítva, nyugodtan részben is alkalmazhat műveleteket a függvényeken belül.</span><span class="sxs-lookup"><span data-stu-id="d086b-340">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="d086b-341">Elméletileg a klasszikus logika `SquareOperation` sokkal jobban érintett, de továbbra is el van különítve a többi művelettől, mert az garantálja, hogy a fordító a functions szolgáltatással kapcsolatban tud nyújtani.</span><span class="sxs-lookup"><span data-stu-id="d086b-341">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="d086b-342">A Q# standard könyvtár ezt a módszert használja a klasszikus vezérlési folyamat kifejezésére, így a kvantum-programok könnyen használhatók.</span><span class="sxs-lookup"><span data-stu-id="d086b-342">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="d086b-343">Rekurzió</span><span class="sxs-lookup"><span data-stu-id="d086b-343">Recursion</span></span>

<span data-ttu-id="d086b-344">Q# a callables közvetlenül vagy közvetve rekurzívak.</span><span class="sxs-lookup"><span data-stu-id="d086b-344">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="d086b-345">Vagyis egy művelet vagy függvény meghívhatja önmagát, vagy hívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.</span><span class="sxs-lookup"><span data-stu-id="d086b-345">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="d086b-346">A rekurzió használatának két fontos megjegyzése van, azonban:</span><span class="sxs-lookup"><span data-stu-id="d086b-346">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="d086b-347">A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.</span><span class="sxs-lookup"><span data-stu-id="d086b-347">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="d086b-348">Ez az interferencia jelentős hatással lehet az algoritmus futási idejére.</span><span class="sxs-lookup"><span data-stu-id="d086b-348">This interference can have a substantial impact on the run time of the algorithm.</span></span>
- <span data-ttu-id="d086b-349">Ha a tényleges kvantum-eszközön fut, előfordulhat, hogy a rendelkezésre állási terület korlátozott, ezért a mélyebb rekurzió hibát okozhat.</span><span class="sxs-lookup"><span data-stu-id="d086b-349">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="d086b-350">Különösen a Q# fordító és a futtatókörnyezet nem azonosítja és optimalizálja a farok rekurzióját.</span><span class="sxs-lookup"><span data-stu-id="d086b-350">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d086b-351">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="d086b-351">Next steps</span></span>

<span data-ttu-id="d086b-352">További tudnivalók a [változóinak](xref:microsoft.quantum.guide.variables) használatáról Q# .</span><span class="sxs-lookup"><span data-stu-id="d086b-352">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>