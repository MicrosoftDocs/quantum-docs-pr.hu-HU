---
title: Broombridge séma specifikációja
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185358"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="2a863-102">Broombridge-specifikáció – v 0.1</span><span class="sxs-lookup"><span data-stu-id="2a863-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="2a863-103">A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.</span><span class="sxs-lookup"><span data-stu-id="2a863-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="2a863-104">A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.</span><span class="sxs-lookup"><span data-stu-id="2a863-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="2a863-105">Introduction (Bevezetés)</span><span class="sxs-lookup"><span data-stu-id="2a863-105">Introduction</span></span> ##

<span data-ttu-id="2a863-106">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-106">This section is informative.</span></span>

<span data-ttu-id="2a863-107">A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="2a863-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="2a863-108">Szerializálási</span><span class="sxs-lookup"><span data-stu-id="2a863-108">Serialization</span></span> ##

<span data-ttu-id="2a863-109">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-109">This section is normative.</span></span>

<span data-ttu-id="2a863-110">Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="2a863-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="2a863-111">A YAML szerializált objektumnak olyan tulajdonsággal kell rendelkeznie, `"$schema"` amelynek értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, és érvényesnek kell lennie a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján.</span><span class="sxs-lookup"><span data-stu-id="2a863-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="2a863-112">A specifikáció hátralévő részében a "The Broombridge Object" kifejezés a Broombridge YAML-dokumentumból deszerializált JSON-objektumra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="2a863-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="2a863-113">Hacsak másként nincs jelezve, az objektumok nem rendelkezhetnek a jelen dokumentumban explicit módon megadott további tulajdonságokkal.</span><span class="sxs-lookup"><span data-stu-id="2a863-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="2a863-114">További definíciók</span><span class="sxs-lookup"><span data-stu-id="2a863-114">Additional Definitions</span></span> ##

<span data-ttu-id="2a863-115">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="2a863-116">Mennyiségi objektumok</span><span class="sxs-lookup"><span data-stu-id="2a863-116">Quantity Objects</span></span> ###

<span data-ttu-id="2a863-117">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-117">This section is normative.</span></span>

<span data-ttu-id="2a863-118">A _mennyiségi objektum_ egy JSON-objektum, és rendelkeznie kell egy tulajdonsággal `units` amelynek értéke az 1. táblázatban felsorolt engedélyezett értékek egyike.</span><span class="sxs-lookup"><span data-stu-id="2a863-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="2a863-119">A mennyiségi objektum egy _egyszerű mennyiségi objektum_ , ha a `units` tulajdonságán felül egyetlen tulajdonság `value` van.</span><span class="sxs-lookup"><span data-stu-id="2a863-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="2a863-120">A `value` tulajdonság értékének számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="2a863-121">A mennyiségi objektum egy _körülhatárolt mennyiségi objektum_ , ha a tulajdonsága `lower` és `upper` a `units` tulajdonság mellett.</span><span class="sxs-lookup"><span data-stu-id="2a863-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="2a863-122">A `lower` és az `upper` tulajdonság értékének számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="2a863-123">A kötött mennyiség objektum rendelkezhet olyan tulajdonsággal, `value` amelynek értéke egy szám.</span><span class="sxs-lookup"><span data-stu-id="2a863-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="2a863-124">A mennyiségi objektum egy _ritka tömbbeli mennyiségű objektum_ , ha a tulajdonsága `format` és egy tulajdonság `values` a `units` tulajdonságán felül.</span><span class="sxs-lookup"><span data-stu-id="2a863-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="2a863-125">`format` értékének a karakterláncnak `sparse`nak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="2a863-126">A `values` tulajdonság értékének tömbnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="2a863-127">`values` minden elemének olyan tömbnek kell lennie, amely a ritka tömb mennyiségének indexeit és értékét jelöli.</span><span class="sxs-lookup"><span data-stu-id="2a863-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="2a863-128">A ritka tömb mennyiségi objektumának minden eleméhez egyedi indexeket kell megadni a teljes ritka tömb mennyiségi objektumán.</span><span class="sxs-lookup"><span data-stu-id="2a863-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="2a863-129">Ha egy index `0`értékkel rendelkezik, akkor az elemzőnek a ritka tömb mennyiségi objektumát azonos módon kell kezelnie egy olyan ritka tömbbeli mennyiség objektummal, amelyben az index egyáltalán nem szerepel.</span><span class="sxs-lookup"><span data-stu-id="2a863-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="2a863-130">Egy mennyiségi objektumnak a következők egyikének kell lennie</span><span class="sxs-lookup"><span data-stu-id="2a863-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="2a863-131">egy egyszerű mennyiségi objektum,</span><span class="sxs-lookup"><span data-stu-id="2a863-131">a simple quantity object,</span></span>
- <span data-ttu-id="2a863-132">egy kötött mennyiségi objektum, vagy</span><span class="sxs-lookup"><span data-stu-id="2a863-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="2a863-133">egy ritka tömb mennyiségi objektuma.</span><span class="sxs-lookup"><span data-stu-id="2a863-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="2a863-134">Példák</span><span class="sxs-lookup"><span data-stu-id="2a863-134">Examples</span></span> ###

<span data-ttu-id="2a863-135">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-135">This section is informative.</span></span>

<span data-ttu-id="2a863-136">Egy egyszerű mennyiség, amely A $1.9844146837\,\mathrm{Ha} $ értéket jelöli:</span><span class="sxs-lookup"><span data-stu-id="2a863-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="2a863-137">Egy kötött mennyiség, amely egységes eloszlást képvisel a $ [-7,-6]\,\mathrm{Ha} $ intervallumban:</span><span class="sxs-lookup"><span data-stu-id="2a863-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="2a863-138">Az alábbiakban egy olyan ritka tömbbeli mennyiség szerepel, amely `[1, 2]` egyenlő `hello` és egy elem `[3, 4]` `world`:</span><span class="sxs-lookup"><span data-stu-id="2a863-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="2a863-139">Formázási szakasz</span><span class="sxs-lookup"><span data-stu-id="2a863-139">Format Section</span></span> ##

<span data-ttu-id="2a863-140">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-140">This section is normative.</span></span>

<span data-ttu-id="2a863-141">A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie, `format` amelynek értéke egy `version`nevű tulajdonságú JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="2a863-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="2a863-142">A `version` tulajdonságnak `"0.1"`értékűnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="2a863-143">Példa</span><span class="sxs-lookup"><span data-stu-id="2a863-143">Example</span></span> ###

<span data-ttu-id="2a863-144">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="2a863-145">Beépített készletek szakasz</span><span class="sxs-lookup"><span data-stu-id="2a863-145">Integral Sets Section</span></span> ##

<span data-ttu-id="2a863-146">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-146">This section is normative.</span></span>

<span data-ttu-id="2a863-147">A Broombridge objektumnak rendelkeznie kell egy olyan tulajdonsággal, `integral_sets` amelynek értéke JSON-tömb.</span><span class="sxs-lookup"><span data-stu-id="2a863-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="2a863-148">A `integral_sets` tulajdonság értékében szereplő összes elemnek egy olyan JSON-objektumnak kell lennie, amely az adott szakasz hátralévő részében leírtak szerint egy egységes készletet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2a863-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="2a863-149">A szakasz hátralévő részében az "integrált készlet objektum" kifejezés a Broombridge objektum `integral_sets` tulajdonságának értékében található elemre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="2a863-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="2a863-150">Minden szerves set objektumnak rendelkeznie kell egy olyan tulajdonsággal, `metadata` amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="2a863-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="2a863-151">`metadata` értéke lehet az üres JSON-objektum (azaz `{}`), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="2a863-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="2a863-152">Hamilton szakasz</span><span class="sxs-lookup"><span data-stu-id="2a863-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="2a863-153">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="2a863-153">Overview</span></span> ####

<span data-ttu-id="2a863-154">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-154">This section is informative.</span></span>

<span data-ttu-id="2a863-155">Az egyes integrált Hamilton `hamiltonian` tulajdonsága egy adott kvantum-kémiai probléma esetén ismerteti az egy-és kéttörzsű kifejezéseket, amelyek valós számok ritka tömbjét jelentik.</span><span class="sxs-lookup"><span data-stu-id="2a863-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="2a863-156">Az egyes integrált Hamilton-kezelők a következő űrlapot írják be:</span><span class="sxs-lookup"><span data-stu-id="2a863-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="2a863-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i \sigma} egy ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="2a863-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="2a863-158">Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.</span><span class="sxs-lookup"><span data-stu-id="2a863-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="2a863-159">Az egyértelműség érdekében az egyelektronos kifejezés a következő:</span><span class="sxs-lookup"><span data-stu-id="2a863-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="2a863-160">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="2a863-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="2a863-161">a két elektron kifejezés pedig</span><span class="sxs-lookup"><span data-stu-id="2a863-161">and the two-electron term is</span></span>

<span data-ttu-id="2a863-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="2a863-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="2a863-163">Ahogy a `integral_sets` tulajdonság egyes elemeinek [`basis_set` tulajdonságának](#basis-set-object) leírásában is látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.</span><span class="sxs-lookup"><span data-stu-id="2a863-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="2a863-164">Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.</span><span class="sxs-lookup"><span data-stu-id="2a863-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="2a863-165">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="2a863-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="2a863-166">Tartalom</span><span class="sxs-lookup"><span data-stu-id="2a863-166">Contents</span></span> ####

<span data-ttu-id="2a863-167">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-167">This section is normative.</span></span>

<span data-ttu-id="2a863-168">Minden szerves készletnek rendelkeznie kell egy olyan tulajdonsággal, `hamiltonian` amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="2a863-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="2a863-169">A `hamiltonian` tulajdonság értéke Hamilton-objektumként ismert, és a tulajdonságok `one_electron_integrals` és `two_electron_integrals` a szakasz hátralévő részében leírtak szerint kell megadni.</span><span class="sxs-lookup"><span data-stu-id="2a863-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="2a863-170">Egy Hamilton objektumhoz `particle_hole_representation`tulajdonság is TARTOZHAT.</span><span class="sxs-lookup"><span data-stu-id="2a863-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="2a863-171">Ha van ilyen, `particle_hole_representation` értékének a szakasz hátralévő részében ismertetett formátumot kell követnie.</span><span class="sxs-lookup"><span data-stu-id="2a863-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="2a863-172">Egy elektronos szerves objektum</span><span class="sxs-lookup"><span data-stu-id="2a863-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="2a863-173">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-173">This section is normative.</span></span>

<span data-ttu-id="2a863-174">A Hamilton objektum `one_electron_integrals` tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.</span><span class="sxs-lookup"><span data-stu-id="2a863-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="2a863-175">Minden kifejezésnek tartalmaznia kell indexekkel `[i, j]`, ahol `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="2a863-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="2a863-176">Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.</span><span class="sxs-lookup"><span data-stu-id="2a863-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="2a863-177">Példa</span><span class="sxs-lookup"><span data-stu-id="2a863-177">Example</span></span> ######

<span data-ttu-id="2a863-178">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-178">This section is informative.</span></span>

<span data-ttu-id="2a863-179">A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 \downarrow} egy\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="2a863-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="2a863-180">A Broombridge 1 alapú indexelést használ.</span><span class="sxs-lookup"><span data-stu-id="2a863-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="2a863-181">Két elektronos szerves objektum</span><span class="sxs-lookup"><span data-stu-id="2a863-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="2a863-182">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-182">This section is normative.</span></span>

<span data-ttu-id="2a863-183">A Hamilton objektum `two_electron_integrals` tulajdonságának olyan ritka tömb mennyiségnek kell lennie, amely egy `index_convention`nevű további tulajdonsággal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="2a863-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="2a863-184">`two_electron_integrals` értékének minden eleméhez négy indexnek kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="2a863-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="2a863-185">Minden `two_electron_integrals` tulajdonságnak rendelkeznie kell `index_convention` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="2a863-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="2a863-186">A `index_convention` tulajdonság értékének az 1. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a863-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="2a863-187">Ha a `index_convention` értéke `mulliken`, akkor a `two_electron_integrals` ritka tömb mennyiségének minden egyes eleméhez egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton kifejezést kell létrehoznia, amely a kételektronos operátor $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , ahol a $i $, $j $, $k $, és $l $ értéknek a befogadó tartomány egész számának kell lennie, amely 1 és az integrált készlet objektum `n_electrons` tulajdonsága által meghatározott elektronok száma, valamint ahol $h _ {i, j, k, l} $ a ritka tömb mennyiségének `[i, j, k, l, h(i, j, k, l)]` eleme.</span><span class="sxs-lookup"><span data-stu-id="2a863-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="2a863-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="2a863-188">Symmetries</span></span> ######

<span data-ttu-id="2a863-189">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-189">This section is normative.</span></span>

<span data-ttu-id="2a863-190">Ha egy `two_electron_integrals` objektum `index_convention` tulajdonsága egyenlő `mulliken`, akkor ha van olyan elem, amely indexekkel `[i, j, k, l]`, akkor a következő indexek nem lehetnek jelen, kivéve, ha `[i, j, k, l]`egyenlőek:</span><span class="sxs-lookup"><span data-stu-id="2a863-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="2a863-191">Mivel a `index_convention` tulajdonság ritka mennyiségű objektum, a különböző elemeken nem lehet megismételni az indexeket.</span><span class="sxs-lookup"><span data-stu-id="2a863-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="2a863-192">Ha a `[i, j, k, l]` indexekkel rendelkező elemek jelen vannak, akkor előfordulhat, hogy más elem nem rendelkezik ezekkel az indexekkel.</span><span class="sxs-lookup"><span data-stu-id="2a863-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="2a863-193">Példa</span><span class="sxs-lookup"><span data-stu-id="2a863-193">Example</span></span> #######

<span data-ttu-id="2a863-194">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-194">This section is informative.</span></span>

<span data-ttu-id="2a863-195">A következő objektum határozza meg a Hamilton</span><span class="sxs-lookup"><span data-stu-id="2a863-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="2a863-196">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 \sigma} egy ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 \sigma} egy ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="2a863-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a><span data-ttu-id="2a863-197">Részecske – Hole reprezentációs objektum</span><span class="sxs-lookup"><span data-stu-id="2a863-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="2a863-198">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-198">This section is normative.</span></span>

<span data-ttu-id="2a863-199">A részecske – Hole reprezentációs objektum azt adja meg, hogy a tárolt alapértékek meghatározása a részecske-furat ábrázolására vonatkozik, amelyben a létrehozási és a megsemmisítési operátorok leírják a használt hivatkozási állapottól (például Hartree) származó izgalomokat. Fock állapota.</span><span class="sxs-lookup"><span data-stu-id="2a863-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="2a863-200">Az objektum nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="2a863-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="2a863-201">Ha az objektum nincs megadva, a Hamilton úgy kell értelmezni, hogy a rendszer ne adja meg a részecske-furatos ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="2a863-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="2a863-202">Ha van, akkor a `particle_hole_representation` értékének olyan ritka tömb mennyiségű objektumnak kell lennie, amelynek indexei négy egész szám, és amelynek értéke egy szám és egy sztring.</span><span class="sxs-lookup"><span data-stu-id="2a863-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="2a863-203">Az egyes elemek értékének karakterlánc-része csak a `'+'` és `'-'` karaktereket tartalmazza, amely megadja, hogy a kifejezésben megadott tényező egy létrehozási vagy megsemmisülési operátor a részecske – Hole ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="2a863-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="2a863-204">Például a `"-+++"` a (z) $i $ helyen létrehozott lyukra reagál, és a $j, a k $ és a $l $ helyen létrehozott részecskéket hozza létre.</span><span class="sxs-lookup"><span data-stu-id="2a863-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="2a863-205">Mivel a `particle_hole_representation` értéke ritka tömb mennyiségű objektum, meg kell adni a `unit` és `format` tulajdonságokat.</span><span class="sxs-lookup"><span data-stu-id="2a863-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="2a863-206">Az elfogadható egységeket az 1. táblázat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2a863-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="2a863-207">A `format` tulajdonság megadása kötelező, és azt jelzi, hogy a Hamilton-együtthatók meg vannak-e adva sűrű vagy ritka tömbként.</span><span class="sxs-lookup"><span data-stu-id="2a863-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="2a863-208">A jelenlegi verzióban csak a ritka tömbök támogatottak, és az értelmezés szerint az összes meghatározatlan elem $0 $, de a jövőbeli verziók támogatják a `format` tulajdonság további értékeit is.</span><span class="sxs-lookup"><span data-stu-id="2a863-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="2a863-209">Kezdeti állapot szakasz</span><span class="sxs-lookup"><span data-stu-id="2a863-209">Initial State Section</span></span> ###

<span data-ttu-id="2a863-210">A initial_state_suggestion objektum a megadott Hamilton tartozó kezdeti kvantum-állapotokat határozza meg.</span><span class="sxs-lookup"><span data-stu-id="2a863-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="2a863-211">Az objektumnak JSON-`state` objektumok tömbjét kell tartalmaznia.</span><span class="sxs-lookup"><span data-stu-id="2a863-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="2a863-212">Állapot objektum</span><span class="sxs-lookup"><span data-stu-id="2a863-212">State object</span></span> ####

<span data-ttu-id="2a863-213">Az egyes állapotok a megszállt pályák felhelyezését jelentik.</span><span class="sxs-lookup"><span data-stu-id="2a863-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="2a863-214">Minden állapot-objektumnak rendelkeznie kell egy karakterláncot tartalmazó `label` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="2a863-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="2a863-215">Minden állapot objektumnak rendelkeznie kell egy olyan `superposition` tulajdonsággal, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2a863-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="2a863-216">Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0} $ $ képviselő</span><span class="sxs-lookup"><span data-stu-id="2a863-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="2a863-217">Alapul szolgáló set objektum</span><span class="sxs-lookup"><span data-stu-id="2a863-217">Basis Set Object</span></span> ####

<span data-ttu-id="2a863-218">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-218">This section is normative.</span></span>

<span data-ttu-id="2a863-219">Az összes szerves set objektum rendelkezhet `basis_set` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="2a863-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="2a863-220">Ha van, akkor a `basis_set` tulajdonság értékének olyan objektumnak kell lennie, amelynek két tulajdonsága van, `type` és `name`.</span><span class="sxs-lookup"><span data-stu-id="2a863-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="2a863-221">A `basis_set` tulajdonság értéke alapján azonosított függvényeknek valós értékűnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="2a863-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="2a863-222">Ennek a specifikációnak a jövőbeli verzióiban a teljes körű függvények valós értékűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="2a863-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="2a863-223">Táblák és felsorolások</span><span class="sxs-lookup"><span data-stu-id="2a863-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="2a863-224">1\. táblázat.</span><span class="sxs-lookup"><span data-stu-id="2a863-224">Table 1.</span></span> <span data-ttu-id="2a863-225">Engedélyezett fizikai egységek</span><span class="sxs-lookup"><span data-stu-id="2a863-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="2a863-226">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-226">This section is normative.</span></span>

<span data-ttu-id="2a863-227">Az egységet megadó összes sztringnek a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="2a863-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="2a863-228">Az elemzőknek és a termelőknek egyenértékűnek kell lenniük a következő egyszerű mennyiségi objektumokkal:</span><span class="sxs-lookup"><span data-stu-id="2a863-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="2a863-229">2\. táblázat</span><span class="sxs-lookup"><span data-stu-id="2a863-229">Table 2.</span></span> <span data-ttu-id="2a863-230">Engedélyezett indexelési konvenciók</span><span class="sxs-lookup"><span data-stu-id="2a863-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="2a863-231">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="2a863-231">This section is normative.</span></span>

<span data-ttu-id="2a863-232">A tárgymutató-konvenciót megadó összes karakterláncnak a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="2a863-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="2a863-233">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-233">This section is informative.</span></span>

<span data-ttu-id="2a863-234">A specifikáció későbbi verzióiban további indexelési konvenciók is bevezethetők.</span><span class="sxs-lookup"><span data-stu-id="2a863-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="2a863-235">Az index konvencióinak értelmezése</span><span class="sxs-lookup"><span data-stu-id="2a863-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="2a863-236">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="2a863-236">This section is informative.</span></span>
