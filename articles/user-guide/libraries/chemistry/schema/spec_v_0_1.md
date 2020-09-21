---
title: Broombridge séma specifikációja (0,1-es verzió)
description: A Broombridge Quantum kémia Schema v 0.1 specifikációinak részletei a Microsoft Quantum kémia Library-hez.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: b99c90c434958f7b04712580789b203766cd084d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835740"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="b8953-103">Broombridge-specifikáció – v 0.1</span><span class="sxs-lookup"><span data-stu-id="b8953-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="b8953-104">A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.</span><span class="sxs-lookup"><span data-stu-id="b8953-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="b8953-105">A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.</span><span class="sxs-lookup"><span data-stu-id="b8953-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="b8953-106">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="b8953-106">Introduction</span></span> ##

<span data-ttu-id="b8953-107">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-107">This section is informative.</span></span>

<span data-ttu-id="b8953-108">A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="b8953-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="b8953-109">Szerializálás</span><span class="sxs-lookup"><span data-stu-id="b8953-109">Serialization</span></span> ##

<span data-ttu-id="b8953-110">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-110">This section is normative.</span></span>

<span data-ttu-id="b8953-111">Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="b8953-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="b8953-112">A YAML szerializált objektumnak rendelkeznie kell egy olyan tulajdonsággal `"$schema"` , amelynek az értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` , és a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján érvényesnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b8953-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="b8953-113">A specifikáció hátralévő részében a "The Broombridge Object" kifejezés a Broombridge YAML-dokumentumból deszerializált JSON-objektumra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="b8953-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="b8953-114">Hacsak másként nincs jelezve, az objektumok nem rendelkezhetnek a jelen dokumentumban explicit módon megadott további tulajdonságokkal.</span><span class="sxs-lookup"><span data-stu-id="b8953-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="b8953-115">További definíciók</span><span class="sxs-lookup"><span data-stu-id="b8953-115">Additional Definitions</span></span> ##

<span data-ttu-id="b8953-116">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="b8953-117">Mennyiségi objektumok</span><span class="sxs-lookup"><span data-stu-id="b8953-117">Quantity Objects</span></span> ###

<span data-ttu-id="b8953-118">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-118">This section is normative.</span></span>

<span data-ttu-id="b8953-119">A _mennyiségi objektum_ egy JSON-objektum, és rendelkeznie kell egy olyan tulajdonsággal, `units` amelynek értéke az 1. táblázatban felsorolt engedélyezett értékek egyike.</span><span class="sxs-lookup"><span data-stu-id="b8953-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="b8953-120">A mennyiségi objektum egy _egyszerű mennyiségi objektum_ , ha a `value` tulajdonsága mellett egyetlen tulajdonsággal rendelkezik `units` .</span><span class="sxs-lookup"><span data-stu-id="b8953-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="b8953-121">A tulajdonság értékének `value` számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b8953-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="b8953-122">A mennyiségi objektum egy _körülhatárolt mennyiségi objektum_ , ha a tulajdonságai és a `lower` `upper` tulajdonsága mellett is szerepel `units` .</span><span class="sxs-lookup"><span data-stu-id="b8953-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="b8953-123">A és a tulajdonság értékének `lower` `upper` számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b8953-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="b8953-124">A kötött mennyiségű objektum rendelkezhet olyan tulajdonsággal `value` , amelynek értéke egy szám.</span><span class="sxs-lookup"><span data-stu-id="b8953-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="b8953-125">A mennyiségi objektum egy _ritka tömbben lévő mennyiség objektum_ , ha a tulajdonsága és tulajdonsága mellett egy tulajdonság is szerepel `format` `values` `units` .</span><span class="sxs-lookup"><span data-stu-id="b8953-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="b8953-126">A értékének `format` a karakterláncnak kell lennie `sparse` .</span><span class="sxs-lookup"><span data-stu-id="b8953-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="b8953-127">A tulajdonság értékének `values` tömbnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b8953-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="b8953-128">Minden elemnek `values` olyan tömbnek kell lennie, amely a ritka tömb mennyiségének indexeit és értékét jelöli.</span><span class="sxs-lookup"><span data-stu-id="b8953-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="b8953-129">A ritka tömb mennyiségi objektumának minden eleméhez egyedi indexeket kell megadni a teljes ritka tömb mennyiségi objektumán.</span><span class="sxs-lookup"><span data-stu-id="b8953-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="b8953-130">Ha egy index a értékkel van megadva `0` , az elemzőnek a ritka tömb mennyiségi objektumát azonos módon kell kezelnie egy olyan ritka tömbbeli mennyiség objektummal, amelyben az index egyáltalán nem szerepel.</span><span class="sxs-lookup"><span data-stu-id="b8953-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="b8953-131">Egy mennyiségi objektumnak a következők egyikének kell lennie</span><span class="sxs-lookup"><span data-stu-id="b8953-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="b8953-132">egy egyszerű mennyiségi objektum,</span><span class="sxs-lookup"><span data-stu-id="b8953-132">a simple quantity object,</span></span>
- <span data-ttu-id="b8953-133">egy kötött mennyiségi objektum, vagy</span><span class="sxs-lookup"><span data-stu-id="b8953-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="b8953-134">egy ritka tömb mennyiségi objektuma.</span><span class="sxs-lookup"><span data-stu-id="b8953-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="b8953-135">Példák</span><span class="sxs-lookup"><span data-stu-id="b8953-135">Examples</span></span> ###

<span data-ttu-id="b8953-136">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-136">This section is informative.</span></span>

<span data-ttu-id="b8953-137">Egy egyszerű mennyiség, amely A $1.9844146837 \Mathrm{ha} $ értéket jelöli \, :</span><span class="sxs-lookup"><span data-stu-id="b8953-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="b8953-138">Egy kötött mennyiség, amely egységes eloszlást jelképez a $ [-7,-6] \, \mathrm{ha} $ intervallumban:</span><span class="sxs-lookup"><span data-stu-id="b8953-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="b8953-139">Az alábbiakban egy olyan ritka tömbbeli mennyiség szerepel, amelynek a eleme egyenlő a következővel `[1, 2]` `hello` `[3, 4]` `world` :</span><span class="sxs-lookup"><span data-stu-id="b8953-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="b8953-140">Formázási szakasz</span><span class="sxs-lookup"><span data-stu-id="b8953-140">Format Section</span></span> ##

<span data-ttu-id="b8953-141">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-141">This section is normative.</span></span>

<span data-ttu-id="b8953-142">A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie `format` , amelynek értéke egy nevű JSON-objektum `version` .</span><span class="sxs-lookup"><span data-stu-id="b8953-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="b8953-143">A `version` tulajdonságnak értékkel kell rendelkeznie `"0.1"` .</span><span class="sxs-lookup"><span data-stu-id="b8953-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="b8953-144">Példa</span><span class="sxs-lookup"><span data-stu-id="b8953-144">Example</span></span> ###

<span data-ttu-id="b8953-145">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="b8953-146">Beépített készletek szakasz</span><span class="sxs-lookup"><span data-stu-id="b8953-146">Integral Sets Section</span></span> ##

<span data-ttu-id="b8953-147">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-147">This section is normative.</span></span>

<span data-ttu-id="b8953-148">A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie `integral_sets` , amelynek értéke JSON-tömb.</span><span class="sxs-lookup"><span data-stu-id="b8953-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="b8953-149">A tulajdonság értékének minden elemének `integral_sets` egy olyan JSON-objektumnak kell lennie, amely a szakasz hátralévő részében leírtak szerint egy egységes készletet ismertet.</span><span class="sxs-lookup"><span data-stu-id="b8953-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="b8953-150">A szakasz hátralévő részében az "integrált készlet objektum" kifejezés a `integral_sets` Broombridge objektum tulajdonságának értékében található elemre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="b8953-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="b8953-151">Minden szerves set objektumnak olyan tulajdonsággal kell rendelkeznie `metadata` , amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="b8953-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="b8953-152">Az értéke lehet `metadata` az üres JSON-objektum (azaz `{}` ), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="b8953-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="b8953-153">Hamilton szakasz</span><span class="sxs-lookup"><span data-stu-id="b8953-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="b8953-154">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b8953-154">Overview</span></span> ####

<span data-ttu-id="b8953-155">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-155">This section is informative.</span></span>

<span data-ttu-id="b8953-156">Az `hamiltonian` egyes beépített objektumok tulajdonsága egy adott Quantum kémiával kapcsolatos probléma Hamilton írja le azáltal, hogy az egy-és kéttörzsű kifejezéseket a valós számok ritka számaként sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="b8953-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="b8953-157">Az egyes integrált Hamilton-kezelők a következő űrlapot írják be:</span><span class="sxs-lookup"><span data-stu-id="b8953-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="b8953-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} h \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="b8953-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="b8953-159">Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.</span><span class="sxs-lookup"><span data-stu-id="b8953-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="b8953-160">Az egyértelműség érdekében az egyelektronos kifejezés a következő:</span><span class="sxs-lookup"><span data-stu-id="b8953-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="b8953-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="b8953-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="b8953-162">a két elektron kifejezés pedig</span><span class="sxs-lookup"><span data-stu-id="b8953-162">and the two-electron term is</span></span>

<span data-ttu-id="b8953-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="b8953-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="b8953-164">Ahogy [ `basis_set` az a](#basis-set-object) tulajdonság egyes elemeinek leírásában is `integral_sets` látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.</span><span class="sxs-lookup"><span data-stu-id="b8953-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="b8953-165">Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8953-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="b8953-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="b8953-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="b8953-167">Tartalom</span><span class="sxs-lookup"><span data-stu-id="b8953-167">Contents</span></span> ####

<span data-ttu-id="b8953-168">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-168">This section is normative.</span></span>

<span data-ttu-id="b8953-169">Minden szerves készletnek rendelkeznie kell egy olyan tulajdonsággal `hamiltonian` , amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="b8953-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="b8953-170">A `hamiltonian` tulajdonság értéke Hamilton objektum, és a `one_electron_integrals` `two_electron_integrals` szakasz hátralévő részében ISMERTETett tulajdonságokkal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="b8953-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="b8953-171">Egy Hamilton objektum is rendelkezhet tulajdonsággal `particle_hole_representation` .</span><span class="sxs-lookup"><span data-stu-id="b8953-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="b8953-172">Ha van, akkor a értékének a `particle_hole_representation` szakasz hátralévő részében ismertetett formátumot kell követnie.</span><span class="sxs-lookup"><span data-stu-id="b8953-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="b8953-173">Egy elektronos szerves objektum</span><span class="sxs-lookup"><span data-stu-id="b8953-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="b8953-174">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-174">This section is normative.</span></span>

<span data-ttu-id="b8953-175">A `one_electron_integrals` Hamilton objektum tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.</span><span class="sxs-lookup"><span data-stu-id="b8953-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="b8953-176">Minden kifejezésnek tartalmaznia kell indexekkel, `[i, j]` ahol `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="b8953-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="b8953-177">Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.</span><span class="sxs-lookup"><span data-stu-id="b8953-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="b8953-178">Példa</span><span class="sxs-lookup"><span data-stu-id="b8953-178">Example</span></span> ######

<span data-ttu-id="b8953-179">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-179">This section is informative.</span></span>

<span data-ttu-id="b8953-180">A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="b8953-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="b8953-181">A Broombridge 1 alapú indexelést használ.</span><span class="sxs-lookup"><span data-stu-id="b8953-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="b8953-182">Két elektronos szerves objektum</span><span class="sxs-lookup"><span data-stu-id="b8953-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="b8953-183">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-183">This section is normative.</span></span>

<span data-ttu-id="b8953-184">A `two_electron_integrals` Hamilton objektum tulajdonságának olyan ritka tömb mennyiségnek kell lennie, amely egy további nevű tulajdonsággal rendelkezik `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="b8953-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="b8953-185">A értékének minden elemének `two_electron_integrals` négy indextel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="b8953-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="b8953-186">Minden `two_electron_integrals` tulajdonságnak RENDELKEZNIE kell `index_convention` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="b8953-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="b8953-187">A tulajdonság értékének az `index_convention` 1. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b8953-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="b8953-188">Ha a értéke `index_convention` `mulliken` , akkor a `two_electron_integrals` ritka tömb mennyiségének minden eleme esetében egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton-kifejezést kell létrehoznia, amely a kételektronos operátorral egyenlő $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, ahol a $i $, $j $, $k $ és $l $ értéknek egész számnak kell lennie a befogadó tartomány 1 és a szerves készlet objektum tulajdonsága által meghatározott elektronok számával `n_electrons` , és ahol $h _ {i, j, k, l} $ a `[i, j, k, l, h(i, j, k, l)]` ritka tömb mennyiségének eleme.</span><span class="sxs-lookup"><span data-stu-id="b8953-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="b8953-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="b8953-189">Symmetries</span></span> ######

<span data-ttu-id="b8953-190">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-190">This section is normative.</span></span>

<span data-ttu-id="b8953-191">Ha `index_convention` egy objektum tulajdonsága `two_electron_integrals` egyenlő `mulliken` , akkor ha az indexekkel rendelkező elem szerepel `[i, j, k, l]` , a következő indexek nem lehetnek jelen, kivéve, ha egyenlőek `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="b8953-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="b8953-192">Mivel a `index_convention` tulajdonság egy ritka mennyiségű objektum, a különböző elemeken nem lehet megismételni az indexeket.</span><span class="sxs-lookup"><span data-stu-id="b8953-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="b8953-193">Ha az indexekkel rendelkező elemek `[i, j, k, l]` jelen vannak, akkor előfordulhat, hogy nincs más elem az indexekkel.</span><span class="sxs-lookup"><span data-stu-id="b8953-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="b8953-194">Példa</span><span class="sxs-lookup"><span data-stu-id="b8953-194">Example</span></span> #######

<span data-ttu-id="b8953-195">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-195">This section is informative.</span></span>

<span data-ttu-id="b8953-196">A következő objektum határozza meg a Hamilton</span><span class="sxs-lookup"><span data-stu-id="b8953-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="b8953-197">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} { \_ 6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} {1, \sigma} a ^ \_ {\dagger} { \_ 6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="b8953-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="b8953-198">Részecske – Hole reprezentációs objektum</span><span class="sxs-lookup"><span data-stu-id="b8953-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="b8953-199">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-199">This section is normative.</span></span>

<span data-ttu-id="b8953-200">A részecske – Hole reprezentációs objektum azt adja meg, hogy a tárolt szerves adatok meghatározása a részecske-furatokra vonatkozik, amelyekben a létrehozási és a megsemmisítési operátorok leírják a használt hivatkozási állapottól, például a Hartree – Fock állapottal kapcsolatos izgalomokat.</span><span class="sxs-lookup"><span data-stu-id="b8953-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="b8953-201">Az objektum nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="b8953-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="b8953-202">Ha az objektum nincs megadva, a Hamilton úgy kell értelmezni, hogy a rendszer ne adja meg a részecske-furatos ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="b8953-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="b8953-203">Ha van, akkor a értékének `particle_hole_representation` olyan ritka tömbbeli mennyiség típusú objektumnak kell lennie, amelynek indexei négy egész szám, és amelynek értéke egy szám és egy sztring.</span><span class="sxs-lookup"><span data-stu-id="b8953-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="b8953-204">Az egyes elemek értékének karakterlánc-részének csak a karaktereket kell tartalmaznia `'+'` , `'-'` amely meghatározza, hogy a kifejezésben megadott tényező egy létrehozási vagy megsemmisülési operátor a részecske – Hole ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="b8953-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="b8953-205">Például `"-+++"` egy, a (z) $i $ helyen létrehozott lyukra válaszol, és a (z) $j, k $ és $l $ helyen létrehozott részecskéket hozza létre.</span><span class="sxs-lookup"><span data-stu-id="b8953-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="b8953-206">Mivel a `particle_hole_representation` egy ritka tömbbeli mennyiség objektum értéke, `unit` meg kell adni a és a `format` tulajdonságokat.</span><span class="sxs-lookup"><span data-stu-id="b8953-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="b8953-207">Az elfogadható egységeket az 1. táblázat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b8953-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="b8953-208">A `format` tulajdonság megadása kötelező, és azt jelzi, hogy a Hamilton-együtthatók egy sűrű vagy ritka tömbként vannak-e megadva.</span><span class="sxs-lookup"><span data-stu-id="b8953-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="b8953-209">A jelenlegi verzióban csak a ritka tömbök támogatottak, és az értelmezés szerint az összes meghatározatlan elem $0 $, a későbbi verziók azonban a tulajdonság további értékeihez is hozzáadhatnak támogatást `format` .</span><span class="sxs-lookup"><span data-stu-id="b8953-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="b8953-210">Kezdeti állapot szakasz</span><span class="sxs-lookup"><span data-stu-id="b8953-210">Initial State Section</span></span> ###

<span data-ttu-id="b8953-211">A initial_state_suggestion objektum a megadott Hamilton tartozó kezdeti kvantum-állapotokat határozza meg.</span><span class="sxs-lookup"><span data-stu-id="b8953-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="b8953-212">Az objektumnak JSON-objektumok tömbje kell, hogy legyen `state` .</span><span class="sxs-lookup"><span data-stu-id="b8953-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="b8953-213">Állapot objektum</span><span class="sxs-lookup"><span data-stu-id="b8953-213">State object</span></span> ####

<span data-ttu-id="b8953-214">Az egyes állapotok a megszállt pályák felhelyezését jelentik.</span><span class="sxs-lookup"><span data-stu-id="b8953-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="b8953-215">Minden állapot objektumnak tartalmaznia kell egy `label` sztringet tartalmazó tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="b8953-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="b8953-216">Minden állapot objektumnak rendelkeznie kell egy olyan `superposition` tulajdonsággal, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b8953-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="b8953-217">Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0.2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ a következőt képviseli:</span><span class="sxs-lookup"><span data-stu-id="b8953-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="b8953-218">Alapul szolgáló set objektum</span><span class="sxs-lookup"><span data-stu-id="b8953-218">Basis Set Object</span></span> ####

<span data-ttu-id="b8953-219">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-219">This section is normative.</span></span>

<span data-ttu-id="b8953-220">Az egyes szerves set objektumok rendelkezhetnek `basis_set` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="b8953-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="b8953-221">Ha van ilyen, a tulajdonság értékének `basis_set` két tulajdonsággal rendelkező objektumnak kell lennie, `type` és `name` .</span><span class="sxs-lookup"><span data-stu-id="b8953-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="b8953-222">A tulajdonság értékével azonosított alap függvényeknek `basis_set` valós értékűnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="b8953-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="b8953-223">Ennek a specifikációnak a jövőbeli verzióiban a teljes körű függvények valós értékűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="b8953-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="b8953-224">Táblák és felsorolások</span><span class="sxs-lookup"><span data-stu-id="b8953-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="b8953-225">1. táblázat</span><span class="sxs-lookup"><span data-stu-id="b8953-225">Table 1.</span></span> <span data-ttu-id="b8953-226">Engedélyezett fizikai egységek</span><span class="sxs-lookup"><span data-stu-id="b8953-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="b8953-227">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-227">This section is normative.</span></span>

<span data-ttu-id="b8953-228">Az egységet megadó összes sztringnek a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="b8953-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="b8953-229">Az elemzőknek és a termelőknek egyenértékűnek kell lenniük a következő egyszerű mennyiségi objektumokkal:</span><span class="sxs-lookup"><span data-stu-id="b8953-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="b8953-230">2. táblázat</span><span class="sxs-lookup"><span data-stu-id="b8953-230">Table 2.</span></span> <span data-ttu-id="b8953-231">Engedélyezett indexelési konvenciók</span><span class="sxs-lookup"><span data-stu-id="b8953-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="b8953-232">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="b8953-232">This section is normative.</span></span>

<span data-ttu-id="b8953-233">A tárgymutató-konvenciót megadó összes karakterláncnak a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="b8953-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="b8953-234">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-234">This section is informative.</span></span>

<span data-ttu-id="b8953-235">A specifikáció későbbi verzióiban további indexelési konvenciók is bevezethetők.</span><span class="sxs-lookup"><span data-stu-id="b8953-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="b8953-236">Az index konvencióinak értelmezése</span><span class="sxs-lookup"><span data-stu-id="b8953-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="b8953-237">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="b8953-237">This section is informative.</span></span>
