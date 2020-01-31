---
title: Fájl szerkezete | Microsoft Docs
description: 'Q # fájl szerkezete'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821082"
---
# <a name="file-structure"></a><span data-ttu-id="2a863-103">Fájlstruktúra</span><span class="sxs-lookup"><span data-stu-id="2a863-103">File Structure</span></span>

<span data-ttu-id="2a863-104">A Q # fájl névtér-deklarációk sorozatából áll.</span><span class="sxs-lookup"><span data-stu-id="2a863-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="2a863-105">Minden névtér deklarációja a felhasználó által definiált típusokra, műveletekre és függvényekre vonatkozó deklarációkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2a863-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="2a863-106">A névtér-deklarációk tetszőleges számú deklarációt tartalmazhatnak, és bármilyen sorrendben megadhatók.</span><span class="sxs-lookup"><span data-stu-id="2a863-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="2a863-107">A névtér deklarációján kívül megjelenő szöveg Megjegyzés.</span><span class="sxs-lookup"><span data-stu-id="2a863-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="2a863-108">Különösen a deklaráció előtt a névtérhez tartozó dokumentációs megjegyzések szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="2a863-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="2a863-109">Névtér-deklarációk</span><span class="sxs-lookup"><span data-stu-id="2a863-109">Namespace Declarations</span></span>

<span data-ttu-id="2a863-110">A Q # fájlnak általában pontosan egy névtér-deklarációja lesz, de a none (és nem lehet üres, vagy csak megjegyzéseket tartalmazhat), vagy több névteret is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="2a863-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="2a863-111">Előfordulhat, hogy a névtér-deklarációk nem ágyazhatók egymásba.</span><span class="sxs-lookup"><span data-stu-id="2a863-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="2a863-112">Előfordulhat, hogy ugyanaz a névtér több, összeállított Q # fájlban van deklarálva, feltéve, hogy nincs ilyen nevű típus, művelet vagy függvény deklarációja.</span><span class="sxs-lookup"><span data-stu-id="2a863-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="2a863-113">Bizonyos esetben a több fájl azonos névterében lévő azonos típust nem lehet megadnia, még akkor is, ha a deklarációk azonosak.</span><span class="sxs-lookup"><span data-stu-id="2a863-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="2a863-114">A névtér deklarációja a következő kulcsszóból áll: `namespace`, majd a névtér neve, egy nyitott kapcsos zárójel `{`, a névtérben található deklarációk és egy záró kapcsos zárójel `}`.</span><span class="sxs-lookup"><span data-stu-id="2a863-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="2a863-115">A névterek nevei egy vagy több, ponttal elválasztott jogi szimbólum sorozatának .NET-mintázatát követik `.`.</span><span class="sxs-lookup"><span data-stu-id="2a863-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="2a863-116">Például `MyQuantumStuff` és `Microsoft.Quantum.Canon` érvényes névterek nevei.</span><span class="sxs-lookup"><span data-stu-id="2a863-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="2a863-117">Az egyezmény szerint a névtér nevében szereplő szimbólumok tőkésítve vannak, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="2a863-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="2a863-118">A deklarációk bármilyen sorrendben szerepelhetnek a névtér deklarációjában.</span><span class="sxs-lookup"><span data-stu-id="2a863-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="2a863-119">A fájlokban lejjebb deklarált típusokra vagy callables mutató hivatkozások megfelelően vannak feloldva; nincs szükség a típus, a művelet vagy a függvény deklarációjának megírására a hivatkozás előtt.</span><span class="sxs-lookup"><span data-stu-id="2a863-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="2a863-120">Megnyitási irányelvek</span><span class="sxs-lookup"><span data-stu-id="2a863-120">Open Directives</span></span>

<span data-ttu-id="2a863-121">Egy névtér-blokkon belül a `open` direktíva használható az adott névtérben definiált összes típus és callables importálására, és azok nem minősített nevük alapján.</span><span class="sxs-lookup"><span data-stu-id="2a863-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="2a863-122">Egy ilyen `open` irányelv a `open` kulcsszóból áll, amelyet a megnyitni kívánt névtér és a megszakítási pontosvesszővel kell elválasztani.</span><span class="sxs-lookup"><span data-stu-id="2a863-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="2a863-123">Például:</span><span class="sxs-lookup"><span data-stu-id="2a863-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="2a863-124">Ha szükséges, a megnyitott névtérhez tartozó rövid név is meghatározható úgy, hogy az adott névtérből származó összes elemet (és szükség esetén) a megadott rövid névvel kell minősíteni.</span><span class="sxs-lookup"><span data-stu-id="2a863-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="2a863-125">Az ilyen rövid név meghatározása úgy történik, hogy hozzáadja a kulcsszót `as` a kívánt rövid nevet, majd a pontosvesszőt a `open` direktívában:</span><span class="sxs-lookup"><span data-stu-id="2a863-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="2a863-126">Minden `open` direktívának szerepelnie kell a névtérbeli blokkban `function`, `operation`vagy `newtype` deklaráció előtt.</span><span class="sxs-lookup"><span data-stu-id="2a863-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="2a863-127">A `open` direktíva a teljes névtér-blokkra vonatkozik a fájlban.</span><span class="sxs-lookup"><span data-stu-id="2a863-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="2a863-128">Felhasználó által definiált típusú deklarációk</span><span class="sxs-lookup"><span data-stu-id="2a863-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="2a863-129">A q # lehetővé teszi a felhasználók számára, hogy új, felhasználó által definiált típusokat állapítsanak meg a [q # Type Model](xref:microsoft.quantum.language.type-model) című szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="2a863-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="2a863-130">A felhasználó által definiált típusok akkor is eltérőek, ha az alaptípusok azonosak.</span><span class="sxs-lookup"><span data-stu-id="2a863-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="2a863-131">Különösen, ha az alapul szolgáló típusok azonosak, a felhasználó által definiált típusok értékei között nincs automatikus konverzió.</span><span class="sxs-lookup"><span data-stu-id="2a863-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="2a863-132">A felhasználó által definiált típusú deklaráció a kulcsszó `newtype`, majd a felhasználó által definiált típus neve, egy `=`, egy érvényes típus-specifikáció és egy megszakítási pontosvessző.</span><span class="sxs-lookup"><span data-stu-id="2a863-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="2a863-133">Példa:</span><span class="sxs-lookup"><span data-stu-id="2a863-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="2a863-134">Minden Q # forrásfájl tetszőleges számú felhasználó által definiált típust deklarálhat.</span><span class="sxs-lookup"><span data-stu-id="2a863-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="2a863-135">A típus nevének egyedinek kell lennie a névtéren belül, és előfordulhat, hogy a művelet és a függvények nevei nem ütköznek egymással.</span><span class="sxs-lookup"><span data-stu-id="2a863-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="2a863-136">Nem lehet körkörös függőségeket definiálni a felhasználó által definiált típusok között.</span><span class="sxs-lookup"><span data-stu-id="2a863-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="2a863-137">A rekurzív típusok ezért nem lehetségesek a Q #-on belül.</span><span class="sxs-lookup"><span data-stu-id="2a863-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="2a863-138">Műveleti deklarációk</span><span class="sxs-lookup"><span data-stu-id="2a863-138">Operation Declarations</span></span>

<span data-ttu-id="2a863-139">A műveletek a Q # magja, ami nagyjából hasonló a függvények más nyelveken való működéséhez.</span><span class="sxs-lookup"><span data-stu-id="2a863-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="2a863-140">A Q # forrásfájl tetszőleges számú műveletet meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="2a863-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="2a863-141">A művelet nevének a névtéren belül egyedinek kell lennie, és nem ütközhet a típus és a függvény nevével.</span><span class="sxs-lookup"><span data-stu-id="2a863-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="2a863-142">A műveleti deklarációk a `operation`kulcsszóból állnak, amelyet a művelet nevét, a művelethez tartozó argumentumokat definiáló típust, egy kettőspontot `:`, a művelet eredményének típusát leíró típusú jegyzetet, opcionálisan a művelet jellemzőinek leírását, egy nyitott kapcsos zárójel `{`, a műveleti nyilatkozat törzsét és egy záró zárójelet `}`.</span><span class="sxs-lookup"><span data-stu-id="2a863-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="2a863-143">A műveleti nyilatkozat törzse az alapértelmezett implementációból vagy a specializációk listájából áll.</span><span class="sxs-lookup"><span data-stu-id="2a863-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="2a863-144">Az alapértelmezett implementáció közvetlenül is megadható a deklarációban, ha csak az alapértelmezett szövegtörzs-specializáció megvalósítását explicit módon kell megadni.</span><span class="sxs-lookup"><span data-stu-id="2a863-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="2a863-145">Ebben az esetben a deklarációban szereplő műveleti jellemzőkkel rendelkező Megjegyzés hasznos annak biztosítására, hogy a fordító automatikusan generáljon más specializációkat az alapértelmezett implementáció alapján.</span><span class="sxs-lookup"><span data-stu-id="2a863-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="2a863-146">Példa:</span><span class="sxs-lookup"><span data-stu-id="2a863-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="2a863-147">A művelet jellemzői határozzák meg, hogy milyen típusú elválasztók alkalmazhatók a deklarált műveletre, és milyen hatással vannak rájuk.</span><span class="sxs-lookup"><span data-stu-id="2a863-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="2a863-148">Ha egy művelet egy egységes átalakítást valósít meg, akkor megadható, hogy a művelet hogyan *adjointed* vagy *vezérelve*legyen.</span><span class="sxs-lookup"><span data-stu-id="2a863-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="2a863-149">Ezeknek a specializációknak a megléte a művelet aláírásának részeként deklarálható.</span><span class="sxs-lookup"><span data-stu-id="2a863-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="2a863-150">Ezután a fordító létrehozza a megfelelő implementációt minden ilyen implicit módon deklarált specializációhoz.</span><span class="sxs-lookup"><span data-stu-id="2a863-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="2a863-151">A fenti példában egy adjoint, egy vezérelt és egy vezérelt adjoint-specializációt generál a fordító.</span><span class="sxs-lookup"><span data-stu-id="2a863-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="2a863-152">Abban az esetben, ha a fordító nem tudja létrehozni a megvalósítást, explicit módon megadható.</span><span class="sxs-lookup"><span data-stu-id="2a863-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="2a863-153">Az ilyen explicit specializációs nyilatkozatok egy megfelelő generációs irányelvből állhatnak, amelyből megtudhatja, hogy egy adott specializáció hogyan épül fel, vagy egy felhasználó által meghatározott implementáció.</span><span class="sxs-lookup"><span data-stu-id="2a863-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="2a863-154">A fenti `PrepareEntangledPair` található kód például az alábbi kóddal egyenértékű, explicit specializációs deklarációkat tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="2a863-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="2a863-155">A kulcsszó `auto` azt jelzi, hogy a fordítónak meg kell határoznia, hogyan hozhatja ki a specializáció megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="2a863-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="2a863-156">Ha a fordító nem tud létrehozni egy bizonyos specializáció megvalósítását további utasítások nélkül – például egy pontosabb létrehozási irányelv –, vagy ha hatékonyabb megvalósítást lehet megadni, akkor a megvalósítás manuálisan is meghatározható.</span><span class="sxs-lookup"><span data-stu-id="2a863-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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

<span data-ttu-id="2a863-157">A fenti példában a `adjoint invert;` azt jelzi, hogy a adjoint specializációt a törzs megvalósításának visszafordításával kell létrehozni, és a `controlled adjoint invert;` azt jelzi, hogy a vezérelt adjoint specializációt úgy kell létrehozni, hogy a vezérelt specializáció adott implementációját visszaállítja.</span><span class="sxs-lookup"><span data-stu-id="2a863-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="2a863-158">Ahhoz, hogy egy művelet támogassa a `Adjoint` és/vagy a `Controlled`-munkafolyamatot, a visszatérési típust szükségszerűen `Unit`kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="2a863-159">Explicit specializációs deklarációk</span><span class="sxs-lookup"><span data-stu-id="2a863-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="2a863-160">A Q # műveletei a következő explicit specializációs deklarációkat tartalmazhatják:</span><span class="sxs-lookup"><span data-stu-id="2a863-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="2a863-161">A `body` specializáció meghatározza a művelet végrehajtását, és nem alkalmazta a műveletet.</span><span class="sxs-lookup"><span data-stu-id="2a863-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="2a863-162">A `adjoint` specializáció meghatározza a művelet végrehajtását a `Adjoint`-felhasználó alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="2a863-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="2a863-163">A `controlled` specializáció meghatározza a művelet végrehajtását a `Controlled`-felhasználó alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="2a863-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="2a863-164">A `controlled adjoint` specializáció a művelet megvalósítását határozza meg a `Adjoint` és az `Controlled` alkalmazott operációs rendszersel együtt.</span><span class="sxs-lookup"><span data-stu-id="2a863-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="2a863-165">Ez a specializáció `adjoint controlled`néven is elnevezhető, mivel a két elválasztó.</span><span class="sxs-lookup"><span data-stu-id="2a863-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="2a863-166">A művelet specializáció a specializációs címkéből (például `body`vagy `adjoint`stb.) áll, amelyet a következők egyike követ:</span><span class="sxs-lookup"><span data-stu-id="2a863-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="2a863-167">Az alább leírtak szerint kifejezett nyilatkozat.</span><span class="sxs-lookup"><span data-stu-id="2a863-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="2a863-168">Egy irányelv, amely közli a fordítóval, hogyan hozhatja ki a specializációt, az egyik:</span><span class="sxs-lookup"><span data-stu-id="2a863-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="2a863-169">`intrinsic`, amely azt jelzi, hogy a specializációt a célszámítógép kapja meg.</span><span class="sxs-lookup"><span data-stu-id="2a863-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="2a863-170">`distribute`, amelyek felhasználhatók a `controlled` és `controlled adjoint` specializációkkal.</span><span class="sxs-lookup"><span data-stu-id="2a863-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="2a863-171">A `controlled`használatakor azt jelzi, hogy a fordítónak a `body`összes műveletére alkalmaznia kell `Controlled` a specializáció kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="2a863-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="2a863-172">A `controlled adjoint`használatakor azt jelzi, hogy a fordítónak ki kell számítania a specializációt úgy, hogy a `adjoint` specializáció összes műveletére alkalmazza a `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="2a863-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="2a863-173">`invert`, amely azt jelzi, hogy a fordítónak a `body`lefordításával kell kiszámítani a `adjoint` specializációt, például a műveletek sorrendjét és a adjoint alkalmazását.</span><span class="sxs-lookup"><span data-stu-id="2a863-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="2a863-174">`adjoint controlled`használata esetén ez azt jelenti, hogy a fordítónak a `controlled` specializáció megfordításával kell kiszámítani a specializációt.</span><span class="sxs-lookup"><span data-stu-id="2a863-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="2a863-175">`self`azt jelzi, hogy a adjoint specializáció megegyezik a `body` specializációval.</span><span class="sxs-lookup"><span data-stu-id="2a863-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="2a863-176">Ez a `adjoint` és az `adjoint controlled` specializációra érvényes.</span><span class="sxs-lookup"><span data-stu-id="2a863-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="2a863-177">`adjoint controlled`esetén `self` azt jelenti, hogy a `adjoint controlled` specializáció megegyezik a `controlled` specializációval.</span><span class="sxs-lookup"><span data-stu-id="2a863-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="2a863-178">`auto`azt jelzi, hogy a fordítónak ki kell választania egy megfelelő irányelvet az alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="2a863-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="2a863-179">Előfordulhat, hogy a `auto` nem használható a `body` specializációhoz.</span><span class="sxs-lookup"><span data-stu-id="2a863-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="2a863-180">Az irányelvek és a `auto` mind a záró pontosvesszővel elválasztott `;`szükségesek.</span><span class="sxs-lookup"><span data-stu-id="2a863-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="2a863-181">A `auto` irányelv a következő generációs irányelvre lesz feloldva, ha a `body` explicit nyilatkozata van megadva:</span><span class="sxs-lookup"><span data-stu-id="2a863-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="2a863-182">A `adjoint` specializáció a `invert`direktíva alapján jön létre.</span><span class="sxs-lookup"><span data-stu-id="2a863-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="2a863-183">A `controlled` specializáció a `distribute`direktíva alapján jön létre.</span><span class="sxs-lookup"><span data-stu-id="2a863-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="2a863-184">Az `adjoint controlled` specializáció az irányelv alapján jön létre `invert` ha a `controlled` kifejezett nyilatkozata van megadva, de nem `adjoint`, és `distribute` másként.</span><span class="sxs-lookup"><span data-stu-id="2a863-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="2a863-185">Ha egy művelet önadjoint, explicit módon megadhatja a adjoint vagy az irányított adjoint specializációt az előállítási irányelv alapján `self`, hogy lehetővé tegye a fordító számára ezen információk használatát optimalizálási célokra.</span><span class="sxs-lookup"><span data-stu-id="2a863-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="2a863-186">A felhasználó által definiált implementációt tartalmazó specializációs nyilatkozat egy argumentummal, majd egy, a specializációt megvalósító Q # kóddal rendelkező utasítási blokkot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2a863-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="2a863-187">A argumentumok listájában `...` a művelet egészének deklarált argumentumait jelöli.</span><span class="sxs-lookup"><span data-stu-id="2a863-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="2a863-188">`body` és `adjoint`esetén az argumentumok listájának mindig `(...)`nak kell lennie; `controlled` és `adjoint controlled`esetében az argumentumok listájának olyan szimbólumnak kell lennie, amely a vezérlési qubits tömbjét jelöli, amelyet a `...`követ, zárójelek közé. például `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="2a863-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="2a863-189">Ha az alapértelmezett törzsön kívül egy vagy több specializációt is explicit módon kell deklarálni, akkor az alapértelmezett törzs megvalósítását megfelelő specializációs nyilatkozatba is kell becsomagolni:</span><span class="sxs-lookup"><span data-stu-id="2a863-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="adjoint"></a><span data-ttu-id="2a863-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="2a863-190">Adjoint</span></span>

<span data-ttu-id="2a863-191">Egy művelet adjoint megadhatja, hogyan történjen a művelet összetett konjugált áttelepítése, azaz hogyan működik a művelet, ha a "Futtatás fordított".</span><span class="sxs-lookup"><span data-stu-id="2a863-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="2a863-192">Adjoint nélküli műveletet kell megadnia. például a mérési műveletek nem rendelkeznek adjoint, mert nem invertálható.</span><span class="sxs-lookup"><span data-stu-id="2a863-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="2a863-193">Egy művelet támogatja a `Adjoint`-kezelőt, ha a deklarációja egy adjoint-specializáció implicit vagy explicit deklarációját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2a863-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="2a863-194">A kifejezetten bejelentett, szabályozott adjoint specializáció egy adjoint specializáció létezését jelenti.</span><span class="sxs-lookup"><span data-stu-id="2a863-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="2a863-195">Azon művelet esetében, amelynek a törzse a REPEAT-ig-Success hurkokat tartalmazza, állítson be utasítások, mérések, visszaküldési utasítások vagy más olyan műveletekre irányuló hívásokat, amelyek nem támogatják a `Adjoint`-adjoint, a `invert` vagy a `auto` direktíva után automatikusan generálja a rendszer-és a-irányelvet.</span><span class="sxs-lookup"><span data-stu-id="2a863-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="2a863-196">Ellenőrzött</span><span class="sxs-lookup"><span data-stu-id="2a863-196">Controlled</span></span>

<span data-ttu-id="2a863-197">Egy művelet ellenőrzött verziója határozza meg, hogy a rendszer hogyan alkalmazza a művelet egy kvantum által vezérelt verzióját, azaz azt, hogy egy adott művelet hogyan viselkedik, ha a rendszer a kvantum-regiszter állapotára alkalmazza a feltételt.</span><span class="sxs-lookup"><span data-stu-id="2a863-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="2a863-198">Az [ellenőrzött](xref:microsoft.quantum.language.type-model#controlled) szakasz részletesebb leírást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2a863-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="2a863-199">A művelet nem érvényes a szabályozott verzió nélküli műveletek megadására; például a mérési műveletek nem rendelkeznek szabályozott verzióval, mert nem ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="2a863-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="2a863-200">Egy művelet támogatja a `Controlled`-kezelőt, ha és csak akkor, ha a deklarációja egy szabályozott specializáció implicit vagy explicit deklarációját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2a863-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="2a863-201">Az explicit módon deklarált, szabályozott adjoint specializáció egy vezérelt specializáció létezését feltételezi.</span><span class="sxs-lookup"><span data-stu-id="2a863-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="2a863-202">Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem támogatják a `Controlled`t, nem lehetséges, hogy a `distribute` vagy `auto` direktíva után automatikusan generáljon egy szabályozott specializációt.</span><span class="sxs-lookup"><span data-stu-id="2a863-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="2a863-203">Vezérelt Adjoint</span><span class="sxs-lookup"><span data-stu-id="2a863-203">Controlled Adjoint</span></span>

<span data-ttu-id="2a863-204">Egy művelet ellenőrzött adjoint-verziója határozza meg, hogy a rendszer milyen módon implementálja a adjoint a művelethez.</span><span class="sxs-lookup"><span data-stu-id="2a863-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="2a863-205">Az adjoint-verzióval nem rendelkező műveletet kell megadnia. például a mérési műveletek nem rendelkeznek szabályozott adjoint-verzióval, mert nem ellenőrizhetők és nem invertálható.</span><span class="sxs-lookup"><span data-stu-id="2a863-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="2a863-206">Egy művelet vezérelt adjoint-specializációjának léteznie kell, ha a adjoint és a szabályozott specializáció is létezik.</span><span class="sxs-lookup"><span data-stu-id="2a863-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="2a863-207">Ebben az esetben a vezérelt adjoint specializáció létezését következtetik ki, és a fordító a megfelelő specializációt hozza létre, ha nincs explicit módon definiált implementáció.</span><span class="sxs-lookup"><span data-stu-id="2a863-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="2a863-208">Egy olyan művelet esetében, amelynek törzse olyan más műveletekre irányuló hívásokat tartalmaz, amelyek nem rendelkeznek szabályozott adjoint-verzióval, a `invert`t követő, `distribute` vagy `auto` direktíva nem lehet automatikusan generálni egy adjoint specializációt.</span><span class="sxs-lookup"><span data-stu-id="2a863-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="2a863-209">Példák</span><span class="sxs-lookup"><span data-stu-id="2a863-209">Examples</span></span>

<span data-ttu-id="2a863-210">A művelet deklarációja olyan egyszerű lehet, mint a következő, amely meghatározza a primitív Pauli X műveletet:</span><span class="sxs-lookup"><span data-stu-id="2a863-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="2a863-211">A következő határozza meg a teleport műveletet.</span><span class="sxs-lookup"><span data-stu-id="2a863-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="2a863-212">Függvények deklarációi</span><span class="sxs-lookup"><span data-stu-id="2a863-212">Function Declarations</span></span>

<span data-ttu-id="2a863-213">A függvények tisztán klasszikus rutinok a Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="2a863-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="2a863-214">A Q # forrásfájl tetszőleges számú funkciót meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="2a863-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="2a863-215">A függvények deklarációja a `function`kulcsszóból áll, amelyet a függvény neve, egy begépelt azonosító rekord, egy Type Megjegyzés, amely leírja a függvény visszatérési típusát, valamint egy, a függvény megvalósítását ismertető utasítási blokkot.</span><span class="sxs-lookup"><span data-stu-id="2a863-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="2a863-216">A függvényt definiáló utasítás blokkjának `{` és `}` kell lennie, mint bármely más utasítás blokkja.</span><span class="sxs-lookup"><span data-stu-id="2a863-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="2a863-217">A függvények nevének egyedinek kell lennie a névtéren belül, és nem ütközhet a művelet és a típus nevével.</span><span class="sxs-lookup"><span data-stu-id="2a863-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="2a863-218">A függvények nem foglalhatnak le és nem kölcsönözhetnek qubits, vagy nem hívhatnak meg műveleteket.</span><span class="sxs-lookup"><span data-stu-id="2a863-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="2a863-219">A műveletek részleges alkalmazása vagy a begépelt műveletekben szereplő értékek meghaladása rendben van.</span><span class="sxs-lookup"><span data-stu-id="2a863-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="2a863-220">Például:</span><span class="sxs-lookup"><span data-stu-id="2a863-220">For example,</span></span>

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
