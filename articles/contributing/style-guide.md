---
title: 'Microsoft Q # Style útmutató'
description: 'A Q # programok és könyvtárak elnevezési, bemeneti, dokumentációs és formázási konvencióinak megismerése.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: dfb2b1779e3ddc77fc74697bc4dc2904b1a0c70f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426925"
---
# <a name="q-style-guide"></a><span data-ttu-id="5596a-103">Q # Style útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="5596a-104">Általános konvenciók</span><span class="sxs-lookup"><span data-stu-id="5596a-104">General Conventions</span></span> ##

<span data-ttu-id="5596a-105">Az ebben az útmutatóban javasolt konvenciók célja, hogy a Q # könnyebben olvasható és értelmezhető programokat és kódtárakat segítse.</span><span class="sxs-lookup"><span data-stu-id="5596a-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="5596a-106">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-106">Guidance</span></span>

<span data-ttu-id="5596a-107">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-107">We suggest:</span></span>

- <span data-ttu-id="5596a-108">Soha ne hagyja figyelmen kívül az egyezményt, hacsak nem ezt szándékosan teszi, hogy könnyebben olvasható és értelmezhető kódot nyújtson a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="5596a-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="5596a-109">Elnevezési konvenciók</span><span class="sxs-lookup"><span data-stu-id="5596a-109">Naming Conventions</span></span> ##

<span data-ttu-id="5596a-110">A Quantum Development Kit szolgáltatásban a függvény-és műveleti nevekre törekszünk, amelyek segítenek a kvantum-fejlesztőknek olyan programok írásához, amelyek könnyen olvashatóak, és a lehető legkevesebb meglepetést okozzák.</span><span class="sxs-lookup"><span data-stu-id="5596a-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="5596a-111">Fontos része annak, hogy ha a függvények, műveletek és típusok neveit választjuk, a programozók a Quantum fogalmak kifejezéséhez használt *szókincset* hoznak létre. a választásunk során segítünk vagy meggátoljuk őket abban, hogy világosan kommunikáljanak.</span><span class="sxs-lookup"><span data-stu-id="5596a-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="5596a-112">Ez felelősséget vállal a számunkra, hogy megbizonyosodjon róla, hogy az általunk bevezetett nevek egyértelműek és nem homályosak.</span><span class="sxs-lookup"><span data-stu-id="5596a-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="5596a-113">Ebben a szakaszban részletesen ismertetjük, hogyan teljesítjük ezt a kötelezettséget olyan explicit útmutatás szempontjából, amely segít a legjobb megoldás a Q # fejlesztői közösség számára.</span><span class="sxs-lookup"><span data-stu-id="5596a-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="5596a-114">Műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="5596a-114">Operations and Functions</span></span> ###

<span data-ttu-id="5596a-115">Az egyik első dolog, amit a névnek meg kell állapítania, hogy egy adott szimbólum függvényt vagy műveletet jelöl.</span><span class="sxs-lookup"><span data-stu-id="5596a-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="5596a-116">A függvények és a műveletek közötti különbség elengedhetetlen a kód egy blokkjának megismeréséhez.</span><span class="sxs-lookup"><span data-stu-id="5596a-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="5596a-117">A függvények és a műveletek a felhasználók közötti megkülönböztetésének közléséhez a Q # modellek kvantum-műveleteire támaszkodunk a mellékhatások használatával.</span><span class="sxs-lookup"><span data-stu-id="5596a-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="5596a-118">*Ez egy művelet végrehajtása* .</span><span class="sxs-lookup"><span data-stu-id="5596a-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="5596a-119">Ezzel szemben a függvények leírják az adatok közötti matematikai kapcsolatokat.</span><span class="sxs-lookup"><span data-stu-id="5596a-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="5596a-120">A kifejezés `Sin(PI() / 2.0)` *az* `1.0` , és nem jelent semmit a program vagy a qubits állapotáról.</span><span class="sxs-lookup"><span data-stu-id="5596a-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="5596a-121">Összefoglalva, a műveletek műveleteket végeznek, miközben a függvények a dolgok.</span><span class="sxs-lookup"><span data-stu-id="5596a-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="5596a-122">Ez a különbségtétel azt sugallja, hogy az Operations és a függvények neve a következő: nevek.</span><span class="sxs-lookup"><span data-stu-id="5596a-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="5596a-123">Felhasználó által definiált típus deklarálása esetén az adott típusú példányokat létrehozó új függvény implicit módon van definiálva egy időben.</span><span class="sxs-lookup"><span data-stu-id="5596a-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="5596a-124">Ebből a szemszögből a felhasználó által definiált típusok neveként kell nevezni, hogy mind a típus, mind a konstruktor függvény konzisztens névvel rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="5596a-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="5596a-125">Ahol ésszerű, győződjön meg arról, hogy a műveleti nevek olyan műveletekkel kezdődnek, amelyek egyértelműen jelzik a művelet által végrehajtott hatást.</span><span class="sxs-lookup"><span data-stu-id="5596a-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="5596a-126">Például:</span><span class="sxs-lookup"><span data-stu-id="5596a-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="5596a-127">Egy eset, amely különleges említést érdemel, ha egy művelet bemenetként egy másik műveletet hajt végre, és meghívja azt.</span><span class="sxs-lookup"><span data-stu-id="5596a-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="5596a-128">Ilyen esetekben a bemeneti művelet által végrehajtott művelet nem egyértelmű, ha a külső művelet definiálva van, úgy, hogy a megfelelő művelet ne legyen azonnal egyértelmű.</span><span class="sxs-lookup"><span data-stu-id="5596a-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="5596a-129">A művelet a, a, a és a esetében ajánlott `Apply` `ApplyIf` `ApplyToEach` `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="5596a-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="5596a-130">Ebben az esetben más igék is hasznosak lehetnek, mint a-ben `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="5596a-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="5596a-131">Művelet</span><span class="sxs-lookup"><span data-stu-id="5596a-131">Verb</span></span> | <span data-ttu-id="5596a-132">Várt hatás</span><span class="sxs-lookup"><span data-stu-id="5596a-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="5596a-133">Alkalmaz</span><span class="sxs-lookup"><span data-stu-id="5596a-133">Apply</span></span> | <span data-ttu-id="5596a-134">A bemenetként megadott műveletet nevezzük</span><span class="sxs-lookup"><span data-stu-id="5596a-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="5596a-135">Assert</span><span class="sxs-lookup"><span data-stu-id="5596a-135">Assert</span></span> | <span data-ttu-id="5596a-136">A lehetséges kvantum-mérés eredményével kapcsolatos hipotézist egy szimulátor ellenőrzi</span><span class="sxs-lookup"><span data-stu-id="5596a-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="5596a-137">Estimate (becslés)</span><span class="sxs-lookup"><span data-stu-id="5596a-137">Estimate</span></span> | <span data-ttu-id="5596a-138">Egy klasszikus értéket ad vissza, amely egy vagy több mérésből álló becslést jelöl.</span><span class="sxs-lookup"><span data-stu-id="5596a-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="5596a-139">Measure</span><span class="sxs-lookup"><span data-stu-id="5596a-139">Measure</span></span> | <span data-ttu-id="5596a-140">A rendszer elvégzi a kvantum-mérést, és annak eredményét visszaadja a felhasználónak</span><span class="sxs-lookup"><span data-stu-id="5596a-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="5596a-141">Előkészítés</span><span class="sxs-lookup"><span data-stu-id="5596a-141">Prepare</span></span> | <span data-ttu-id="5596a-142">A qubits adott regisztrálása egy adott állapotba van inicializálva</span><span class="sxs-lookup"><span data-stu-id="5596a-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="5596a-143">Sample</span><span class="sxs-lookup"><span data-stu-id="5596a-143">Sample</span></span> | <span data-ttu-id="5596a-144">Egy klasszikus értéket ad vissza véletlenszerűen egy bizonyos eloszlásból</span><span class="sxs-lookup"><span data-stu-id="5596a-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="5596a-145">A függvények esetében javasoljuk, hogy kerülje a műveletek használatát a közös nevek mellett (lásd az alábbi, a földrajzi nevekkel kapcsolatos útmutatót) vagy a mellékneveket:</span><span class="sxs-lookup"><span data-stu-id="5596a-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="5596a-146">Különösen, ha szinte minden esetben azt javasoljuk, hogy a múltbeli táblázatos adatok használatával jelezze, hogy egy függvény neve erősen csatlakozik egy művelethez vagy egy mellékhatáshoz a kvantum-programban másutt.</span><span class="sxs-lookup"><span data-stu-id="5596a-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="5596a-147">Például a `ControlledOnInt` "vezérlő" művelet "Control" utasításának "a" kifejezés formája, amely azt jelzi, hogy a függvény melléknévként viselkedik az argumentumának módosításához.</span><span class="sxs-lookup"><span data-stu-id="5596a-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="5596a-148">Ennek a névnek a további előnye, hogy összefoglalja a beépített felépítmény szemantikai `Controlled` feltételeit, ahogy azt az alábbiakban tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="5596a-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="5596a-149">Hasonlóképpen, az _ügynökök_ nevei a függvények és a UDT alapján is felhasználhatók a műveleti nevekből, például egy, a szolgáltatáshoz `Encoder` szorosan társított UDT neve esetén `Encode` .</span><span class="sxs-lookup"><span data-stu-id="5596a-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-150">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-151">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-151">We suggest:</span></span>

- <span data-ttu-id="5596a-152">Műveletek neveihez használjon műveleteket.</span><span class="sxs-lookup"><span data-stu-id="5596a-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="5596a-153">Nevek vagy melléknevek használata a függvények neveihez.</span><span class="sxs-lookup"><span data-stu-id="5596a-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="5596a-154">A felhasználó által definiált típusokhoz és attribútumokhoz tartozó nevek használata.</span><span class="sxs-lookup"><span data-stu-id="5596a-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="5596a-155">Az összes hívható név esetében használjon `CamelCase` erős preferenciát a `pascalCase` ,, vagy rendszerre `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="5596a-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="5596a-156">Különösen ügyeljen arra, hogy a hívható nevek nagybetűvel kezdődjön.</span><span class="sxs-lookup"><span data-stu-id="5596a-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="5596a-157">Az összes helyi változó esetében használjon `pascalCase` erős preferenciát a `CamelCase` ,, vagy rendszerre `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="5596a-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="5596a-158">Különösen ügyeljen arra, hogy a helyi változók kisbetűkkel kezdődjön.</span><span class="sxs-lookup"><span data-stu-id="5596a-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="5596a-159">Kerülje az aláhúzások használatát a `_` függvények és a műveletek neveiben; ahol további hierarchiára van szükség, használja a névtereket és a névterek aliasait.</span><span class="sxs-lookup"><span data-stu-id="5596a-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-160">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5596a-161">Name</span><span class="sxs-lookup"><span data-stu-id="5596a-161">Name</span></span> | <span data-ttu-id="5596a-162">Leírás</span><span class="sxs-lookup"><span data-stu-id="5596a-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5596a-163">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="5596a-164">A művelet hatásának jelzéséhez törölje a műveletet ("tükrözze").</span><span class="sxs-lookup"><span data-stu-id="5596a-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="5596a-165">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="5596a-166">A főnévi kifejezés a művelet helyett a függvényt javasolja.</span><span class="sxs-lookup"><span data-stu-id="5596a-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="5596a-167">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="5596a-168">Az `snake_case` ellentétes Q # jelölés használata.</span><span class="sxs-lookup"><span data-stu-id="5596a-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="5596a-169">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="5596a-170">A belső és a műveleti név közötti aláhúzás használata a Q # jelöléssel ellentétes.</span><span class="sxs-lookup"><span data-stu-id="5596a-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="5596a-171">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="5596a-172">A főnévi kifejezés használata azt sugallja, hogy a függvény egy műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="5596a-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="5596a-173">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="5596a-174">A főnév ("Fact") egyértelmű használata annak jelzésére, hogy ez egy függvény, míg a melléknév.</span><span class="sxs-lookup"><span data-stu-id="5596a-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="5596a-175">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="5596a-176">Az ige ("Get") használata azt jelzi, hogy ez egy művelet.</span><span class="sxs-lookup"><span data-stu-id="5596a-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="5596a-177">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="5596a-178">A főnévi kifejezés használata egyértelműen a UDT konstruktor hívásának eredményét jelenti.</span><span class="sxs-lookup"><span data-stu-id="5596a-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="5596a-179">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="5596a-180">A ige kifejezés használata azt sugallja, hogy a UDT konstruktora egy művelet.</span><span class="sxs-lookup"><span data-stu-id="5596a-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="5596a-181">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="5596a-182">A főnévi kifejezés használata az attribútum használatát közli.</span><span class="sxs-lookup"><span data-stu-id="5596a-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="5596a-183">Rövidítések és rövidítések</span><span class="sxs-lookup"><span data-stu-id="5596a-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="5596a-184">A fenti tanácsokban a Gyorsírás számos formája létezik, amely a kvantum-számítástechnika általános és átható használatát látja el.</span><span class="sxs-lookup"><span data-stu-id="5596a-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="5596a-185">Javasoljuk, hogy meglévő és közös gyorsírást használjon, ahol létezik, különösen olyan műveletek esetén, amelyek a célszámítógép működéséhez tartoznak.</span><span class="sxs-lookup"><span data-stu-id="5596a-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="5596a-186">Például a helyett a nevet választjuk `X` `ApplyX` `Rz` `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="5596a-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="5596a-187">Ilyen rövidítés használatakor a művelet neve csak nagybetűs lehet (például: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="5596a-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="5596a-188">Erre az egyezményre akkor van szükség, ha gyakran használt betűszók és nagybetűk, például "QFT" a "Quantum Fourier átalakítás" kifejezésre alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5596a-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="5596a-189">Javasoljuk, hogy az általános .NET-konvenciókat a betűszók és a nagyszótárak teljes névben való használatára ajánljuk, amely az alábbiakat írja elő:</span><span class="sxs-lookup"><span data-stu-id="5596a-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="5596a-190">a kétbetűs betűszók és a nagyvállalatok neve nagybetűs (például: `BE` "big-endian"),</span><span class="sxs-lookup"><span data-stu-id="5596a-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="5596a-191">az összes további betűszó és a nagybetűk neve `CamelCase` (például: `Qft` "Quantum Fourier Transform")</span><span class="sxs-lookup"><span data-stu-id="5596a-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="5596a-192">Így a QFT megvalósító művelet lehet `QFT` rövidített vagy kiírva `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="5596a-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="5596a-193">A gyakran használt műveletek és függvények esetében érdemes lehet egy rövidített nevet megadni egy hosszú űrlap _aliasként_ való megadásához:</span><span class="sxs-lookup"><span data-stu-id="5596a-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="5596a-194">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-195">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-195">We suggest:</span></span>

- <span data-ttu-id="5596a-196">Ha szükséges, tekintse meg a gyakran elfogadott és széles körben használt rövidített neveket.</span><span class="sxs-lookup"><span data-stu-id="5596a-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="5596a-197">Kis-és nagybetűk használata a gyorsíráshoz.</span><span class="sxs-lookup"><span data-stu-id="5596a-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="5596a-198">Rövid (kétbetűs) betűszók és nagybetűk használata.</span><span class="sxs-lookup"><span data-stu-id="5596a-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="5596a-199">`CamelCase`Hosszabb (három vagy több betűs) rövidítéssel és nagybetűkkel is használható.</span><span class="sxs-lookup"><span data-stu-id="5596a-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-200">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5596a-201">Name</span><span class="sxs-lookup"><span data-stu-id="5596a-201">Name</span></span> | <span data-ttu-id="5596a-202">Leírás</span><span class="sxs-lookup"><span data-stu-id="5596a-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5596a-203">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-203">☑</span></span> | `X` | <span data-ttu-id="5596a-204">Jól ismert Gyorsírás a "$X $ átalakítás alkalmazása"</span><span class="sxs-lookup"><span data-stu-id="5596a-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="5596a-205">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-205">☑</span></span> | `CNOT` | <span data-ttu-id="5596a-206">Jól értelmezhető Gyorsírás a "vezérelt – nem"</span><span class="sxs-lookup"><span data-stu-id="5596a-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="5596a-207">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="5596a-208">A Gyorsírás nem lehet a-ben `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="5596a-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="5596a-209">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="5596a-210">A "QFT" általános inicializálás a hosszú formátumú név részeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5596a-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="5596a-211">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-211">☑</span></span> | `QFT` | <span data-ttu-id="5596a-212">A "QFT" általános inicializálás egy rövidített név részeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5596a-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="5596a-213">Megfelelő nevek a névben</span><span class="sxs-lookup"><span data-stu-id="5596a-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="5596a-214">A fizikában gyakran előfordul, hogy az első személynek a róluk való közzétételét követően a legtöbb nem fizikus nem ismeri a mindenki nevét és az előzményeket.</span><span class="sxs-lookup"><span data-stu-id="5596a-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="5596a-215">A fizika elnevezési konvenciói alapján túl nagy mértékben támaszkodhat a beléptetésre, mivel a más hátterű felhasználóknak nagy mennyiségű látszólag átlátszatlan nevet kell megtanulniuk ahhoz, hogy közös műveleteket és fogalmakat lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="5596a-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="5596a-216">Ezért azt javasoljuk, hogy ha ésszerű, a fogalmakat leíró általános nevek erős előnyben legyenek kitéve a fogalmak közzétételének előzményeit leíró földrajzi nevek iránt.</span><span class="sxs-lookup"><span data-stu-id="5596a-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="5596a-217">Egy adott példának megfelelően az "Fredkin" és a "Toffoli" műveletet gyakran nevezik a tudományos irodalomban, de a Q # elsődlegesen a és a kifejezéssel azonosítják őket `CSWAP` `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="5596a-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="5596a-218">Az API-dokumentációs megjegyzések mindkét esetben a megfelelő neveken alapuló szinonimákat biztosítanak az összes megfelelő hivatkozással együtt.</span><span class="sxs-lookup"><span data-stu-id="5596a-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="5596a-219">Ez a beállítás különösen fontos, mivel a megfelelő főnevek bizonyos használata mindig szükséges – a Q # a sok klasszikus nyelv által meghatározott hagyományt követi, és a `Bool` logikai logikára hivatkozó típusokra hivatkozik, ami pedig George Boole tiszteletében megnevezett.</span><span class="sxs-lookup"><span data-stu-id="5596a-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="5596a-220">Ehhez hasonló módon kell megneveznie a kvantum-fogalmakat, beleértve a `Pauli` Q # nyelv beépített típusát is.</span><span class="sxs-lookup"><span data-stu-id="5596a-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="5596a-221">A megfelelő főnevek használatának minimalizálása, ha az ilyen használat nem alapvető fontosságú, csökkentik annak a hatását, hogy a megfelelő földrajzi nevek ne legyenek ésszerűen elkerülhetők.</span><span class="sxs-lookup"><span data-stu-id="5596a-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-222">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="5596a-223">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-223">We suggest:</span></span>

- <span data-ttu-id="5596a-224">Kerülje a nevekben a megfelelő nevek használatát.</span><span class="sxs-lookup"><span data-stu-id="5596a-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-225">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="5596a-226">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="5596a-226">Type Conversions</span></span> ###

<span data-ttu-id="5596a-227">Mivel a Q # egy erősen és statikusan beírt nyelv, az egyik típusú érték csak egy másik típusú értékként használható egy típus-átalakítási függvény kifejezett hívásával.</span><span class="sxs-lookup"><span data-stu-id="5596a-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="5596a-228">Ez ellentétben áll azokkal a nyelvekkel, amelyek lehetővé teszik, hogy az értékek implicit módon módosítsák a típusokat (pl.: Type Promotion) vagy a casting használatával.</span><span class="sxs-lookup"><span data-stu-id="5596a-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="5596a-229">Ennek eredményeképpen az átalakítási függvények fontos szerepet játszanak a Q # könyvtár fejlesztésében, és az elnevezéssel kapcsolatban leggyakrabban felmerülő döntések egyikét alkotják.</span><span class="sxs-lookup"><span data-stu-id="5596a-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="5596a-230">Azonban ez azt jelzi, hogy mivel a Type konverziók mindig _determinisztikus_, a függvények is megírhatók, ezért a fenti tanács alá tartoznak.</span><span class="sxs-lookup"><span data-stu-id="5596a-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="5596a-231">Különösen azt javasoljuk, hogy a Type konverziós függvények soha ne legyenek elnevezve műveleteknek (pl.: `ConvertToX` ) vagy a határozószók előírási kifejezéseknek ( `ToX` ), hanem a forrás és a cél típusokat () jelző, melléknévi előírási kifejezéseknek kell nevezni `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="5596a-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="5596a-232">Ha a tömb típusait a konverziós függvények neveiben listázza, javasoljuk a gyorsírást `Arr` .</span><span class="sxs-lookup"><span data-stu-id="5596a-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="5596a-233">A kivételes körülmények korlátozásával azt javasoljuk, hogy az összes Type konverziós függvény neve legyen, hogy `As` gyorsan azonosítható legyen.</span><span class="sxs-lookup"><span data-stu-id="5596a-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-234">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-235">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-235">We suggest:</span></span>

- <span data-ttu-id="5596a-236">Ha egy függvény Type típusú értéket alakít át `X` `Y` , használja a nevet vagy a értéket `AsY` `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="5596a-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-237">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5596a-238">Name</span><span class="sxs-lookup"><span data-stu-id="5596a-238">Name</span></span> | <span data-ttu-id="5596a-239">Leírás</span><span class="sxs-lookup"><span data-stu-id="5596a-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5596a-240">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="5596a-241">A "to" utasítás a művelethez tartozó kifejezést eredményez, és nem függvényt jelez.</span><span class="sxs-lookup"><span data-stu-id="5596a-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="5596a-242">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="5596a-243">A bemeneti típus nem egyértelmű a függvény nevéből.</span><span class="sxs-lookup"><span data-stu-id="5596a-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="5596a-244">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="5596a-245">A bemeneti és a kimeneti típusok nem megfelelő sorrendben jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="5596a-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="5596a-246">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="5596a-247">A bemeneti típusok és a kimeneti típusok egyaránt törlődnek.</span><span class="sxs-lookup"><span data-stu-id="5596a-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="5596a-248">Magán-vagy belső nevek</span><span class="sxs-lookup"><span data-stu-id="5596a-248">Private or Internal Names</span></span> ###

<span data-ttu-id="5596a-249">Sok esetben a név kifejezetten a belső könyvtárakhoz vagy projektekhez való használatra szolgál, és nem a könyvtár által kínált API garantált részét képezi.</span><span class="sxs-lookup"><span data-stu-id="5596a-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="5596a-250">Hasznos lehet egyértelműen jelezni, hogy ez a helyzet az elnevezési függvények és műveletek esetében, hogy a csak belső kódok véletlen függőségei legyenek egyértelműek.</span><span class="sxs-lookup"><span data-stu-id="5596a-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="5596a-251">Ha egy művelet vagy függvény nem közvetlen használatra készült, hanem egy, a részleges alkalmazás által elvégezhető egyező meghívónak kell használnia, érdemes lehet a `_` részben alkalmazott hívható nevet használni.</span><span class="sxs-lookup"><span data-stu-id="5596a-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-252">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-253">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-253">We suggest:</span></span>

- <span data-ttu-id="5596a-254">Ha egy függvény, művelet vagy felhasználó által definiált típus nem része a Q # függvénytárának vagy programjának a nyilvános API-nak, akkor győződjön meg arról, hogy a neve kezdő aláhúzással ( `_` ) kezdődik.</span><span class="sxs-lookup"><span data-stu-id="5596a-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-255">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5596a-256">Name</span><span class="sxs-lookup"><span data-stu-id="5596a-256">Name</span></span> | <span data-ttu-id="5596a-257">Leírás</span><span class="sxs-lookup"><span data-stu-id="5596a-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5596a-258">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="5596a-259">Az aláhúzás `_` nem szerepelhet a név végén.</span><span class="sxs-lookup"><span data-stu-id="5596a-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="5596a-260">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="5596a-261">Az aláhúzás `_` kezdetben egyértelműen azt jelzi, hogy ez a művelet csak belső használatra szolgál.</span><span class="sxs-lookup"><span data-stu-id="5596a-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="5596a-262">Változatok</span><span class="sxs-lookup"><span data-stu-id="5596a-262">Variants</span></span> ###

<span data-ttu-id="5596a-263">Bár ez a korlátozás nem szűnik meg a Q # jövőbeli verzióiban, jelenleg a kapcsolódó műveletek vagy függvények olyan csoportjai lesznek, amelyek megkülönböztetni egymástól a bemenők által támogatott, illetve az argumentumok konkrét típusait.</span><span class="sxs-lookup"><span data-stu-id="5596a-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="5596a-264">Ezek a csoportok megkülönböztetni ugyanazt a legfelső szintű nevet, majd egy vagy két betűt, amelyek jelzik a változatát.</span><span class="sxs-lookup"><span data-stu-id="5596a-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="5596a-265">Utótag</span><span class="sxs-lookup"><span data-stu-id="5596a-265">Suffix</span></span> | <span data-ttu-id="5596a-266">Jelentés</span><span class="sxs-lookup"><span data-stu-id="5596a-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="5596a-267">Várhatóan támogatott bemenet`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="5596a-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="5596a-268">Várhatóan támogatott bemenet`Controlled`</span><span class="sxs-lookup"><span data-stu-id="5596a-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="5596a-269">A várt támogatás `Controlled` és`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="5596a-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="5596a-270">Bemenet vagy bemenet típusa`Int`</span><span class="sxs-lookup"><span data-stu-id="5596a-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="5596a-271">Bemenet vagy bemenet típusa`Double`</span><span class="sxs-lookup"><span data-stu-id="5596a-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="5596a-272">Bemenet vagy bemenet típusa`BigInt`</span><span class="sxs-lookup"><span data-stu-id="5596a-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="5596a-273">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-274">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-274">We suggest:</span></span>

- <span data-ttu-id="5596a-275">Ha egy függvény vagy művelet nem kapcsolódik hasonló funkciókhoz vagy műveletekhez a bemenetek típusai és a nem megfelelő működésének támogatásával, ne használjon utótagot.</span><span class="sxs-lookup"><span data-stu-id="5596a-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="5596a-276">Ha egy függvény vagy művelet bármely hasonló függvényhez vagy művelethez kapcsolódik, és a bemenetek típusai és az azokon lévők is támogatják, a változatok megkülönböztetéséhez használja a fenti táblázatban szereplő utótagokat.</span><span class="sxs-lookup"><span data-stu-id="5596a-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-277">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="5596a-278">Argumentumok és változók</span><span class="sxs-lookup"><span data-stu-id="5596a-278">Arguments and Variables</span></span> ###

<span data-ttu-id="5596a-279">Egy függvény vagy művelet Q # kódjának fő célja, hogy könnyen olvasható és értelmezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="5596a-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="5596a-280">Hasonlóképpen, a bemenetek és a Type argumentumok neveinek kell megadniuk, hogy a rendszer hogyan használja a függvényt vagy az argumentumot.</span><span class="sxs-lookup"><span data-stu-id="5596a-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="5596a-281">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-282">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-282">We suggest:</span></span>

- <span data-ttu-id="5596a-283">Az összes változó és bemeneti név esetében használjon `pascalCase` erős preferenciát a `CamelCase` ,, vagy rendszerhez `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="5596a-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="5596a-284">A bemeneti névnek leírónak kell lennie. lehetőleg ne adjon meg egy vagy két betűt.</span><span class="sxs-lookup"><span data-stu-id="5596a-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="5596a-285">A pontosan egy típusú argumentumot elfogadó műveletek és függvények a Type argumentumot jelölik, `T` Ha a szerepköre nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="5596a-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="5596a-286">Ha egy függvény vagy művelet több típusú argumentumot is igénybe vesz, vagy ha egy adott típusú argumentum szerepköre nem egyértelmű, érdemes lehet egy rövid, tőkésített szót `T` (például:) használni `TOutput` az egyes típusokhoz.</span><span class="sxs-lookup"><span data-stu-id="5596a-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="5596a-287">Az argumentumban és a változók neveiben ne szerepeljenek a nevek. ezt az információt a fejlesztési környezetnek is meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="5596a-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="5596a-288">Skaláris típusokat jelöl a literális nevük ( `flagQubit` ) és a tömb típusa szerint egy többes szám ( `measResults` ) alapján.</span><span class="sxs-lookup"><span data-stu-id="5596a-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="5596a-289">A qubits-tömbök esetében érdemes lehet olyan típusokat megjelölni, `Register` amelyek alapján a név olyan qubits-sorozatra hivatkozik, amely valamilyen módon szorosan összefügg egymással.</span><span class="sxs-lookup"><span data-stu-id="5596a-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="5596a-290">A tömbökbe indexként használt változóknak a (z) értékkel kell kezdődnie, `idx` és csak néhány lehet (például: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="5596a-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="5596a-291">Különösen érdemes elkerülni az egybetűs változók nevének indexként való használatát. ajánlott legalább a használata `idx` .</span><span class="sxs-lookup"><span data-stu-id="5596a-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="5596a-292">A tömbök hosszának megtartására használt változóknak a (z) értékkel kell kezdődnie, `n` és a (z) számnak kell lennie (például: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="5596a-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-293">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="5596a-294">A felhasználó által definiált típusú elemek neve</span><span class="sxs-lookup"><span data-stu-id="5596a-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="5596a-295">A felhasználó által definiált típusokban megnevezett elemek neveként kell nevezni `CamelCase` , még a UDT konstruktorok számára is.</span><span class="sxs-lookup"><span data-stu-id="5596a-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="5596a-296">Ez segít az elnevezett elemek egyértelmű elkülönítésében a helyileg hatókörön belüli változókra mutató hivatkozásokkal a hozzáférési jelölés (például: `callable::Apply` ) vagy a másolási és frissítési jelölés ( `set arr w/= Data <- newData` ) használatakor.</span><span class="sxs-lookup"><span data-stu-id="5596a-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-297">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-298">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-298">We suggest:</span></span>

- <span data-ttu-id="5596a-299">A UDT konstruktorokban megnevezett elemek neveként kell nevezni, `CamelCase` azaz kezdeti nagybetűvel kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="5596a-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="5596a-300">A műveletekhez feloldani megnevezett elemek művelet fázisként kell nevezni.</span><span class="sxs-lookup"><span data-stu-id="5596a-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="5596a-301">A műveleteknek nem feloldható megnevezett elemeknek főnévi kifejezéseknek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="5596a-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="5596a-302">A műveleteket UDT egyetlen elnevezett elemnek kell `Apply` definiálni.</span><span class="sxs-lookup"><span data-stu-id="5596a-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-303">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5596a-304">Snippet</span><span class="sxs-lookup"><span data-stu-id="5596a-304">Snippet</span></span> | <span data-ttu-id="5596a-305">Leírás</span><span class="sxs-lookup"><span data-stu-id="5596a-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="5596a-306">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="5596a-307">A név `Apply` egy `CamelCase` formázott igei kifejezés, amely arra utal, hogy az elnevezett elem egy művelet.</span><span class="sxs-lookup"><span data-stu-id="5596a-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="5596a-308">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="5596a-309">Az elnevezett elemeknek kezdeti nagybetűvel kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="5596a-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="5596a-310">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="5596a-311">A függvények feloldására szolgáló névvel ellátott elemeknek főnévi kifejezéseknek kell lenniük, nem pedig ige kifejezéseknek.</span><span class="sxs-lookup"><span data-stu-id="5596a-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="5596a-312">Bemeneti konvenciók</span><span class="sxs-lookup"><span data-stu-id="5596a-312">Input Conventions</span></span> ##

<span data-ttu-id="5596a-313">Amikor egy fejlesztő meghívja a műveletet vagy a függvényt, az adott művelethez vagy függvényhez tartozó különböző bemeneteket egy adott sorrendben kell megadnia, ami növeli a fejlesztők által felhasználható kognitív terhelést, hogy használhassa a kódtárat.</span><span class="sxs-lookup"><span data-stu-id="5596a-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="5596a-314">A bemeneti sorrendek megemlékezésének feladata különösen az, ha a feladatból gyakran elkerülnek a következők: egy kvantum-algoritmus megvalósításának programozása.</span><span class="sxs-lookup"><span data-stu-id="5596a-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="5596a-315">Bár a gazdag IDE-támogatás nagy mértékben csökkentheti ezt a megoldást, a jó tervezés és a közös konvenciók betartása is segítheti az API-k által kiszabott kognitív terhelés minimalizálását.</span><span class="sxs-lookup"><span data-stu-id="5596a-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="5596a-316">Ahol lehetséges, hasznos lehet csökkenteni a művelet vagy a függvény által várt bemenetek számát, így az egyes bemenetek szerepe azonnal nyilvánvalóvá válik az adott művelethez vagy függvényhez tartozó fejlesztők számára, valamint a programkódot később olvasó fejlesztők számára.</span><span class="sxs-lookup"><span data-stu-id="5596a-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="5596a-317">Különösen, ha nem lehetséges vagy ésszerű az argumentumok számának csökkentése egy művelet vagy függvény számára, fontos, hogy konzisztens megrendelés álljon rendelkezésre, amely minimalizálja azt a meglepetést, amelyet a felhasználó a bemenetek sorrendjének előrejelzése során szembesül.</span><span class="sxs-lookup"><span data-stu-id="5596a-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="5596a-318">Javasoljuk, hogy olyan bemeneti rendezési konvenciókat ajánlunk, amelyek nagyrészt az f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="5596a-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="5596a-319">Ezért az első argumentumok részleges alkalmazása olyan meghívót eredményezhet, amely a saját jogon hasznos, ha ésszerű.</span><span class="sxs-lookup"><span data-stu-id="5596a-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="5596a-320">Ezt az elvet követve érdemes lehet a következő argumentumokat használni:</span><span class="sxs-lookup"><span data-stu-id="5596a-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="5596a-321">Klasszikus, nem hívható argumentumok, például szögek, hatáskörök vektorai stb.</span><span class="sxs-lookup"><span data-stu-id="5596a-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="5596a-322">Hívható argumentumok (függvények és argumentumok).</span><span class="sxs-lookup"><span data-stu-id="5596a-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="5596a-323">Ha a functions és a Operations is argumentumként van megadva, érdemes lehet műveleteket végrehajtani a függvények után.</span><span class="sxs-lookup"><span data-stu-id="5596a-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="5596a-324">A gyűjtemények a,, és rendszerhez hasonló módon, meghívásos argumentumok alapján jártak el `Map` `Iter` `Enumerate` `Fold` .</span><span class="sxs-lookup"><span data-stu-id="5596a-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="5596a-325">A vezérlőkként használt Qubit argumentumok.</span><span class="sxs-lookup"><span data-stu-id="5596a-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="5596a-326">Qubit használt argumentumok.</span><span class="sxs-lookup"><span data-stu-id="5596a-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="5596a-327">Vegye fontolóra egy olyan művelet használatát, amellyel a `ApplyPhaseEstimationIteration` fázis becslése egy szöget és egy Oracle-t vesz igénybe, és a szöget átadja a `Rz` különböző skálázási tényezők tömbje által módosítottnak, majd az Oracle alkalmazásait vezérli.</span><span class="sxs-lookup"><span data-stu-id="5596a-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="5596a-328">A bemeneteket a következő módon kell megrendelni `ApplyPhaseEstimationIteration` :</span><span class="sxs-lookup"><span data-stu-id="5596a-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="5596a-329">A kis-és nagybetűk minimálisra csökkentése érdekében egyes függvények és műveletek a beépített és a rendszer működését utánozzák `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="5596a-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="5596a-330">`ControlledOnInt<'T>` `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` Ilyen például a típus, amely a következőhöz hasonló módon viselkedik:, `ControlledOnInt<Qubit[]>(5, _)` `Controlled` de abban a feltétellel, hogy a vezérlő regisztrálása a $ \ket {5} = \ket $ állapotot jelöli {101} .</span><span class="sxs-lookup"><span data-stu-id="5596a-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="5596a-331">Így a fejlesztő azt várja, hogy a `ControlledOnInt` meghívót a legutóbb átalakított értékre helyezze át, és hogy az eredményül kapott művelet a bemeneti---ugyanolyan sorrendben legyen, mint az ellátottak `(Qubit[], 'T)` kimenete `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="5596a-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-332">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-333">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-333">We suggest:</span></span>

- <span data-ttu-id="5596a-334">A részleges alkalmazás használatával összhangban lévő bemeneti sorrendek használata.</span><span class="sxs-lookup"><span data-stu-id="5596a-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="5596a-335">Beépített feladatokkal konzisztens bemeneti sorrendek használata.</span><span class="sxs-lookup"><span data-stu-id="5596a-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="5596a-336">Helyezzen minden klasszikus bemenetet a kvantum-bevitel előtt.</span><span class="sxs-lookup"><span data-stu-id="5596a-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-337">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="5596a-338">Dokumentációs konvenciók</span><span class="sxs-lookup"><span data-stu-id="5596a-338">Documentation Conventions</span></span> ##

<span data-ttu-id="5596a-339">A Q # nyelv lehetővé teszi a dokumentáció csatolását a műveletekhez, a függvényekhez és a felhasználó által definiált típusokhoz a speciálisan formázott dokumentációs megjegyzések használatával.</span><span class="sxs-lookup"><span data-stu-id="5596a-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="5596a-340">A Triple-ferde ( `///` ) függvényekkel ezek a dokumentációs megjegyzések kisméretű, [DocFX Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) dokumentumok, amelyek az egyes műveletek, függvények és felhasználó által definiált típusok, valamint a várt bemeneti adatok céljának leírására használhatók.</span><span class="sxs-lookup"><span data-stu-id="5596a-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="5596a-341">A Quantum Development Kit által biztosított fordító kibontja ezeket a megjegyzéseket, és a segítségével a következőhöz hasonló dokumentációt videótartalmakban https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="5596a-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="5596a-342">Hasonlóképpen, a Quantum Development Kit által biztosított nyelvi kiszolgáló ezeket a megjegyzéseket használja, hogy segítséget nyújtson a felhasználóknak a Q # kódjában lévő szimbólumok fölé helyezve.</span><span class="sxs-lookup"><span data-stu-id="5596a-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="5596a-343">A dokumentációs megjegyzések használata így segítheti a felhasználókat a kód értelmezésében azáltal, hogy a jelen dokumentum többi konvenciója alapján nem könnyen elérhetővé tett részletekre vonatkozó hasznos hivatkozást biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="5596a-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="5596a-344">
    [Dokumentációs Megjegyzés szintaxisának leírása](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="5596a-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="5596a-345">Ahhoz, hogy hatékonyan használhassa ezt a funkciót a felhasználók számára, javasoljuk, hogy a dokumentációs megjegyzések írásakor ne feledje el néhány dolgot.</span><span class="sxs-lookup"><span data-stu-id="5596a-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-346">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5596a-347">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-347">We suggest:</span></span>

- <span data-ttu-id="5596a-348">Minden nyilvános funkciót, műveletet és felhasználó által definiált típust közvetlenül a dokumentációs Megjegyzés előtt kell megadni.</span><span class="sxs-lookup"><span data-stu-id="5596a-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="5596a-349">Az egyes dokumentációs megjegyzéseknek legalább a következő részeket kell tartalmazniuk:</span><span class="sxs-lookup"><span data-stu-id="5596a-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="5596a-350">Összefoglalás</span><span class="sxs-lookup"><span data-stu-id="5596a-350">Summary</span></span>
    - <span data-ttu-id="5596a-351">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5596a-351">Input</span></span>
    - <span data-ttu-id="5596a-352">Kimenet (ha van ilyen)</span><span class="sxs-lookup"><span data-stu-id="5596a-352">Output (if applicable)</span></span>
- <span data-ttu-id="5596a-353">Győződjön meg arról, hogy minden összefoglaló két mondat vagy kevesebb.</span><span class="sxs-lookup"><span data-stu-id="5596a-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="5596a-354">Ha további helyiségre van szükség, adjon meg egy szakaszt, amely `# Description` azonnal követi a `# Summary` teljes részleteket.</span><span class="sxs-lookup"><span data-stu-id="5596a-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="5596a-355">Ahol ésszerű, ne szerepeljenek a matematika az összefoglalókban, mivel nem minden ügyfél támogatja a TeX-jelöléseket az összefoglalók között.</span><span class="sxs-lookup"><span data-stu-id="5596a-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="5596a-356">Vegye figyelembe, hogy a prózai dokumentumok (például a TeX vagy a Markdown) írásakor érdemes lehet hosszabb vonali hosszúságot használni.</span><span class="sxs-lookup"><span data-stu-id="5596a-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="5596a-357">Adja meg az összes releváns matematikai kifejezést a `# Description` szakaszban.</span><span class="sxs-lookup"><span data-stu-id="5596a-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="5596a-358">A bemenetek leírásakor ne ismételje meg az egyes bemenetek típusait, mivel ezek a fordító számára következtetni tudnak, és az inkonzisztencia bevezetését kockáztatják.</span><span class="sxs-lookup"><span data-stu-id="5596a-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="5596a-359">Szükség szerint adjon meg példákat a saját `# Example` szakaszában.</span><span class="sxs-lookup"><span data-stu-id="5596a-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="5596a-360">A kód listázása előtt röviden ismertesse az egyes példákat.</span><span class="sxs-lookup"><span data-stu-id="5596a-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="5596a-361">Sorolja fel az összes releváns tanulmányi kiadványt (például: dokumentumok, eljárások, blogbejegyzések és alternatív implementációk) a `# References` szakaszokban a hivatkozások felsorolásával.</span><span class="sxs-lookup"><span data-stu-id="5596a-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="5596a-362">Győződjön meg arról, hogy ha lehetséges, az összes hivatkozási hivatkozás állandó és megváltoztathatatlan azonosítók (DOIs vagy verziószámmal ellátott arXiv-számok).</span><span class="sxs-lookup"><span data-stu-id="5596a-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="5596a-363">Ha egy művelet vagy függvény más műveletekhez vagy függvényekhez kapcsolódik, és az esetlegesen előforduló változatok is szerepelnek, a szakaszokban listajelként sorolja fel a többi változatot `# See Also` .</span><span class="sxs-lookup"><span data-stu-id="5596a-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="5596a-364">Hagyjon üres megjegyzést a Level-1 ( `/// #` ) szakaszban, de ne hagyjon üres vonalat a 2. szint ( `/// ##` ) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="5596a-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-365">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="5596a-366">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-366">☑</span></span> ####

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

***

## <a name="formatting-conventions"></a><span data-ttu-id="5596a-367">Formázási konvenciók</span><span class="sxs-lookup"><span data-stu-id="5596a-367">Formatting Conventions</span></span> ##

<span data-ttu-id="5596a-368">Az előző javaslatok mellett hasznos lehet a kód a lehető legkönnyebben felismerhetővé tétele a konzisztens formázási szabályok használatához.</span><span class="sxs-lookup"><span data-stu-id="5596a-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="5596a-369">A természet szerinti formázási szabályok általában némileg önkényesak és szigorúan személyes esztétikai jellegűek.</span><span class="sxs-lookup"><span data-stu-id="5596a-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="5596a-370">Ugyanakkor javasolt a formázási konvenciók egységes csoportjának fenntartása a közreműködők csoportjain belül, és különösen a nagy Q # projektekhez, például a Quantum Development Kit-hoz.</span><span class="sxs-lookup"><span data-stu-id="5596a-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="5596a-371">Ezek a szabályok automatikusan alkalmazhatók a Q # fordítóprogrammal integrált formázó eszköz használatával.</span><span class="sxs-lookup"><span data-stu-id="5596a-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="5596a-372">Útmutató</span><span class="sxs-lookup"><span data-stu-id="5596a-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="5596a-373">Javasoljuk, hogy:</span><span class="sxs-lookup"><span data-stu-id="5596a-373">We suggest:</span></span>

- <span data-ttu-id="5596a-374">A hordozhatósághoz tabulátorok helyett négy szóközt használjon.</span><span class="sxs-lookup"><span data-stu-id="5596a-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="5596a-375">Például a VS Code-ban:</span><span class="sxs-lookup"><span data-stu-id="5596a-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="5596a-376">A sortörés 79 karakternél, ahol ésszerű.</span><span class="sxs-lookup"><span data-stu-id="5596a-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="5596a-377">Használjon szóközöket a bináris operátorok köré.</span><span class="sxs-lookup"><span data-stu-id="5596a-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="5596a-378">Használjon szóközöket a típushoz tartozó kettőspontok egyik oldalán.</span><span class="sxs-lookup"><span data-stu-id="5596a-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="5596a-379">A tömbben és a rekordokban lévő literálokban (például a functions és a Operations műveletekben) használt vesszők után egyetlen helyet használjon.</span><span class="sxs-lookup"><span data-stu-id="5596a-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="5596a-380">Ne használjon szóközt a függvény, a művelet vagy a UDT neve után, vagy a `@` in attribútum deklarációja után.</span><span class="sxs-lookup"><span data-stu-id="5596a-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="5596a-381">Minden attribútum deklarációjának saját sorban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="5596a-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="5596a-382">Példák</span><span class="sxs-lookup"><span data-stu-id="5596a-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5596a-383">Snippet</span><span class="sxs-lookup"><span data-stu-id="5596a-383">Snippet</span></span> | <span data-ttu-id="5596a-384">Leírás</span><span class="sxs-lookup"><span data-stu-id="5596a-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="5596a-385">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="5596a-386">Használjon szóközöket a bináris operátorok köré.</span><span class="sxs-lookup"><span data-stu-id="5596a-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="5596a-387">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="5596a-388">Használjon szóközt a típus megjegyzési kettőspontok használatával.</span><span class="sxs-lookup"><span data-stu-id="5596a-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="5596a-389">☑</span><span class="sxs-lookup"><span data-stu-id="5596a-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="5596a-390">A bemeneti rekordban lévő elemek megfelelően vannak elfoglalva az olvashatóság érdekében.</span><span class="sxs-lookup"><span data-stu-id="5596a-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="5596a-391">☒</span><span class="sxs-lookup"><span data-stu-id="5596a-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="5596a-392">A szóközöket a függvény, a művelet vagy a UDT neve után le kell tiltani.</span><span class="sxs-lookup"><span data-stu-id="5596a-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

