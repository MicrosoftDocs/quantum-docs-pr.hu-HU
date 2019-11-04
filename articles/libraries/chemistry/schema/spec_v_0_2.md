---
title: Broombridge séma specifikációja
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: 2f4be96bc6f1e8e6fe21b93bc0d9ab2aa367fd53
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185307"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="ab58e-102">Broombridge-specifikáció – v 0.2</span><span class="sxs-lookup"><span data-stu-id="ab58e-102">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="ab58e-103">A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.</span><span class="sxs-lookup"><span data-stu-id="ab58e-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="ab58e-104">A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.</span><span class="sxs-lookup"><span data-stu-id="ab58e-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="ab58e-105">Introduction (Bevezetés)</span><span class="sxs-lookup"><span data-stu-id="ab58e-105">Introduction</span></span> ##

<span data-ttu-id="ab58e-106">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-106">This section is informative.</span></span>

<span data-ttu-id="ab58e-107">A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="ab58e-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="ab58e-108">Szerializálási</span><span class="sxs-lookup"><span data-stu-id="ab58e-108">Serialization</span></span> ##

<span data-ttu-id="ab58e-109">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-109">This section is normative.</span></span>

<span data-ttu-id="ab58e-110">Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="ab58e-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="ab58e-111">A YAML szerializált objektumnak olyan tulajdonsággal kell rendelkeznie, `"$schema"` amelynek értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, és érvényesnek kell lennie a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján.</span><span class="sxs-lookup"><span data-stu-id="ab58e-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="ab58e-112">A specifikáció hátralévő részében a "The Broombridge Object" kifejezés a Broombridge YAML-dokumentumból deszerializált JSON-objektumra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="ab58e-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="ab58e-113">Hacsak másként nincs jelezve, az objektumok nem rendelkezhetnek a jelen dokumentumban explicit módon megadott további tulajdonságokkal.</span><span class="sxs-lookup"><span data-stu-id="ab58e-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="ab58e-114">További definíciók</span><span class="sxs-lookup"><span data-stu-id="ab58e-114">Additional Definitions</span></span> ##

<span data-ttu-id="ab58e-115">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="ab58e-116">Mennyiségi objektumok</span><span class="sxs-lookup"><span data-stu-id="ab58e-116">Quantity Objects</span></span> ###

<span data-ttu-id="ab58e-117">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-117">This section is normative.</span></span>

<span data-ttu-id="ab58e-118">A _mennyiségi objektum_ egy JSON-objektum, és rendelkeznie kell egy tulajdonsággal `units` amelynek értéke az 1. táblázatban felsorolt engedélyezett értékek egyike.</span><span class="sxs-lookup"><span data-stu-id="ab58e-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="ab58e-119">A mennyiségi objektum egy _egyszerű mennyiségi objektum_ , ha a `units` tulajdonságán felül egyetlen tulajdonság `value` van.</span><span class="sxs-lookup"><span data-stu-id="ab58e-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="ab58e-120">A `value` tulajdonság értékének számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="ab58e-121">A mennyiségi objektum egy _körülhatárolt mennyiségi objektum_ , ha a tulajdonsága `lower` és `upper` a `units` tulajdonság mellett.</span><span class="sxs-lookup"><span data-stu-id="ab58e-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="ab58e-122">A `lower` és az `upper` tulajdonság értékének számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="ab58e-123">A kötött mennyiség objektum rendelkezhet olyan tulajdonsággal, `value` amelynek értéke egy szám.</span><span class="sxs-lookup"><span data-stu-id="ab58e-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="ab58e-124">A mennyiségi objektum egy _ritka tömbbeli mennyiségű objektum_ , ha a tulajdonsága `format` és egy tulajdonság `values` a `units` tulajdonságán felül.</span><span class="sxs-lookup"><span data-stu-id="ab58e-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="ab58e-125">`format` értékének a karakterláncnak `sparse`nak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="ab58e-126">A `values` tulajdonság értékének tömbnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="ab58e-127">`values` minden elemének olyan tömbnek kell lennie, amely a ritka tömb mennyiségének indexeit és értékét jelöli.</span><span class="sxs-lookup"><span data-stu-id="ab58e-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="ab58e-128">A ritka tömb mennyiségi objektumának minden eleméhez egyedi indexeket kell megadni a teljes ritka tömb mennyiségi objektumán.</span><span class="sxs-lookup"><span data-stu-id="ab58e-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="ab58e-129">Ha egy index `0`értékkel rendelkezik, akkor az elemzőnek a ritka tömb mennyiségi objektumát azonos módon kell kezelnie egy olyan ritka tömbbeli mennyiség objektummal, amelyben az index egyáltalán nem szerepel.</span><span class="sxs-lookup"><span data-stu-id="ab58e-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="ab58e-130">Egy mennyiségi objektumnak a következők egyikének kell lennie</span><span class="sxs-lookup"><span data-stu-id="ab58e-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="ab58e-131">egy egyszerű mennyiségi objektum,</span><span class="sxs-lookup"><span data-stu-id="ab58e-131">a simple quantity object,</span></span>
- <span data-ttu-id="ab58e-132">egy kötött mennyiségi objektum, vagy</span><span class="sxs-lookup"><span data-stu-id="ab58e-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="ab58e-133">egy ritka tömb mennyiségi objektuma.</span><span class="sxs-lookup"><span data-stu-id="ab58e-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="ab58e-134">Példák</span><span class="sxs-lookup"><span data-stu-id="ab58e-134">Examples</span></span> ###

<span data-ttu-id="ab58e-135">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-135">This section is informative.</span></span>

<span data-ttu-id="ab58e-136">Egy egyszerű mennyiség, amely A $1.9844146837\,\mathrm{Ha} $ értéket jelöli:</span><span class="sxs-lookup"><span data-stu-id="ab58e-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="ab58e-137">Egy kötött mennyiség, amely egységes eloszlást képvisel a $ [-7,-6]\,\mathrm{Ha} $ intervallumban:</span><span class="sxs-lookup"><span data-stu-id="ab58e-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="ab58e-138">Az alábbiakban egy olyan ritka tömbbeli mennyiség szerepel, amely `[1, 2]` egyenlő `hello` és egy elem `[3, 4]` `world`:</span><span class="sxs-lookup"><span data-stu-id="ab58e-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="ab58e-139">Formázási szakasz</span><span class="sxs-lookup"><span data-stu-id="ab58e-139">Format Section</span></span> ##

<span data-ttu-id="ab58e-140">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-140">This section is normative.</span></span>

<span data-ttu-id="ab58e-141">A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie, `format` amelynek értéke egy `version`nevű tulajdonságú JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="ab58e-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="ab58e-142">A `version` tulajdonságnak `"0.2"`értékűnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-142">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="ab58e-143">Példa</span><span class="sxs-lookup"><span data-stu-id="ab58e-143">Example</span></span> ###

<span data-ttu-id="ab58e-144">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="ab58e-145">Probléma leírása szakasz</span><span class="sxs-lookup"><span data-stu-id="ab58e-145">Problem Description Section</span></span> ##

<span data-ttu-id="ab58e-146">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-146">This section is normative.</span></span>

<span data-ttu-id="ab58e-147">A Broombridge objektumnak rendelkeznie kell egy olyan tulajdonsággal, `problem_description` amelynek értéke JSON-tömb.</span><span class="sxs-lookup"><span data-stu-id="ab58e-147">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="ab58e-148">A `problem_description` tulajdonság értékében szereplő összes elemnek egy olyan JSON-objektumnak kell lennie, amely az adott szakasz hátralévő részében leírtak szerint egy egységes készletet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ab58e-148">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="ab58e-149">A szakasz további részében a "probléma leírása objektum" kifejezés a Broombridge objektum `problem_description` tulajdonságának értékében található elemre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="ab58e-149">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="ab58e-150">Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `metadata` amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="ab58e-150">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="ab58e-151">`metadata` értéke lehet az üres JSON-objektum (azaz `{}`), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="ab58e-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="ab58e-152">Hamilton szakasz</span><span class="sxs-lookup"><span data-stu-id="ab58e-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="ab58e-153">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ab58e-153">Overview</span></span> ####

<span data-ttu-id="ab58e-154">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-154">This section is informative.</span></span>

<span data-ttu-id="ab58e-155">Az egyes problémák Description objektum `hamiltonian` tulajdonsága egy adott kvantum-kémiai probléma Hamilton írja le azáltal, hogy az egy-és kéttörzsű kifejezéseket valós számú ritka tömbként sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="ab58e-155">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="ab58e-156">Az egyes problémák Description objektuma által leírt Hamilton-operátorok az űrlapot</span><span class="sxs-lookup"><span data-stu-id="ab58e-156">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="ab58e-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i \sigma} egy ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="ab58e-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="ab58e-158">Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.</span><span class="sxs-lookup"><span data-stu-id="ab58e-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="ab58e-159">Az egyértelműség érdekében az egyelektronos kifejezés a következő:</span><span class="sxs-lookup"><span data-stu-id="ab58e-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="ab58e-160">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="ab58e-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="ab58e-161">a két elektron kifejezés pedig</span><span class="sxs-lookup"><span data-stu-id="ab58e-161">and the two-electron term is</span></span>

<span data-ttu-id="ab58e-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="ab58e-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="ab58e-163">Ahogy a `integral_sets` tulajdonság egyes elemeinek [`basis_set` tulajdonságának](#basis-set-object) leírásában is látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.</span><span class="sxs-lookup"><span data-stu-id="ab58e-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="ab58e-164">Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ab58e-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="ab58e-165">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="ab58e-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="ab58e-166">Tartalom</span><span class="sxs-lookup"><span data-stu-id="ab58e-166">Contents</span></span> ####

<span data-ttu-id="ab58e-167">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-167">This section is normative.</span></span>

<span data-ttu-id="ab58e-168">Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `hamiltonian` amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="ab58e-168">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="ab58e-169">A `hamiltonian` tulajdonság értéke Hamilton-objektumként ismert, és a tulajdonságok `one_electron_integrals` és `two_electron_integrals` a szakasz hátralévő részében leírtak szerint kell megadni.</span><span class="sxs-lookup"><span data-stu-id="ab58e-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="ab58e-170">Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `coulomb_repulsion` amelynek értéke egyszerű mennyiségi objektum.</span><span class="sxs-lookup"><span data-stu-id="ab58e-170">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="ab58e-171">Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `energy_offet` amelynek értéke egyszerű mennyiségi objektum.</span><span class="sxs-lookup"><span data-stu-id="ab58e-171">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="ab58e-172">Megjegyzés A `coulomb_repulsion` és a `energy_offet` értékei együttesen rögzítik a Hamilton identitási idejét.</span><span class="sxs-lookup"><span data-stu-id="ab58e-172">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="ab58e-173">Egy elektronos szerves objektum</span><span class="sxs-lookup"><span data-stu-id="ab58e-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="ab58e-174">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-174">This section is normative.</span></span>

<span data-ttu-id="ab58e-175">A Hamilton objektum `one_electron_integrals` tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.</span><span class="sxs-lookup"><span data-stu-id="ab58e-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="ab58e-176">Minden kifejezésnek tartalmaznia kell indexekkel `[i, j]`, ahol `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="ab58e-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="ab58e-177">Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.</span><span class="sxs-lookup"><span data-stu-id="ab58e-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="ab58e-178">Példa</span><span class="sxs-lookup"><span data-stu-id="ab58e-178">Example</span></span> ######

<span data-ttu-id="ab58e-179">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-179">This section is informative.</span></span>

<span data-ttu-id="ab58e-180">A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 \downarrow} egy\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="ab58e-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="ab58e-181">A Broombridge 1 alapú indexelést használ.</span><span class="sxs-lookup"><span data-stu-id="ab58e-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="ab58e-182">Két elektronos szerves objektum</span><span class="sxs-lookup"><span data-stu-id="ab58e-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="ab58e-183">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-183">This section is normative.</span></span>

<span data-ttu-id="ab58e-184">A Hamilton objektum `two_electron_integrals` tulajdonságának olyan ritka tömb mennyiségnek kell lennie, amely egy `index_convention`nevű további tulajdonsággal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="ab58e-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="ab58e-185">`two_electron_integrals` értékének minden eleméhez négy indexnek kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="ab58e-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="ab58e-186">Minden `two_electron_integrals` tulajdonságnak rendelkeznie kell `index_convention` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="ab58e-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="ab58e-187">A `index_convention` tulajdonság értékének az 1. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="ab58e-188">Ha a `index_convention` értéke `mulliken`, akkor a `two_electron_integrals` ritka tömb mennyiségének minden egyes eleméhez egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton kifejezést kell létrehoznia, amely a kételektronos operátor $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , ahol $i $, $j $, $k $ és $l $ értéknek legalább 1 egész számnak kell lennie, és ahol $h _ {i, j, k, l} $ a ritka tömb mennyiségének `[i, j, k, l, h(i, j, k, l)]` eleme.</span><span class="sxs-lookup"><span data-stu-id="ab58e-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="ab58e-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="ab58e-189">Symmetries</span></span> ######

<span data-ttu-id="ab58e-190">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-190">This section is normative.</span></span>

<span data-ttu-id="ab58e-191">Ha egy `two_electron_integrals` objektum `index_convention` tulajdonsága egyenlő `mulliken`, akkor ha van olyan elem, amely indexekkel `[i, j, k, l]`, akkor a következő indexek nem lehetnek jelen, kivéve, ha `[i, j, k, l]`egyenlőek:</span><span class="sxs-lookup"><span data-stu-id="ab58e-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="ab58e-192">Mivel a `index_convention` tulajdonság ritka mennyiségű objektum, a különböző elemeken nem lehet megismételni az indexeket.</span><span class="sxs-lookup"><span data-stu-id="ab58e-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="ab58e-193">Ha a `[i, j, k, l]` indexekkel rendelkező elemek jelen vannak, akkor előfordulhat, hogy más elem nem rendelkezik ezekkel az indexekkel.</span><span class="sxs-lookup"><span data-stu-id="ab58e-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="ab58e-194">Példa</span><span class="sxs-lookup"><span data-stu-id="ab58e-194">Example</span></span> #######

<span data-ttu-id="ab58e-195">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-195">This section is informative.</span></span>

<span data-ttu-id="ab58e-196">A következő objektum határozza meg a Hamilton</span><span class="sxs-lookup"><span data-stu-id="ab58e-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="ab58e-197">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 \sigma} egy ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 \sigma} egy ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="ab58e-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="ab58e-198">Kezdeti állapot szakasz</span><span class="sxs-lookup"><span data-stu-id="ab58e-198">Initial State Section</span></span> ###

<span data-ttu-id="ab58e-199">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-199">This section is normative.</span></span>

<span data-ttu-id="ab58e-200">Az a `initial_state_suggestion` objektum, amelynek az értéke egy JSON-tömb, megadja a megadott Hamilton érdeklődésének kezdeti kvantum állapotait.</span><span class="sxs-lookup"><span data-stu-id="ab58e-200">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="ab58e-201">A `initial_state_suggestion` tulajdonság értékének minden elemének egy kvantum-állapotot leíró JSON-objektumnak kell lennie, a szakasz hátralévő részében leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="ab58e-201">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="ab58e-202">A szakasz hátralévő részében az "állam objektum" kifejezés a Broombridge objektum `initial_state_suggestion` tulajdonságának értékében található elemre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="ab58e-202">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="ab58e-203">Állapot objektum</span><span class="sxs-lookup"><span data-stu-id="ab58e-203">State object</span></span> ####

<span data-ttu-id="ab58e-204">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-204">This section is normative.</span></span>

<span data-ttu-id="ab58e-205">Minden állapot-objektumnak rendelkeznie kell egy karakterláncot tartalmazó `label` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="ab58e-205">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="ab58e-206">Minden állapot objektumnak rendelkeznie kell `method` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="ab58e-206">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="ab58e-207">A `method` tulajdonság értékének a 3. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab58e-207">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="ab58e-208">Minden állapot objektum rendelkezhet olyan tulajdonsággal, `energy` amelynek értéke csak egyszerű mennyiség objektum lehet.</span><span class="sxs-lookup"><span data-stu-id="ab58e-208">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="ab58e-209">Ha a `method` tulajdonság értéke `sparse_multi_configurational`, az állapot objektumnak olyan `superposition` tulajdonsággal kell rendelkeznie, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ab58e-209">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="ab58e-210">Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}, $ $, ahol a $ \ket{E} $ rendelkezik Energy $0,987 \textrm{Ha} $ azonosítóval, amelyet a</span><span class="sxs-lookup"><span data-stu-id="ab58e-210">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
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

<span data-ttu-id="ab58e-211">Ha a `method` tulajdonság értéke `unitary_coupled_cluster`, az állapot objektumnak olyan `cluster_operator` tulajdonsággal kell rendelkeznie, amelynek értéke JSON-objektum.</span><span class="sxs-lookup"><span data-stu-id="ab58e-211">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="ab58e-212">A JSON-objektumnak olyan `reference_state` tulajdonsággal kell rendelkeznie, amelynek értéke egy alap állapot.</span><span class="sxs-lookup"><span data-stu-id="ab58e-212">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="ab58e-213">A JSON-objektum rendelkezhet olyan `one_body_amplitudes` tulajdonsággal, amelynek értéke az egytörzsű fürtözött operátorok tömbje és az amplitúdójuk.</span><span class="sxs-lookup"><span data-stu-id="ab58e-213">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="ab58e-214">A JSON-objektum rendelkezhet olyan `two_body_amplitudes` tulajdonsággal, amelynek értéke a kéttörzsű fürtcsomópontok tömbje és az amplitúdójuk.</span><span class="sxs-lookup"><span data-stu-id="ab58e-214">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="ab58e-215">az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ab58e-215">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="ab58e-216">Például a $ $ \ket{\text{Reference}} = (^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="ab58e-216">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="ab58e-217">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="ab58e-217">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="ab58e-218">$ $ T = 0,1 a ^ {\dagger}\_{3, \uparrow}a\_{2, \downarrow} + 0,2 a ^ {\dagger}\_{2, \uparrow}a\_{2, \downarrow}-0,3 a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \downarrow}a\_{3 , a \uparrow}a\_{2, \downarrow} $ $ értéket jelképezi</span><span class="sxs-lookup"><span data-stu-id="ab58e-218">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="ab58e-219">Alapul szolgáló set objektum</span><span class="sxs-lookup"><span data-stu-id="ab58e-219">Basis Set Object</span></span> ####

<span data-ttu-id="ab58e-220">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-220">This section is normative.</span></span>

<span data-ttu-id="ab58e-221">Az egyes problémák leírási objektumai rendelkezhetnek `basis_set` tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="ab58e-221">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="ab58e-222">Ha van, akkor a `basis_set` tulajdonság értékének olyan objektumnak kell lennie, amelynek két tulajdonsága van, `type` és `name`.</span><span class="sxs-lookup"><span data-stu-id="ab58e-222">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="ab58e-223">A `basis_set` tulajdonság értéke alapján azonosított függvényeknek valós értékűnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="ab58e-223">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="ab58e-224">Ennek a specifikációnak a jövőbeli verzióiban a teljes körű függvények valós értékűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="ab58e-224">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="ab58e-225">Táblák és felsorolások</span><span class="sxs-lookup"><span data-stu-id="ab58e-225">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="ab58e-226">1\. táblázat.</span><span class="sxs-lookup"><span data-stu-id="ab58e-226">Table 1.</span></span> <span data-ttu-id="ab58e-227">Engedélyezett fizikai egységek</span><span class="sxs-lookup"><span data-stu-id="ab58e-227">Allowed Physical Units</span></span> ###

<span data-ttu-id="ab58e-228">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-228">This section is normative.</span></span>

<span data-ttu-id="ab58e-229">Az egységet megadó összes sztringnek a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="ab58e-229">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="ab58e-230">Az elemzőknek és a termelőknek egyenértékűnek kell lenniük a következő egyszerű mennyiségi objektumokkal:</span><span class="sxs-lookup"><span data-stu-id="ab58e-230">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="ab58e-231">2\. táblázat</span><span class="sxs-lookup"><span data-stu-id="ab58e-231">Table 2.</span></span> <span data-ttu-id="ab58e-232">Engedélyezett indexelési konvenciók</span><span class="sxs-lookup"><span data-stu-id="ab58e-232">Allowed Index Conventions</span></span> ###

<span data-ttu-id="ab58e-233">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-233">This section is normative.</span></span>

<span data-ttu-id="ab58e-234">A tárgymutató-konvenciót megadó összes karakterláncnak a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="ab58e-234">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="ab58e-235">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-235">This section is informative.</span></span>

<span data-ttu-id="ab58e-236">A specifikáció későbbi verzióiban további indexelési konvenciók is bevezethetők.</span><span class="sxs-lookup"><span data-stu-id="ab58e-236">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="ab58e-237">Az index konvencióinak értelmezése</span><span class="sxs-lookup"><span data-stu-id="ab58e-237">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="ab58e-238">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-238">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="ab58e-239">3\. táblázat.</span><span class="sxs-lookup"><span data-stu-id="ab58e-239">Table 3.</span></span> <span data-ttu-id="ab58e-240">Engedélyezett állapotú metódusok</span><span class="sxs-lookup"><span data-stu-id="ab58e-240">Allowed State methods</span></span> ###

<span data-ttu-id="ab58e-241">Ez a szakasz a normatív.</span><span class="sxs-lookup"><span data-stu-id="ab58e-241">This section is normative.</span></span>

<span data-ttu-id="ab58e-242">Az állapot-metódust megadó összes karakterláncnak a következők egyikének kell lennie:</span><span class="sxs-lookup"><span data-stu-id="ab58e-242">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="ab58e-243">Ez a szakasz tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="ab58e-243">This section is informative.</span></span>

<span data-ttu-id="ab58e-244">További állapot-módszerek is bevezethetők a specifikáció jövőbeli verzióiban.</span><span class="sxs-lookup"><span data-stu-id="ab58e-244">Additional state methods may be introduced in future versions of this specification.</span></span>
