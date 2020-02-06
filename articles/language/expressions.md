---
title: Kifejezések | Microsoft Docs
description: Kifejezések
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036313"
---
# <a name="expressions"></a><span data-ttu-id="b0ca6-103">Kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="b0ca6-104">Csoportosítás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-104">Grouping</span></span>

<span data-ttu-id="b0ca6-105">Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="b0ca6-106">Például a `(7)` egy `Int` kifejezés, `([1,2,3])` `Int`s tömb típusú kifejezés, a `((1,2))` pedig `(Int, Int)`típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="b0ca6-107">A [modellben](xref:microsoft.quantum.language.type-model#tuple-types) leírt egyszerű értékek és egyelemes rekordok közötti egyenértékűség eltávolítja a `(6)` csoportként való kétértelműség és a `(6)` egyelemű rekord között.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="b0ca6-108">Szimbólumok</span><span class="sxs-lookup"><span data-stu-id="b0ca6-108">Symbols</span></span>

<span data-ttu-id="b0ca6-109">Egy `'T` típusú értékhez kötött vagy hozzárendelt szimbólum neve `'T`típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="b0ca6-110">Ha például a szimbólum `count` az egész értékhez van kötve `5`, akkor `count` egy egész szám kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="b0ca6-111">Numerikus kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-111">Numeric Expressions</span></span>

<span data-ttu-id="b0ca6-112">A numerikus kifejezések `Int`, `BigInt`vagy `Double`típusú kifejezések.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="b0ca6-113">Vagyis egész vagy lebegőpontos számok.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="b0ca6-114">a Q # `Int` literálok a (z) értékekben egyeznek C#meg, azzal a különbséggel, hogy nincs szükség "l" vagy "l" kifejezésre (vagy engedélyezett).</span><span class="sxs-lookup"><span data-stu-id="b0ca6-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="b0ca6-115">A hexadecimális és a bináris egész számok "0x" és "0b" előtaggal támogatottak.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="b0ca6-116">a Q # `BigInt` literálok megegyeznek a .NET-ben található Big Integer karakterláncokkal, amelyek "l" vagy "L" karakterrel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="b0ca6-117">A hexadecimális nagy egész számok "0x" előtaggal támogatottak.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="b0ca6-118">Így az alábbi `BigInt` literálok összes érvényes használata:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="b0ca6-119">a Q # `Double` literálok megegyeznek a kettős literálokkal, C#azzal a különbséggel, hogy a "d" vagy a "d" kifejezés nem kötelező (vagy engedélyezett).</span><span class="sxs-lookup"><span data-stu-id="b0ca6-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="b0ca6-120">Bármely elemtípus tömb kifejezése miatt a `Int` kifejezés a `Length` beépített függvény használatával hozható létre, a tömb kifejezés zárójelek közé, `(` és `)`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="b0ca6-121">Ha például `a` egy tömbhöz van kötve, akkor `Length(a)` egy egész szám kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="b0ca6-122">Ha `b` az egész számokból álló tömbök tömbje, `Int[][]`, `Length(b)` a `b`ban található altömbök száma, és a `Length(b[1])` a második altömbben lévő egész számok száma `b`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="b0ca6-123">Adott típusú két numerikus kifejezés, a bináris operátorok `+`, `-`, `*`és `/` használhatók új numerikus kifejezés megírásához.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="b0ca6-124">Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="b0ca6-125">A két egész szám kifejezés miatt a bináris operátor `^` (Power) egy új egész kifejezés kiírására használható.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="b0ca6-126">Hasonlóképpen, `^` két kettős kifejezéssel is használható, amelyek új dupla kifejezést alkotnak.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="b0ca6-127">Végezetül `^` a bal oldalon egy nagy egész számmal, a jobb oldalon pedig egy egész számmal, egy új Big Integer típusú kifejezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="b0ca6-128">Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, a rendszer futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="b0ca6-129">A két egész vagy nagy egész szám típusú kifejezés esetében egy új egész vagy Big Integer kifejezés is létrehozható a `%` (modulus), a `&&&` (bitenkénti és), a `|||` (bitenkénti vagy), vagy a `^^^` (bitenkénti XOR) operátorok használatával.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="b0ca6-130">A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) vagy `>>>` (aritmetikai jobbra váltás) operátorok használhatók a bal oldali kifejezéssel megegyező típusú új kifejezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="b0ca6-131">A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="b0ca6-132">A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, a rendszer futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="b0ca6-133">Ha az elmozdulni kívánt szám egész szám, akkor a rendszer a váltási összeget `mod 64`értelmezi. Ez azt eredményezi, hogy az 1. és a 65 eltolása ugyanaz a hatása.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="b0ca6-134">Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="b0ca6-135">A negatív érték eltolása balra vagy jobbra is negatív számot eredményez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="b0ca6-136">Ez azt okozhatja, hogy az egyik lépés balra vagy jobbra való eltolása pontosan ugyanaz, mint a 2. számú szorzás vagy osztás.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="b0ca6-137">Az egész szám és az egész számú modulus ugyanazt a viselkedést C#követi, mint a negatív számok.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="b0ca6-138">Ez azt eredményezi, hogy a `a % b` mindig ugyanazzal a jellel fog rendelkezni, mint `a`, és a `b * (a / b) + a % b` mindig egyenlő lesz `a`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="b0ca6-139">Például:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="b0ca6-140">5</span><span class="sxs-lookup"><span data-stu-id="b0ca6-140">5</span></span> | <span data-ttu-id="b0ca6-141">2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-141">2</span></span> | <span data-ttu-id="b0ca6-142">2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-142">2</span></span> | <span data-ttu-id="b0ca6-143">1</span><span class="sxs-lookup"><span data-stu-id="b0ca6-143">1</span></span>
 <span data-ttu-id="b0ca6-144">5</span><span class="sxs-lookup"><span data-stu-id="b0ca6-144">5</span></span> | <span data-ttu-id="b0ca6-145">-2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-145">-2</span></span> | <span data-ttu-id="b0ca6-146">-2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-146">-2</span></span> | <span data-ttu-id="b0ca6-147">1</span><span class="sxs-lookup"><span data-stu-id="b0ca6-147">1</span></span>
 <span data-ttu-id="b0ca6-148">– 5</span><span class="sxs-lookup"><span data-stu-id="b0ca6-148">-5</span></span> | <span data-ttu-id="b0ca6-149">2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-149">2</span></span> | <span data-ttu-id="b0ca6-150">-2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-150">-2</span></span> | <span data-ttu-id="b0ca6-151">-1</span><span class="sxs-lookup"><span data-stu-id="b0ca6-151">-1</span></span>
 <span data-ttu-id="b0ca6-152">– 5</span><span class="sxs-lookup"><span data-stu-id="b0ca6-152">-5</span></span> | <span data-ttu-id="b0ca6-153">-2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-153">-2</span></span> | <span data-ttu-id="b0ca6-154">2</span><span class="sxs-lookup"><span data-stu-id="b0ca6-154">2</span></span> | <span data-ttu-id="b0ca6-155">-1</span><span class="sxs-lookup"><span data-stu-id="b0ca6-155">-1</span></span>

<span data-ttu-id="b0ca6-156">A Big Integer osztás és a modulus hasonló módon működik.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="b0ca6-157">A numerikus kifejezéseket megadva egy új kifejezés hozható létre a `-` egyoperandusú operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="b0ca6-158">Az új kifejezés ugyanolyan típusú lesz, mint az összetevő kifejezése.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="b0ca6-159">Adott egész szám vagy nagy egész szám kifejezés esetén az azonos típusú új kifejezés az `~~~` (bitenkénti komplement) egyoperandusú operátor használatával hozható létre.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="b0ca6-160">Logikai kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-160">Boolean Expressions</span></span>

<span data-ttu-id="b0ca6-161">A két `Bool` literális érték `true` és `false`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="b0ca6-162">Az azonos primitív típus két kifejezése miatt a `==` és a `!=` bináris operátorok is használhatók `Bool` kifejezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="b0ca6-163">A kifejezés akkor igaz, ha a két kifejezés egyenlő, és hamis, ha nem.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="b0ca6-164">A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="b0ca6-165">Például a "kicsomagolás" operátor használatával `!` (a [Q # Type Model lapon](xref:microsoft.quantum.language.type-model#user-defined-types)magyarázva)</span><span class="sxs-lookup"><span data-stu-id="b0ca6-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="b0ca6-166">`Qubit` értékek egyenlőségének összehasonlítása az identitások egyenlősége; Ez azt jelzi, hogy a két kifejezés ugyanazt a qubit azonosítja-e.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="b0ca6-167">A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="b0ca6-168">A `Double` értékek egyenlőségének összehasonlítása a kerekítési hatások miatt félrevezető lehet.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="b0ca6-169">Például `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="b0ca6-170">A két numerikus kifejezés miatt a bináris operátorok `>`, `<`, `>=`és `<=` használhatók olyan új logikai kifejezés létrehozásához, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, vagy a második kifejezésnél kisebb vagy azzal egyenlő.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="b0ca6-171">A két logikai kifejezés miatt a `and` és `or` bináris operátorok egy olyan új logikai kifejezés létrehozásához használhatók, amely igaz, ha a két kifejezés mindkét (ill. vagy mindkettő) értéke igaz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="b0ca6-172">A logikai kifejezéseket megadva a `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="b0ca6-173">Karakterlánc-kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-173">String Expressions</span></span>

<span data-ttu-id="b0ca6-174">A Q # lehetővé teszi a karakterláncok használatát a `fail` utasításban és a `Log` standard függvényben.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="b0ca6-175">A Q # sztringek literálok vagy interpolált karakterláncok.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="b0ca6-176">A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterláncokhoz: az Unicode-karakterek egy számsorozata idézőjelek között, `"`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="b0ca6-177">Egy karakterláncon belül a háttér-perjel karakter `\` a kettős idézőjelek karakterének kiírására, valamint egy új vonal `\n`ba való beszúrására, egy kocsivissza karaktert `\r`ként, és egy tabulátort `\t`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="b0ca6-178">Például:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="b0ca6-179">A Q # szintaxis a karakterlánc-interpolációhoz az C# 7,0 szintaxis részhalmaza. A Q # nem támogatja a Verbatim (többsoros) interpolált karakterláncokat.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="b0ca6-180">Lásd: [*interpolált karakterláncok*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) a C# szintaxishoz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="b0ca6-181">Az interpolált karakterláncban szereplő kifejezések a Q # szintaxist követik C# , nem pedig a szintaxist.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="b0ca6-182">Bármely érvényes Q # kifejezés egy interpolált karakterláncban jelenhet meg.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="b0ca6-183">Qubit kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-183">Qubit Expressions</span></span>

<span data-ttu-id="b0ca6-184">Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékekhez vagy `Qubit` tömbök tömb elemeihez van kötve.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="b0ca6-185">Nincsenek `Qubit` literálok.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="b0ca6-186">Pauli-kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-186">Pauli Expressions</span></span>

<span data-ttu-id="b0ca6-187">A négy `Pauli` érték, `PauliI`, `PauliX`, `PauliY`és `PauliZ`egyaránt érvényes `Pauli` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="b0ca6-188">Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékekhez vagy `Pauli` tömbök tömb elemeihez van kötve.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="b0ca6-189">Eredmény kifejezései</span><span class="sxs-lookup"><span data-stu-id="b0ca6-189">Result Expressions</span></span>

<span data-ttu-id="b0ca6-190">A két `Result` érték, `One` és `Zero`érvényes `Result` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="b0ca6-191">Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékekhez vagy `Result` tömbök tömb elemeihez van kötve.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="b0ca6-192">Fontos megjegyezni, hogy `One` nem egyezik meg a `1`egész számmal, és a között nincs közvetlen konverzió.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="b0ca6-193">Ugyanez érvényes a `Zero` és a `0`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="b0ca6-194">Tartomány kifejezései</span><span class="sxs-lookup"><span data-stu-id="b0ca6-194">Range Expressions</span></span>

<span data-ttu-id="b0ca6-195">A három `Int` kifejezés `start`, `step`és `stop`esetén a `start .. step .. stop` egy olyan tartomány kifejezés, amelynek első eleme `start`, a második elem `start+step`, a harmadik elem `start+step+step`, stb., amíg `stop` át nem adja.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="b0ca6-196">A tartomány lehet üres, ha például `step` pozitív és `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="b0ca6-197">A tartomány utolsó eleme akkor `stop`, ha a `start` és a `stop` közötti különbség a `step`elválaszthatatlan többszöröse. vagyis a tartomány mindkét végén szerepel.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="b0ca6-198">`start` és `stop`két `Int` kifejezést adott meg, `start .. stop` egy tartománybeli kifejezés, amely `start .. 1 .. stop`egyenlő.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="b0ca6-199">Vegye figyelembe, hogy a hallgatólagos `step` akkor is + 1, ha a `stop` kisebb, mint `start`; ilyen esetben a tartomány üres.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="b0ca6-200">Néhány példa a tartományokra:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-200">Some example ranges are:</span></span>

- <span data-ttu-id="b0ca6-201">`1..3` az 1., 2. és 3. tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="b0ca6-202">`2..2..5` a 2, 4 tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="b0ca6-203">`2..2..6` a 2, 4, 6 tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="b0ca6-204">`6..-2..2` a 6, 4, 2 tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="b0ca6-205">`2..1` az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="b0ca6-206">`2..6..7` a 2. tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="b0ca6-207">`2..2..1` az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="b0ca6-208">`1..-1..2` az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="b0ca6-209">Hívható kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-209">Callable Expressions</span></span>

<span data-ttu-id="b0ca6-210">A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="b0ca6-211">Például a `X` egy olyan műveleti literál, amely a szabványos függvénytár `X` műveletre hivatkozik, és a `Message` egy függvény literál, amely a szabványos függvénytár `Message` függvényre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="b0ca6-212">Ha egy művelet támogatja a `Adjoint`-kezelőt, akkor `Adjoint op` egy műveleti kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="b0ca6-213">Hasonlóképpen, ha a művelet támogatja a `Controlled`t, akkor `Controlled op` egy műveleti kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="b0ca6-214">Ezeknek a kifejezéseknek a típusai a következőben vannak [megadva.](xref:microsoft.quantum.language.type-model#functors)</span><span class="sxs-lookup"><span data-stu-id="b0ca6-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="b0ca6-215">A következő operátorok (`Adjoint` és `Controlled`) jobban kötődik az összes többi kezelőhöz, kivéve a kicsomagolási operátort, `!` és a tömb indexelését `[]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="b0ca6-216">Így a következők mindegyike jogi, feltételezve, hogy a műveletek támogatják a használt munkafolyamatokat:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="b0ca6-217">Egy meghívásos literál is használható értékként, azaz egy változóhoz való hozzárendeléshez, vagy egy másik meghíváshoz való továbbításhoz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="b0ca6-218">Ebben az esetben, ha a meghívható paraméterekkel rendelkezik, azokat a meghívásos érték részeként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="b0ca6-219">Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b0ca6-220">Ha például az `Fun` egy aláírással `'T1->Unit`függvény:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="b0ca6-221">Hívható hívási kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="b0ca6-222">Egy meghívásos (művelet vagy függvény) kifejezés és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos kifejezés úgy hozható létre, hogy hozzáfűzi a rekord kifejezését a meghívható kifejezéshez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="b0ca6-223">A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="b0ca6-224">Ha például az `Op` egy `((Int, Qubit) => Double)`aláírással rendelkező művelet, `Op(3, qubit1)` `Double`típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b0ca6-225">Hasonlóképpen, ha a `Sin` az aláírás `(Double -> Double)`függvény, `Sin(0.1)` `Double`típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b0ca6-226">Végül, ha a `Builder` egy aláírási `(Int -> (Int -> Int))`függvény, akkor a `Builder(3)` függvény a-tól az int-ig.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="b0ca6-227">Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="b0ca6-228">Így a `Builder` az előző bekezdésből való meghívása eredményének meghívásához a helyes szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="b0ca6-229">A típus-paraméteres metódus meghívásakor a tényleges Type paraméterek megadhatók a szögletes zárójelek között `<` és `>` a meghívásos kifejezés után.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="b0ca6-230">Ez általában szükségtelen, mivel a Q # fordítóprogram a tényleges típusokat fogja kikövetkeztetni.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="b0ca6-231">A részleges alkalmazáshoz szükséges (lásd alább), ha egy Type-paraméteres argumentum nincs megadva.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="b0ca6-232">Időnként hasznos lehet, ha a különböző felállókkal rendelkező műveletek átadása meghívásos támogatással történik.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="b0ca6-233">Ha például `Func` rendelkezik aláírással `('T1, 'T2, 'T1) -> 'T2`, `Op1` és `Op2` rendelkezik aláírási `(Qubit[] => Unit is Adj)`, és `Op3` aláírása `(Qubit[] => Unit)`, hogy meghívja `Func` az `Op1` az első argumentumként, `Op2` a másodikként, és `Op3` a harmadikként:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="b0ca6-234">A típus specifikációjának megadása kötelező, mert `Op3` és `Op1` különböző típusúak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="b0ca6-235">Részleges alkalmazás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-235">Partial Application</span></span>

<span data-ttu-id="b0ca6-236">Egy meghívásos kifejezés miatt egy új hívható is létrehozható az argumentumok egy részhalmazának megadásával a meghívónak.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="b0ca6-237">Ezt nevezzük _részleges alkalmazásnak_.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-237">This is called _partial application_.</span></span>

<span data-ttu-id="b0ca6-238">A Q #-ban a részlegesen alkalmazott meghívót normál meghívásos kifejezés megírásával fejezzük ki, de a meghatározatlan argumentumok esetében aláhúzást `_`használ.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="b0ca6-239">Az eredményül kapott meghívó ugyanazzal az eredménnyel rendelkezik, mint az alapszintű hívható, és ugyanazokat a specializációkat kell megadnia a műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="b0ca6-240">A részleges alkalmazás bemeneti típusa egyszerűen az eredeti típus, ahol a megadott argumentumok el lettek távolítva.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="b0ca6-241">Ha egy megváltoztathatatlan változót egy részleges alkalmazás létrehozásakor megadott argumentumként ad át, a rendszer a változó aktuális értékét használja.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="b0ca6-242">A változó értékének módosítása később nem befolyásolja a részleges alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="b0ca6-243">Ha például `Op` típusa `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="b0ca6-244">`Op(5,(_,_))` típusa `(((Qubit,Qubit), Double) => Unit is Adj)`, ezért `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="b0ca6-245">a `Op(_,(_,1.0))` típusa `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="b0ca6-246">a `Op(_,((q1,q2),_))` típusa `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="b0ca6-247">Vegye figyelembe, hogy itt is alkalmazunk egy Egyrekordos egyenértékűséget.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="b0ca6-248">Ha a részben alkalmazott hívható olyan paraméterekkel rendelkezik, amelyeket a fordító nem tud következtetni, meg kell adni azokat a Meghívási helyen.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="b0ca6-249">A részleges alkalmazás nem rendelkezhet meghatározatlan típusú paraméterekkel.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b0ca6-250">Ha például `Op` típusa `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="b0ca6-251">Rekurzió</span><span class="sxs-lookup"><span data-stu-id="b0ca6-251">Recursion</span></span>

<span data-ttu-id="b0ca6-252">A Q # callables közvetlenül vagy közvetve rekurzívak.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="b0ca6-253">Ez azt is megteheti, hogy egy művelet vagy funkció meghívhatja magát, vagy meghívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="b0ca6-254">A rekurzió használatának két fontos megjegyzése van, azonban:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="b0ca6-255">A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="b0ca6-256">Ez jelentős hatással lehet az algoritmus végrehajtási idejére.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="b0ca6-257">Ha tényleges kvantum-eszközön végez végrehajtást, előfordulhat, hogy a halmozott terület korlátozva van, ezért a mélyebb rekurzió hibát okozhat.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="b0ca6-258">A Q # Compiler és a Runtime nem azonosítja és optimalizálja a farok rekurzióját.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="b0ca6-259">Rekordos kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-259">Tuple Expressions</span></span>

<span data-ttu-id="b0ca6-260">A rekordos literál a megfelelő típusú elem-kifejezések sorozata, vesszővel elválasztva, `(` és `)`között.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="b0ca6-261">A `(1, One)` például egy `(Int, Result)` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="b0ca6-262">A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="b0ca6-263">Felhasználó által definiált típusú kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="b0ca6-264">A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="b0ca6-265">Ha például a `IntPair` felhasználó által definiált típus `(Int, Int)`alapján, akkor `IntPair(2,3)` a típus érvényes konstansa lesz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="b0ca6-266">A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="b0ca6-267">Kifejezések kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="b0ca6-267">Unwrap Expressions</span></span>

<span data-ttu-id="b0ca6-268">A Q #-ban a kicsomagolás operátor egy záró felkiáltójel `!`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="b0ca6-269">Ha például `IntPair` egy olyan felhasználó által definiált típus, amelynek típusa `(Int, Int)`, és a `s` `IntPair(2,3)`értékkel rendelkező változó volt, `s!` `(2,3)`lenne.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="b0ca6-270">A felhasználó által definiált típusok esetében definiált más felhasználók által definiált típusok esetében.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="b0ca6-271">lehet, hogy a kicsomagolási operátor megismétlődik; a `s!!` például a `s`kétszeresen kicsomagolt értékét jelzi.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="b0ca6-272">Így ha `WrappedPair` egy alapul szolgáló típusú `IntPair`felhasználó által definiált típus, és a `t` egy `WrappedPair(IntPair(1,2))`értékkel rendelkező változó, `t!!` `(1,2)`lenne.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="b0ca6-273">A `!` operátor magasabb prioritású, mint az összes többi operátor, amely nem `[]` a tömb indexeléséhez és a szeleteléshez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="b0ca6-274">`!` és `[]` a kötés elhelyezése; Ez azt is megteheti, hogy a `a[i]![3]` `((a[i])!)[3]`ként kell olvasni: vegye fel a `i`"th elemét `a`, csomagolja ki, majd a nem burkolt érték harmadik elemét (amely tömbnek kell lennie).</span><span class="sxs-lookup"><span data-stu-id="b0ca6-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="b0ca6-275">A `!` operátor elsőbbsége egy olyan hatással van, amely esetleg nem nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="b0ca6-276">Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="b0ca6-277">Például:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="b0ca6-278">Tömb kifejezései</span><span class="sxs-lookup"><span data-stu-id="b0ca6-278">Array Expressions</span></span>

<span data-ttu-id="b0ca6-279">A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, `[` és `]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="b0ca6-280">Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="b0ca6-281">Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="b0ca6-282">A tömb elemének típusa az összes elem által támogatott összes olyan futtatót támogatni fogja.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="b0ca6-283">Ha például `Op1`, `Op2`és `Op3` mind `Qubit[] => Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja a `Controlled`, és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b0ca6-284">a `[Op1, Op2]` `(Qubit[] => Unit)` műveletek tömbje.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="b0ca6-285">a `[Op1, Op3]` `(Qubit[] => Unit is Adj)` műveletek tömbje.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="b0ca6-286">a `[Op2, Op3]` `(Qubit[] => Unit is Ctl)` műveletek tömbje.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="b0ca6-287">Az üres tömb literálok, `[]`ek nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="b0ca6-288">A `new ★[0]`használata helyett, ahol a `★` a megfelelő típus helyőrzője, lehetővé teszi a nulla hosszúságú kívánt tömb létrehozását.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="b0ca6-289">Az azonos típusú két tömb esetében a bináris `+` operátor egy olyan új tömb létrehozásához használható, amely a két tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="b0ca6-290">Például `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="b0ca6-291">Tömb létrehozása</span><span class="sxs-lookup"><span data-stu-id="b0ca6-291">Array Creation</span></span>

<span data-ttu-id="b0ca6-292">A megadott típus és `Int` kifejezés alapján a `new` operátor a megadott méretű új tömb kiosztására használható.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="b0ca6-293">A `new Int[i+1]` például egy új `Int` tömböt foglal le `i+1` elemmel.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="b0ca6-294">Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="b0ca6-295">A legtöbb esetben ez a nulla valamilyen változata.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="b0ca6-296">Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="b0ca6-297">Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely futásidejű hiba nélkül nem használható.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="b0ca6-298">Ez hasonló a más nyelveken (például C# vagy Java) található null hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="b0ca6-299">A qubits vagy callables tartalmazó tömböket megfelelően kell inicializálni a nem alapértelmezett értékekkel, mielőtt az elemek biztonságosan használhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="b0ca6-300">A megfelelő inicializálási rutinok a <xref:microsoft.quantum.arrays>ban találhatók.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="b0ca6-301">Az egyes típusok alapértelmezett értékei a következők:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-301">The default values for each type are:</span></span>

<span data-ttu-id="b0ca6-302">Típus</span><span class="sxs-lookup"><span data-stu-id="b0ca6-302">Type</span></span> | <span data-ttu-id="b0ca6-303">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="b0ca6-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="b0ca6-304">_Érvénytelen qubit_</span><span class="sxs-lookup"><span data-stu-id="b0ca6-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="b0ca6-305">Az üres tartomány, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="b0ca6-306">_Érvénytelen hívható_</span><span class="sxs-lookup"><span data-stu-id="b0ca6-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="b0ca6-307">A rekord típusú típusok inicializálása elem-by-Element.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="b0ca6-308">Szaggatott tömbök</span><span class="sxs-lookup"><span data-stu-id="b0ca6-308">Jagged Arrays</span></span>

<span data-ttu-id="b0ca6-309">Egy szaggatott tömb, más néven "tömbök tömbje", egy tömb, amelynek elemei tömbök.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="b0ca6-310">A szaggatott tömb elemei eltérő méretűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="b0ca6-311">Az alábbi példa azt szemlélteti, hogyan deklarálható és inicializálható egy többrészes táblát jelképező szaggatott tömb.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a><span data-ttu-id="b0ca6-312">Tömb szeletek</span><span class="sxs-lookup"><span data-stu-id="b0ca6-312">Array Slices</span></span>

<span data-ttu-id="b0ca6-313">Egy tömböt megadó kifejezés és egy `Range` kifejezés miatt a `[` és `]` tömb szelet operátor használatával új kifejezés hozható létre.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="b0ca6-314">Az új kifejezés ugyanolyan típusú, mint a tömb, és a `Range`által definiált sorrendben tartalmazza a `Range`elemei által indexelt tömbös elemeket.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="b0ca6-315">Ha például a `a` `Double`s tömbhöz van kötve, akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely a `a` első négy elemét tartalmazza, de a fordított sorrendben, ahogy az `a`ban szerepel.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="b0ca6-316">Ha a `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú lesz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="b0ca6-317">Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell tenni a szelethez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="b0ca6-318">Ha például a `a` és az `b` a `Int`s tömbje, az összefűzésből származó szeletek a következőképpen lesznek kifejezve:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="b0ca6-319">A Q # összes tömbje nulla-alapú.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b0ca6-320">Vagyis a tömb `a` első eleme mindig `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="b0ca6-321">A 0,8-es verziótól kezdődően a hatókör-szeletelők környezetfüggő kifejezéseket támogatunk.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="b0ca6-322">A tartomány indítási és befejezési értékei a tartomány-szeletelő kifejezés kontextusában is kihagyhatók.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="b0ca6-323">Ebben az esetben a fordító a következő szabályok alkalmazásával következteti ki a tartományhoz tartozó elhatárolókat.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="b0ca6-324">Ha például a tartomány indítási értéke kimarad, akkor a késleltetett indítási érték</span><span class="sxs-lookup"><span data-stu-id="b0ca6-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="b0ca6-325">nulla, ha nincs megadva lépés, vagy a megadott lépés pozitív, és</span><span class="sxs-lookup"><span data-stu-id="b0ca6-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b0ca6-326">a szeletelt tömb hossza mínusz eggyel, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="b0ca6-327">Ha a tartomány befejezési értéke kimarad, akkor a következtetett vég értéke</span><span class="sxs-lookup"><span data-stu-id="b0ca6-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="b0ca6-328">a szeletelt tömb hossza mínusz eggyel, ha nincs megadva lépés, vagy a megadott lépés pozitív, és</span><span class="sxs-lookup"><span data-stu-id="b0ca6-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b0ca6-329">nulla, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-329">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a><span data-ttu-id="b0ca6-330">Tömb elem kifejezései</span><span class="sxs-lookup"><span data-stu-id="b0ca6-330">Array Element Expressions</span></span>

<span data-ttu-id="b0ca6-331">Egy tömb kifejezése és egy `Int` kifejezés miatt a `[` és a `]` Array Element operátor használatával új kifejezés hozható létre.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="b0ca6-332">Az új kifejezés ugyanolyan típusú lesz, mint a tömb elemének típusa.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="b0ca6-333">Ha például a `a` `Double`s tömbhöz van kötve, akkor `a[4]` `Double` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="b0ca6-334">Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell foglalni, hogy ki lehessen választani egy elemet.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="b0ca6-335">Ha például a `a` és az `b` a `Int`s tömbje, az összefűzésből származó elemek a következőképpen lesznek kifejezve:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="b0ca6-336">A Q # összes tömbje nulla-alapú.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b0ca6-337">Vagyis a tömb `a` első eleme mindig `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="b0ca6-338">Másolás és frissítés kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="b0ca6-339">Új tömbök hozhatók létre a meglévő példányokból másolás és frissítés kifejezések használatával.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="b0ca6-340">A copy-Update kifejezés a `expression1 w/ expression2 <- expression3`űrlap kifejezése, amelyben a `expression1` típusa csak `T[]` lehet `T`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="b0ca6-341">A második `expression2` meghatározza, hogy az elem (ek) milyen indexeket módosítson a `expression1` tömbhöz képest, és a típusnak `Int` vagy `Range`típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="b0ca6-342">Ha `expression2` `Int`típusú, a `expression3`nak `T`típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="b0ca6-343">Ha `expression2` `Range`típusú, a `expression3`nak `T[]`típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="b0ca6-344">A copy-Update kifejezés `arr w/ idx <- value` egy új tömböt hoz létre, amely a `arr`megfelelő elemére van beállítva, kivéve a (z) `idx`elem (ek) et, amely a `value`ban található egy értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="b0ca6-345">Ha például `arr` tartalmaz egy tömböt `[0,1,2,3]`, akkor</span><span class="sxs-lookup"><span data-stu-id="b0ca6-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="b0ca6-346">`arr w/ 0 <- 10` a tömb `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="b0ca6-347">`arr w/ 2 <- 10` a tömb `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="b0ca6-348">`arr w/ 0..2..3 <- [10,12]` a tömb `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="b0ca6-349">A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="b0ca6-350">Vegyük például a típust</span><span class="sxs-lookup"><span data-stu-id="b0ca6-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="b0ca6-351">Ha `c` a `Complex(1.,-1.)`típusú értéket tartalmazza, akkor a `c w/ Re <- 0.` egy `Complex` típusú kifejezés, amely kiértékeli a `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="b0ca6-352">Feltételes kifejezések</span><span class="sxs-lookup"><span data-stu-id="b0ca6-352">Conditional Expressions</span></span>

<span data-ttu-id="b0ca6-353">Egy adott típus és egy logikai kifejezés két másik kifejezése alapján a feltételes kifejezés a kérdőjel `?` és a függőleges sáv `|`használatával hozható létre.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="b0ca6-354">Például `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="b0ca6-355">Ebben a példában a feltételes kifejezés értéke `c`, ha `a==b` igaz, és `d` hamis.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="b0ca6-356">A két kifejezés kiértékelheti azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="b0ca6-357">Ebben az esetben a feltételes kifejezés típusa olyan művelet, amely azokat a bemeneteket és kimeneteket támogatja, amelyek a mindkét kifejezés által támogatott összes feltételt támogatják.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="b0ca6-358">Ha például `Op1`, `Op2`és `Op3` mind `Qubit[]=>Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja a `Controlled`, és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b0ca6-359">a `flag ? Op1 | Op2` `(Qubit[] => Unit)` művelet.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="b0ca6-360">a `flag ? Op1 | Op3` `(Qubit[] => Unit is Adj)` művelet.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="b0ca6-361">a `flag ? Op2 | Op3` `(Qubit[] => Unit is Ctl)` művelet.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="b0ca6-362">Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor ez a hívás csak akkor kerül sor, ha az eredmény a hívás értéke lesz.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="b0ca6-363">Ha például a `a==b ? C(qs) | D(qs)`, ha `a==b` igaz, akkor a rendszer meghívja a `C` műveletet, és ha hamis, akkor csak `D` fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="b0ca6-364">Ez hasonló a más nyelvek rövid összekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="b0ca6-365">Operátori prioritás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-365">Operator Precedence</span></span>

<span data-ttu-id="b0ca6-366">Minden bináris operátor megfelelő társítású, a `^`kivételével.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="b0ca6-367">Zárójelek, `[` és `]`a tömb szeleteléséhez és indexeléséhez, az operátorok megkötése előtt.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="b0ca6-368">Az operátorok a tömb indexelése után `Adjoint` és `Controlled` a kötést.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="b0ca6-369">A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.</span><span class="sxs-lookup"><span data-stu-id="b0ca6-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="b0ca6-370">Az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:</span><span class="sxs-lookup"><span data-stu-id="b0ca6-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="b0ca6-371">Művelet</span><span class="sxs-lookup"><span data-stu-id="b0ca6-371">Operator</span></span> | <span data-ttu-id="b0ca6-372">Aritása</span><span class="sxs-lookup"><span data-stu-id="b0ca6-372">Arity</span></span> | <span data-ttu-id="b0ca6-373">Leírás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-373">Description</span></span> | <span data-ttu-id="b0ca6-374">Operandusok típusai</span><span class="sxs-lookup"><span data-stu-id="b0ca6-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="b0ca6-375">záró `!`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-375">trailing `!`</span></span> | <span data-ttu-id="b0ca6-376">Unáris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-376">Unary</span></span> | <span data-ttu-id="b0ca6-377">Kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="b0ca6-377">Unwrap</span></span> | <span data-ttu-id="b0ca6-378">Bármely felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="b0ca6-378">Any user-defined type</span></span>
 <span data-ttu-id="b0ca6-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="b0ca6-380">Unáris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-380">Unary</span></span> | <span data-ttu-id="b0ca6-381">Numerikus negatív, bitenkénti komplement, logikai tagadás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="b0ca6-382">`Int`, `BigInt` vagy `Double` `-`, `Int` vagy `BigInt` esetében `~~~``Bool``not`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="b0ca6-383">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-383">Binary</span></span> | <span data-ttu-id="b0ca6-384">Egész számú Power</span><span class="sxs-lookup"><span data-stu-id="b0ca6-384">Integer power</span></span> | <span data-ttu-id="b0ca6-385">`Int` vagy `BigInt` az alaphoz, `Int` a kitevőhöz</span><span class="sxs-lookup"><span data-stu-id="b0ca6-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="b0ca6-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="b0ca6-387">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-387">Binary</span></span> | <span data-ttu-id="b0ca6-388">Osztás, szorzás, egész szám modulusa</span><span class="sxs-lookup"><span data-stu-id="b0ca6-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="b0ca6-389">`Int`, `BigInt` vagy `Double` `/` és `*`, `Int` vagy `BigInt` számára `%`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="b0ca6-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-390">`+`, `-`</span></span> | <span data-ttu-id="b0ca6-391">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-391">Binary</span></span> | <span data-ttu-id="b0ca6-392">Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="b0ca6-393">`Int`, `BigInt` vagy `Double`, továbbá `String` vagy bármely tömb típusa `+`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="b0ca6-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="b0ca6-395">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-395">Binary</span></span> | <span data-ttu-id="b0ca6-396">Bal SHIFT, jobb SHIFT</span><span class="sxs-lookup"><span data-stu-id="b0ca6-396">Left shift, right shift</span></span> | <span data-ttu-id="b0ca6-397">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="b0ca6-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="b0ca6-399">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-399">Binary</span></span> | <span data-ttu-id="b0ca6-400">Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="b0ca6-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="b0ca6-401">`Int`, `BigInt` vagy `Double`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="b0ca6-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-402">`==`, `!=`</span></span> | <span data-ttu-id="b0ca6-403">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-403">Binary</span></span> | <span data-ttu-id="b0ca6-404">egyenlő, nem egyenlő összehasonlítások</span><span class="sxs-lookup"><span data-stu-id="b0ca6-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="b0ca6-405">bármely primitív típus</span><span class="sxs-lookup"><span data-stu-id="b0ca6-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="b0ca6-406">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-406">Binary</span></span> | <span data-ttu-id="b0ca6-407">Bitenkénti és</span><span class="sxs-lookup"><span data-stu-id="b0ca6-407">Bitwise AND</span></span> | <span data-ttu-id="b0ca6-408">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="b0ca6-409">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-409">Binary</span></span> | <span data-ttu-id="b0ca6-410">Bitenkénti XOR</span><span class="sxs-lookup"><span data-stu-id="b0ca6-410">Bitwise XOR</span></span> | <span data-ttu-id="b0ca6-411">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="b0ca6-412">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-412">Binary</span></span> | <span data-ttu-id="b0ca6-413">Bitenkénti vagy</span><span class="sxs-lookup"><span data-stu-id="b0ca6-413">Bitwise OR</span></span> | <span data-ttu-id="b0ca6-414">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="b0ca6-415">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-415">Binary</span></span> | <span data-ttu-id="b0ca6-416">Logikai és</span><span class="sxs-lookup"><span data-stu-id="b0ca6-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="b0ca6-417">Bináris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-417">Binary</span></span> | <span data-ttu-id="b0ca6-418">Logikai vagy</span><span class="sxs-lookup"><span data-stu-id="b0ca6-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="b0ca6-419">Bináris/Ternáris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-419">Binary/Ternary</span></span> | <span data-ttu-id="b0ca6-420">Tartomány operátora</span><span class="sxs-lookup"><span data-stu-id="b0ca6-420">Range operator</span></span> | `Int`
 <span data-ttu-id="b0ca6-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-421">`?` `|`</span></span> | <span data-ttu-id="b0ca6-422">Ternáris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-422">Ternary</span></span> | <span data-ttu-id="b0ca6-423">Feltételes</span><span class="sxs-lookup"><span data-stu-id="b0ca6-423">Conditional</span></span> | <span data-ttu-id="b0ca6-424">a bal oldali `Bool`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="b0ca6-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="b0ca6-425">`w/` `<-`</span></span> | <span data-ttu-id="b0ca6-426">Ternáris</span><span class="sxs-lookup"><span data-stu-id="b0ca6-426">Ternary</span></span> | <span data-ttu-id="b0ca6-427">Másolás és frissítés</span><span class="sxs-lookup"><span data-stu-id="b0ca6-427">Copy-and-update</span></span> | <span data-ttu-id="b0ca6-428">Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="b0ca6-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
