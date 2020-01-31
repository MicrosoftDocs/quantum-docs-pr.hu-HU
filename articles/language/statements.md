---
title: 'Q # utasítások | Microsoft Docs'
description: 'Q # utasítások'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9157cf3336ce0894816dbfbaf13ce0e712a6b096
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821065"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="73f5f-103">Utasítások és egyéb szerkezetek</span><span class="sxs-lookup"><span data-stu-id="73f5f-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="73f5f-104">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="73f5f-104">Comments</span></span>

<span data-ttu-id="73f5f-105">A megjegyzések két továbbítási perjeltel kezdődnek, `//`, és a sor végéig folytatódnak.</span><span class="sxs-lookup"><span data-stu-id="73f5f-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="73f5f-106">Egy Megjegyzés a Q # forrásfájlban bárhol megjelenhet.</span><span class="sxs-lookup"><span data-stu-id="73f5f-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="73f5f-107">Dokumentációs megjegyzések</span><span class="sxs-lookup"><span data-stu-id="73f5f-107">Documentation Comments</span></span>

<span data-ttu-id="73f5f-108">A három továbbítási perjelet, `///`t tartalmazó megjegyzéseket a fordító kifejezetten akkor kezeli, ha közvetlenül a névtér, a művelet, a specializáció, a függvény vagy a típus definíciója előtt jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="73f5f-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="73f5f-109">Ebben az esetben a tartalmuk a definiált vagy felhasználó által definiált, a többi .NET-nyelvhez hasonlóan dokumentációként szolgál.</span><span class="sxs-lookup"><span data-stu-id="73f5f-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="73f5f-110">`///` megjegyzésekben az API dokumentációjának részeként megjelenő szöveg [Markdown](https://daringfireball.net/projects/markdown/syntax)van formázva, és a dokumentáció különböző részeit a speciális névvel ellátott fejlécek jelölik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="73f5f-111">A Markdown bővítmény a műveletekre, a függvényekre és a felhasználó által definiált típusokra mutató hivatkozásokat tartalmazhatja a Q #-ban a `@"<ref target>"`használatával, ahol a `<ref target>` a hivatkozott kód objektum teljesen minősített nevével helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="73f5f-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="73f5f-112">Szükség esetén a dokumentációs motor további Markdown-bővítményeket is támogat.</span><span class="sxs-lookup"><span data-stu-id="73f5f-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="73f5f-113">Példa:</span><span class="sxs-lookup"><span data-stu-id="73f5f-113">For example:</span></span>

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

<span data-ttu-id="73f5f-114">A rendszer a következő neveket ismeri fel dokumentációs Megjegyzés fejlécként.</span><span class="sxs-lookup"><span data-stu-id="73f5f-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="73f5f-115">**Összefoglalás**: egy függvény vagy művelet viselkedésének, vagy egy típus céljának rövid összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="73f5f-116">Az összefoglalás első bekezdése a hover-információkhoz használatos.</span><span class="sxs-lookup"><span data-stu-id="73f5f-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="73f5f-117">Egyszerű szövegnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="73f5f-117">It should be plain text.</span></span>
- <span data-ttu-id="73f5f-118">**Leírás**: függvény vagy művelet viselkedésének vagy egy típusnak a leírása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="73f5f-119">Az összefoglalás és a Leírás össze van fűzve, hogy a generált dokumentációs fájlt hozza létre a függvényhez, a művelethez vagy a típushoz.</span><span class="sxs-lookup"><span data-stu-id="73f5f-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="73f5f-120">A Leírás tartalmazhat beágyazott LaTeX-formátumú szimbólumokat és egyenleteket is.</span><span class="sxs-lookup"><span data-stu-id="73f5f-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="73f5f-121">**Bemenet**: egy művelet vagy függvény bemeneti rekordjának leírása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="73f5f-122">Tartalmazhat további Markdown alszakaszokat is, amelyek a bemeneti rekord egyes elemeit jelzik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="73f5f-123">**Kimenet**: egy művelet vagy függvény által visszaadott rekord leírása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="73f5f-124">**Type Parameters**: üres szakasz, amely minden általános típusparaméter esetében egy további alszakaszt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="73f5f-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="73f5f-125">**Példa**: egy rövid példa a művelet, a függvény vagy a típus használatban.</span><span class="sxs-lookup"><span data-stu-id="73f5f-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="73f5f-126">**Megjegyzések**: a művelet, a függvény vagy a típus néhány aspektusát ismertető egyéb próza.</span><span class="sxs-lookup"><span data-stu-id="73f5f-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="73f5f-127">**Lásd még**: a kapcsolódó függvényeket, műveleteket vagy felhasználó által meghatározott típusokat jelölő teljes nevek listája.</span><span class="sxs-lookup"><span data-stu-id="73f5f-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="73f5f-128">**Hivatkozások**: a dokumentált elemre vonatkozó hivatkozások és idézetek listája.</span><span class="sxs-lookup"><span data-stu-id="73f5f-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="73f5f-129">Névterek</span><span class="sxs-lookup"><span data-stu-id="73f5f-129">Namespaces</span></span>

<span data-ttu-id="73f5f-130">Minden Q # művelet, függvény és felhasználó által definiált típus definiálva van egy névtéren belül.</span><span class="sxs-lookup"><span data-stu-id="73f5f-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="73f5f-131">A Q # ugyanazokat a szabályokat követi, mint az egyéb .NET-nyelvek elnevezése.</span><span class="sxs-lookup"><span data-stu-id="73f5f-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="73f5f-132">A Q # azonban nem támogatja a névterek relatív hivatkozásait.</span><span class="sxs-lookup"><span data-stu-id="73f5f-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="73f5f-133">Ha a névtér `a.b` megnyitása megtörtént, a rendszer nem oldja meg a műveleti nevekre mutató hivatkozást, `c.d` a teljes nevű művelet `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="73f5f-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="73f5f-134">Egy névtér-blokkon belül a `open` direktíva használható a megadott névtérben deklarált összes típus és callables importálására, és azok nem minősített nevük alapján.</span><span class="sxs-lookup"><span data-stu-id="73f5f-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="73f5f-135">Ha szükséges, a megnyitott névtérhez tartozó rövid név is meghatározható úgy, hogy az adott névtérből származó összes elemet (és szükség esetén) a megadott rövid névvel kell minősíteni.</span><span class="sxs-lookup"><span data-stu-id="73f5f-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="73f5f-136">A `open` direktíva a teljes névtér-blokkra vonatkozik a fájlban.</span><span class="sxs-lookup"><span data-stu-id="73f5f-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="73f5f-137">Egy másik névtérben definiált típust vagy meghívást, amelyet a jelenlegi névtérben nem nyitott meg, a teljes névvel kell hivatkozni.</span><span class="sxs-lookup"><span data-stu-id="73f5f-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="73f5f-138">Ha például egy `Op` nevű műveletet a `X.Y` névtérben kell megadnia, akkor a teljes neve `X.Y.Op`, kivéve, ha az aktuális blokkban korábban megnyitotta a `X.Y` névteret.</span><span class="sxs-lookup"><span data-stu-id="73f5f-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="73f5f-139">Ahogy fent említettük, még akkor is, ha a `X` névteret megnyitották, nem lehet a műveletre hivatkozni `Y.Op`ként.</span><span class="sxs-lookup"><span data-stu-id="73f5f-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="73f5f-140">Ha a névtérben és a fájlban a `X.Y` rövid neve `Z` lett definiálva, akkor `Op`nak `Z.Op`néven kell szerepelnie.</span><span class="sxs-lookup"><span data-stu-id="73f5f-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="73f5f-141">Általában jobb, ha a névteret egy `open` direktíva használatával is felveszi.</span><span class="sxs-lookup"><span data-stu-id="73f5f-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="73f5f-142">Teljesen minősített név használata kötelező, ha két névtér definiálja ugyanazt a nevet, és a jelenlegi forrás mindkettőből származó szerkezeteket használ.</span><span class="sxs-lookup"><span data-stu-id="73f5f-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="73f5f-143">Formátum</span><span class="sxs-lookup"><span data-stu-id="73f5f-143">Formatting</span></span>

<span data-ttu-id="73f5f-144">A legtöbb Q # utasítás és direktíva véget ér a pontosvesszővel, `;`.</span><span class="sxs-lookup"><span data-stu-id="73f5f-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="73f5f-145">Az olyan utasítások és deklarációk, mint például a `for` és `operation`, amelyek egy utasítási blokk végén nem igénylik a megszakítást pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="73f5f-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="73f5f-146">Minden utasítás leírása megállapítja, hogy kötelező-e lezáró pontosvessző.</span><span class="sxs-lookup"><span data-stu-id="73f5f-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="73f5f-147">Az utasítások, például a kifejezések, a deklarációk és az irányelvek több sorban is kibonthatók.</span><span class="sxs-lookup"><span data-stu-id="73f5f-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="73f5f-148">Az egyetlen sorban több utasítást kell elkerülni.</span><span class="sxs-lookup"><span data-stu-id="73f5f-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="73f5f-149">Utasítások blokkja</span><span class="sxs-lookup"><span data-stu-id="73f5f-149">Statement Blocks</span></span>

<span data-ttu-id="73f5f-150">A Q # utasítások utasítás blokkokba vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="73f5f-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="73f5f-151">Egy utasítás-blokk egy nyitó `{` kezdődik, és záró `}`végződik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="73f5f-152">Egy másik blokkban található, lexikálisan zárt utasítási blokk a tartalmazó blokk alblokkjának tekintendő; a és az alblokkokat külső és belső blokkoknak is nevezik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="73f5f-153">Szimbólum kötése és hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="73f5f-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="73f5f-154">A Q # megkülönbözteti a megváltoztathatatlan és a nem módosítható szimbólumokat.</span><span class="sxs-lookup"><span data-stu-id="73f5f-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="73f5f-155">Általánosságban a nem módosítható szimbólumok használata javasolt, mivel lehetővé teszi, hogy a fordító több optimalizációt végezzen.</span><span class="sxs-lookup"><span data-stu-id="73f5f-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="73f5f-156">A kötés bal oldali lapja egy szimbólumból álló rekordból és egy kifejezés jobb oldaláról áll.</span><span class="sxs-lookup"><span data-stu-id="73f5f-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="73f5f-157">Mivel az összes Q # típus a Value types – a qubits valamivel speciális szerepkört használ – a "Copy" szó akkor jön létre, amikor egy érték egy szimbólumhoz van kötve, vagy ha egy szimbólum van kötve.</span><span class="sxs-lookup"><span data-stu-id="73f5f-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="73f5f-158">Ez azt jelenti, hogy a Q # viselkedése megegyezik azzal, mintha egy másolat lett létrehozva a hozzárendelésen.</span><span class="sxs-lookup"><span data-stu-id="73f5f-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="73f5f-159">Ez különösen magában foglalja a tömböket is.</span><span class="sxs-lookup"><span data-stu-id="73f5f-159">This in particular also includes arrays.</span></span> <span data-ttu-id="73f5f-160">A gyakorlatban természetesen csak az érintett darabok szükségesek a létrehozásuk során.</span><span class="sxs-lookup"><span data-stu-id="73f5f-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="73f5f-161">Rekord kiépítése</span><span class="sxs-lookup"><span data-stu-id="73f5f-161">Tuple Deconstruction</span></span>

<span data-ttu-id="73f5f-162">Ha a kötés jobb oldalán egy rekord található, akkor a rekord a hozzárendelés után kiépíthető.</span><span class="sxs-lookup"><span data-stu-id="73f5f-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="73f5f-163">Ezek a dekonstrukciók beágyazott rekordok tartalmazhatnak, és a teljes vagy részleges kiépítés akkor érvényes, ha a jobb oldalon lévő rekord alakja kompatibilis a szimbólum rekordjának formájával.</span><span class="sxs-lookup"><span data-stu-id="73f5f-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="73f5f-164">A rekord Dekonstrukciója különösen akkor használható, ha a `=` jobb oldalán egy rekord értékű kifejezés szerepel.</span><span class="sxs-lookup"><span data-stu-id="73f5f-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="73f5f-165">Nem változtatható szimbólumok</span><span class="sxs-lookup"><span data-stu-id="73f5f-165">Immutable Symbols</span></span>

<span data-ttu-id="73f5f-166">A megváltoztathatatlan szimbólumok a `let` utasítással köthetők.</span><span class="sxs-lookup"><span data-stu-id="73f5f-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="73f5f-167">Ez nagyjából megegyezik a változó deklarációval és az inicializálással olyan nyelveken C#, mint például a Q # szimbólumok, ha a kötés nem módosítható; `let` kötések nem változtathatók meg.</span><span class="sxs-lookup"><span data-stu-id="73f5f-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="73f5f-168">A nem módosítható kötés a következő kulcsszóból áll: `let`, majd egy szimbólum vagy egy Symbol rekord, egy egyenlőségjel `=`, egy kifejezés, amely a szimbólum (oka) t köti, és leállítja a pontosvesszőt.</span><span class="sxs-lookup"><span data-stu-id="73f5f-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="73f5f-169">A kötött szimbólum (ok) típusa a jobb oldali kifejezésen alapul.</span><span class="sxs-lookup"><span data-stu-id="73f5f-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="73f5f-170">Változtatható szimbólumok</span><span class="sxs-lookup"><span data-stu-id="73f5f-170">Mutable Symbols</span></span>

<span data-ttu-id="73f5f-171">A megváltoztathatatlan szimbólumok meghatározása és inicializálása a `mutable` utasítás használatával történik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="73f5f-172">Előfordulhat, hogy egy `mutable` utasítás részeként deklarált és kötött szimbólumok a kód későbbi részében más értékre lesznek kötve.</span><span class="sxs-lookup"><span data-stu-id="73f5f-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="73f5f-173">A megváltoztathatatlan kötési utasítás a `mutable`kulcsszót, egy szimbólum vagy egy Symbol rekord, egy egyenlőségjel `=`, egy kifejezés, amely a szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.</span><span class="sxs-lookup"><span data-stu-id="73f5f-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="73f5f-174">A kötött szimbólum (ok) típusa a jobb oldali kifejezésen alapul.</span><span class="sxs-lookup"><span data-stu-id="73f5f-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="73f5f-175">Ha egy szimbólum később van kötve a kódban, a típusa nem változik, és a kötött értéknek kompatibilisnek kell lennie az adott típussal.</span><span class="sxs-lookup"><span data-stu-id="73f5f-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="73f5f-176">Változtatható szimbólumok újrakötése</span><span class="sxs-lookup"><span data-stu-id="73f5f-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="73f5f-177">Egy változtatható változó lehet egy `set` utasítás használatával.</span><span class="sxs-lookup"><span data-stu-id="73f5f-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="73f5f-178">Az ilyen újrakötések a kulcsszó `set`, majd egy szimbólum vagy egy Symbol rekord, egy egyenlőségjel `=`, egy kifejezés, amely a szimbólum (oka) t a (z) és egy megszakítási pontosvesszővel köti össze.</span><span class="sxs-lookup"><span data-stu-id="73f5f-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="73f5f-179">Az értéknek kompatibilisnek kell lennie azon szimbólum (ok) típusával, amelyhez hozzá van kötve.</span><span class="sxs-lookup"><span data-stu-id="73f5f-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="73f5f-180">Alkalmazás-és ismételt hozzárendelési utasítás</span><span class="sxs-lookup"><span data-stu-id="73f5f-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="73f5f-181">A set-utasítás egy adott típusra hivatkozik, amely az alkalmazási és az ismételt hozzárendelési utasításra utal, és a jobb oldali összefűzést is lehetővé teszi, ha a jobb oldal egy bináris operátor alkalmazásából áll, és az eredmény a kezelőhöz a bal argumentumhoz lesz kötve.</span><span class="sxs-lookup"><span data-stu-id="73f5f-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="73f5f-182">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="73f5f-183">a `for` hurok minden egyes iterációjában növeli a számláló `counter` értékét.</span><span class="sxs-lookup"><span data-stu-id="73f5f-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="73f5f-184">A fenti kód egyenértékű a következővel</span><span class="sxs-lookup"><span data-stu-id="73f5f-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="73f5f-185">Hasonló utasítások érhetők el minden olyan bináris operátor esetében, amelyben a bal oldali oldal típusa megegyezik a kifejezés típusával.</span><span class="sxs-lookup"><span data-stu-id="73f5f-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="73f5f-186">Ez például az értékek összegyűjtésének kényelmes módja:</span><span class="sxs-lookup"><span data-stu-id="73f5f-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="73f5f-187">Utasítás frissítése és újbóli társítása</span><span class="sxs-lookup"><span data-stu-id="73f5f-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="73f5f-188">Hasonló Összefűzés található a jobb oldali másolási és frissítési kifejezésekhez.</span><span class="sxs-lookup"><span data-stu-id="73f5f-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="73f5f-189">Ennek megfelelően a rendszer a felhasználó által definiált típusokban és a tömbökben lévő megnevezett elemek esetében is tartalmazza a frissítés és az ismételt hozzárendelés utasításait.</span><span class="sxs-lookup"><span data-stu-id="73f5f-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ElementwisePlus(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="73f5f-190">Tömbök esetén a szabványos kódtárak tartalmazzák a szükséges eszközöket számos gyakori tömb inicializálási és manipulációs igényéhez, így elkerülhető, hogy az első helyen ne kelljen frissíteni a tömb elemeit.</span><span class="sxs-lookup"><span data-stu-id="73f5f-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="73f5f-191">Az Update-and-reassign utasítások szükség esetén alternatív megoldást nyújtanak:</span><span class="sxs-lookup"><span data-stu-id="73f5f-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="73f5f-192">A <xref:microsoft.quantum.arrays>által biztosított eszközök kihasználása révén elkerülhető a frissítési és a hozzárendelési utasítások szükségtelen használata.</span><span class="sxs-lookup"><span data-stu-id="73f5f-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="73f5f-193">A függvény</span><span class="sxs-lookup"><span data-stu-id="73f5f-193">The function</span></span>
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="73f5f-194">például egyszerűen egyszerűsíthető a `Microsoft.Quantum.Arrays``ConstantArray` függvény, valamint egy másolási és frissítési kifejezés visszaadása:</span><span class="sxs-lookup"><span data-stu-id="73f5f-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="73f5f-195">Kötési hatókörök</span><span class="sxs-lookup"><span data-stu-id="73f5f-195">Binding Scopes</span></span>

<span data-ttu-id="73f5f-196">Általánosságban elmondható, hogy a szimbólumokra vonatkozó kötések kikerülnek a hatókörből, és a blokk végén nem válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="73f5f-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="73f5f-197">A szabálynak két kivétele van:</span><span class="sxs-lookup"><span data-stu-id="73f5f-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="73f5f-198">Egy `for` hurok loop változójának kötése a for loop törzséhez tartozik, de a hurok vége után nem.</span><span class="sxs-lookup"><span data-stu-id="73f5f-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="73f5f-199">A `repeat`/`until` hurok (a törzs, a teszt és a javítás) mindhárom része egyetlen hatókörként van kezelve, így a törzsben lévő szimbólumok a tesztben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="73f5f-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="73f5f-200">Mindkét típusú hurok esetében a hurok továbbítása a saját hatókörében történik, így a korábbi pass-kötések nem érhetők el egy későbbi menetben.</span><span class="sxs-lookup"><span data-stu-id="73f5f-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="73f5f-201">A külső blokkokból származó szimbólum-kötéseket belső blokkok öröklik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="73f5f-202">Egy szimbólum csak egyszer köthető egy blokkban; nem engedélyezett olyan szimbólumot definiálni, amelynek a neve megegyezik a hatókörön belüli másik szimbólummal (nincs "árnyék").</span><span class="sxs-lookup"><span data-stu-id="73f5f-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="73f5f-203">A következő szakaszokban lenne jogi:</span><span class="sxs-lookup"><span data-stu-id="73f5f-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="73f5f-204">és</span><span class="sxs-lookup"><span data-stu-id="73f5f-204">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

<span data-ttu-id="73f5f-205">Ez azonban nem engedélyezett:</span><span class="sxs-lookup"><span data-stu-id="73f5f-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="73f5f-206">például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="73f5f-207">Átvitelvezérlés</span><span class="sxs-lookup"><span data-stu-id="73f5f-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="73f5f-208">Hurok esetén</span><span class="sxs-lookup"><span data-stu-id="73f5f-208">For Loop</span></span>

<span data-ttu-id="73f5f-209">A `for` utasítás egy egész tartományon vagy egy tömbön keresztül támogatja az ismétlést.</span><span class="sxs-lookup"><span data-stu-id="73f5f-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="73f5f-210">Az utasítás a következő kulcsszóból áll: `for`, egy nyitó zárójel `(`, amelyet egy szimbólum vagy egy szimbólum, a kulcsszó `in`, egy `Range` vagy tömb típusú kifejezés, egy záró zárójel `)`és egy utasítás blokkja.</span><span class="sxs-lookup"><span data-stu-id="73f5f-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="73f5f-211">A rendszer az utasítás blokkját (a hurok törzsét) többször hajtja végre, és a definiált szimbólum (ok) (a hurok változói) a tartomány vagy tömb egyes értékeihez van kötve.</span><span class="sxs-lookup"><span data-stu-id="73f5f-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="73f5f-212">Vegye figyelembe, hogy ha a Range kifejezés üres tartományba vagy tömbbe van kiértékelve, a törzs egyáltalán nem lesz végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="73f5f-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="73f5f-213">A kifejezés teljes mértékben ki van értékelve a hurok megadása előtt, és a hurok végrehajtása közben nem változik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="73f5f-214">A deklarált szimbólum (ok) kötése nem módosítható, és ugyanazokat a szabályokat követi, mint a többi változó kötése.</span><span class="sxs-lookup"><span data-stu-id="73f5f-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="73f5f-215">Különösen lehetséges az elpusztulás, például a tömb elemeinek megismétlése egy tömbben a hurok változóhoz való hozzárendelés után.</span><span class="sxs-lookup"><span data-stu-id="73f5f-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="73f5f-216">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-216">For example,</span></span>

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="73f5f-217">A hurok változó a hurok törzsének minden bejáratánál, a törzs végén pedig nem köthető.</span><span class="sxs-lookup"><span data-stu-id="73f5f-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="73f5f-218">A Loop változó nem kötődik a for ciklus befejeződése után.</span><span class="sxs-lookup"><span data-stu-id="73f5f-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="73f5f-219">REPEAT-ig-Success hurok</span><span class="sxs-lookup"><span data-stu-id="73f5f-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="73f5f-220">A `repeat` utasítás az "ismétlés a sikerig" mintát támogatja.</span><span class="sxs-lookup"><span data-stu-id="73f5f-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="73f5f-221">A kulcsszó `repeat`, majd egy utasítási blokk (a _hurok_ törzse), a kulcsszó `until`, a logikai kifejezés, valamint a lezáró pontosvessző vagy a kulcsszó `fixup`, amelyet egy másik utasítás (a _javítás_) követ.</span><span class="sxs-lookup"><span data-stu-id="73f5f-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="73f5f-222">A hurok törzse, állapota és kijavítása egyetlen hatókörnek tekintendő, így a törzsben lévő szimbólumok a feltételben és a javításban is elérhetők.</span><span class="sxs-lookup"><span data-stu-id="73f5f-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

<span data-ttu-id="73f5f-223">A rendszer végrehajtja a hurok törzsét, majd kiértékeli a feltételt.</span><span class="sxs-lookup"><span data-stu-id="73f5f-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="73f5f-224">Ha a feltétel igaz, az utasítás befejeződött; Ellenkező esetben a rendszer végrehajtja a javítást, és az utasítást a hurok törzsének megfelelően újra végrehajtja.</span><span class="sxs-lookup"><span data-stu-id="73f5f-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="73f5f-225">Vegye figyelembe, hogy a javítás végrehajtásának befejezése befejezi az utasítás hatókörét, így a törzs vagy a javítás során végrehajtott szimbólum-kötések nem érhetők el a későbbi ismétlődésekben.</span><span class="sxs-lookup"><span data-stu-id="73f5f-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="73f5f-226">A következő kód például egy olyan valószínűségi áramkör, amely egy fontos rotációs kaput valósít meg $V _3 = (\boldone + 2 i Z)/\sqrt{5}$-T a Hadamard és a T Gates használatával.</span><span class="sxs-lookup"><span data-stu-id="73f5f-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="73f5f-227">A hurok a $ \frac{8}{5}$ ismétlődések átlagában leáll.</span><span class="sxs-lookup"><span data-stu-id="73f5f-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="73f5f-228">A részletekért lásd [ *: egyszeres qubit unitaries*](https://arxiv.org/abs/1311.1074) (Petrovics és Svore, 2014) nem determinisztikus bontása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="73f5f-229">Kerülje a függvényekben a REPEAT-ig-Success hurkok használatát.</span><span class="sxs-lookup"><span data-stu-id="73f5f-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="73f5f-230">A kapcsolódó funkciókat a függvények hurkoi is biztosítják.</span><span class="sxs-lookup"><span data-stu-id="73f5f-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="73f5f-231">Ciklus közben</span><span class="sxs-lookup"><span data-stu-id="73f5f-231">While Loop</span></span>

<span data-ttu-id="73f5f-232">A REPEAT-ig-Success mintázat nagyon Quantum-specifikus konnotációval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="73f5f-233">Ezek széles körben használatosak a kvantum-algoritmusok bizonyos osztályaiban – ezért a dedikált nyelvi összeállítás Q #-ban.</span><span class="sxs-lookup"><span data-stu-id="73f5f-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="73f5f-234">Azonban az olyan hurkok, amelyek feltételen alapulnak, és amelynek végrehajtási hosszát a fordítási időn belül ismeretlennek kell lenniük, a kvantum-futtatókörnyezetben különös gondossággal kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="73f5f-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="73f5f-235">A függvényeken belüli használatuk azonban nem problémamentes, mivel ezek csak a hagyományos (nem Quantum) hardveren végrehajtandó kódokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="73f5f-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="73f5f-236">A Q # ezért a csak functions-ben lévő hurkok használatát támogatja.</span><span class="sxs-lookup"><span data-stu-id="73f5f-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="73f5f-237">A `while` utasítás a kulcsszó `while`, egy nyitó zárójel `(`, egy feltétel (például egy logikai kifejezés), egy záró zárójel `)`és egy utasítás blokkból áll.</span><span class="sxs-lookup"><span data-stu-id="73f5f-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="73f5f-238">A rendszer az utasítás blokkját (a hurok törzsét) hajtja végre, amíg a feltétel kiértékelése `true`.</span><span class="sxs-lookup"><span data-stu-id="73f5f-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="73f5f-239">Feltételes utasítás</span><span class="sxs-lookup"><span data-stu-id="73f5f-239">Conditional Statement</span></span>

<span data-ttu-id="73f5f-240">A `if` utasítás támogatja a feltételes végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="73f5f-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="73f5f-241">A kulcsszó `if`, egy nyitó zárójel `(`, egy logikai kifejezésből, egy záró zárójelből `)`ből és egy utasításból álló blokkból áll ( _Ez a blokk_ ).</span><span class="sxs-lookup"><span data-stu-id="73f5f-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="73f5f-242">Ezt követheti tetszőleges számú Else-if záradék, amelyek mindegyike a következő kulcsszóból áll: `elif`, egy nyitó zárójel `(`, egy logikai kifejezés, egy záró zárójel `)`és egy utasítás blokkja (a _másik, ha_ blokk).</span><span class="sxs-lookup"><span data-stu-id="73f5f-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="73f5f-243">Végül az utasítás opcionálisan egy másik záradékkal is kiegészíthető, amely a kulcsszó `else` és egy másik utasítás (az _Else_ blokk) után következik be.</span><span class="sxs-lookup"><span data-stu-id="73f5f-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="73f5f-244">A rendszer kiértékeli a feltételt, és ha az értéke igaz, a rendszer végrehajtja a letiltást.</span><span class="sxs-lookup"><span data-stu-id="73f5f-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="73f5f-245">Ha a feltétel hamis, akkor az első más-if feltétel kiértékelése megtörténik. Ha az értéke igaz, akkor ez a másik a blokkolás végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="73f5f-246">Ellenkező esetben a második, ha a blokkot teszteli, majd a harmadikat, és így tovább, amíg egy igaz állapotú záradékot nem talál, vagy ha nincs több más – if záradék.</span><span class="sxs-lookup"><span data-stu-id="73f5f-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="73f5f-247">Ha az eredeti if feltétel és az összes más-if záradék hamis értéket ad vissza, akkor a rendszer a másik blokkot hajtja végre, ha meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="73f5f-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="73f5f-248">Vegye figyelembe, hogy a rendszer bármelyik blokkot a saját hatókörében hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="73f5f-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="73f5f-249">Az IF utasítás vége után nem láthatók az olyan kötések, amelyek egy, a "Máskülönben" vagy "else" blokkon belül történnek.</span><span class="sxs-lookup"><span data-stu-id="73f5f-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="73f5f-250">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="73f5f-251">vagy</span><span class="sxs-lookup"><span data-stu-id="73f5f-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="73f5f-252">Visszatérési</span><span class="sxs-lookup"><span data-stu-id="73f5f-252">Return</span></span>

<span data-ttu-id="73f5f-253">A Return utasítás egy művelet vagy függvény végrehajtását hajtja végre, és egy értéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="73f5f-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="73f5f-254">A kulcsszó `return`, majd a megfelelő típusú kifejezéssel, valamint egy pontosvesszővel végződik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="73f5f-255">Egy üres rekordot visszaadó hívható, `()`, nem igényel visszatérési utasítást.</span><span class="sxs-lookup"><span data-stu-id="73f5f-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="73f5f-256">Ha korai kilépés szükséges, `return ()` lehet használni ebben az esetben.</span><span class="sxs-lookup"><span data-stu-id="73f5f-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="73f5f-257">A más típusokat visszaadó Callables a végső visszatérési utasítást kell megadni.</span><span class="sxs-lookup"><span data-stu-id="73f5f-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="73f5f-258">Egy műveletben nem engedélyezett a visszaküldési utasítások maximális száma.</span><span class="sxs-lookup"><span data-stu-id="73f5f-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="73f5f-259">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli visszatérési utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="73f5f-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="73f5f-260">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="73f5f-261">vagy</span><span class="sxs-lookup"><span data-stu-id="73f5f-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="73f5f-262">vagy</span><span class="sxs-lookup"><span data-stu-id="73f5f-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="73f5f-263">Sikertelen</span><span class="sxs-lookup"><span data-stu-id="73f5f-263">Fail</span></span>

<span data-ttu-id="73f5f-264">A Fail utasítás befejezi a művelet végrehajtását, és hibaértéket ad vissza a hívónak.</span><span class="sxs-lookup"><span data-stu-id="73f5f-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="73f5f-265">A kulcsszó `fail`, majd egy karakterláncot és egy lezáró pontosvesszőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="73f5f-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="73f5f-266">A rendszer a karakterláncot a klasszikus illesztőprogramnak adja vissza hibaüzenetként.</span><span class="sxs-lookup"><span data-stu-id="73f5f-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="73f5f-267">A műveleteken belüli sikertelen utasítások száma nincs korlátozva.</span><span class="sxs-lookup"><span data-stu-id="73f5f-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="73f5f-268">A fordító kibocsáthat egy figyelmeztetést, ha a utasítások egy blokkon belüli sikertelen utasítást követnek.</span><span class="sxs-lookup"><span data-stu-id="73f5f-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="73f5f-269">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="73f5f-270">vagy</span><span class="sxs-lookup"><span data-stu-id="73f5f-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="73f5f-271">Qubit-kezelés</span><span class="sxs-lookup"><span data-stu-id="73f5f-271">Qubit Management</span></span>

<span data-ttu-id="73f5f-272">Vegye figyelembe, hogy a függvények törzsében egyik utasítás sem engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="73f5f-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="73f5f-273">Csak a műveleteken belül érvényesek.</span><span class="sxs-lookup"><span data-stu-id="73f5f-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="73f5f-274">Qubits tisztítása</span><span class="sxs-lookup"><span data-stu-id="73f5f-274">Clean Qubits</span></span>

<span data-ttu-id="73f5f-275">A `using` utasítás az új qubits beolvasására szolgál az utasítási blokkokban való használatra.</span><span class="sxs-lookup"><span data-stu-id="73f5f-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="73f5f-276">A qubits a számítási `Zero` állapotba való inicializálása garantált.</span><span class="sxs-lookup"><span data-stu-id="73f5f-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="73f5f-277">A qubits a számlakivonat végén lévő számítási `Zero` állapotban kell lennie; a szimulátorokat javasoljuk, hogy kényszerítse ezt.</span><span class="sxs-lookup"><span data-stu-id="73f5f-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="73f5f-278">Az utasítás a `using`kulcsszóból áll, amelyet egy nyitó zárójel `(`, egy kötés, egy záró zárójel `)`, valamint a qubits elérhetővé tételére szolgáló utasítás blokkja is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="73f5f-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="73f5f-279">A kötés ugyanazt a mintát követi, mint a `let`i utasítások: vagy egy szimbólumot vagy egy szimbólumot, majd egy egyenlőségjel `=`, és egy vagy több inicializáló egyező rekordot.</span><span class="sxs-lookup"><span data-stu-id="73f5f-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="73f5f-280">Az inicializálók egyetlen qubit érhetők el, amelyek `Qubit()`ként vannak megjelölve, vagy egy `Qubit[`, `Int` kifejezés és `]`által jelzett qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="73f5f-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="73f5f-281">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="73f5f-282">Kölcsönzött qubits</span><span class="sxs-lookup"><span data-stu-id="73f5f-282">Borrowed Qubits</span></span>

<span data-ttu-id="73f5f-283">A `borrowing` utasítás az ideiglenes használatra szolgáló qubits beszerzésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="73f5f-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="73f5f-284">Az utasítás a `borrowing`kulcsszóból áll, amelyet egy nyitó zárójel `(`, egy kötés, egy záró zárójel `)`, valamint a qubits elérhetővé tételére szolgáló utasítás blokkja is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="73f5f-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="73f5f-285">A kötés ugyanazokat a mintákat és szabályokat követi, mint egy `using` utasításban.</span><span class="sxs-lookup"><span data-stu-id="73f5f-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="73f5f-286">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="73f5f-287">A kölcsönzött qubits ismeretlen állapotban vannak, és az utasítás blokk végén kiléphetnek a hatókörből.</span><span class="sxs-lookup"><span data-stu-id="73f5f-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="73f5f-288">A hitelfelvevő vállalja, hogy a qubits ugyanabban az állapotban hagyja, mint amikor a kölcsönbe kerültek, azaz az utasítás blokkjának elején és végén lévő állapotuknak azonosnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="73f5f-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="73f5f-289">Ez az állapot különösen nem feltétlenül klasszikus állapotban van, így a legtöbb esetben a hitelfelvételi hatókörök nem tartalmazhatnak mértékeket.</span><span class="sxs-lookup"><span data-stu-id="73f5f-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="73f5f-290">Tekintse meg a [*Toffoli-alapú Többtényezős 2017 (2n + 2) qubits a*](https://arxiv.org/abs/1611.07995) kölcsönzött Svore-használatra vonatkozó példát.</span><span class="sxs-lookup"><span data-stu-id="73f5f-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="73f5f-291">A qubits hitelfelvételkor a rendszer először megpróbálja betölteni a kérést a használatban lévő qubits, de a `borrowing` utasítás törzsében nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="73f5f-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="73f5f-292">Ha nincs elég ilyen qubits, akkor a kérés teljesítéséhez új qubits fog kiosztani.</span><span class="sxs-lookup"><span data-stu-id="73f5f-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="73f5f-293">Conjugations</span><span class="sxs-lookup"><span data-stu-id="73f5f-293">Conjugations</span></span>

<span data-ttu-id="73f5f-294">A klasszikus BITS-vel szemben a kvantum-memória felszabadítása valamivel nagyobb mértékben történik, mivel a qubits vakon alaphelyzetbe állítása nem kívánt hatással lehet a fennmaradó számításra, ha a qubits továbbra is összefonódik.</span><span class="sxs-lookup"><span data-stu-id="73f5f-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="73f5f-295">Ezt elkerülheti, ha a memóriát a memória felszabadítása előtt megfelelően elvégezte.</span><span class="sxs-lookup"><span data-stu-id="73f5f-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="73f5f-296">A kvantum-számítástechnika általános mintája a következő:</span><span class="sxs-lookup"><span data-stu-id="73f5f-296">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="73f5f-297">: új: a 0,9-es verziótól kezdődően a fenti átalakítást megvalósító ragozó utasítást támogatunk.</span><span class="sxs-lookup"><span data-stu-id="73f5f-297">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="73f5f-298">Az utasítás használatával a `ApplyWith` művelet a következő módon valósítható meg:</span><span class="sxs-lookup"><span data-stu-id="73f5f-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="73f5f-299">Egy ilyen ragozó utasítás nyilvánvalóan sokkal hasznosabb lehet, ha a külső és belső átalakítás nem érhető el azonnal, hanem több utasításból álló blokk alapján.</span><span class="sxs-lookup"><span data-stu-id="73f5f-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="73f5f-300">A blokkon belül definiált utasítások inverz átalakítását a fordító automatikusan hozza létre, és az Apply-Block befejeződése után hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="73f5f-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="73f5f-301">Mivel a blokk részeként használt változó változók nem használhatók fel az alkalmazás-blokkban, a generált transzformáció garantált, hogy a adjoint a blokkon belül.</span><span class="sxs-lookup"><span data-stu-id="73f5f-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="73f5f-302">Kifejezés-értékelési utasítások</span><span class="sxs-lookup"><span data-stu-id="73f5f-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="73f5f-303">A `Unit` típusú hívási kifejezések utasításként is használhatók.</span><span class="sxs-lookup"><span data-stu-id="73f5f-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="73f5f-304">Ez elsősorban akkor használatos, ha a qubits olyan műveleteket hív meg, amelyek `Unit` adnak vissza, mert az utasítás célja az implicit kvantum állapotának módosítása.</span><span class="sxs-lookup"><span data-stu-id="73f5f-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="73f5f-305">A kifejezés-értékelési utasításokhoz pontosvesszőt kell lezárni.</span><span class="sxs-lookup"><span data-stu-id="73f5f-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="73f5f-306">Például:</span><span class="sxs-lookup"><span data-stu-id="73f5f-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
