---
title: 'Q # kifejezések'
description: 'Megtudhatja, hogyan adhat meg, hivatkozhat és egyesíthet állandókat, változókat, operátorokat, műveleteket és függvényeket kifejezésként a Q #-ban.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683929"
---
# <a name="expressions"></a><span data-ttu-id="6fb10-103">Kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="6fb10-104">Csoportosítás</span><span class="sxs-lookup"><span data-stu-id="6fb10-104">Grouping</span></span>

<span data-ttu-id="6fb10-105">Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="6fb10-106">`(7)` `Int` Például egy `([1,2,3])` kifejezés, amely egy tömb `Int`típusú kifejezés, és `((1,2))` egy típusú `(Int, Int)`kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="6fb10-107">A [típus modellben](xref:microsoft.quantum.language.type-model#tuple-types) leírt egyszerű értékek és egyelemes rekordok közötti egyenértékűség eltávolítja a kétértelműség `(6)` csoportot és `(6)` egy egyelemű rekordot.</span><span class="sxs-lookup"><span data-stu-id="6fb10-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="6fb10-108">Szimbólumok</span><span class="sxs-lookup"><span data-stu-id="6fb10-108">Symbols</span></span>

<span data-ttu-id="6fb10-109">Egy Type értékhez `'T` kötött vagy hozzárendelt szimbólum neve egy típusú `'T`kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="6fb10-110">Ha például a szimbólum `count` az egész értékhez `5`van kötve, akkor `count` az egy egész szám kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="6fb10-111">Numerikus kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-111">Numeric Expressions</span></span>

<span data-ttu-id="6fb10-112">A numerikus kifejezések a következő típusú `Int` `BigInt`kifejezések:, `Double`vagy.</span><span class="sxs-lookup"><span data-stu-id="6fb10-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="6fb10-113">Vagyis egész vagy lebegőpontos számok.</span><span class="sxs-lookup"><span data-stu-id="6fb10-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="6fb10-114">`Int`a Q # konstansai azonosak a C#-ban az egész szám literálokkal, azzal a különbséggel, hogy nincs szükség "l" vagy "L" értékre (vagy engedélyezett).</span><span class="sxs-lookup"><span data-stu-id="6fb10-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="6fb10-115">A hexadecimális és a bináris egész számok "0x" és "0b" előtaggal támogatottak.</span><span class="sxs-lookup"><span data-stu-id="6fb10-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="6fb10-116">`BigInt`a Q #-ban szereplő literálok azonosak a .NET-ben található Big Integer karakterláncokkal, amelyek egy "l" vagy "L" záró karakterrel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="6fb10-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="6fb10-117">A hexadecimális nagy egész számok "0x" előtaggal támogatottak.</span><span class="sxs-lookup"><span data-stu-id="6fb10-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="6fb10-118">Így az alábbi `BigInt` értékek érvényesek a literálok összes érvényes használatára:</span><span class="sxs-lookup"><span data-stu-id="6fb10-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="6fb10-119">`Double`a Q # konstansai a C#-ban dupla literálok, azzal a különbséggel, hogy a "d" vagy a "D" nem kötelező (vagy engedélyezett).</span><span class="sxs-lookup"><span data-stu-id="6fb10-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="6fb10-120">Egy adott elemtípus tömb `Int` kifejezése miatt a `Length` beépített függvénnyel létrehozható egy kifejezés, amely zárójelek közé foglalt tömb kifejezéssel `(` és. `)`</span><span class="sxs-lookup"><span data-stu-id="6fb10-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="6fb10-121">Ha `a` például egy tömbhöz van kötve, akkor `Length(a)` az egy egész szám kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="6fb10-122">Ha `b` `Int[][]`az egész számokból álló tömbök tömbje, akkor `Length(b)` a-ben `b`az altömbök száma, a `Length(b[1])` pedig a második altömbben lévő egész számok száma. `b`</span><span class="sxs-lookup"><span data-stu-id="6fb10-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="6fb10-123">Az adott típus két numerikus kifejezése, a bináris operátorok `+` `-` `*`, a, és `/` az új numerikus kifejezéseket is felhasználhatja.</span><span class="sxs-lookup"><span data-stu-id="6fb10-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="6fb10-124">Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.</span><span class="sxs-lookup"><span data-stu-id="6fb10-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="6fb10-125">A két egész szám kifejezés miatt a bináris `^` operátor (Power) egy új egész kifejezés létrehozásához használható.</span><span class="sxs-lookup"><span data-stu-id="6fb10-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="6fb10-126">Hasonlóképpen, `^` két kettős kifejezéssel is használható, amelyek új dupla kifejezést alkotnak.</span><span class="sxs-lookup"><span data-stu-id="6fb10-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="6fb10-127">Végül a `^` bal oldalon egy nagy egész számmal, a jobb oldalon pedig egy egész számmal, egy új Big Integer típusú kifejezés létrehozásához is használható.</span><span class="sxs-lookup"><span data-stu-id="6fb10-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="6fb10-128">Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, a rendszer futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="6fb10-129">A két egész vagy nagy egész szám típusú kifejezés esetében egy új egész vagy Big Integer kifejezés is létrehozható `%` a (modulus) `&&&` , (bitenkénti és) `|||` , (bitenkénti vagy), `^^^` vagy (bitenkénti XOR) operátorok használatával.</span><span class="sxs-lookup"><span data-stu-id="6fb10-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="6fb10-130">A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) `>>>` vagy (aritmetikai jobbra váltás) operátorok használhatók a bal oldali kifejezéssel megegyező típusú új kifejezés létrehozására.</span><span class="sxs-lookup"><span data-stu-id="6fb10-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="6fb10-131">A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="6fb10-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="6fb10-132">A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, a rendszer futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="6fb10-133">Ha a áthelyezhető szám egész szám, akkor a rendszer a eltolás mértékét értelmezi `mod 64`. Ez azt eredményezi, hogy az 1. és a 65 eltolása ugyanaz a hatása.</span><span class="sxs-lookup"><span data-stu-id="6fb10-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="6fb10-134">Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.</span><span class="sxs-lookup"><span data-stu-id="6fb10-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="6fb10-135">A negatív érték eltolása balra vagy jobbra is negatív számot eredményez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="6fb10-136">Ez azt okozhatja, hogy az egyik lépés balra vagy jobbra való eltolása pontosan ugyanaz, mint a 2. számú szorzás vagy osztás.</span><span class="sxs-lookup"><span data-stu-id="6fb10-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="6fb10-137">Az egész szám és az Integer modulus ugyanazt a viselkedést követi a negatív számok esetében, mint a C#.</span><span class="sxs-lookup"><span data-stu-id="6fb10-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="6fb10-138">Ez azt eredményezi `a % b` , hogy mindig ugyanazzal a jellel `a`fog rendelkezni, `b * (a / b) + a % b` és `a`mindig egyenlő lesz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="6fb10-139">Például:</span><span class="sxs-lookup"><span data-stu-id="6fb10-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="6fb10-140">5</span><span class="sxs-lookup"><span data-stu-id="6fb10-140">5</span></span> | <span data-ttu-id="6fb10-141">2</span><span class="sxs-lookup"><span data-stu-id="6fb10-141">2</span></span> | <span data-ttu-id="6fb10-142">2</span><span class="sxs-lookup"><span data-stu-id="6fb10-142">2</span></span> | <span data-ttu-id="6fb10-143">1</span><span class="sxs-lookup"><span data-stu-id="6fb10-143">1</span></span>
 <span data-ttu-id="6fb10-144">5</span><span class="sxs-lookup"><span data-stu-id="6fb10-144">5</span></span> | <span data-ttu-id="6fb10-145">-2</span><span class="sxs-lookup"><span data-stu-id="6fb10-145">-2</span></span> | <span data-ttu-id="6fb10-146">-2</span><span class="sxs-lookup"><span data-stu-id="6fb10-146">-2</span></span> | <span data-ttu-id="6fb10-147">1</span><span class="sxs-lookup"><span data-stu-id="6fb10-147">1</span></span>
 <span data-ttu-id="6fb10-148">-5</span><span class="sxs-lookup"><span data-stu-id="6fb10-148">-5</span></span> | <span data-ttu-id="6fb10-149">2</span><span class="sxs-lookup"><span data-stu-id="6fb10-149">2</span></span> | <span data-ttu-id="6fb10-150">-2</span><span class="sxs-lookup"><span data-stu-id="6fb10-150">-2</span></span> | <span data-ttu-id="6fb10-151">-1</span><span class="sxs-lookup"><span data-stu-id="6fb10-151">-1</span></span>
 <span data-ttu-id="6fb10-152">-5</span><span class="sxs-lookup"><span data-stu-id="6fb10-152">-5</span></span> | <span data-ttu-id="6fb10-153">-2</span><span class="sxs-lookup"><span data-stu-id="6fb10-153">-2</span></span> | <span data-ttu-id="6fb10-154">2</span><span class="sxs-lookup"><span data-stu-id="6fb10-154">2</span></span> | <span data-ttu-id="6fb10-155">-1</span><span class="sxs-lookup"><span data-stu-id="6fb10-155">-1</span></span>

<span data-ttu-id="6fb10-156">A Big Integer osztás és a modulus hasonló módon működik.</span><span class="sxs-lookup"><span data-stu-id="6fb10-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="6fb10-157">A numerikus kifejezéseket megadva egy új kifejezés hozható létre az `-` unáris operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="6fb10-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="6fb10-158">Az új kifejezés ugyanolyan típusú lesz, mint az összetevő kifejezése.</span><span class="sxs-lookup"><span data-stu-id="6fb10-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="6fb10-159">Adott egész szám vagy nagy egész szám kifejezés esetén az azonos típusú új kifejezés az `~~~` (bitenkénti komplement) unáris operátor használatával hozható létre.</span><span class="sxs-lookup"><span data-stu-id="6fb10-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="6fb10-160">Logikai kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-160">Boolean Expressions</span></span>

<span data-ttu-id="6fb10-161">A két `Bool` literális érték `true` a `false`és a.</span><span class="sxs-lookup"><span data-stu-id="6fb10-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="6fb10-162">Az azonos primitív típusú két kifejezés miatt a és `==` `!=` a bináris operátor is használható `Bool` kifejezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6fb10-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="6fb10-163">A kifejezés akkor igaz, ha a két kifejezés egyenlő, és hamis, ha nem.</span><span class="sxs-lookup"><span data-stu-id="6fb10-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="6fb10-164">A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani.</span><span class="sxs-lookup"><span data-stu-id="6fb10-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="6fb10-165">Például a "kicsomagolás" operátor `!` használatával (amely a [Q # Type Model oldalon](xref:microsoft.quantum.language.type-model#user-defined-types)látható),</span><span class="sxs-lookup"><span data-stu-id="6fb10-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="6fb10-166">Az `Qubit` értékek egyenlőségének összehasonlítása az identitással egyenlő; Ez azt jelzi, hogy a két kifejezés ugyanazt a qubit azonosítja-e.</span><span class="sxs-lookup"><span data-stu-id="6fb10-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="6fb10-167">A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.</span><span class="sxs-lookup"><span data-stu-id="6fb10-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="6fb10-168">Az `Double` értékek egyenlőségének összehasonlítása a kerekítési hatások miatt félrevezető lehet.</span><span class="sxs-lookup"><span data-stu-id="6fb10-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="6fb10-169">Például: `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="6fb10-170">A két numerikus kifejezéstől függően a bináris `>`operátorok `<` `>=`, a, `<=` és felhasználhatók egy olyan új logikai kifejezés létrehozására, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, mint a második kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="6fb10-171">A két logikai kifejezés miatt a és `and` `or` a bináris operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha a két kifejezés mindkét (vagy mindkét) értéke igaz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="6fb10-172">A logikai kifejezéseket megadva az `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.</span><span class="sxs-lookup"><span data-stu-id="6fb10-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="6fb10-173">Karakterlánc-kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-173">String Expressions</span></span>

<span data-ttu-id="6fb10-174">A Q # lehetővé teszi a karakterláncok használatát `fail` az utasításban `Log` és a standard függvényben.</span><span class="sxs-lookup"><span data-stu-id="6fb10-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="6fb10-175">A Q # sztringek literálok vagy interpolált karakterláncok.</span><span class="sxs-lookup"><span data-stu-id="6fb10-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="6fb10-176">A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterlánc-literálokra: az Unicode-karakterek egy számsorozata `"`idézőjelek közé.</span><span class="sxs-lookup"><span data-stu-id="6fb10-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="6fb10-177">Egy karakterláncon belül a háttér `\` -perjel karakter felhasználható dupla idézőjelek kiírására, valamint egy új vonal `\n`beszúrására, a kocsivissza `\r`karaktert és a lapot. `\t`</span><span class="sxs-lookup"><span data-stu-id="6fb10-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="6fb10-178">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="6fb10-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="6fb10-179">A Q # szintaxis a karakterlánc-interpolációhoz a C# 7,0 szintaxis részhalmaza. A Q # nem támogatja a Verbatim (többsoros) interpolált karakterláncokat.</span><span class="sxs-lookup"><span data-stu-id="6fb10-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="6fb10-180">Lásd: [*interpolált karakterláncok*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) a C# szintaxishoz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="6fb10-181">Az interpolált karakterláncban szereplő kifejezések a Q # szintaxist követik, nem a C# szintaxist.</span><span class="sxs-lookup"><span data-stu-id="6fb10-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="6fb10-182">Bármely érvényes Q # kifejezés egy interpolált karakterláncban jelenhet meg.</span><span class="sxs-lookup"><span data-stu-id="6fb10-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="6fb10-183">Qubit kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-183">Qubit Expressions</span></span>

<span data-ttu-id="6fb10-184">Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékek vagy tömb elemeihez `Qubit` van kötve.</span><span class="sxs-lookup"><span data-stu-id="6fb10-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="6fb10-185">Nincsenek `Qubit` literálok.</span><span class="sxs-lookup"><span data-stu-id="6fb10-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="6fb10-186">Pauli-kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-186">Pauli Expressions</span></span>

<span data-ttu-id="6fb10-187">A négy `Pauli` érték `PauliI` `PauliX` `PauliY`:,,, és `PauliZ`, minden érvényes `Pauli` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="6fb10-188">Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékek vagy tömb elemeihez `Pauli` van kötve.</span><span class="sxs-lookup"><span data-stu-id="6fb10-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="6fb10-189">Eredmény kifejezései</span><span class="sxs-lookup"><span data-stu-id="6fb10-189">Result Expressions</span></span>

<span data-ttu-id="6fb10-190">A két `Result` érték ( `One` és `Zero`) érvényes `Result` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="6fb10-191">Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékek vagy tömb elemeihez `Result` van kötve.</span><span class="sxs-lookup"><span data-stu-id="6fb10-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="6fb10-192">Különösen fontos megjegyezni, hogy `One` nem ugyanaz, mint az egész szám `1`, és nincs közvetlen konverzió a közöttük.</span><span class="sxs-lookup"><span data-stu-id="6fb10-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="6fb10-193">Ugyanez érvényes a és `Zero` `0`a esetében is.</span><span class="sxs-lookup"><span data-stu-id="6fb10-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="6fb10-194">Tartomány kifejezései</span><span class="sxs-lookup"><span data-stu-id="6fb10-194">Range Expressions</span></span>

<span data-ttu-id="6fb10-195">Egy három `Int` kifejezés `start`, `step`a és `stop` `start .. step .. stop` a egy olyan tartomány kifejezése, amelynek első eleme `start`a, a második `start+step`elem, a harmadik `start+step+step`elem, stb., `stop` amíg a rendszer át nem adja.</span><span class="sxs-lookup"><span data-stu-id="6fb10-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="6fb10-196">A tartomány lehet üres, ha például `step` a pozitív és `stop < start`a.</span><span class="sxs-lookup"><span data-stu-id="6fb10-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="6fb10-197">A tartomány utolsó `stop` eleme lesz, ha a és `start` `stop` a közötti különbség a többszöröse; `step` vagyis a tartomány mindkét végén szerepel.</span><span class="sxs-lookup"><span data-stu-id="6fb10-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="6fb10-198">A két `Int` kifejezésnek `start` megfelelő `stop`, `start .. stop` és egy tartománybeli kifejezés, amely egyenlő `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="6fb10-199">Vegye figyelembe, hogy `step` a vélelmezett érték + 1 `stop` , még akkor `start`is, ha a értéke kisebb, mint; ilyen esetben a tartomány üres.</span><span class="sxs-lookup"><span data-stu-id="6fb10-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="6fb10-200">Néhány példa a tartományokra:</span><span class="sxs-lookup"><span data-stu-id="6fb10-200">Some example ranges are:</span></span>

- <span data-ttu-id="6fb10-201">`1..3`az 1., 2. és 3. tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="6fb10-202">`2..2..5`a 2. és 4. tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="6fb10-203">`2..2..6`a 2, 4, 6. tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="6fb10-204">`6..-2..2`a 6, 4, 2 tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="6fb10-205">`2..1`az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="6fb10-206">`2..6..7`a 2. tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="6fb10-207">`2..2..1`az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="6fb10-208">`1..-1..2`az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="6fb10-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="6fb10-209">Hívható kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-209">Callable Expressions</span></span>

<span data-ttu-id="6fb10-210">A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.</span><span class="sxs-lookup"><span data-stu-id="6fb10-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="6fb10-211">`X` Például egy olyan műveleti literál, amely a szabványos könyvtári `X` műveletre hivatkozik, `Message` és egy függvény literál, amely a standard Library `Message` függvényre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="6fb10-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="6fb10-212">Ha egy művelet támogatja az `Adjoint` elválasztó műveletet `Adjoint op` , akkor egy művelet kifejezése.</span><span class="sxs-lookup"><span data-stu-id="6fb10-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="6fb10-213">Hasonlóképpen, ha a művelet támogatja az `Controlled` elválasztó műveletet `Controlled op` , akkor egy művelet kifejezése.</span><span class="sxs-lookup"><span data-stu-id="6fb10-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="6fb10-214">Ezeknek a kifejezéseknek a típusai a következőben vannak [megadva.](xref:microsoft.quantum.language.type-model#functors)</span><span class="sxs-lookup"><span data-stu-id="6fb10-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="6fb10-215">A (`Adjoint` és `Controlled`) az összes többi operátorral szorosabban kötődik, kivéve a kicsomagolási operátort `!` és a tömb `[]`indexelését.</span><span class="sxs-lookup"><span data-stu-id="6fb10-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="6fb10-216">Így a következők mindegyike jogi, feltételezve, hogy a műveletek támogatják a használt munkafolyamatokat:</span><span class="sxs-lookup"><span data-stu-id="6fb10-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="6fb10-217">Egy meghívásos literál is használható értékként, azaz egy változóhoz való hozzárendeléshez, vagy egy másik meghíváshoz való továbbításhoz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="6fb10-218">Ebben az esetben, ha a meghívható paraméterekkel rendelkezik, azokat a meghívásos érték részeként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="6fb10-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="6fb10-219">Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel.</span><span class="sxs-lookup"><span data-stu-id="6fb10-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6fb10-220">Ha `Fun` például a függvény aláírása `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="6fb10-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="6fb10-221">Hívható hívási kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="6fb10-222">Egy meghívásos (művelet vagy függvény) kifejezés és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos kifejezés úgy hozható létre, hogy hozzáfűzi a rekord kifejezését a meghívható kifejezéshez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="6fb10-223">A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6fb10-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="6fb10-224">Ha `Op` például az egy `((Int, Qubit) => Double)`aláírással rendelkező művelet, `Op(3, qubit1)` a egy típusú `Double`kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6fb10-225">Hasonlóképpen, ha `Sin` az egy függvény az `(Double -> Double)`aláírással `Sin(0.1)` , egy típusú `Double`kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6fb10-226">Végül, ha `Builder` az a függvény az aláírással `(Int -> (Int -> Int))`, `Builder(3)` akkor a függvény a from int értékre.</span><span class="sxs-lookup"><span data-stu-id="6fb10-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="6fb10-227">Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.</span><span class="sxs-lookup"><span data-stu-id="6fb10-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="6fb10-228">Így az előző bekezdésből történő hívás `Builder` eredményének meghívásához a helyes szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="6fb10-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="6fb10-229">A típus-paraméteres metódus meghívásakor a tényleges Type paraméterek a szögletes zárójelben `<` és `>` a meghívásos kifejezés után is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="6fb10-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="6fb10-230">Ez általában szükségtelen, mivel a Q # fordítóprogram a tényleges típusokat fogja kikövetkeztetni.</span><span class="sxs-lookup"><span data-stu-id="6fb10-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="6fb10-231">A részleges alkalmazáshoz szükséges (lásd alább), ha egy Type-paraméteres argumentum nincs megadva.</span><span class="sxs-lookup"><span data-stu-id="6fb10-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="6fb10-232">Időnként hasznos lehet, ha a különböző felállókkal rendelkező műveletek átadása meghívásos támogatással történik.</span><span class="sxs-lookup"><span data-stu-id="6fb10-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="6fb10-233">Ha `Func` `('T1, 'T2, 'T1) -> 'T2`például rendelkezik aláírással, `Op1` és `Op2` `(Qubit[] => Unit is Adj)`aláírással rendelkezik, és `Op3` aláírással `(Qubit[] => Unit)`rendelkezik, az `Func` első `Op1` argumentumként, `Op2` a másodikként és `Op3` a harmadikként való meghívásához:</span><span class="sxs-lookup"><span data-stu-id="6fb10-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="6fb10-234">A típus specifikációjának megadása kötelező `Op3` , `Op1` mert különböző típusok vannak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="6fb10-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="6fb10-235">Részleges alkalmazás</span><span class="sxs-lookup"><span data-stu-id="6fb10-235">Partial Application</span></span>

<span data-ttu-id="6fb10-236">Egy meghívásos kifejezés miatt egy új hívható is létrehozható az argumentumok egy részhalmazának megadásával a meghívónak.</span><span class="sxs-lookup"><span data-stu-id="6fb10-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="6fb10-237">Ezt nevezzük _részleges alkalmazásnak_.</span><span class="sxs-lookup"><span data-stu-id="6fb10-237">This is called _partial application_.</span></span>

<span data-ttu-id="6fb10-238">A Q #-ban a részlegesen alkalmazott meghívót egy normál meghívásos kifejezés megírásával, de aláhúzással `_`, a meghatározatlan argumentumok használatával fejezzük ki.</span><span class="sxs-lookup"><span data-stu-id="6fb10-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="6fb10-239">Az eredményül kapott meghívó ugyanazzal az eredménnyel rendelkezik, mint az alapszintű hívható, és ugyanazokat a specializációkat kell megadnia a műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="6fb10-240">A részleges alkalmazás bemeneti típusa egyszerűen az eredeti típus, ahol a megadott argumentumok el lettek távolítva.</span><span class="sxs-lookup"><span data-stu-id="6fb10-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="6fb10-241">Ha egy megváltoztathatatlan változót egy részleges alkalmazás létrehozásakor megadott argumentumként ad át, a rendszer a változó aktuális értékét használja.</span><span class="sxs-lookup"><span data-stu-id="6fb10-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="6fb10-242">A változó értékének módosítása később nem befolyásolja a részleges alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="6fb10-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="6fb10-243">Például ha `Op` a típus `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="6fb10-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="6fb10-244">`Op(5,(_,_))`típus `(((Qubit,Qubit), Double) => Unit is Adj)`, és így van `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="6fb10-245">`Op(_,(_,1.0))`típusa `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="6fb10-246">`Op(_,((q1,q2),_))`típusa `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="6fb10-247">Vegye figyelembe, hogy itt is alkalmazunk egy Egyrekordos egyenértékűséget.</span><span class="sxs-lookup"><span data-stu-id="6fb10-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="6fb10-248">Ha a részben alkalmazott hívható olyan paraméterekkel rendelkezik, amelyeket a fordító nem tud következtetni, meg kell adni azokat a Meghívási helyen.</span><span class="sxs-lookup"><span data-stu-id="6fb10-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="6fb10-249">A részleges alkalmazás nem rendelkezhet meghatározatlan típusú paraméterekkel.</span><span class="sxs-lookup"><span data-stu-id="6fb10-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6fb10-250">Például ha `Op` a típus `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="6fb10-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="6fb10-251">Rekurzió</span><span class="sxs-lookup"><span data-stu-id="6fb10-251">Recursion</span></span>

<span data-ttu-id="6fb10-252">A Q # callables közvetlenül vagy közvetve rekurzívak.</span><span class="sxs-lookup"><span data-stu-id="6fb10-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="6fb10-253">Ez azt is megteheti, hogy egy művelet vagy funkció meghívhatja magát, vagy meghívhat egy másik meghívót, amely közvetlenül vagy közvetett módon hívja meg a meghívásos műveletet.</span><span class="sxs-lookup"><span data-stu-id="6fb10-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="6fb10-254">A rekurzió használatának két fontos megjegyzése van, azonban:</span><span class="sxs-lookup"><span data-stu-id="6fb10-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="6fb10-255">A rekurzió a műveletekben való használata valószínűleg ütközik bizonyos optimalizálásokkal.</span><span class="sxs-lookup"><span data-stu-id="6fb10-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="6fb10-256">Ez jelentős hatással lehet az algoritmus végrehajtási idejére.</span><span class="sxs-lookup"><span data-stu-id="6fb10-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="6fb10-257">Ha tényleges kvantum-eszközön végez végrehajtást, előfordulhat, hogy a halmozott terület korlátozva van, ezért a mélyebb rekurzió hibát okozhat.</span><span class="sxs-lookup"><span data-stu-id="6fb10-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="6fb10-258">A Q # Compiler és a Runtime nem azonosítja és optimalizálja a farok rekurzióját.</span><span class="sxs-lookup"><span data-stu-id="6fb10-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="6fb10-259">Rekordos kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-259">Tuple Expressions</span></span>

<span data-ttu-id="6fb10-260">A rekordos literál a megfelelő típusú elemek sorozata, vesszővel elválasztva, a és `(` `)`a közé foglalt módon.</span><span class="sxs-lookup"><span data-stu-id="6fb10-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="6fb10-261">`(1, One)` Például egy `(Int, Result)` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="6fb10-262">A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.</span><span class="sxs-lookup"><span data-stu-id="6fb10-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="6fb10-263">Felhasználó által definiált típusú kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="6fb10-264">A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.</span><span class="sxs-lookup"><span data-stu-id="6fb10-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="6fb10-265">Ha `IntPair` például a felhasználó által definiált típus a `(Int, Int)`(z) alapján, `IntPair(2,3)` akkor az adott típusú érvényes literál lenne.</span><span class="sxs-lookup"><span data-stu-id="6fb10-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="6fb10-266">A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.</span><span class="sxs-lookup"><span data-stu-id="6fb10-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="6fb10-267">Kifejezések kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="6fb10-267">Unwrap Expressions</span></span>

<span data-ttu-id="6fb10-268">A Q # értéknél a kicsomagolás operátor egy záró felkiáltójel `!`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="6fb10-269">`IntPair` Például, ha egy felhasználó által definiált típus, amely egy alapul `(Int, Int)`szolgáló típussal rendelkezik `s` , és egy `IntPair(2,3)`változó értékkel rendelkezik, akkor `s!` a következő lesz `(2,3)`:.</span><span class="sxs-lookup"><span data-stu-id="6fb10-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="6fb10-270">A felhasználó által definiált típusok esetében definiált más felhasználók által definiált típusok esetében.</span><span class="sxs-lookup"><span data-stu-id="6fb10-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="6fb10-271">lehet, hogy a kicsomagolási operátor megismétlődik; például a kétszeresen kicsomagolt értéket `s!!` jelöli. `s`</span><span class="sxs-lookup"><span data-stu-id="6fb10-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="6fb10-272">Így `WrappedPair` ha a felhasználó által definiált típus egy alapul szolgáló típusú `IntPair`, és `t` egy változó értékkel `WrappedPair(IntPair(1,2))`, akkor `t!!` a következő lesz `(1,2)`:.</span><span class="sxs-lookup"><span data-stu-id="6fb10-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="6fb10-273">Az `!` operátor magasabb prioritású, mint az összes többi operátor `[]` , mint a tömb indexelése és a szeletelése.</span><span class="sxs-lookup"><span data-stu-id="6fb10-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="6fb10-274">`!`és `[]` a kötés elhelyezése; `a[i]![3]` azaz a következőt kell elolvasnia `((a[i])!)[3]`: a `i`"th elemének `a`kicsomagolása, majd a nem burkolt érték harmadik elemének beolvasása (tömbnek kell lennie).</span><span class="sxs-lookup"><span data-stu-id="6fb10-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="6fb10-275">Az `!` operátor elsőbbsége egy olyan hatással van, amely esetleg nem nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="6fb10-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="6fb10-276">Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.</span><span class="sxs-lookup"><span data-stu-id="6fb10-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="6fb10-277">Például:</span><span class="sxs-lookup"><span data-stu-id="6fb10-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="6fb10-278">Tömb kifejezései</span><span class="sxs-lookup"><span data-stu-id="6fb10-278">Array Expressions</span></span>

<span data-ttu-id="6fb10-279">A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, a és `[` `]`a közé.</span><span class="sxs-lookup"><span data-stu-id="6fb10-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="6fb10-280">Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.</span><span class="sxs-lookup"><span data-stu-id="6fb10-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="6fb10-281">Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="6fb10-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="6fb10-282">A tömb elemének típusa az összes elem által támogatott összes olyan futtatót támogatni fogja.</span><span class="sxs-lookup"><span data-stu-id="6fb10-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="6fb10-283">Például, ha `Op1` `Op2`, és `Op3` mind a `Qubit[] => Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja `Controlled`és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="6fb10-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6fb10-284">`[Op1, Op2]`a a `(Qubit[] => Unit)` műveletek tömbje.</span><span class="sxs-lookup"><span data-stu-id="6fb10-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="6fb10-285">`[Op1, Op3]`a a `(Qubit[] => Unit is Adj)` műveletek tömbje.</span><span class="sxs-lookup"><span data-stu-id="6fb10-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="6fb10-286">`[Op2, Op3]`a a `(Qubit[] => Unit is Ctl)` műveletek tömbje.</span><span class="sxs-lookup"><span data-stu-id="6fb10-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="6fb10-287">Az üres tömb literálok `[]`nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="6fb10-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="6fb10-288">A használata `new ★[0]`helyett, `★` ahol a egy megfelelő típusú helyőrző, lehetővé teszi a nulla hosszúságú kívánt tömb létrehozását.</span><span class="sxs-lookup"><span data-stu-id="6fb10-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="6fb10-289">Mivel a két tömb azonos típusú, a bináris `+` operátor egy olyan új tömb létrehozásához használható, amely a két tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="6fb10-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="6fb10-290">`[1,2,3] + [4,5,6]` Például: `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="6fb10-291">Tömb létrehozása</span><span class="sxs-lookup"><span data-stu-id="6fb10-291">Array Creation</span></span>

<span data-ttu-id="6fb10-292">Adott típus és `Int` kifejezés alapján az `new` operátor felhasználható a megadott méretű új tömb kiosztására.</span><span class="sxs-lookup"><span data-stu-id="6fb10-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="6fb10-293">`new Int[i+1]` Például lefoglalhat egy új `Int` tömböt `i+1` elemekkel.</span><span class="sxs-lookup"><span data-stu-id="6fb10-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="6fb10-294">Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.</span><span class="sxs-lookup"><span data-stu-id="6fb10-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="6fb10-295">A legtöbb esetben ez a nulla valamilyen változata.</span><span class="sxs-lookup"><span data-stu-id="6fb10-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="6fb10-296">Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="6fb10-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="6fb10-297">Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely futásidejű hiba nélkül nem használható.</span><span class="sxs-lookup"><span data-stu-id="6fb10-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="6fb10-298">Ez hasonló a más nyelveken (például C# vagy Java) található null hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="6fb10-299">A qubits vagy callables tartalmazó tömböket megfelelően kell inicializálni a nem alapértelmezett értékekkel, mielőtt az elemek biztonságosan használhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="6fb10-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="6fb10-300">A megfelelő inicializálási rutinok a következő címen <xref:microsoft.quantum.arrays>találhatók:.</span><span class="sxs-lookup"><span data-stu-id="6fb10-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6fb10-301">Az egyes típusok alapértelmezett értékei a következők:</span><span class="sxs-lookup"><span data-stu-id="6fb10-301">The default values for each type are:</span></span>

<span data-ttu-id="6fb10-302">Típus</span><span class="sxs-lookup"><span data-stu-id="6fb10-302">Type</span></span> | <span data-ttu-id="6fb10-303">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="6fb10-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="6fb10-304">_Érvénytelen qubit_</span><span class="sxs-lookup"><span data-stu-id="6fb10-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="6fb10-305">Az üres tartomány,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="6fb10-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="6fb10-306">_Érvénytelen hívható_</span><span class="sxs-lookup"><span data-stu-id="6fb10-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="6fb10-307">A rekord típusú típusok inicializálása elem-by-Element.</span><span class="sxs-lookup"><span data-stu-id="6fb10-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="6fb10-308">Szaggatott tömbök</span><span class="sxs-lookup"><span data-stu-id="6fb10-308">Jagged Arrays</span></span>

<span data-ttu-id="6fb10-309">Egy szaggatott tömb, más néven "tömbök tömbje", egy tömb, amelynek elemei tömbök.</span><span class="sxs-lookup"><span data-stu-id="6fb10-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="6fb10-310">A szaggatott tömb elemei eltérő méretűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="6fb10-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="6fb10-311">Az alábbi példa azt szemlélteti, hogyan deklarálható és inicializálható egy többrészes táblát jelképező szaggatott tömb.</span><span class="sxs-lookup"><span data-stu-id="6fb10-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="6fb10-312">Tömb szeletek</span><span class="sxs-lookup"><span data-stu-id="6fb10-312">Array Slices</span></span>

<span data-ttu-id="6fb10-313">Egy tömböt megadó kifejezés és `Range` egy kifejezés alapján egy új kifejezés is létrehozható a `[` és `]` a tömb szelet operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="6fb10-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="6fb10-314">Az új kifejezés ugyanolyan típusú, mint a tömb, és a ( `Range` `Range`) elemei által indexelt tömb elemeket fogja tartalmazni a által definiált sorrendben.</span><span class="sxs-lookup"><span data-stu-id="6fb10-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="6fb10-315">`a` Ha `Double`például egy tömbhöz van kötve, akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely az első négy elemét tartalmazza, `a` de a fordított sorrendben, ahogy azok megjelennek a következőben: `a`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="6fb10-316">Ha az `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú lesz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="6fb10-317">Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell tenni a szelethez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="6fb10-318">Ha `a` például a és `b` mindkét tömbje `Int`, az összefűzésből származó szeletek a következőképpen lesznek kifejezve:</span><span class="sxs-lookup"><span data-stu-id="6fb10-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="6fb10-319">A Q # összes tömbje nulla-alapú.</span><span class="sxs-lookup"><span data-stu-id="6fb10-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6fb10-320">Vagyis a tömb `a` első eleme mindig `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="6fb10-321">A 0,8-es verziótól kezdődően a hatókör-szeletelők környezetfüggő kifejezéseket támogatunk.</span><span class="sxs-lookup"><span data-stu-id="6fb10-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="6fb10-322">A tartomány indítási és befejezési értékei a tartomány-szeletelő kifejezés kontextusában is kihagyhatók.</span><span class="sxs-lookup"><span data-stu-id="6fb10-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="6fb10-323">Ebben az esetben a fordító a következő szabályok alkalmazásával következteti ki a tartományhoz tartozó elhatárolókat.</span><span class="sxs-lookup"><span data-stu-id="6fb10-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="6fb10-324">Ha például a tartomány indítási értéke kimarad, akkor a késleltetett indítási érték</span><span class="sxs-lookup"><span data-stu-id="6fb10-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="6fb10-325">nulla, ha nincs megadva lépés, vagy a megadott lépés pozitív, és</span><span class="sxs-lookup"><span data-stu-id="6fb10-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6fb10-326">a szeletelt tömb hossza mínusz eggyel, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="6fb10-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="6fb10-327">Ha a tartomány befejezési értéke kimarad, akkor a következtetett vég értéke</span><span class="sxs-lookup"><span data-stu-id="6fb10-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="6fb10-328">a szeletelt tömb hossza mínusz eggyel, ha nincs megadva lépés, vagy a megadott lépés pozitív, és</span><span class="sxs-lookup"><span data-stu-id="6fb10-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6fb10-329">nulla, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="6fb10-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="6fb10-330">Tömb elem kifejezései</span><span class="sxs-lookup"><span data-stu-id="6fb10-330">Array Element Expressions</span></span>

<span data-ttu-id="6fb10-331">Egy tömb kifejezése és egy `Int` kifejezés alapján egy új kifejezés is létrehozható a és `[` `]` a tömb elem operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="6fb10-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="6fb10-332">Az új kifejezés ugyanolyan típusú lesz, mint a tömb elemének típusa.</span><span class="sxs-lookup"><span data-stu-id="6fb10-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="6fb10-333">Ha `a` például egy `Double`tömbhöz van kötve, akkor `a[4]` egy `Double` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="6fb10-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="6fb10-334">Ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell foglalni, hogy ki lehessen választani egy elemet.</span><span class="sxs-lookup"><span data-stu-id="6fb10-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="6fb10-335">Ha `a` például a és `b` mindkét tömbje, az összefűzésből származó elem a `Int`következőként lesz kifejezve:</span><span class="sxs-lookup"><span data-stu-id="6fb10-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="6fb10-336">A Q # összes tömbje nulla-alapú.</span><span class="sxs-lookup"><span data-stu-id="6fb10-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6fb10-337">Vagyis a tömb `a` első eleme mindig `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="6fb10-338">Másolás és frissítés kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="6fb10-339">Új tömbök hozhatók létre a meglévő példányokból másolás és frissítés kifejezések használatával.</span><span class="sxs-lookup"><span data-stu-id="6fb10-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="6fb10-340">A copy-Update `expression1 w/ expression2 <- expression3`kifejezés az űrlap kifejezése, amelyben `expression1` valamilyen típusú típusnak kell lennie. `T[]` `T`</span><span class="sxs-lookup"><span data-stu-id="6fb10-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="6fb10-341">A második `expression2` meghatározza, hogy az elem (ek) milyen indexeket módosítson a tömbhöz képest, `expression1` és a típusnak `Int` vagy típusúnak kell lennie `Range`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="6fb10-342">Ha `expression2` a típusa típusú `Int`, `expression3` a típusnak `T`kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6fb10-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="6fb10-343">Ha `expression2` a típusa típusú `Range`, `expression3` a típusnak `T[]`kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6fb10-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="6fb10-344">`arr w/ idx <- value` A másolási és frissítési kifejezés egy új tömböt hoz létre `arr`, amely a megfelelő elemre van állítva, kivéve a (z) elem (ek) `idx`et, amely a (z) értékre van beállítva `value`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="6fb10-345">Ha `arr` például egy tömböt `[0,1,2,3]`tartalmaz, akkor</span><span class="sxs-lookup"><span data-stu-id="6fb10-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="6fb10-346">`arr w/ 0 <- 10`a tömb `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="6fb10-347">`arr w/ 2 <- 10`a tömb `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="6fb10-348">`arr w/ 0..2..3 <- [10,12]`a tömb `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="6fb10-349">A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez.</span><span class="sxs-lookup"><span data-stu-id="6fb10-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="6fb10-350">Vegyük például a típust</span><span class="sxs-lookup"><span data-stu-id="6fb10-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="6fb10-351">Ha `c` a érték tartalmazza a Type `Complex(1.,-1.)`értéket, `c w/ Re <- 0.` akkor a a következő típusú `Complex` kifejezést adja vissza: `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="6fb10-352">Feltételes kifejezések</span><span class="sxs-lookup"><span data-stu-id="6fb10-352">Conditional Expressions</span></span>

<span data-ttu-id="6fb10-353">Egy adott típus és egy logikai kifejezés két másik kifejezése alapján a feltételes kifejezés a kérdőjel `?` és a függőleges sáv `|`használatával hozható létre.</span><span class="sxs-lookup"><span data-stu-id="6fb10-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="6fb10-354">Például: `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="6fb10-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="6fb10-355">Ebben a példában a feltételes kifejezés értéke TRUE (igaz) és `c` `d` false `a==b` (hamis) lesz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="6fb10-356">A két kifejezés kiértékelheti azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.</span><span class="sxs-lookup"><span data-stu-id="6fb10-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="6fb10-357">Ebben az esetben a feltételes kifejezés típusa olyan művelet, amely azokat a bemeneteket és kimeneteket támogatja, amelyek a mindkét kifejezés által támogatott összes feltételt támogatják.</span><span class="sxs-lookup"><span data-stu-id="6fb10-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="6fb10-358">Például, ha `Op1` `Op2`, és `Op3` mind a `Qubit[]=>Unit`, de `Op1` támogatja `Adjoint`, `Op2` támogatja `Controlled`és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="6fb10-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6fb10-359">`flag ? Op1 | Op2`egy `(Qubit[] => Unit)` művelet.</span><span class="sxs-lookup"><span data-stu-id="6fb10-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="6fb10-360">`flag ? Op1 | Op3`egy `(Qubit[] => Unit is Adj)` művelet.</span><span class="sxs-lookup"><span data-stu-id="6fb10-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="6fb10-361">`flag ? Op2 | Op3`egy `(Qubit[] => Unit is Ctl)` művelet.</span><span class="sxs-lookup"><span data-stu-id="6fb10-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="6fb10-362">Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor ez a hívás csak akkor kerül sor, ha az eredmény a hívás értéke lesz.</span><span class="sxs-lookup"><span data-stu-id="6fb10-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="6fb10-363">Ha `a==b ? C(qs) | D(qs)` `a==b` például igaz, akkor a rendszer meghívja a `C` műveletet, és ha hamis, akkor csak `D` a rendszer hívja meg.</span><span class="sxs-lookup"><span data-stu-id="6fb10-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="6fb10-364">Ez hasonló a más nyelvek rövid összekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="6fb10-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="6fb10-365">Operátori prioritás</span><span class="sxs-lookup"><span data-stu-id="6fb10-365">Operator Precedence</span></span>

<span data-ttu-id="6fb10-366">Minden bináris operátor megfelelő társítású, kivéve a következőt `^`:.</span><span class="sxs-lookup"><span data-stu-id="6fb10-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="6fb10-367">Szögletes zárójelek `[` , `]`valamint a tömb szeleteléséhez és indexeléséhez minden operátor előtt kötést kell kötni.</span><span class="sxs-lookup"><span data-stu-id="6fb10-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="6fb10-368">A `Adjoint` kikapcsolók `Controlled` és a kötés a tömb indexelése után, de az összes többi operátor előtt.</span><span class="sxs-lookup"><span data-stu-id="6fb10-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="6fb10-369">A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.</span><span class="sxs-lookup"><span data-stu-id="6fb10-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="6fb10-370">Az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:</span><span class="sxs-lookup"><span data-stu-id="6fb10-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="6fb10-371">Művelet</span><span class="sxs-lookup"><span data-stu-id="6fb10-371">Operator</span></span> | <span data-ttu-id="6fb10-372">Aritása</span><span class="sxs-lookup"><span data-stu-id="6fb10-372">Arity</span></span> | <span data-ttu-id="6fb10-373">Leírás</span><span class="sxs-lookup"><span data-stu-id="6fb10-373">Description</span></span> | <span data-ttu-id="6fb10-374">Operandusok típusai</span><span class="sxs-lookup"><span data-stu-id="6fb10-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="6fb10-375">záró`!`</span><span class="sxs-lookup"><span data-stu-id="6fb10-375">trailing `!`</span></span> | <span data-ttu-id="6fb10-376">Unáris</span><span class="sxs-lookup"><span data-stu-id="6fb10-376">Unary</span></span> | <span data-ttu-id="6fb10-377">Kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="6fb10-377">Unwrap</span></span> | <span data-ttu-id="6fb10-378">Bármely felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="6fb10-378">Any user-defined type</span></span>
 <span data-ttu-id="6fb10-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="6fb10-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="6fb10-380">Unáris</span><span class="sxs-lookup"><span data-stu-id="6fb10-380">Unary</span></span> | <span data-ttu-id="6fb10-381">Numerikus negatív, bitenkénti komplement, logikai tagadás</span><span class="sxs-lookup"><span data-stu-id="6fb10-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="6fb10-382">`Int`, `BigInt` vagy `Double` `-` `BigInt` esetén a `Int` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="6fb10-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="6fb10-383">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-383">Binary</span></span> | <span data-ttu-id="6fb10-384">Egész számú Power</span><span class="sxs-lookup"><span data-stu-id="6fb10-384">Integer power</span></span> | <span data-ttu-id="6fb10-385">`Int`vagy `BigInt` az alaphoz a `Int` kitevő esetében</span><span class="sxs-lookup"><span data-stu-id="6fb10-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="6fb10-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="6fb10-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="6fb10-387">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-387">Binary</span></span> | <span data-ttu-id="6fb10-388">Osztás, szorzás, egész szám modulusa</span><span class="sxs-lookup"><span data-stu-id="6fb10-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="6fb10-389">`Int`, `BigInt` vagy `Double` `/` `*` `Int` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="6fb10-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="6fb10-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="6fb10-390">`+`, `-`</span></span> | <span data-ttu-id="6fb10-391">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-391">Binary</span></span> | <span data-ttu-id="6fb10-392">Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás</span><span class="sxs-lookup"><span data-stu-id="6fb10-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="6fb10-393">`Int``BigInt` vagy `Double`, `String` vagy bármely tömb típusa a következőhöz:`+`</span><span class="sxs-lookup"><span data-stu-id="6fb10-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="6fb10-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="6fb10-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="6fb10-395">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-395">Binary</span></span> | <span data-ttu-id="6fb10-396">Bal SHIFT, jobb SHIFT</span><span class="sxs-lookup"><span data-stu-id="6fb10-396">Left shift, right shift</span></span> | <span data-ttu-id="6fb10-397">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6fb10-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="6fb10-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="6fb10-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="6fb10-399">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-399">Binary</span></span> | <span data-ttu-id="6fb10-400">Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="6fb10-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="6fb10-401">`Int`, `BigInt` vagy`Double`</span><span class="sxs-lookup"><span data-stu-id="6fb10-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="6fb10-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="6fb10-402">`==`, `!=`</span></span> | <span data-ttu-id="6fb10-403">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-403">Binary</span></span> | <span data-ttu-id="6fb10-404">egyenlő, nem egyenlő összehasonlítások</span><span class="sxs-lookup"><span data-stu-id="6fb10-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="6fb10-405">bármely primitív típus</span><span class="sxs-lookup"><span data-stu-id="6fb10-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="6fb10-406">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-406">Binary</span></span> | <span data-ttu-id="6fb10-407">Bitenkénti és</span><span class="sxs-lookup"><span data-stu-id="6fb10-407">Bitwise AND</span></span> | <span data-ttu-id="6fb10-408">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6fb10-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="6fb10-409">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-409">Binary</span></span> | <span data-ttu-id="6fb10-410">Bitenkénti XOR</span><span class="sxs-lookup"><span data-stu-id="6fb10-410">Bitwise XOR</span></span> | <span data-ttu-id="6fb10-411">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6fb10-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="6fb10-412">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-412">Binary</span></span> | <span data-ttu-id="6fb10-413">Bitenkénti vagy</span><span class="sxs-lookup"><span data-stu-id="6fb10-413">Bitwise OR</span></span> | <span data-ttu-id="6fb10-414">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6fb10-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="6fb10-415">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-415">Binary</span></span> | <span data-ttu-id="6fb10-416">Logikai és</span><span class="sxs-lookup"><span data-stu-id="6fb10-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="6fb10-417">Bináris</span><span class="sxs-lookup"><span data-stu-id="6fb10-417">Binary</span></span> | <span data-ttu-id="6fb10-418">Logikai vagy</span><span class="sxs-lookup"><span data-stu-id="6fb10-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="6fb10-419">Bináris/Ternáris</span><span class="sxs-lookup"><span data-stu-id="6fb10-419">Binary/Ternary</span></span> | <span data-ttu-id="6fb10-420">Tartomány operátora</span><span class="sxs-lookup"><span data-stu-id="6fb10-420">Range operator</span></span> | `Int`
 <span data-ttu-id="6fb10-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="6fb10-421">`?` `|`</span></span> | <span data-ttu-id="6fb10-422">Ternáris</span><span class="sxs-lookup"><span data-stu-id="6fb10-422">Ternary</span></span> | <span data-ttu-id="6fb10-423">Feltételes</span><span class="sxs-lookup"><span data-stu-id="6fb10-423">Conditional</span></span> | <span data-ttu-id="6fb10-424">`Bool`a bal oldali</span><span class="sxs-lookup"><span data-stu-id="6fb10-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="6fb10-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="6fb10-425">`w/` `<-`</span></span> | <span data-ttu-id="6fb10-426">Ternáris</span><span class="sxs-lookup"><span data-stu-id="6fb10-426">Ternary</span></span> | <span data-ttu-id="6fb10-427">Másolás és frissítés</span><span class="sxs-lookup"><span data-stu-id="6fb10-427">Copy-and-update</span></span> | <span data-ttu-id="6fb10-428">Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="6fb10-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
