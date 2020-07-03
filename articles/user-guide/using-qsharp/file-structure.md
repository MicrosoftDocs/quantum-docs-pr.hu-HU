---
title: 'Q # fájl szerkezete'
description: 'A Q # fájl szerkezetét és szintaxisát ismerteti.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884177"
---
# <a name="q-file-structure"></a><span data-ttu-id="88a4e-103">Q # fájl szerkezete</span><span class="sxs-lookup"><span data-stu-id="88a4e-103">Q# File Structure</span></span>

<span data-ttu-id="88a4e-104">A Q # fájl *névtér-deklarációk*sorozatából áll.</span><span class="sxs-lookup"><span data-stu-id="88a4e-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="88a4e-105">Minden névtér-deklaráció a felhasználó által definiált típusokra, műveletekre és függvényekre vonatkozó deklarációkat tartalmaz, és tetszőleges számú deklarációt és sorrendet is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="88a4e-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="88a4e-106">A névtéren belüli deklarációkkal kapcsolatos további információkért lásd: [felhasználó által definiált típusok](xref:microsoft.quantum.guide.types#user-defined-types), [műveletek](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)és [függvények](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span><span class="sxs-lookup"><span data-stu-id="88a4e-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="88a4e-107">A névtér deklarációján kívül megjelenő szöveg Megjegyzés.</span><span class="sxs-lookup"><span data-stu-id="88a4e-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="88a4e-108">Különösen a deklaráció előtt a névtérhez tartozó dokumentációs megjegyzések szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="88a4e-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="88a4e-109">További információ: [dokumentációs megjegyzések](#documentation-comments) ebben a cikkben.</span><span class="sxs-lookup"><span data-stu-id="88a4e-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="88a4e-110">Névtér-deklarációk</span><span class="sxs-lookup"><span data-stu-id="88a4e-110">Namespace Declarations</span></span>

<span data-ttu-id="88a4e-111">A Q # fájlnak általában csak egy névtér-deklarációja van, de a none (és nem lehet üres, vagy csak megjegyzéseket tartalmazhat), vagy több névteret tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="88a4e-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="88a4e-112">A névtér deklarációi nem ágyazhatók egymásba.</span><span class="sxs-lookup"><span data-stu-id="88a4e-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="88a4e-113">Megadhatja ugyanazt a névteret több, egymással összeállított Q #-fájlban, feltéve, hogy nincs ilyen nevű típus, művelet vagy függvény deklarációja.</span><span class="sxs-lookup"><span data-stu-id="88a4e-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="88a4e-114">Bizonyos esetben a több fájl azonos névterében lévő azonos típust nem lehet megadnia, még akkor is, ha a deklarációk azonosak.</span><span class="sxs-lookup"><span data-stu-id="88a4e-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="88a4e-115">A névtér deklarációja a kulcsszóból áll `namespace` , amelyet a névtér neve, valamint a névtérben található, kapcsos zárójelek közé tartozó deklarációk követnek `{ }` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="88a4e-116">A névterek nevei egy vagy több, ponttal elválasztott jogi szimbólum sorozatának .NET-mintáját követik `.` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="88a4e-117">Például `MyQuantumStuff` és `Microsoft.Quantum.Intrinsic` érvényes névterek nevei.</span><span class="sxs-lookup"><span data-stu-id="88a4e-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="88a4e-118">A (z) konvenció szerint kihasználja a névterek nevét, azonban ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="88a4e-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="88a4e-119">A fájlokban a fájlban lejjebb szereplő típusokra vagy callables mutató hivatkozások megfelelően vannak deklarálva; nincs szükség a típus, a művelet vagy a függvény deklarációjának megírására a hivatkozás előtt.</span><span class="sxs-lookup"><span data-stu-id="88a4e-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="88a4e-120">Megnyitási irányelvek</span><span class="sxs-lookup"><span data-stu-id="88a4e-120">Open Directives</span></span>

<span data-ttu-id="88a4e-121">Egy névtérbeli blokkon belül a `open` direktívával importálhat egy adott névtérben deklarált összes típust és callables, és azok nem minősített nevük alapján is hivatkozhat rájuk.</span><span class="sxs-lookup"><span data-stu-id="88a4e-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="88a4e-122">Egy ilyen `open` irányelv a `open` kulcsszóból áll, amelyet a megnyitandó névtér és a lezáró pontosvessző követ.</span><span class="sxs-lookup"><span data-stu-id="88a4e-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="88a4e-123">`open`Az összes direktívának szerepelnie `function` kell `operation` `newtype` a névtér blokkjában, a vagy deklaráció előtt.</span><span class="sxs-lookup"><span data-stu-id="88a4e-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="88a4e-124">Igény szerint megadhat egy rövid nevet a megnyitott névtérhez.</span><span class="sxs-lookup"><span data-stu-id="88a4e-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="88a4e-125">Ha meg van adva egy rövid név, a megadott rövid névvel meg kell felelnie a névtér összes elemének.</span><span class="sxs-lookup"><span data-stu-id="88a4e-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="88a4e-126">Például a következő névtér-deklaráció és a megnyitási irányelvek miatt</span><span class="sxs-lookup"><span data-stu-id="88a4e-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="88a4e-127">Ha egy deklarált művelet `Op` a-ból származó műveletet használ `Microsoft.Quantum.Intrinsic` , egyszerűen hívja meg a következő használatával: `Op` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="88a4e-128">Ahhoz azonban, hogy egy bizonyos függvényt meghívjon `Fn` `Microsoft.Quantum.Math` , azt a használatával kell meghívnia `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="88a4e-129">Az `open` irányelv a teljes névtér-blokkra vonatkozik egy fájlon belül.</span><span class="sxs-lookup"><span data-stu-id="88a4e-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="88a4e-130">Ezért ha egy további névteret határoz meg ugyanabban a Q # fájlban, mint `NS` korábban, akkor a második névtérben definiált összes művelet/függvény/típus nem fér hozzá semmihez, `Microsoft.Quantum.Intrinsic` vagy `Microsoft.Quantum.Math` csak abban az esetben, ha megismétli a megnyitott irányelveket.</span><span class="sxs-lookup"><span data-stu-id="88a4e-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="88a4e-131">Ha olyan típusra vagy hívható hivatkozásra szeretne hivatkozni, amely *nem* az aktuális névtérben van megnyitva, akkor azt a teljesen minősített névvel kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="88a4e-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="88a4e-132">Például `Op` a névtérből megnevezett művelet miatt `X.Y` :</span><span class="sxs-lookup"><span data-stu-id="88a4e-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="88a4e-133">Ezt a teljes név alapján kell megadnia `X.Y.Op` , kivéve, ha a `X.Y` névteret már korábban megnyitották az aktuális blokkban.</span><span class="sxs-lookup"><span data-stu-id="88a4e-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="88a4e-134">Még ha a `X` névtér is meg van nyitva, a műveletre nem lehet hivatkozni `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="88a4e-135">Ha a rövid nevet adta meg `Z` a `X.Y` névtérben és a fájlban, a következőre kell hivatkoznia: `Op` `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="88a4e-136">Általában jobb, ha egy direktíva segítségével egy névteret is tartalmaz `open` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="88a4e-137">Teljesen minősített név használata kötelező, ha két névtér definiálja ugyanazt a nevet, és a jelenlegi forrás mindkettőből származó szerkezeteket használ.</span><span class="sxs-lookup"><span data-stu-id="88a4e-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="88a4e-138">A Q # ugyanazokat a szabályokat követi, mint az egyéb .NET-nyelvek elnevezése.</span><span class="sxs-lookup"><span data-stu-id="88a4e-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="88a4e-139">A Q # azonban nem támogatja a névterek relatív hivatkozásait.</span><span class="sxs-lookup"><span data-stu-id="88a4e-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="88a4e-140">Ha például a névtér `a.b` meg van nyitva, egy nevű műveletre mutató hivatkozás `c.d` *nem* oldható fel teljes nevű műveletre `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="88a4e-141">Formátum</span><span class="sxs-lookup"><span data-stu-id="88a4e-141">Formatting</span></span>

<span data-ttu-id="88a4e-142">A legtöbb Q # utasítás és direktíva véget ér a záró pontosvesszővel `;` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="88a4e-143">Az olyan utasítások és deklarációk, mint a `for` és az `operation` egy utasítás blokkja (lásd a következő szakaszt) nem igénylik a megszakítást pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="88a4e-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="88a4e-144">Minden utasítás leírása megállapítja, hogy kötelező-e lezáró pontosvessző.</span><span class="sxs-lookup"><span data-stu-id="88a4e-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="88a4e-145">Az utasítások, például a kifejezések, a deklarációk és az irányelvek több sorban is kibonthatók.</span><span class="sxs-lookup"><span data-stu-id="88a4e-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="88a4e-146">Kerülje a több utasítás egyetlen sorra való elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="88a4e-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="88a4e-147">Utasítások blokkja</span><span class="sxs-lookup"><span data-stu-id="88a4e-147">Statement Blocks</span></span>

<span data-ttu-id="88a4e-148">A Q # utasítások a kapcsos zárójelek közé tartozó utasítási blokkokba vannak csoportosítva `{ }` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="88a4e-149">Egy utasítás-blokk egy nyitó karakterrel kezdődik, `{` és egy zárással végződik `}` .</span><span class="sxs-lookup"><span data-stu-id="88a4e-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="88a4e-150">Egy másik blokkban található, lexikálisan zárt utasítási blokk a tartalmazó blokk alblokkjának tekintendő; a és az alblokkokat külső és belső blokkoknak is nevezik.</span><span class="sxs-lookup"><span data-stu-id="88a4e-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="88a4e-151">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="88a4e-151">Comments</span></span>

<span data-ttu-id="88a4e-152">A megjegyzések két továbbítási perjeltel kezdődnek, `//` és a sor végéig folytatódnak.</span><span class="sxs-lookup"><span data-stu-id="88a4e-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="88a4e-153">A megjegyzések bárhol megjelenhetnek a Q # forrásfájlban.</span><span class="sxs-lookup"><span data-stu-id="88a4e-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="88a4e-154">Dokumentációs megjegyzések</span><span class="sxs-lookup"><span data-stu-id="88a4e-154">Documentation Comments</span></span>

<span data-ttu-id="88a4e-155">A három továbbítási perjeltel kezdődő megjegyzéseket `///` a fordító kifejezetten akkor kezeli, ha közvetlenül a névtér, a művelet, a specializáció, a függvény vagy a típus definíciója előtt jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="88a4e-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="88a4e-156">Ebben az esetben a fordító dokumentációként kezeli őket a definiált vagy felhasználó által definiált típushoz, ugyanúgy, mint a többi .NET-nyelvre.</span><span class="sxs-lookup"><span data-stu-id="88a4e-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="88a4e-157">A `///` megjegyzéseken belül az API dokumentációjának részeként megjelenő szöveg [Markdown](https://daringfireball.net/projects/markdown/syntax)van formázva, a dokumentáció különböző részeivel, amelyeket a speciális névvel ellátott fejlécek jeleznek.</span><span class="sxs-lookup"><span data-stu-id="88a4e-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="88a4e-158">A Markdown használja a `@"<ref target>"` bővítményt a Q #-ban a kereszthivatkozási műveletekhez, a függvényekhez és a felhasználó által definiált típusokhoz.</span><span class="sxs-lookup"><span data-stu-id="88a4e-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="88a4e-159">Cserélje le a helyére a `<ref target>` hivatkozott kód objektum teljes nevét.</span><span class="sxs-lookup"><span data-stu-id="88a4e-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="88a4e-160">A különböző dokumentációs motorok további Markdown-bővítményeket is támogatnak.</span><span class="sxs-lookup"><span data-stu-id="88a4e-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="88a4e-161">Például:</span><span class="sxs-lookup"><span data-stu-id="88a4e-161">For example:</span></span>

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

<span data-ttu-id="88a4e-162">A következő nevek érvényesek a dokumentációs Megjegyzés fejlécei.</span><span class="sxs-lookup"><span data-stu-id="88a4e-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="88a4e-163">**Összefoglalás**: egy függvény vagy művelet viselkedésének vagy egy típus célnak a rövid összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="88a4e-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="88a4e-164">Az összefoglalás első bekezdése a hover-információkhoz használatos.</span><span class="sxs-lookup"><span data-stu-id="88a4e-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="88a4e-165">Egyszerű szövegnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="88a4e-165">It should be plain text.</span></span>
- <span data-ttu-id="88a4e-166">**Leírás**: egy függvény vagy művelet viselkedésének vagy egy típus céljának a leírása.</span><span class="sxs-lookup"><span data-stu-id="88a4e-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="88a4e-167">Az összefoglalás és a Leírás együttesen a függvény, művelet vagy típus számára létrehozott dokumentációs fájlt alkotja.</span><span class="sxs-lookup"><span data-stu-id="88a4e-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="88a4e-168">A Leírás támogatja a beépített LaTeX formátumú szimbólumokat és egyenleteket.</span><span class="sxs-lookup"><span data-stu-id="88a4e-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="88a4e-169">**Bemenet**: egy művelet vagy függvény bemeneti rekordjának leírása.</span><span class="sxs-lookup"><span data-stu-id="88a4e-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="88a4e-170">Tartalmazhat további Markdown alszakaszokat is, amelyek a bemeneti rekord egyes elemeit jelzik.</span><span class="sxs-lookup"><span data-stu-id="88a4e-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="88a4e-171">**Kimenet**: egy művelet vagy függvény által visszaadott rekord leírása.</span><span class="sxs-lookup"><span data-stu-id="88a4e-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="88a4e-172">**Type Parameters**: üres szakasz, amely minden általános típusparaméter esetében egy további alszakaszt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="88a4e-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="88a4e-173">**Példa**: a művelet, a függvény vagy a típus használatának rövid példája.</span><span class="sxs-lookup"><span data-stu-id="88a4e-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="88a4e-174">**Megjegyzések**: a művelet, a függvény vagy a típus néhány aspektusát ismertető egyéb próza.</span><span class="sxs-lookup"><span data-stu-id="88a4e-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="88a4e-175">**Lásd még**: a kapcsolódó függvényeket, műveleteket vagy felhasználó által meghatározott típusokat jelölő teljes nevek listája.</span><span class="sxs-lookup"><span data-stu-id="88a4e-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="88a4e-176">**Hivatkozások**: a dokumentált elemre vonatkozó hivatkozások és idézetek listája.</span><span class="sxs-lookup"><span data-stu-id="88a4e-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="88a4e-177">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="88a4e-177">Next steps</span></span>

<span data-ttu-id="88a4e-178">További információ a Q #-ban [végzett műveletekről és függvényekről](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="88a4e-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>