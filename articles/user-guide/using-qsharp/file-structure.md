---
title: 'Q # fájl szerkezete'
description: 'A Q # fájl szerkezetét és szintaxisát ismerteti.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430968"
---
# <a name="q-file-structure"></a><span data-ttu-id="6f73b-103">Q # fájl szerkezete</span><span class="sxs-lookup"><span data-stu-id="6f73b-103">Q# File Structure</span></span>

<span data-ttu-id="6f73b-104">Minden Q # művelet, függvény és felhasználó által definiált típus definiálva van egy névtéren belül.</span><span class="sxs-lookup"><span data-stu-id="6f73b-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="6f73b-105">A Q # fájl *névtér-deklarációk*sorozatából áll.</span><span class="sxs-lookup"><span data-stu-id="6f73b-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="6f73b-106">Minden névtér deklarációja a felhasználó által definiált típusokra, műveletekre és függvényekre vonatkozó deklarációkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6f73b-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="6f73b-107">A névtér-deklarációk tetszőleges számú deklarációt tartalmazhatnak, és bármilyen sorrendben megadhatók.</span><span class="sxs-lookup"><span data-stu-id="6f73b-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="6f73b-108">Az alábbi hivatkozásokra kattintva további részleteket tudhat meg a [felhasználó által definiált típusokról](xref:microsoft.quantum.guide.types#user-defined-types), [műveletekről](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)és [függvényekről](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) a névtéren belül.</span><span class="sxs-lookup"><span data-stu-id="6f73b-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="6f73b-109">A névtér deklarációján kívül megjelenő szöveg Megjegyzés.</span><span class="sxs-lookup"><span data-stu-id="6f73b-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="6f73b-110">A dokumentációval kapcsolatos megjegyzések (az alábbi további részletek) a deklaráció előtt találhatók a névtérhez.</span><span class="sxs-lookup"><span data-stu-id="6f73b-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="6f73b-111">Névtér-deklarációk</span><span class="sxs-lookup"><span data-stu-id="6f73b-111">Namespace Declarations</span></span>

<span data-ttu-id="6f73b-112">A Q # fájlnak általában pontosan egy névtér-deklarációja lesz, de a none (és nem lehet üres, vagy csak megjegyzéseket tartalmazhat), vagy több névteret is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="6f73b-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="6f73b-113">Előfordulhat, hogy a névtér-deklarációk nem ágyazhatók egymásba.</span><span class="sxs-lookup"><span data-stu-id="6f73b-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="6f73b-114">Előfordulhat, hogy ugyanaz a névtér több, összeállított Q # fájlban van deklarálva, feltéve, hogy nincs ilyen nevű típus, művelet vagy függvény deklarációja.</span><span class="sxs-lookup"><span data-stu-id="6f73b-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="6f73b-115">Bizonyos esetben a több fájl azonos névterében lévő azonos típust nem lehet megadnia, még akkor is, ha a deklarációk azonosak.</span><span class="sxs-lookup"><span data-stu-id="6f73b-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="6f73b-116">A névtér deklarációja a kulcsszóból áll `namespace` , amelyet a névtér neve, egy nyitott kapcsos zárójel `{` , a névtérben található deklarációk és egy záró zárójel követ `}` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="6f73b-117">A névterek nevei egy vagy több, ponttal elválasztott jogi szimbólum sorozatának .NET-mintáját követik `.` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="6f73b-118">Például a `MyQuantumStuff` és az `Microsoft.Quantum.Intrinsic` érvényes névterek nevei.</span><span class="sxs-lookup"><span data-stu-id="6f73b-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="6f73b-119">Az egyezmény szerint a névtér nevében szereplő szimbólumok tőkésítve vannak, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="6f73b-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="6f73b-120">A fájlokban lejjebb deklarált típusokra vagy callables mutató hivatkozások megfelelően vannak feloldva; nincs szükség a típus, a művelet vagy a függvény deklarációjának megírására a hivatkozás előtt.</span><span class="sxs-lookup"><span data-stu-id="6f73b-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="6f73b-121">Megnyitási irányelvek</span><span class="sxs-lookup"><span data-stu-id="6f73b-121">Open Directives</span></span>

<span data-ttu-id="6f73b-122">Egy névtér-blokkon belül az `open` direktíva egy adott névtérben deklarált összes típus és callables importálására használható, és nem minősített nevük alapján.</span><span class="sxs-lookup"><span data-stu-id="6f73b-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="6f73b-123">Egy ilyen `open` irányelv a `open` kulcsszóból áll, amelyet a megnyitandó névtér és a lezáró pontosvessző követ.</span><span class="sxs-lookup"><span data-stu-id="6f73b-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="6f73b-124">`open`Az összes direktívának szerepelnie `function` kell `operation` `newtype` a névtér blokkjában, a vagy deklaráció előtt.</span><span class="sxs-lookup"><span data-stu-id="6f73b-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="6f73b-125">Ha szükséges, a megnyitott névtérhez tartozó rövid név is meghatározható úgy, hogy az adott névtérből származó összes elemet (és szükség esetén) a megadott rövid névvel kell minősíteni.</span><span class="sxs-lookup"><span data-stu-id="6f73b-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="6f73b-126">Például a következő névtér-deklaráció és a megnyitási irányelvek miatt</span><span class="sxs-lookup"><span data-stu-id="6f73b-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="6f73b-127">Ha a deklarált művelet egy műveletet használ `Op` a `Microsoft.Quantum.Intrinsic` alkalmazásból, akkor egyszerűen csak a használatával hívjuk meg `Op` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="6f73b-128">Ha azonban egy bizonyos függvényt hív meg, akkor azt a `Fn` `Microsoft.Quantum.Math` használatával kell meghívni `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="6f73b-129">Az `open` irányelv a teljes névtér-blokkra vonatkozik egy fájlon belül.</span><span class="sxs-lookup"><span data-stu-id="6f73b-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="6f73b-130">Ezért ha egy további névteret definiálunk a fenti Q # fájlban `NS` , akkor a második névtérben definiált összes művelet/függvény/típus nem férhet hozzá a ( `Microsoft.Quantum.Intrinsic` vagy) nem a `Microsoft.Quantum.Math` nyílt irányelvek megismétléséhez, vagy nem.</span><span class="sxs-lookup"><span data-stu-id="6f73b-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="6f73b-131">Egy másik névtérben definiált típust vagy meghívást, amelyet a jelenlegi névtérben *nem* nyitott meg, a teljes névvel kell hivatkozni.</span><span class="sxs-lookup"><span data-stu-id="6f73b-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="6f73b-132">Például a névtérből megnevezett műveletnek a `Op` `X.Y` teljesen minősített nevével kell hivatkoznia `X.Y.Op` , kivéve, ha a `X.Y` névteret az aktuális blokkban korábban megnyitották.</span><span class="sxs-lookup"><span data-stu-id="6f73b-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="6f73b-133">Ahogy fent említettük, még akkor is, ha a `X` névteret megnyitották, nem lehet a műveletre hivatkozni `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="6f73b-134">Ha egy rövid név `Z` `X.Y` van definiálva a névtérben és a fájlban, akkor a következőnek `Op` kell lennie: `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="6f73b-135">Általában jobb, ha egy direktíva segítségével egy névteret is tartalmaz `open` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="6f73b-136">Teljesen minősített név használata kötelező, ha két névtér definiálja ugyanazt a nevet, és a jelenlegi forrás mindkettőből származó szerkezeteket használ.</span><span class="sxs-lookup"><span data-stu-id="6f73b-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="6f73b-137">A Q # ugyanazokat a szabályokat követi, mint az egyéb .NET-nyelvek elnevezése.</span><span class="sxs-lookup"><span data-stu-id="6f73b-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="6f73b-138">A Q # azonban nem támogatja a névterek relatív hivatkozásait.</span><span class="sxs-lookup"><span data-stu-id="6f73b-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="6f73b-139">Ha a névtér `a.b` meg lett nyitva, a nevű műveletre mutató hivatkozás `c.d` *nem* oldható fel teljes névvel rendelkező művelethez `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="6f73b-140">Formátum</span><span class="sxs-lookup"><span data-stu-id="6f73b-140">Formatting</span></span>

<span data-ttu-id="6f73b-141">A legtöbb Q # utasítás és direktíva véget ér a záró pontosvesszővel `;` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="6f73b-142">Az olyan utasítások és nyilatkozatok, mint a `for` és az `operation` egy utasítás blokkja (lásd alább) nem igénylik a megszakítást pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="6f73b-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="6f73b-143">Minden utasítás leírása megállapítja, hogy kötelező-e lezáró pontosvessző.</span><span class="sxs-lookup"><span data-stu-id="6f73b-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="6f73b-144">Az utasítások, például a kifejezések, a deklarációk és az irányelvek több sorban is kibonthatók.</span><span class="sxs-lookup"><span data-stu-id="6f73b-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="6f73b-145">Az egyetlen sorban több utasítást kell elkerülni.</span><span class="sxs-lookup"><span data-stu-id="6f73b-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="6f73b-146">Utasítások blokkja</span><span class="sxs-lookup"><span data-stu-id="6f73b-146">Statement Blocks</span></span>

<span data-ttu-id="6f73b-147">A Q # utasítások utasítás blokkokba vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="6f73b-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="6f73b-148">Egy utasítás-blokk egy nyitó karakterrel kezdődik, `{` és egy zárással végződik `}` .</span><span class="sxs-lookup"><span data-stu-id="6f73b-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="6f73b-149">Egy másik blokkban található, lexikálisan zárt utasítási blokk a tartalmazó blokk alblokkjának tekintendő; a és az alblokkokat külső és belső blokkoknak is nevezik.</span><span class="sxs-lookup"><span data-stu-id="6f73b-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="6f73b-150">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6f73b-150">Comments</span></span>

<span data-ttu-id="6f73b-151">A megjegyzések két továbbítási ferde vonallal kezdődnek, `//` és a sor végéig folytatódnak.</span><span class="sxs-lookup"><span data-stu-id="6f73b-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="6f73b-152">Egy Megjegyzés a Q # forrásfájlban bárhol megjelenhet.</span><span class="sxs-lookup"><span data-stu-id="6f73b-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="6f73b-153">Dokumentációs megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6f73b-153">Documentation Comments</span></span>

<span data-ttu-id="6f73b-154">A három továbbítási perjeltel kezdődő megjegyzéseket `///` a fordító kifejezetten akkor kezeli, ha közvetlenül a névtér, a művelet, a specializáció, a függvény vagy a típus definíciója előtt jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="6f73b-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="6f73b-155">Ebben az esetben a tartalmuk a definiált vagy felhasználó által definiált, a többi .NET-nyelvhez hasonlóan dokumentációként szolgál.</span><span class="sxs-lookup"><span data-stu-id="6f73b-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="6f73b-156">A `///` megjegyzéseken belül az API dokumentációjának részeként megjelenítendő szöveg [Markdown](https://daringfireball.net/projects/markdown/syntax)van formázva, és a dokumentáció különböző részeit a speciális névvel ellátott fejlécek jelölik.</span><span class="sxs-lookup"><span data-stu-id="6f73b-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="6f73b-157">A Markdown kiterjesztéseként a Q # által a műveletekre, a függvényekre és a felhasználó által definiált típusokra mutató kereszthivatkozások a (z) használatával is szerepelhetnek, ahol a a `@"<ref target>"` `<ref target>` hivatkozott kód objektum teljesen minősített nevével helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="6f73b-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="6f73b-158">Szükség esetén a dokumentációs motor további Markdown-bővítményeket is támogat.</span><span class="sxs-lookup"><span data-stu-id="6f73b-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="6f73b-159">Például:</span><span class="sxs-lookup"><span data-stu-id="6f73b-159">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="6f73b-160">A rendszer a következő neveket ismeri fel dokumentációs Megjegyzés fejlécként.</span><span class="sxs-lookup"><span data-stu-id="6f73b-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="6f73b-161">**Összefoglalás**: egy függvény vagy művelet viselkedésének, vagy egy típus céljának rövid összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="6f73b-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="6f73b-162">Az összefoglalás első bekezdése a hover-információkhoz használatos.</span><span class="sxs-lookup"><span data-stu-id="6f73b-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="6f73b-163">Egyszerű szövegnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6f73b-163">It should be plain text.</span></span>
- <span data-ttu-id="6f73b-164">**Leírás**: függvény vagy művelet viselkedésének vagy egy típusnak a leírása.</span><span class="sxs-lookup"><span data-stu-id="6f73b-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="6f73b-165">Az összefoglalás és a Leírás össze van fűzve, hogy a generált dokumentációs fájlt hozza létre a függvényhez, a művelethez vagy a típushoz.</span><span class="sxs-lookup"><span data-stu-id="6f73b-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="6f73b-166">A Leírás tartalmazhat beágyazott LaTeX-formátumú szimbólumokat és egyenleteket is.</span><span class="sxs-lookup"><span data-stu-id="6f73b-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="6f73b-167">**Bemenet**: egy művelet vagy függvény bemeneti rekordjának leírása.</span><span class="sxs-lookup"><span data-stu-id="6f73b-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="6f73b-168">Tartalmazhat további Markdown alszakaszokat is, amelyek a bemeneti rekord egyes elemeit jelzik.</span><span class="sxs-lookup"><span data-stu-id="6f73b-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="6f73b-169">**Kimenet**: egy művelet vagy függvény által visszaadott rekord leírása.</span><span class="sxs-lookup"><span data-stu-id="6f73b-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="6f73b-170">**Type Parameters**: üres szakasz, amely minden általános típusparaméter esetében egy további alszakaszt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6f73b-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="6f73b-171">**Példa**: egy rövid példa a művelet, a függvény vagy a típus használatban.</span><span class="sxs-lookup"><span data-stu-id="6f73b-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="6f73b-172">**Megjegyzések**: a művelet, a függvény vagy a típus néhány aspektusát ismertető egyéb próza.</span><span class="sxs-lookup"><span data-stu-id="6f73b-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="6f73b-173">**Lásd még**: a kapcsolódó függvényeket, műveleteket vagy felhasználó által meghatározott típusokat jelölő teljes nevek listája.</span><span class="sxs-lookup"><span data-stu-id="6f73b-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="6f73b-174">**Hivatkozások**: a dokumentált elemre vonatkozó hivatkozások és idézetek listája.</span><span class="sxs-lookup"><span data-stu-id="6f73b-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="whats-next"></a><span data-ttu-id="6f73b-175">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="6f73b-175">What's Next?</span></span>
<span data-ttu-id="6f73b-176">További információ a Q #-ban [végzett műveletekről és függvényekről](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="6f73b-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>