---
title: Broombridge séma specifikációja (0,2-es verzió)
description: A Broombridge Quantum kémia Schema v 0.2 specifikációit részletezi a Microsoft Quantum kémia Library-hez.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8d26b56d88f365144510692466bfffc7feb71d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854063"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="e8e28-103">Broombridge-specifikáció – v 0.2</span><span class="sxs-lookup"><span data-stu-id="e8e28-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="e8e28-104">A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.</span><span class="sxs-lookup"><span data-stu-id="e8e28-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="e8e28-105">A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.</span><span class="sxs-lookup"><span data-stu-id="e8e28-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="e8e28-106">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="e8e28-106">Introduction</span></span> ##

<span data-ttu-id="e8e28-107">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-107">This section is informative.</span></span>

<span data-ttu-id="e8e28-108">A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="e8e28-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="e8e28-109">Szerializálás</span><span class="sxs-lookup"><span data-stu-id="e8e28-109">Serialization</span></span> ##

<span data-ttu-id="e8e28-110">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-110">This section is normative.</span></span>

<span data-ttu-id="e8e28-111">Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="e8e28-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="e8e28-112">A YAML szerializált objektumnak rendelkeznie kell egy olyan tulajdonsággal `"$schema"` , amelynek az értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` , és a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján érvényesnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="e8e28-113">A specifikáció hátralévő részében a "The Broombridge Object" kifejezés a Broombridge YAML-dokumentumból deszerializált JSON-objektumra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="e8e28-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="e8e28-114">Hacsak másként nincs jelezve, az objektumok nem rendelkezhetnek a jelen dokumentumban explicit módon megadott további tulajdonságokkal.</span><span class="sxs-lookup"><span data-stu-id="e8e28-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="e8e28-115">További definíciók</span><span class="sxs-lookup"><span data-stu-id="e8e28-115">Additional Definitions</span></span> ##

<span data-ttu-id="e8e28-116">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="e8e28-117">Mennyiségi objektumok</span><span class="sxs-lookup"><span data-stu-id="e8e28-117">Quantity Objects</span></span> ###

<span data-ttu-id="e8e28-118">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-118">This section is normative.</span></span>

<span data-ttu-id="e8e28-119">A _mennyiségi objektum_ egy JSON-objektum, és rendelkeznie kell egy olyan tulajdonsággal, `units` amelynek értéke az 1. táblázatban felsorolt engedélyezett értékek egyike.</span><span class="sxs-lookup"><span data-stu-id="e8e28-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="e8e28-120">A mennyiségi objektum egy _egyszerű mennyiségi objektum_ , ha a `value` tulajdonsága mellett egyetlen tulajdonsággal rendelkezik `units` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="e8e28-121">A tulajdonság értékének `value` számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="e8e28-122">A mennyiségi objektum egy _körülhatárolt mennyiségi objektum_ , ha a tulajdonságai és a `lower` `upper` tulajdonsága mellett is szerepel `units` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="e8e28-123">A és a tulajdonság értékének `lower` `upper` számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="e8e28-124">A kötött mennyiségű objektum rendelkezhet olyan tulajdonsággal `value` , amelynek értéke egy szám.</span><span class="sxs-lookup"><span data-stu-id="e8e28-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="e8e28-125">A mennyiségi objektum egy _ritka tömbben lévő mennyiség objektum_ , ha a tulajdonsága és tulajdonsága mellett egy tulajdonság is szerepel `format` `values` `units` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="e8e28-126">A értékének `format` a karakterláncnak kell lennie `sparse` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="e8e28-127">A tulajdonság értékének `values` tömbnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="e8e28-128">Minden elemnek `values` olyan tömbnek kell lennie, amely a ritka tömb mennyiségének indexeit és értékét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e8e28-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="e8e28-129">A ritka tömb mennyiségi objektumának minden eleméhez egyedi indexeket kell megadni a teljes ritka tömb mennyiségi objektumán.</span><span class="sxs-lookup"><span data-stu-id="e8e28-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="e8e28-130">Ha egy index a értékkel van megadva `0` , az elemzőnek a ritka tömb mennyiségi objektumát azonos módon kell kezelnie egy olyan ritka tömbbeli mennyiség objektummal, amelyben az index egyáltalán nem szerepel.</span><span class="sxs-lookup"><span data-stu-id="e8e28-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="e8e28-131">Egy mennyiségi objektumnak a következők egyikének kell lennie</span><span class="sxs-lookup"><span data-stu-id="e8e28-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="e8e28-132">egy egyszerű mennyiségi objektum,</span><span class="sxs-lookup"><span data-stu-id="e8e28-132">a simple quantity object,</span></span>
- <span data-ttu-id="e8e28-133">egy kötött mennyiségi objektum, vagy</span><span class="sxs-lookup"><span data-stu-id="e8e28-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="e8e28-134">egy ritka tömb mennyiségi objektuma.</span><span class="sxs-lookup"><span data-stu-id="e8e28-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="e8e28-135">Példák</span><span class="sxs-lookup"><span data-stu-id="e8e28-135">Examples</span></span> ###

<span data-ttu-id="e8e28-136">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-136">This section is informative.</span></span>

<span data-ttu-id="e8e28-137">Egy egyszerű mennyiség, amely A $1.9844146837 \Mathrm{ha} $ értéket jelöli \, :</span><span class="sxs-lookup"><span data-stu-id="e8e28-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="e8e28-138">Egy kötött mennyiség, amely egységes eloszlást jelképez a $ [-7,-6] \, \mathrm{ha} $ intervallumban:</span><span class="sxs-lookup"><span data-stu-id="e8e28-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="e8e28-139">Az alábbiakban egy olyan ritka tömbbeli mennyiség szerepel, amelynek a eleme egyenlő a következővel `[1, 2]` `hello` `[3, 4]` `world` :</span><span class="sxs-lookup"><span data-stu-id="e8e28-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="e8e28-140">Formázási szakasz</span><span class="sxs-lookup"><span data-stu-id="e8e28-140">Format Section</span></span> ##

<span data-ttu-id="e8e28-141">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-141">This section is normative.</span></span>

<span data-ttu-id="e8e28-142">A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie `format` , amelynek értéke egy nevű JSON-objektum `version` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="e8e28-143">A `version` tulajdonságnak értékkel kell rendelkeznie `"0.2"` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="e8e28-144">Példa</span><span class="sxs-lookup"><span data-stu-id="e8e28-144">Example</span></span> ###

<span data-ttu-id="e8e28-145">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="e8e28-146">Probléma leírása szakasz</span><span class="sxs-lookup"><span data-stu-id="e8e28-146">Problem Description Section</span></span> ##

<span data-ttu-id="e8e28-147">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-147">This section is normative.</span></span>

<span data-ttu-id="e8e28-148">A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie `problem_description` , amelynek értéke JSON-tömb.</span><span class="sxs-lookup"><span data-stu-id="e8e28-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="e8e28-149">A tulajdonság értékének minden elemének `problem_description` egy olyan JSON-objektumnak kell lennie, amely a szakasz hátralévő részében leírtak szerint egy egységes készletet ismertet.</span><span class="sxs-lookup"><span data-stu-id="e8e28-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="e8e28-150">A szakasz további részében a "probléma leírása objektum" kifejezés a `problem_description` Broombridge objektum tulajdonságának értékében található elemre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="e8e28-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="e8e28-151">Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal `metadata` , amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="e8e28-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="e8e28-152">Az értéke lehet `metadata` az üres JSON-objektum (azaz `{}` ), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="e8e28-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="e8e28-153">Hamilton szakasz</span><span class="sxs-lookup"><span data-stu-id="e8e28-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="e8e28-154">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="e8e28-154">Overview</span></span> ####

<span data-ttu-id="e8e28-155">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-155">This section is informative.</span></span>

<span data-ttu-id="e8e28-156">Az `hamiltonian` egyes problémák Description objektum tulajdonsága egy adott kvantum-kémiai probléma Hamilton írja le azáltal, hogy az egy-és kéttörzsű kifejezéseket a valós számok ritka számaként sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="e8e28-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="e8e28-157">Az egyes problémák Description objektuma által leírt Hamilton-operátorok az űrlapot</span><span class="sxs-lookup"><span data-stu-id="e8e28-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="e8e28-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} h \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="e8e28-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="e8e28-159">Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.</span><span class="sxs-lookup"><span data-stu-id="e8e28-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="e8e28-160">Az egyértelműség érdekében az egyelektronos kifejezés a következő:</span><span class="sxs-lookup"><span data-stu-id="e8e28-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="e8e28-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="e8e28-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="e8e28-162">a két elektron kifejezés pedig</span><span class="sxs-lookup"><span data-stu-id="e8e28-162">and the two-electron term is</span></span>

<span data-ttu-id="e8e28-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="e8e28-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="e8e28-164">Ahogy [ `basis_set` az a](#basis-set-object) tulajdonság egyes elemeinek leírásában is `integral_sets` látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.</span><span class="sxs-lookup"><span data-stu-id="e8e28-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="e8e28-165">Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e8e28-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="e8e28-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="e8e28-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="e8e28-167">Tartalom</span><span class="sxs-lookup"><span data-stu-id="e8e28-167">Contents</span></span> ####

<span data-ttu-id="e8e28-168">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-168">This section is normative.</span></span>

<span data-ttu-id="e8e28-169">Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal `hamiltonian` , amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="e8e28-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="e8e28-170">A `hamiltonian` tulajdonság értéke Hamilton objektum, és a `one_electron_integrals` `two_electron_integrals` szakasz hátralévő részében ISMERTETett tulajdonságokkal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="e8e28-171">Minden probléma leírása objektumnak rendelkeznie kell egy `coulomb_repulsion` egyszerű mennyiségi objektum értékkel rendelkező tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="e8e28-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="e8e28-172">Minden probléma leírása objektumnak rendelkeznie kell egy `energy_offet` egyszerű mennyiségi objektum értékkel rendelkező tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="e8e28-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="e8e28-173">Megjegyzés A és a `coulomb_repulsion` `energy_offet` hozzáadott értékek rögzítik a Hamilton identitási idejét.</span><span class="sxs-lookup"><span data-stu-id="e8e28-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="e8e28-174">One-Electron szerves objektum</span><span class="sxs-lookup"><span data-stu-id="e8e28-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="e8e28-175">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-175">This section is normative.</span></span>

<span data-ttu-id="e8e28-176">A `one_electron_integrals` Hamilton objektum tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.</span><span class="sxs-lookup"><span data-stu-id="e8e28-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="e8e28-177">Minden kifejezésnek tartalmaznia kell indexekkel, `[i, j]` ahol `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="e8e28-178">Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.</span><span class="sxs-lookup"><span data-stu-id="e8e28-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="e8e28-179">Példa</span><span class="sxs-lookup"><span data-stu-id="e8e28-179">Example</span></span> ######

<span data-ttu-id="e8e28-180">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-180">This section is informative.</span></span>

<span data-ttu-id="e8e28-181">A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="e8e28-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="e8e28-182">A Broombridge 1 alapú indexelést használ.</span><span class="sxs-lookup"><span data-stu-id="e8e28-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="e8e28-183">Two-Electron szerves objektum</span><span class="sxs-lookup"><span data-stu-id="e8e28-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="e8e28-184">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-184">This section is normative.</span></span>

<span data-ttu-id="e8e28-185">A `two_electron_integrals` Hamilton objektum tulajdonságának olyan ritka tömb mennyiségnek kell lennie, amely egy további nevű tulajdonsággal rendelkezik `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="e8e28-186">A értékének minden elemének `two_electron_integrals` négy indextel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="e8e28-187">Minden `two_electron_integrals` tulajdonságnak RENDELKEZNIE kell `index_convention` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="e8e28-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="e8e28-188">A tulajdonság értékének az `index_convention` 1. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="e8e28-189">Ha a értéke `index_convention` `mulliken` , akkor a `two_electron_integrals` ritka tömb mennyiségének minden eleme esetében egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton-kifejezést kell létrehoznia, amely a kételektronos operátorral egyenlő $h _ {i, j, k, l} a ^ \ dagger_i a (z) ^ \ dagger_j a_k a_l $, ahol $i $, $j $, $k $ és $l $ értékének legalább 1 egész számnak kell lennie, és ahol $h _ {i, j, k, l} $ a `[i, j, k, l, h(i, j, k, l)]` ritka tömb mennyiségének eleme.</span><span class="sxs-lookup"><span data-stu-id="e8e28-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="e8e28-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="e8e28-190">Symmetries</span></span> ######

<span data-ttu-id="e8e28-191">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-191">This section is normative.</span></span>

<span data-ttu-id="e8e28-192">Ha `index_convention` egy objektum tulajdonsága `two_electron_integrals` egyenlő `mulliken` , akkor ha az indexekkel rendelkező elem szerepel `[i, j, k, l]` , a következő indexek nem lehetnek jelen, kivéve, ha egyenlőek `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="e8e28-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="e8e28-193">Mivel a `index_convention` tulajdonság egy ritka mennyiségű objektum, a különböző elemeken nem lehet megismételni az indexeket.</span><span class="sxs-lookup"><span data-stu-id="e8e28-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="e8e28-194">Ha az indexekkel rendelkező elemek `[i, j, k, l]` jelen vannak, akkor előfordulhat, hogy nincs más elem az indexekkel.</span><span class="sxs-lookup"><span data-stu-id="e8e28-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="e8e28-195">Példa</span><span class="sxs-lookup"><span data-stu-id="e8e28-195">Example</span></span> #######

<span data-ttu-id="e8e28-196">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-196">This section is informative.</span></span>

<span data-ttu-id="e8e28-197">A következő objektum határozza meg a Hamilton</span><span class="sxs-lookup"><span data-stu-id="e8e28-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="e8e28-198">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} { \_ 6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} {1, \sigma} a ^ \_ {\dagger} { \_ 6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="e8e28-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="e8e28-199">Kezdeti állapot szakasz</span><span class="sxs-lookup"><span data-stu-id="e8e28-199">Initial State Section</span></span> ###

<span data-ttu-id="e8e28-200">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-200">This section is normative.</span></span>

<span data-ttu-id="e8e28-201">Az az `initial_state_suggestion` objektum, amelynek az értéke JSON-tömb, megadja a megadott Hamilton érdekes kezdeti kvantum-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="e8e28-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="e8e28-202">A tulajdonság értékében szereplő összes elemnek `initial_state_suggestion` egy kvantum-állapotot leíró JSON-objektumnak kell lennie, a szakasz hátralévő részében leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="e8e28-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="e8e28-203">A szakasz hátralévő részében az "állam objektum" kifejezés a `initial_state_suggestion` Broombridge objektum tulajdonságának értékében található elemre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="e8e28-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="e8e28-204">Állapot objektum</span><span class="sxs-lookup"><span data-stu-id="e8e28-204">State object</span></span> ####

<span data-ttu-id="e8e28-205">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-205">This section is normative.</span></span>

<span data-ttu-id="e8e28-206">Minden állapot objektumnak tartalmaznia kell egy `label` sztringet tartalmazó tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="e8e28-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="e8e28-207">Minden állapot objektumnak rendelkeznie kell `method` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="e8e28-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="e8e28-208">A tulajdonság értékének a `method` 3. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="e8e28-209">Az egyes állapot-objektumok rendelkezhetnek olyan tulajdonsággal, `energy` amelynek értékének egyszerű mennyiségi objektumnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e8e28-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="e8e28-210">Ha a `method` tulajdonság értéke `sparse_multi_configurational` , az állapot objektumnak rendelkeznie kell egy olyan `superposition` tulajdonsággal, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e8e28-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="e8e28-211">Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0.2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} , $ $, ahol a $ \ket{E} $ energia $0,987 \textrm{ha} $, képviseli</span><span class="sxs-lookup"><span data-stu-id="e8e28-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="e8e28-212">Ha a `method` tulajdonság értéke `unitary_coupled_cluster` , az állapot objektumnak olyan tulajdonsággal kell rendelkeznie, `cluster_operator` amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="e8e28-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="e8e28-213">A JSON-objektumnak olyan `reference_state` tulajdonsággal kell rendelkeznie, amelynek értéke az alap állapot.</span><span class="sxs-lookup"><span data-stu-id="e8e28-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="e8e28-214">A JSON-objektum rendelkezhet egy olyan `one_body_amplitudes` tulajdonsággal, amelynek értéke egytörzsű fürtözött operátorok tömbje és amplitúdójuk.</span><span class="sxs-lookup"><span data-stu-id="e8e28-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="e8e28-215">A JSON-objektum rendelkezhet olyan `two_body_amplitudes` tulajdonsággal, amelynek értéke a kéttörzsű fürtcsomópontok tömbje és az amplitúdójuk.</span><span class="sxs-lookup"><span data-stu-id="e8e28-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="e8e28-216">az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e8e28-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="e8e28-217">Például a $ $ \ket{\text{Reference}} = (^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="e8e28-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="e8e28-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="e8e28-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="e8e28-219">$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} { \_ 3, \downarrow}a \_ {3, \uparrow}a { \_ 2, \downarrow} $ $ a jelölője</span><span class="sxs-lookup"><span data-stu-id="e8e28-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="e8e28-220">Alapul szolgáló set objektum</span><span class="sxs-lookup"><span data-stu-id="e8e28-220">Basis Set Object</span></span> ####

<span data-ttu-id="e8e28-221">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-221">This section is normative.</span></span>

<span data-ttu-id="e8e28-222">Előfordulhat, hogy az egyes problémák leírásának objektuma `basis_set` tulajdonsággal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="e8e28-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="e8e28-223">Ha van ilyen, a tulajdonság értékének `basis_set` két tulajdonsággal rendelkező objektumnak kell lennie, `type` és `name` .</span><span class="sxs-lookup"><span data-stu-id="e8e28-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="e8e28-224">A tulajdonság értékével azonosított alap függvényeknek `basis_set` valós értékűnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="e8e28-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="e8e28-225">Ennek a specifikációnak a jövőbeli verzióiban a teljes körű függvények valós értékűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="e8e28-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="e8e28-226">Táblák és felsorolások</span><span class="sxs-lookup"><span data-stu-id="e8e28-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="e8e28-227">1. táblázat</span><span class="sxs-lookup"><span data-stu-id="e8e28-227">Table 1.</span></span> <span data-ttu-id="e8e28-228">Engedélyezett fizikai egységek</span><span class="sxs-lookup"><span data-stu-id="e8e28-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="e8e28-229">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-229">This section is normative.</span></span>

<span data-ttu-id="e8e28-230">Az egységet megadó összes sztringnek a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="e8e28-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="e8e28-231">Az elemzőknek és a termelőknek egyenértékűnek kell lenniük a következő egyszerű mennyiségi objektumokkal:</span><span class="sxs-lookup"><span data-stu-id="e8e28-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="e8e28-232">2. táblázat</span><span class="sxs-lookup"><span data-stu-id="e8e28-232">Table 2.</span></span> <span data-ttu-id="e8e28-233">Engedélyezett indexelési konvenciók</span><span class="sxs-lookup"><span data-stu-id="e8e28-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="e8e28-234">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-234">This section is normative.</span></span>

<span data-ttu-id="e8e28-235">A tárgymutató-konvenciót megadó összes karakterláncnak a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="e8e28-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="e8e28-236">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-236">This section is informative.</span></span>

<span data-ttu-id="e8e28-237">A specifikáció későbbi verzióiban további indexelési konvenciók is bevezethetők.</span><span class="sxs-lookup"><span data-stu-id="e8e28-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="e8e28-238">Az index konvencióinak értelmezése</span><span class="sxs-lookup"><span data-stu-id="e8e28-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="e8e28-239">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="e8e28-240">3. táblázat</span><span class="sxs-lookup"><span data-stu-id="e8e28-240">Table 3.</span></span> <span data-ttu-id="e8e28-241">Engedélyezett állapotú metódusok</span><span class="sxs-lookup"><span data-stu-id="e8e28-241">Allowed State methods</span></span> ###

<span data-ttu-id="e8e28-242">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="e8e28-242">This section is normative.</span></span>

<span data-ttu-id="e8e28-243">Az állapot-metódust megadó összes karakterláncnak a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="e8e28-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="e8e28-244">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="e8e28-244">This section is informative.</span></span>

<span data-ttu-id="e8e28-245">További állapot-módszerek is bevezethetők a specifikáció jövőbeli verzióiban.</span><span class="sxs-lookup"><span data-stu-id="e8e28-245">Additional state methods may be introduced in future versions of this specification.</span></span>
