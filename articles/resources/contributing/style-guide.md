---
title: Microsoft Q# stílusú útmutató
description: A programok és könyvtárak elnevezési, bemeneti, dokumentációs és formázási konvencióinak megismerése Q# .
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: cfc201a16b1b42c82314220f77ae120076291759
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231655"
---
# <a name="no-locq-style-guide"></a><span data-ttu-id="1e601-103">Q# Stílus útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="1e601-104">Általános konvenciók</span><span class="sxs-lookup"><span data-stu-id="1e601-104">General Conventions</span></span> ##

<span data-ttu-id="1e601-105">Az útmutatóban javasolt konvenciók célja, hogy megkönnyítse a programok és a kódtárak írását Q# és értelmezését.</span><span class="sxs-lookup"><span data-stu-id="1e601-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="1e601-106">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-106">Guidance</span></span>

<span data-ttu-id="1e601-107">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-107">We suggest:</span></span>

- <span data-ttu-id="1e601-108">Soha ne hagyja figyelmen kívül az egyezményt, hacsak nem ezt szándékosan teszi, hogy könnyebben olvasható és értelmezhető kódot nyújtson a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="1e601-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="1e601-109">Elnevezési konvenciók</span><span class="sxs-lookup"><span data-stu-id="1e601-109">Naming Conventions</span></span> ##

<span data-ttu-id="1e601-110">A Quantum Development Kit szolgáltatásban a függvény-és műveleti nevekre törekszünk, amelyek segítenek a kvantum-fejlesztőknek olyan programok írásához, amelyek könnyen olvashatóak, és a lehető legkevesebb meglepetést okozzák.</span><span class="sxs-lookup"><span data-stu-id="1e601-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="1e601-111">Fontos része annak, hogy ha a függvények, műveletek és típusok neveit választjuk, a programozók a Quantum fogalmak kifejezéséhez használt *szókincset* hoznak létre. a választásunk során segítünk vagy meggátoljuk őket abban, hogy világosan kommunikáljanak.</span><span class="sxs-lookup"><span data-stu-id="1e601-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="1e601-112">Ez felelősséget vállal a számunkra, hogy megbizonyosodjon róla, hogy az általunk bevezetett nevek egyértelműek és nem homályosak.</span><span class="sxs-lookup"><span data-stu-id="1e601-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="1e601-113">Ebben a szakaszban részletesen ismertetjük, hogyan teljesítjük ezt a kötelezettséget olyan explicit útmutatás szempontjából, amely segít a fejlesztő Közösség által nyújtott legjobb megoldásban Q# .</span><span class="sxs-lookup"><span data-stu-id="1e601-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="1e601-114">Műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="1e601-114">Operations and Functions</span></span> ###

<span data-ttu-id="1e601-115">Az egyik első dolog, amit a névnek meg kell állapítania, hogy egy adott szimbólum függvényt vagy műveletet jelöl.</span><span class="sxs-lookup"><span data-stu-id="1e601-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="1e601-116">A függvények és a műveletek közötti különbség elengedhetetlen a kód egy blokkjának megismeréséhez.</span><span class="sxs-lookup"><span data-stu-id="1e601-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="1e601-117">A függvények és a műveletek közötti különbségtételt a felhasználók számára is Q# felhasználjuk.</span><span class="sxs-lookup"><span data-stu-id="1e601-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="1e601-118">*Ez egy művelet végrehajtása* .</span><span class="sxs-lookup"><span data-stu-id="1e601-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="1e601-119">Ezzel szemben a függvények leírják az adatok közötti matematikai kapcsolatokat.</span><span class="sxs-lookup"><span data-stu-id="1e601-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="1e601-120">A kifejezés `Sin(PI() / 2.0)` *az* `1.0` , és nem jelent semmit a program vagy a qubits állapotáról.</span><span class="sxs-lookup"><span data-stu-id="1e601-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="1e601-121">Összefoglalva, a műveletek műveleteket végeznek, miközben a függvények a dolgok.</span><span class="sxs-lookup"><span data-stu-id="1e601-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="1e601-122">Ez a különbségtétel azt sugallja, hogy az Operations és a függvények neve a következő: nevek.</span><span class="sxs-lookup"><span data-stu-id="1e601-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="1e601-123">Felhasználó által definiált típus deklarálása esetén az adott típusú példányokat létrehozó új függvény implicit módon van definiálva egy időben.</span><span class="sxs-lookup"><span data-stu-id="1e601-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="1e601-124">Ebből a szemszögből a felhasználó által definiált típusok neveként kell nevezni, hogy mind a típus, mind a konstruktor függvény konzisztens névvel rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="1e601-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="1e601-125">Ahol ésszerű, győződjön meg arról, hogy a műveleti nevek olyan műveletekkel kezdődnek, amelyek egyértelműen jelzik a művelet által végrehajtott hatást.</span><span class="sxs-lookup"><span data-stu-id="1e601-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="1e601-126">Például:</span><span class="sxs-lookup"><span data-stu-id="1e601-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="1e601-127">Egy eset, amely különleges említést érdemel, ha egy művelet bemenetként egy másik műveletet hajt végre, és meghívja azt.</span><span class="sxs-lookup"><span data-stu-id="1e601-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="1e601-128">Ilyen esetekben a bemeneti művelet által végrehajtott művelet nem egyértelmű, ha a külső művelet definiálva van, úgy, hogy a megfelelő művelet ne legyen azonnal egyértelmű.</span><span class="sxs-lookup"><span data-stu-id="1e601-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="1e601-129">A művelet a, a, a és a esetében ajánlott `Apply` `ApplyIf` `ApplyToEach` `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="1e601-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="1e601-130">Ebben az esetben más igék is hasznosak lehetnek, mint a-ben `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="1e601-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="1e601-131">Művelet</span><span class="sxs-lookup"><span data-stu-id="1e601-131">Verb</span></span> | <span data-ttu-id="1e601-132">Várt hatás</span><span class="sxs-lookup"><span data-stu-id="1e601-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="1e601-133">Alkalmaz</span><span class="sxs-lookup"><span data-stu-id="1e601-133">Apply</span></span> | <span data-ttu-id="1e601-134">A bemenetként megadott műveletet nevezzük</span><span class="sxs-lookup"><span data-stu-id="1e601-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="1e601-135">Assert</span><span class="sxs-lookup"><span data-stu-id="1e601-135">Assert</span></span> | <span data-ttu-id="1e601-136">A lehetséges kvantum-mérés eredményével kapcsolatos hipotézist egy szimulátor ellenőrzi</span><span class="sxs-lookup"><span data-stu-id="1e601-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="1e601-137">Becslés</span><span class="sxs-lookup"><span data-stu-id="1e601-137">Estimate</span></span> | <span data-ttu-id="1e601-138">Egy klasszikus értéket ad vissza, amely egy vagy több mérésből álló becslést jelöl.</span><span class="sxs-lookup"><span data-stu-id="1e601-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="1e601-139">Measure</span><span class="sxs-lookup"><span data-stu-id="1e601-139">Measure</span></span> | <span data-ttu-id="1e601-140">A rendszer elvégzi a kvantum-mérést, és annak eredményét visszaadja a felhasználónak</span><span class="sxs-lookup"><span data-stu-id="1e601-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="1e601-141">Előkészítés</span><span class="sxs-lookup"><span data-stu-id="1e601-141">Prepare</span></span> | <span data-ttu-id="1e601-142">A qubits adott regisztrálása egy adott állapotba van inicializálva</span><span class="sxs-lookup"><span data-stu-id="1e601-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="1e601-143">Sample</span><span class="sxs-lookup"><span data-stu-id="1e601-143">Sample</span></span> | <span data-ttu-id="1e601-144">Egy klasszikus értéket ad vissza véletlenszerűen egy bizonyos eloszlásból</span><span class="sxs-lookup"><span data-stu-id="1e601-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="1e601-145">A függvények esetében javasoljuk, hogy kerülje a műveletek használatát a közös nevek mellett (lásd az alábbi, a földrajzi nevekkel kapcsolatos útmutatót) vagy a mellékneveket:</span><span class="sxs-lookup"><span data-stu-id="1e601-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="1e601-146">Különösen, ha szinte minden esetben azt javasoljuk, hogy a múltbeli táblázatos adatok használatával jelezze, hogy egy függvény neve erősen csatlakozik egy művelethez vagy egy mellékhatáshoz a kvantum-programban másutt.</span><span class="sxs-lookup"><span data-stu-id="1e601-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="1e601-147">Például a  `ControlledOnInt` "vezérlő" művelet "Control" utasításának "a" kifejezés formája, amely azt jelzi, hogy a függvény melléknévként viselkedik az argumentumának módosításához.</span><span class="sxs-lookup"><span data-stu-id="1e601-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="1e601-148">Ennek a névnek a további előnye, hogy összefoglalja a beépített felépítmény szemantikai `Controlled` feltételeit, ahogy azt az alábbiakban tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="1e601-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="1e601-149">Hasonlóképpen, az _ügynökök_ nevei a függvények és a UDT alapján is felhasználhatók a műveleti nevekből, például egy, a szolgáltatáshoz `Encoder` szorosan társított UDT neve esetén `Encode` .</span><span class="sxs-lookup"><span data-stu-id="1e601-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-150">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-151">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-151">We suggest:</span></span>

- <span data-ttu-id="1e601-152">Műveletek neveihez használjon műveleteket.</span><span class="sxs-lookup"><span data-stu-id="1e601-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="1e601-153">Nevek vagy melléknevek használata a függvények neveihez.</span><span class="sxs-lookup"><span data-stu-id="1e601-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="1e601-154">A felhasználó által definiált típusokhoz és attribútumokhoz tartozó nevek használata.</span><span class="sxs-lookup"><span data-stu-id="1e601-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="1e601-155">Az összes hívható név esetében használjon `CamelCase` erős preferenciát a `pascalCase` ,, vagy rendszerre `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="1e601-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="1e601-156">Különösen ügyeljen arra, hogy a hívható nevek nagybetűvel kezdődjön.</span><span class="sxs-lookup"><span data-stu-id="1e601-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="1e601-157">Az összes helyi változó esetében használjon `pascalCase` erős preferenciát a `CamelCase` ,, vagy rendszerre `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="1e601-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="1e601-158">Különösen ügyeljen arra, hogy a helyi változók kisbetűkkel kezdődjön.</span><span class="sxs-lookup"><span data-stu-id="1e601-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="1e601-159">Kerülje az aláhúzások használatát a `_` függvények és a műveletek neveiben; ahol további hierarchiára van szükség, használja a névtereket és a névterek aliasait.</span><span class="sxs-lookup"><span data-stu-id="1e601-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-160">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-160">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="1e601-161">Név</span><span class="sxs-lookup"><span data-stu-id="1e601-161">Name</span></span> | <span data-ttu-id="1e601-162">Leírás</span><span class="sxs-lookup"><span data-stu-id="1e601-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="1e601-163">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="1e601-164">A művelet hatásának jelzéséhez törölje a műveletet ("tükrözze").</span><span class="sxs-lookup"><span data-stu-id="1e601-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="1e601-165">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="1e601-166">A főnévi kifejezés a művelet helyett a függvényt javasolja.</span><span class="sxs-lookup"><span data-stu-id="1e601-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="1e601-167">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="1e601-168">`snake_case`Ellentétes Q# jelölés használata.</span><span class="sxs-lookup"><span data-stu-id="1e601-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="1e601-169">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="1e601-170">A belső és a műveleti név közötti aláhúzások használatának Q# megjelölése.</span><span class="sxs-lookup"><span data-stu-id="1e601-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="1e601-171">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="1e601-172">A főnévi kifejezés használata azt sugallja, hogy a függvény egy műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="1e601-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="1e601-173">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="1e601-174">A főnév ("Fact") egyértelmű használata annak jelzésére, hogy ez egy függvény, míg a melléknév.</span><span class="sxs-lookup"><span data-stu-id="1e601-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="1e601-175">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="1e601-176">Az ige ("Get") használata azt jelzi, hogy ez egy művelet.</span><span class="sxs-lookup"><span data-stu-id="1e601-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="1e601-177">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="1e601-178">A főnévi kifejezés használata egyértelműen a UDT konstruktor hívásának eredményét jelenti.</span><span class="sxs-lookup"><span data-stu-id="1e601-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="1e601-179">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="1e601-180">A ige kifejezés használata azt sugallja, hogy a UDT konstruktora egy művelet.</span><span class="sxs-lookup"><span data-stu-id="1e601-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="1e601-181">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="1e601-182">A főnévi kifejezés használata az attribútum használatát közli.</span><span class="sxs-lookup"><span data-stu-id="1e601-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="entry-points"></a><span data-ttu-id="1e601-183">Belépési pontok</span><span class="sxs-lookup"><span data-stu-id="1e601-183">Entry Points</span></span>

<span data-ttu-id="1e601-184">Egy belépési pont programba való definiálásakor Q# a Q# fordító felismeri az [ `@EntryPoint()` attribútumot](xref:Microsoft.Quantum.Core.EntryPoint) , ami azt igényli, hogy a belépési pontok egy adott névvel rendelkezzenek (például: `main` , `Main` , vagy `__main__` ).</span><span class="sxs-lookup"><span data-stu-id="1e601-184">When defining an entry point into a Q# program, the Q# compiler recognizes the [`@EntryPoint()` attribute](xref:Microsoft.Quantum.Core.EntryPoint) rather requiring that entry points have a particular name (e.g.: `main`, `Main`, or `__main__`).</span></span>
<span data-ttu-id="1e601-185">Ez a fejlesztő szemszögéből a Q# beléptetési pontok a következőhöz fűzött általános műveletek: `@EntryPoint()` .</span><span class="sxs-lookup"><span data-stu-id="1e601-185">That is, from the perspective of a Q# developer, entry points are ordinary operations annotated with `@EntryPoint()`.</span></span>
<span data-ttu-id="1e601-186">Emellett a Q# belépési pontok egy teljes alkalmazáshoz (például Q# önálló végrehajtható programokban), vagy a Q# program és az alkalmazáshoz tartozó gazda program (azaz a Python vagy a .NET használatával) közötti kapcsolat lehet Q# , ha a "Main" név félrevezető lehet, ha egy Q# belépési pontra alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="1e601-186">Moreover, Q# entry points may be entry points for an entire application (for example, in Q# standalone executable programs), or may be an interface between a Q# program and the host program for an application (i.e.: when using Q# with Python or .NET), such that the name "main" could be misleading when applied to a Q# entry point.</span></span>

<span data-ttu-id="1e601-187">Javasoljuk, hogy az elnevezési belépési pontok használatával tükrözze az `@EntryPoint()` attribútum használatát a fent felsorolt elnevezési műveletek általános tanácsainak használatával.</span><span class="sxs-lookup"><span data-stu-id="1e601-187">We suggest using naming entry points to reflect the use of the `@EntryPoint()` attribute by using the general advice for naming operations listed above.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="1e601-188">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-188">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-189">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-189">We suggest:</span></span>

- <span data-ttu-id="1e601-190">Ne nevezze a belépési pont műveleteit "Main"-ként.</span><span class="sxs-lookup"><span data-stu-id="1e601-190">Do not name entry point operations as "main."</span></span>
- <span data-ttu-id="1e601-191">A név belépési pont műveletei szokásos műveletként.</span><span class="sxs-lookup"><span data-stu-id="1e601-191">Name entry point operations as ordinary operations.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-192">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-192">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="1e601-193">Név</span><span class="sxs-lookup"><span data-stu-id="1e601-193">Name</span></span> | <span data-ttu-id="1e601-194">Leírás</span><span class="sxs-lookup"><span data-stu-id="1e601-194">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="1e601-195">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-195">☑</span></span> | `@EntryPoint() operation RunSimulation` | <span data-ttu-id="1e601-196">A művelet neve a belépési pont célját egyértelműen közli.</span><span class="sxs-lookup"><span data-stu-id="1e601-196">Clearly communicates purpose of entry point through operation name.</span></span> |
| <span data-ttu-id="1e601-197">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-197">☒</span></span> | <s>`@EntryPoint() operation Main`</s> | <span data-ttu-id="1e601-198">A használata `Main` nem jelent egyértelmű kommunikációt a belépési pont céljával, és redundáns az `@EntryPoint()` attribútummal.</span><span class="sxs-lookup"><span data-stu-id="1e601-198">Use of `Main` doesn't clearly communicate purpose of entry point, and is redundant with `@EntryPoint()` attribute.</span></span> |

<span data-ttu-id="1e601-199">\*\*_</span><span class="sxs-lookup"><span data-stu-id="1e601-199">\*\*_</span></span>

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="1e601-200">Rövidítések és rövidítések</span><span class="sxs-lookup"><span data-stu-id="1e601-200">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="1e601-201">A fenti tanácsokban a Gyorsírás számos formája létezik, amely a kvantum-számítástechnika általános és átható használatát látja el.</span><span class="sxs-lookup"><span data-stu-id="1e601-201">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="1e601-202">Javasoljuk, hogy meglévő és közös gyorsírást használjon, ahol létezik, különösen olyan műveletek esetén, amelyek a célszámítógép működéséhez tartoznak.</span><span class="sxs-lookup"><span data-stu-id="1e601-202">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="1e601-203">Például a helyett a nevet választjuk `X` `ApplyX` `Rz` `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="1e601-203">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="1e601-204">Ilyen rövidítés használatakor a művelet neve csak nagybetűs lehet (például: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="1e601-204">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="1e601-205">Erre az egyezményre akkor van szükség, ha gyakran használt betűszók és nagybetűk, például "QFT" a "Quantum Fourier átalakítás" kifejezésre alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="1e601-205">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="1e601-206">Javasoljuk, hogy az általános .NET-konvenciókat a betűszók és a nagyszótárak teljes névben való használatára ajánljuk, amely az alábbiakat írja elő:</span><span class="sxs-lookup"><span data-stu-id="1e601-206">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="1e601-207">a kétbetűs betűszók és a nagyvállalatok neve nagybetűs (például: `BE` "big-endian"),</span><span class="sxs-lookup"><span data-stu-id="1e601-207">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="1e601-208">az összes további betűszó és a nagybetűk neve `CamelCase` (például: `Qft` "Quantum Fourier Transform")</span><span class="sxs-lookup"><span data-stu-id="1e601-208">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="1e601-209">Így a QFT megvalósító művelet lehet `QFT` rövidített vagy kiírva `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="1e601-209">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="1e601-210">A gyakran használt műveletek és függvények esetében érdemes lehet egy rövidített nevet megadni egy hosszú űrlap _aliasként_ való megadásához:</span><span class="sxs-lookup"><span data-stu-id="1e601-210">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="1e601-211">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-211">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-212">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-212">We suggest:</span></span>

- <span data-ttu-id="1e601-213">Ha szükséges, tekintse meg a gyakran elfogadott és széles körben használt rövidített neveket.</span><span class="sxs-lookup"><span data-stu-id="1e601-213">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="1e601-214">Kis-és nagybetűk használata a gyorsíráshoz.</span><span class="sxs-lookup"><span data-stu-id="1e601-214">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="1e601-215">Rövid (kétbetűs) betűszók és nagybetűk használata.</span><span class="sxs-lookup"><span data-stu-id="1e601-215">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="1e601-216">`CamelCase`Hosszabb (három vagy több betűs) rövidítéssel és nagybetűkkel is használható.</span><span class="sxs-lookup"><span data-stu-id="1e601-216">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-217">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-217">Examples</span></span>](#tab/examples)

| &nbsp;   | <span data-ttu-id="1e601-218">Név</span><span class="sxs-lookup"><span data-stu-id="1e601-218">Name</span></span> | <span data-ttu-id="1e601-219">Leírás</span><span class="sxs-lookup"><span data-stu-id="1e601-219">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="1e601-220">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-220">☑</span></span> | `X` | <span data-ttu-id="1e601-221">Jól ismert Gyorsírás a "$X $ átalakítás alkalmazása"</span><span class="sxs-lookup"><span data-stu-id="1e601-221">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="1e601-222">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-222">☑</span></span> | `CNOT` | <span data-ttu-id="1e601-223">Jól értelmezhető Gyorsírás a "vezérelt – nem"</span><span class="sxs-lookup"><span data-stu-id="1e601-223">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="1e601-224">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-224">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="1e601-225">A Gyorsírás nem lehet a-ben `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="1e601-225">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="1e601-226">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-226">☑</span></span> | `ApplyQft` | <span data-ttu-id="1e601-227">A "QFT" általános inicializálás a hosszú formátumú név részeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1e601-227">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="1e601-228">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-228">☑</span></span> | `QFT` | <span data-ttu-id="1e601-229">A "QFT" általános inicializálás egy rövidített név részeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1e601-229">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



_*_


### <a name="proper-nouns-in-names"></a><span data-ttu-id="1e601-230">Megfelelő nevek a névben</span><span class="sxs-lookup"><span data-stu-id="1e601-230">Proper Nouns in Names</span></span> ###

<span data-ttu-id="1e601-231">A fizikában gyakran előfordul, hogy az első személynek a róluk való közzétételét követően a legtöbb nem fizikus nem ismeri a mindenki nevét és az előzményeket.</span><span class="sxs-lookup"><span data-stu-id="1e601-231">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="1e601-232">A fizika elnevezési konvenciói alapján túl nagy mértékben támaszkodhat a beléptetésre, mivel a más hátterű felhasználóknak nagy mennyiségű látszólag átlátszatlan nevet kell megtanulniuk ahhoz, hogy közös műveleteket és fogalmakat lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="1e601-232">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="1e601-233">Ezért azt javasoljuk, hogy ha ésszerű, a fogalmakat leíró általános nevek erős előnyben legyenek kitéve a fogalmak közzétételének előzményeit leíró földrajzi nevek iránt.</span><span class="sxs-lookup"><span data-stu-id="1e601-233">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="1e601-234">Ebben az esetben a nem megfelelően vezérelt SWAP-és kettős vezérlésű, nem műveleti műveleteket gyakran a tudományos irodalomban található "Fredkin" és "Toffoli" műveletnek nevezzük, de a rendszer elsősorban a és a esetében azonosítja őket Q# `CSWAP` `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="1e601-234">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="1e601-235">Az API-dokumentációs megjegyzések mindkét esetben a megfelelő neveken alapuló szinonimákat biztosítanak az összes megfelelő hivatkozással együtt.</span><span class="sxs-lookup"><span data-stu-id="1e601-235">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="1e601-236">Ez a beállítás különösen fontos, hogy a megfelelő főnevek bizonyos használata mindig kötelező legyen – Q# a számos klasszikus nyelv által meghatározott hagyományt követi, és a `Bool` típusokat a logikai logikára mutató hivatkozásokra utal, amely George Boole tiszteletben tartásával lett elnevezve.</span><span class="sxs-lookup"><span data-stu-id="1e601-236">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="1e601-237">Ehhez hasonló módon kell elnevezni néhány kvantum-fogalmat, például a `Pauli` nyelvhez beépített típust Q# .</span><span class="sxs-lookup"><span data-stu-id="1e601-237">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="1e601-238">A megfelelő főnevek használatának minimalizálása, ha az ilyen használat nem alapvető fontosságú, csökkentik annak a hatását, hogy a megfelelő földrajzi nevek ne legyenek ésszerűen elkerülhetők.</span><span class="sxs-lookup"><span data-stu-id="1e601-238">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-239">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-239">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="1e601-240">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-240">We suggest:</span></span>

- <span data-ttu-id="1e601-241">Kerülje a nevekben a megfelelő nevek használatát.</span><span class="sxs-lookup"><span data-stu-id="1e601-241">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-242">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-242">Examples</span></span>](#tab/examples)

_*_

### <a name="type-conversions"></a><span data-ttu-id="1e601-243">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="1e601-243">Type Conversions</span></span> ###

<span data-ttu-id="1e601-244">Mivel a Q# egy erősen és statikusan beírt nyelv, az egyik típus értéke csak más típusú érték lehet, mint egy típus-átalakítási függvény kifejezett hívása.</span><span class="sxs-lookup"><span data-stu-id="1e601-244">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="1e601-245">Ez ellentétben áll azokkal a nyelvekkel, amelyek lehetővé teszik, hogy az értékek implicit módon módosítsák a típusokat (pl.: Type Promotion) vagy a casting használatával.</span><span class="sxs-lookup"><span data-stu-id="1e601-245">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="1e601-246">Ennek eredményeképpen a konvertálási függvények fontos szerepet játszanak a Q# kódtár fejlesztésében, és az elnevezéssel kapcsolatban leggyakrabban felmerülő döntések egyikét alkotják.</span><span class="sxs-lookup"><span data-stu-id="1e601-246">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="1e601-247">Azonban ez azt jelzi, hogy mivel a Type konverziók mindig _determinisztikus_, a függvények is megírhatók, ezért a fenti tanács alá tartoznak.</span><span class="sxs-lookup"><span data-stu-id="1e601-247">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="1e601-248">Különösen azt javasoljuk, hogy a Type konverziós függvények soha ne legyenek elnevezve műveleteknek (pl.: `ConvertToX` ) vagy a határozószók előírási kifejezéseknek ( `ToX` ), hanem a forrás és a cél típusokat () jelző, melléknévi előírási kifejezéseknek kell nevezni `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="1e601-248">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="1e601-249">Ha a tömb típusait a konverziós függvények neveiben listázza, javasoljuk a gyorsírást `Arr` .</span><span class="sxs-lookup"><span data-stu-id="1e601-249">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="1e601-250">A kivételes körülmények korlátozásával azt javasoljuk, hogy az összes Type konverziós függvény neve legyen, hogy `As` gyorsan azonosítható legyen.</span><span class="sxs-lookup"><span data-stu-id="1e601-250">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-251">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-251">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-252">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-252">We suggest:</span></span>

- <span data-ttu-id="1e601-253">Ha egy függvény Type típusú értéket alakít át `X` `Y` , használja a nevet vagy a értéket `AsY` `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="1e601-253">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-254">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-254">Examples</span></span>](#tab/examples)

| &nbsp;   | <span data-ttu-id="1e601-255">Név</span><span class="sxs-lookup"><span data-stu-id="1e601-255">Name</span></span> | <span data-ttu-id="1e601-256">Leírás</span><span class="sxs-lookup"><span data-stu-id="1e601-256">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="1e601-257">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-257">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="1e601-258">A "to" utasítás a művelethez tartozó kifejezést eredményez, és nem függvényt jelez.</span><span class="sxs-lookup"><span data-stu-id="1e601-258">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="1e601-259">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-259">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="1e601-260">A bemeneti típus nem egyértelmű a függvény nevéből.</span><span class="sxs-lookup"><span data-stu-id="1e601-260">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="1e601-261">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-261">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="1e601-262">A bemeneti és a kimeneti típusok nem megfelelő sorrendben jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="1e601-262">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="1e601-263">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-263">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="1e601-264">A bemeneti típusok és a kimeneti típusok egyaránt törlődnek.</span><span class="sxs-lookup"><span data-stu-id="1e601-264">Both the input types and output types are clear.</span></span> |

_*_

### <a name="private-or-internal-names"></a><span data-ttu-id="1e601-265">Magán-vagy belső nevek</span><span class="sxs-lookup"><span data-stu-id="1e601-265">Private or Internal Names</span></span> ###

<span data-ttu-id="1e601-266">Sok esetben a név kifejezetten a belső könyvtárakhoz vagy projektekhez való használatra szolgál, és nem a könyvtár által kínált API garantált részét képezi.</span><span class="sxs-lookup"><span data-stu-id="1e601-266">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="1e601-267">Hasznos lehet egyértelműen jelezni, hogy ez a helyzet az elnevezési függvények és műveletek esetében, hogy a csak belső kódok véletlen függőségei legyenek egyértelműek.</span><span class="sxs-lookup"><span data-stu-id="1e601-267">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="1e601-268">Ha egy művelet vagy függvény nem közvetlen használatra készült, hanem egy, a részleges alkalmazás által elvégezhető egyező meghívót kell használni, érdemes lehet egy olyan nevet használni, amely a `internal` részben alkalmazott hívható kulcsszóval kezdődik.</span><span class="sxs-lookup"><span data-stu-id="1e601-268">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with the `internal` keyword for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-269">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-269">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-270">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-270">We suggest:</span></span>

- <span data-ttu-id="1e601-271">Ha egy függvény, művelet vagy felhasználó által definiált típus nem része a nyilvános API-nak egy Q# könyvtár vagy program számára, győződjön meg arról, hogy belső jelöléssel van megjelölve, ha a `internal` , vagy a deklaráció előtt elhelyezi a kulcsszót `function` `operation` `newtype` .</span><span class="sxs-lookup"><span data-stu-id="1e601-271">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that it is marked as internal by placing the `internal` keyword before the `function`, `operation`, or `newtype` declaration.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-272">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-272">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="1e601-273">Név</span><span class="sxs-lookup"><span data-stu-id="1e601-273">Name</span></span> | <span data-ttu-id="1e601-274">Leírás</span><span class="sxs-lookup"><span data-stu-id="1e601-274">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="1e601-275">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-275">☒</span></span> | <s>`operation _ApplyDecomposedOperation`</s> | <span data-ttu-id="1e601-276">Ne használjon aláhúzást `_` annak jelzésére, hogy a művelet csak belső használatra szolgál.</span><span class="sxs-lookup"><span data-stu-id="1e601-276">Do not use an underscore `_` to indicate that this operation is for internal use only.</span></span> |
| <span data-ttu-id="1e601-277">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-277">☑</span></span> | `internal operation ApplyDecomposedOperation` | <span data-ttu-id="1e601-278">Az `internal` elején lévő kulcsszó egyértelműen azt jelzi, hogy ez a művelet csak belső használatra szolgál.</span><span class="sxs-lookup"><span data-stu-id="1e601-278">The `internal` keyword at the beginning clearly indicates that this operation is for internal use only.</span></span> |

_*_
### <a name="variants"></a><span data-ttu-id="1e601-279">Változatok</span><span class="sxs-lookup"><span data-stu-id="1e601-279">Variants</span></span> ###

<span data-ttu-id="1e601-280">Bár ez a korlátozás nem szűnik meg a későbbi verzióiban Q# , jelenleg a kapcsolódó műveletek vagy függvények olyan csoportjai lesznek, amelyek megkülönböztetni a bemenetek támogatását, illetve az argumentumok konkrét típusait.</span><span class="sxs-lookup"><span data-stu-id="1e601-280">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="1e601-281">Ezek a csoportok megkülönböztetni ugyanazt a legfelső szintű nevet, majd egy vagy két betűt, amelyek jelzik a változatát.</span><span class="sxs-lookup"><span data-stu-id="1e601-281">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="1e601-282">Utótag</span><span class="sxs-lookup"><span data-stu-id="1e601-282">Suffix</span></span> | <span data-ttu-id="1e601-283">Értelmezés</span><span class="sxs-lookup"><span data-stu-id="1e601-283">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="1e601-284">Várhatóan támogatott bemenet `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="1e601-284">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="1e601-285">Várhatóan támogatott bemenet `Controlled`</span><span class="sxs-lookup"><span data-stu-id="1e601-285">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="1e601-286">A várt támogatás `Controlled` és `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="1e601-286">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="1e601-287">Bemenet vagy bemenet típusa `Int`</span><span class="sxs-lookup"><span data-stu-id="1e601-287">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="1e601-288">Bemenet vagy bemenet típusa `Double`</span><span class="sxs-lookup"><span data-stu-id="1e601-288">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="1e601-289">Bemenet vagy bemenet típusa `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1e601-289">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="1e601-290">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-290">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-291">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-291">We suggest:</span></span>

- <span data-ttu-id="1e601-292">Ha egy függvény vagy művelet nem kapcsolódik hasonló funkciókhoz vagy műveletekhez a bemenetek típusai és a nem megfelelő működésének támogatásával, ne használjon utótagot.</span><span class="sxs-lookup"><span data-stu-id="1e601-292">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="1e601-293">Ha egy függvény vagy művelet bármely hasonló függvényhez vagy művelethez kapcsolódik, és a bemenetek típusai és az azokon lévők is támogatják, a változatok megkülönböztetéséhez használja a fenti táblázatban szereplő utótagokat.</span><span class="sxs-lookup"><span data-stu-id="1e601-293">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-294">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-294">Examples</span></span>](#tab/examples)

_*_

### <a name="arguments-and-variables"></a><span data-ttu-id="1e601-295">Argumentumok és változók</span><span class="sxs-lookup"><span data-stu-id="1e601-295">Arguments and Variables</span></span> ###

<span data-ttu-id="1e601-296">Egy Q# függvény vagy művelet kódjának kulcsfontosságú célja, hogy könnyen olvasható és értelmezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="1e601-296">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="1e601-297">Hasonlóképpen, a bemenetek és a Type argumentumok neveinek kell megadniuk, hogy a rendszer hogyan használja a függvényt vagy az argumentumot.</span><span class="sxs-lookup"><span data-stu-id="1e601-297">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="1e601-298">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-298">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-299">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-299">We suggest:</span></span>

- <span data-ttu-id="1e601-300">Az összes változó és bemeneti név esetében használjon `pascalCase` erős preferenciát a `CamelCase` ,, vagy rendszerhez `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="1e601-300">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="1e601-301">A bemeneti névnek leírónak kell lennie. lehetőleg ne adjon meg egy vagy két betűt.</span><span class="sxs-lookup"><span data-stu-id="1e601-301">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="1e601-302">A pontosan egy típusú argumentumot elfogadó műveletek és függvények a Type argumentumot jelölik, `T` Ha a szerepköre nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="1e601-302">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="1e601-303">Ha egy függvény vagy művelet több típusú argumentumot is igénybe vesz, vagy ha egy adott típusú argumentum szerepköre nem egyértelmű, érdemes lehet egy rövid, tőkésített szót `T` (például:) használni `TOutput` az egyes típusokhoz.</span><span class="sxs-lookup"><span data-stu-id="1e601-303">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="1e601-304">Az argumentumban és a változók neveiben ne szerepeljenek a nevek. ezt az információt a fejlesztési környezetnek is meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="1e601-304">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="1e601-305">Skaláris típusokat jelöl a literális nevük ( `flagQubit` ) és a tömb típusa szerint egy többes szám ( `measResults` ) alapján.</span><span class="sxs-lookup"><span data-stu-id="1e601-305">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="1e601-306">A qubits-tömbök esetében érdemes lehet olyan típusokat megjelölni, `Register` amelyek alapján a név olyan qubits-sorozatra hivatkozik, amely valamilyen módon szorosan összefügg egymással.</span><span class="sxs-lookup"><span data-stu-id="1e601-306">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="1e601-307">A tömbökbe indexként használt változóknak a (z) értékkel kell kezdődnie, `idx` és csak néhány lehet (például: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="1e601-307">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="1e601-308">Különösen érdemes elkerülni az egybetűs változók nevének indexként való használatát. ajánlott legalább a használata `idx` .</span><span class="sxs-lookup"><span data-stu-id="1e601-308">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="1e601-309">A tömbök hosszának megtartására használt változóknak a (z) értékkel kell kezdődnie, `n` és a (z) számnak kell lennie (például: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="1e601-309">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-310">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-310">Examples</span></span>](#tab/examples)

_*_

### <a name="user-defined-type-named-items"></a><span data-ttu-id="1e601-311">User-Defined megnevezett elemek típusa</span><span class="sxs-lookup"><span data-stu-id="1e601-311">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="1e601-312">A felhasználó által definiált típusokban megnevezett elemek neveként kell nevezni `CamelCase` , még a UDT konstruktorok számára is.</span><span class="sxs-lookup"><span data-stu-id="1e601-312">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="1e601-313">Ez segít az elnevezett elemek egyértelmű elkülönítésében a helyileg hatókörön belüli változókra mutató hivatkozásokkal a hozzáférési jelölés (például: `callable::Apply` ) vagy a másolási és frissítési jelölés ( `set arr w/= Data <- newData` ) használatakor.</span><span class="sxs-lookup"><span data-stu-id="1e601-313">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-314">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-314">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-315">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-315">We suggest:</span></span>

- <span data-ttu-id="1e601-316">A UDT konstruktorokban megnevezett elemek neveként kell nevezni, `CamelCase` azaz kezdeti nagybetűvel kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="1e601-316">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="1e601-317">A műveletekhez feloldani megnevezett elemek művelet fázisként kell nevezni.</span><span class="sxs-lookup"><span data-stu-id="1e601-317">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="1e601-318">A műveleteknek nem feloldható megnevezett elemeknek főnévi kifejezéseknek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="1e601-318">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="1e601-319">A műveleteket UDT egyetlen elnevezett elemnek kell `Apply` definiálni.</span><span class="sxs-lookup"><span data-stu-id="1e601-319">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-320">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-320">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="1e601-321">Snippet</span><span class="sxs-lookup"><span data-stu-id="1e601-321">Snippet</span></span> | <span data-ttu-id="1e601-322">Description</span><span class="sxs-lookup"><span data-stu-id="1e601-322">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="1e601-323">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-323">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="1e601-324">A név `Apply` egy `CamelCase` formázott igei kifejezés, amely arra utal, hogy az elnevezett elem egy művelet.</span><span class="sxs-lookup"><span data-stu-id="1e601-324">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="1e601-325">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-325">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="1e601-326">Az elnevezett elemeknek kezdeti nagybetűvel kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="1e601-326">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="1e601-327">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-327">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="1e601-328">A függvények feloldására szolgáló névvel ellátott elemeknek főnévi kifejezéseknek kell lenniük, nem pedig ige kifejezéseknek.</span><span class="sxs-lookup"><span data-stu-id="1e601-328">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

_*_

## <a name="input-conventions"></a><span data-ttu-id="1e601-329">Bemeneti konvenciók</span><span class="sxs-lookup"><span data-stu-id="1e601-329">Input Conventions</span></span> ##

<span data-ttu-id="1e601-330">Amikor egy fejlesztő meghívja a műveletet vagy a függvényt, az adott művelethez vagy függvényhez tartozó különböző bemeneteket egy adott sorrendben kell megadnia, ami növeli a fejlesztők által felhasználható kognitív terhelést, hogy használhassa a kódtárat.</span><span class="sxs-lookup"><span data-stu-id="1e601-330">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="1e601-331">A bemeneti sorrendek megemlékezésének feladata különösen az, ha a feladatból gyakran elkerülnek a következők: egy kvantum-algoritmus megvalósításának programozása.</span><span class="sxs-lookup"><span data-stu-id="1e601-331">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="1e601-332">Bár a gazdag IDE-támogatás nagy mértékben csökkentheti ezt a megoldást, a jó tervezés és a közös konvenciók betartása is segítheti az API-k által kiszabott kognitív terhelés minimalizálását.</span><span class="sxs-lookup"><span data-stu-id="1e601-332">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="1e601-333">Ahol lehetséges, hasznos lehet csökkenteni a művelet vagy a függvény által várt bemenetek számát, így az egyes bemenetek szerepe azonnal nyilvánvalóvá válik az adott művelethez vagy függvényhez tartozó fejlesztők számára, valamint a programkódot később olvasó fejlesztők számára.</span><span class="sxs-lookup"><span data-stu-id="1e601-333">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="1e601-334">Különösen, ha nem lehetséges vagy ésszerű az argumentumok számának csökkentése egy művelet vagy függvény számára, fontos, hogy konzisztens megrendelés álljon rendelkezésre, amely minimalizálja azt a meglepetést, amelyet a felhasználó a bemenetek sorrendjének előrejelzése során szembesül.</span><span class="sxs-lookup"><span data-stu-id="1e601-334">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="1e601-335">Javasoljuk, hogy olyan bemeneti rendezési konvenciókat ajánlunk, amelyek nagyrészt az f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="1e601-335">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="1e601-336">Ezért az első argumentumok részleges alkalmazása olyan meghívót eredményezhet, amely a saját jogon hasznos, ha ésszerű.</span><span class="sxs-lookup"><span data-stu-id="1e601-336">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="1e601-337">Ezt az elvet követve érdemes lehet a következő argumentumokat használni:</span><span class="sxs-lookup"><span data-stu-id="1e601-337">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="1e601-338">Klasszikus, nem hívható argumentumok, például szögek, hatáskörök vektorai stb.</span><span class="sxs-lookup"><span data-stu-id="1e601-338">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="1e601-339">Hívható argumentumok (függvények és argumentumok).</span><span class="sxs-lookup"><span data-stu-id="1e601-339">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="1e601-340">Ha a functions és a Operations is argumentumként van megadva, érdemes lehet műveleteket végrehajtani a függvények után.</span><span class="sxs-lookup"><span data-stu-id="1e601-340">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="1e601-341">A gyűjtemények a,, és rendszerhez hasonló módon, meghívásos argumentumok alapján jártak el `Map` `Iter` `Enumerate` `Fold` .</span><span class="sxs-lookup"><span data-stu-id="1e601-341">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="1e601-342">A vezérlőkként használt Qubit argumentumok.</span><span class="sxs-lookup"><span data-stu-id="1e601-342">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="1e601-343">Qubit használt argumentumok.</span><span class="sxs-lookup"><span data-stu-id="1e601-343">Qubit arguments used as targets.</span></span>

<span data-ttu-id="1e601-344">Vegye fontolóra egy olyan művelet használatát, amellyel a `ApplyPhaseEstimationIteration` fázis becslése egy szöget és egy Oracle-t vesz igénybe, és a szöget átadja a `Rz` különböző skálázási tényezők tömbje által módosítottnak, majd az Oracle alkalmazásait vezérli.</span><span class="sxs-lookup"><span data-stu-id="1e601-344">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="1e601-345">A bemeneteket a következő módon kell megrendelni `ApplyPhaseEstimationIteration` :</span><span class="sxs-lookup"><span data-stu-id="1e601-345">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="1e601-346">A kis-és nagybetűk minimálisra csökkentése érdekében egyes függvények és műveletek a beépített és a rendszer működését utánozzák `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="1e601-346">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="1e601-347">`ControlledOnInt<'T>` `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` Ilyen például a típus, amely a következőhöz hasonló módon viselkedik:, `ControlledOnInt<Qubit[]>(5, _)` `Controlled` de abban a feltétellel, hogy a vezérlő regisztrálása a $ \ket {5} = \ket $ állapotot jelöli {101} .</span><span class="sxs-lookup"><span data-stu-id="1e601-347">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="1e601-348">Így a fejlesztő azt várja, hogy a `ControlledOnInt` meghívót a legutóbb átalakított értékre helyezze át, és hogy az eredményül kapott művelet a bemeneti---ugyanolyan sorrendben legyen, mint az ellátottak `(Qubit[], 'T)` kimenete `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="1e601-348">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-349">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-349">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-350">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-350">We suggest:</span></span>

- <span data-ttu-id="1e601-351">A részleges alkalmazás használatával összhangban lévő bemeneti sorrendek használata.</span><span class="sxs-lookup"><span data-stu-id="1e601-351">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="1e601-352">Beépített feladatokkal konzisztens bemeneti sorrendek használata.</span><span class="sxs-lookup"><span data-stu-id="1e601-352">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="1e601-353">Helyezzen minden klasszikus bemenetet a kvantum-bevitel előtt.</span><span class="sxs-lookup"><span data-stu-id="1e601-353">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-354">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-354">Examples</span></span>](#tab/examples)

_*_

## <a name="documentation-conventions"></a><span data-ttu-id="1e601-355">Dokumentációs konvenciók</span><span class="sxs-lookup"><span data-stu-id="1e601-355">Documentation Conventions</span></span> ##

<span data-ttu-id="1e601-356">A Q# nyelv lehetővé teszi a dokumentáció csatolását a műveletekhez, a függvényekhez és a felhasználó által definiált típusokhoz a speciálisan formázott dokumentációs megjegyzések használatával.</span><span class="sxs-lookup"><span data-stu-id="1e601-356">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="1e601-357">A Triple-ferde ( `///` ) függvényekkel ezek a dokumentációs megjegyzések kisméretű, [DocFX Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) dokumentumok, amelyek az egyes műveletek, függvények és felhasználó által definiált típusok, valamint a várt bemeneti adatok céljának leírására használhatók.</span><span class="sxs-lookup"><span data-stu-id="1e601-357">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="1e601-358">A Quantum Development Kit által biztosított fordító kibontja ezeket a megjegyzéseket, és a segítségével a következőhöz hasonló dokumentációt videótartalmakban https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="1e601-358">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="1e601-359">Hasonlóképpen, a Quantum Development Kit által biztosított nyelvi kiszolgáló ezeket a megjegyzéseket használja, hogy segítséget nyújtson a felhasználóknak a kódban lévő szimbólumok fölé helyezve Q# .</span><span class="sxs-lookup"><span data-stu-id="1e601-359">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="1e601-360">A dokumentációs megjegyzések használata így segítheti a felhasználókat a kód értelmezésében azáltal, hogy a jelen dokumentum többi konvenciója alapján nem könnyen elérhetővé tett részletekre vonatkozó hasznos hivatkozást biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="1e601-360">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="1e601-361">[Dokumentációs Megjegyzés szintaxisának leírása](xref:microsoft.quantum.qsharp.comments#documentation-comments).</span><span class="sxs-lookup"><span data-stu-id="1e601-361">[Documentation comment syntax reference](xref:microsoft.quantum.qsharp.comments#documentation-comments).</span></span>

<span data-ttu-id="1e601-362">Ahhoz, hogy hatékonyan használhassa ezt a funkciót a felhasználók számára, javasoljuk, hogy a dokumentációs megjegyzések írásakor ne feledje el néhány dolgot.</span><span class="sxs-lookup"><span data-stu-id="1e601-362">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-363">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-363">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="1e601-364">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-364">We suggest:</span></span>

- <span data-ttu-id="1e601-365">Minden nyilvános funkciót, műveletet és felhasználó által definiált típust közvetlenül a dokumentációs Megjegyzés előtt kell megadni.</span><span class="sxs-lookup"><span data-stu-id="1e601-365">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="1e601-366">Az egyes dokumentációs megjegyzéseknek legalább a következő részeket kell tartalmazniuk:</span><span class="sxs-lookup"><span data-stu-id="1e601-366">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="1e601-367">Összefoglalás</span><span class="sxs-lookup"><span data-stu-id="1e601-367">Summary</span></span>
    - <span data-ttu-id="1e601-368">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1e601-368">Input</span></span>
    - <span data-ttu-id="1e601-369">Kimenet (ha van ilyen)</span><span class="sxs-lookup"><span data-stu-id="1e601-369">Output (if applicable)</span></span>
- <span data-ttu-id="1e601-370">Győződjön meg arról, hogy minden összefoglaló két mondat vagy kevesebb.</span><span class="sxs-lookup"><span data-stu-id="1e601-370">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="1e601-371">Ha további helyiségre van szükség, adjon meg egy szakaszt, amely `# Description` azonnal követi a `# Summary` teljes részleteket.</span><span class="sxs-lookup"><span data-stu-id="1e601-371">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="1e601-372">Ahol ésszerű, ne szerepeljenek a matematika az összefoglalókban, mivel nem minden ügyfél támogatja a TeX-jelöléseket az összefoglalók között.</span><span class="sxs-lookup"><span data-stu-id="1e601-372">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="1e601-373">Vegye figyelembe, hogy a prózai dokumentumok (például a TeX vagy a Markdown) írásakor érdemes lehet hosszabb vonali hosszúságot használni.</span><span class="sxs-lookup"><span data-stu-id="1e601-373">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="1e601-374">Adja meg az összes releváns matematikai kifejezést a `# Description` szakaszban.</span><span class="sxs-lookup"><span data-stu-id="1e601-374">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="1e601-375">A bemenetek leírásakor ne ismételje meg az egyes bemenetek típusait, mivel ezek a fordító számára következtetni tudnak, és az inkonzisztencia bevezetését kockáztatják.</span><span class="sxs-lookup"><span data-stu-id="1e601-375">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="1e601-376">Szükség szerint adjon meg példákat a saját `# Example` szakaszában.</span><span class="sxs-lookup"><span data-stu-id="1e601-376">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="1e601-377">A kód listázása előtt röviden ismertesse az egyes példákat.</span><span class="sxs-lookup"><span data-stu-id="1e601-377">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="1e601-378">Sorolja fel az összes releváns tanulmányi kiadványt (például: dokumentumok, eljárások, blogbejegyzések és alternatív implementációk) a `# References` szakaszokban a hivatkozások felsorolásával.</span><span class="sxs-lookup"><span data-stu-id="1e601-378">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="1e601-379">Győződjön meg arról, hogy ha lehetséges, az összes hivatkozási hivatkozás állandó és megváltoztathatatlan azonosítók (DOIs vagy verziószámmal ellátott arXiv-számok).</span><span class="sxs-lookup"><span data-stu-id="1e601-379">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="1e601-380">Ha egy művelet vagy függvény más műveletekhez vagy függvényekhez kapcsolódik, és az esetlegesen előforduló változatok is szerepelnek, a szakaszokban listajelként sorolja fel a többi változatot `# See Also` .</span><span class="sxs-lookup"><span data-stu-id="1e601-380">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="1e601-381">Hagyjon üres megjegyzést a Level-1 ( `/// #` ) szakaszban, de ne hagyjon üres vonalat a 2. szint ( `/// ##` ) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="1e601-381">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-382">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-382">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="1e601-383">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-383">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

_*_

## <a name="formatting-conventions"></a><span data-ttu-id="1e601-384">Formázási konvenciók</span><span class="sxs-lookup"><span data-stu-id="1e601-384">Formatting Conventions</span></span> ##

<span data-ttu-id="1e601-385">Az előző javaslatok mellett hasznos lehet a kód a lehető legkönnyebben felismerhetővé tétele a konzisztens formázási szabályok használatához.</span><span class="sxs-lookup"><span data-stu-id="1e601-385">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="1e601-386">A természet szerinti formázási szabályok általában némileg önkényesak és szigorúan személyes esztétikai jellegűek.</span><span class="sxs-lookup"><span data-stu-id="1e601-386">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="1e601-387">Ugyanakkor javasolt a formázási konvenciók egységes csoportjának fenntartása a közreműködők csoportjain belül, és különösen a nagy Q# projektek, például a Quantum Development Kit esetében.</span><span class="sxs-lookup"><span data-stu-id="1e601-387">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="1e601-388">Ezek a szabályok automatikusan alkalmazhatók a fordítóval integrált formázó eszköz használatával Q# .</span><span class="sxs-lookup"><span data-stu-id="1e601-388">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="1e601-389">Útmutató</span><span class="sxs-lookup"><span data-stu-id="1e601-389">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="1e601-390">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="1e601-390">We suggest:</span></span>

- <span data-ttu-id="1e601-391">A hordozhatósághoz tabulátorok helyett négy szóközt használjon.</span><span class="sxs-lookup"><span data-stu-id="1e601-391">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="1e601-392">Például a VS Code-ban:</span><span class="sxs-lookup"><span data-stu-id="1e601-392">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="1e601-393">A sortörés 79 karakternél, ahol ésszerű.</span><span class="sxs-lookup"><span data-stu-id="1e601-393">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="1e601-394">Használjon szóközöket a bináris operátorok köré.</span><span class="sxs-lookup"><span data-stu-id="1e601-394">Use spaces around binary operators.</span></span>
- <span data-ttu-id="1e601-395">Használjon szóközöket a típushoz tartozó kettőspontok egyik oldalán.</span><span class="sxs-lookup"><span data-stu-id="1e601-395">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="1e601-396">A tömbben és a rekordokban lévő literálokban (például a functions és a Operations műveletekben) használt vesszők után egyetlen helyet használjon.</span><span class="sxs-lookup"><span data-stu-id="1e601-396">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="1e601-397">Ne használjon szóközt a függvény, a művelet vagy a UDT neve után, vagy a `@` in attribútum deklarációja után.</span><span class="sxs-lookup"><span data-stu-id="1e601-397">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="1e601-398">Minden attribútum deklarációjának saját sorban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1e601-398">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="1e601-399">Példák</span><span class="sxs-lookup"><span data-stu-id="1e601-399">Examples</span></span>](#tab/examples)

| &nbsp; | <span data-ttu-id="1e601-400">Snippet</span><span class="sxs-lookup"><span data-stu-id="1e601-400">Snippet</span></span> | <span data-ttu-id="1e601-401">Description</span><span class="sxs-lookup"><span data-stu-id="1e601-401">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="1e601-402">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-402">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="1e601-403">Használjon szóközöket a bináris operátorok köré.</span><span class="sxs-lookup"><span data-stu-id="1e601-403">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="1e601-404">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-404">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="1e601-405">Használjon szóközt a típus megjegyzési kettőspontok használatával.</span><span class="sxs-lookup"><span data-stu-id="1e601-405">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="1e601-406">☑</span><span class="sxs-lookup"><span data-stu-id="1e601-406">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="1e601-407">A bemeneti rekordban lévő elemek megfelelően vannak elfoglalva az olvashatóság érdekében.</span><span class="sxs-lookup"><span data-stu-id="1e601-407">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="1e601-408">☒</span><span class="sxs-lookup"><span data-stu-id="1e601-408">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="1e601-409">A szóközöket a függvény, a művelet vagy a UDT neve után le kell tiltani.</span><span class="sxs-lookup"><span data-stu-id="1e601-409">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

<span data-ttu-id="1e601-410">_\*\*</span><span class="sxs-lookup"><span data-stu-id="1e601-410">_\*\*</span></span>
