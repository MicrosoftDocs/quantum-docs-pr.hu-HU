---
title: 'Kifejezések a Q#'
description: 'Megtudhatja, hogyan adhat meg, hivatkozhat és egyesíthet állandókat, változókat, operátorokat, műveleteket és függvényeket kifejezésként a alkalmazásban Q# .'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691601"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="4ce2b-103">Kifejezések a Q#</span><span class="sxs-lookup"><span data-stu-id="4ce2b-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="4ce2b-104">Numerikus kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-104">Numeric Expressions</span></span>

<span data-ttu-id="4ce2b-105">A numerikus kifejezések a következő típusú kifejezések:, `Int` `BigInt` vagy `Double` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="4ce2b-106">Vagyis egész vagy lebegőpontos számok.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="4ce2b-107">`Int` a konstansok Q# számjegyek sorozatából vannak írva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="4ce2b-108">A hexadecimális és a bináris egész számok támogatottak, és a `0x` és `0b` előtaggal vannak írva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="4ce2b-109">`BigInt` a konstansok Q# záró `l` vagy `L` utótaggal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="4ce2b-110">A hexadecimális nagy egész számok támogatottak, és "0x" előtaggal írhatók.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="4ce2b-111">Így az alábbi értékek érvényesek a literálok összes érvényes használatára `BigInt` :</span><span class="sxs-lookup"><span data-stu-id="4ce2b-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="4ce2b-112">`Double` a-ben a konstansok Q# számjegyek használatával írt lebegőpontos számok.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="4ce2b-113">Megírhatók decimális ponttal vagy anélkül `.` , illetve az "e" vagy az "e" karakterrel jelzett exponenciális rész (amely után csak egy lehetséges negatív jel és decimális számjegy érvényes).</span><span class="sxs-lookup"><span data-stu-id="4ce2b-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="4ce2b-114">A következő érvényes `Double` literálok: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="4ce2b-115">Bármilyen típusú tömb kifejezése miatt `Int` a beépített függvény használatával kifejezéseket állíthat be a [`Length`](xref:Microsoft.Quantum.Core.Length) tömb kifejezés zárójelek közé.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:Microsoft.Quantum.Core.Length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="4ce2b-116">Ha például `a` egy tömbhöz van kötve, akkor az egy `Length(a)` egész szám kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="4ce2b-117">Ha `b` az egész számokból álló tömbök tömbje, akkor a- `Int[][]` ben az `Length(b)` altömbök száma, a `b` `Length(b[1])` pedig a második altömbben lévő egész számok száma `b` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="4ce2b-118">Az adott típus két numerikus kifejezése, a bináris operátorok, a, `+` `-` és az `*` `/` új numerikus kifejezéseket is felhasználhatja.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="4ce2b-119">Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="4ce2b-120">A két egész szám kifejezésnek megfelelően a bináris operátor `^` (Power) használatával új egész kifejezést formálhat.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="4ce2b-121">Ehhez hasonlóan két dupla kifejezés is használható `^` egy új dupla kifejezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="4ce2b-122">Végül a `^` bal oldalon egy nagy egész számot és egy egész számot is használhat a jobb oldalon egy új Big Integer típusú kifejezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="4ce2b-123">Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="4ce2b-124">A megadott két egész vagy nagy egész szám típusú kifejezés egy új egész számot vagy egy Big Integer kifejezést alkot a `%` (modulus), `&&&` (bitenkénti és), `|||` (bitenkénti vagy), vagy `^^^` (bitenkénti XOR) operátorok használatával.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="4ce2b-125">A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) vagy `>>>` (aritmetikai jobbra váltás) operátorok segítségével hozzon létre egy új kifejezést a bal oldali kifejezéssel megegyező típussal.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="4ce2b-126">A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="4ce2b-127">A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="4ce2b-128">Ha az áthelyezett szám egész szám, akkor a rendszer a eltolási értéket fogja értelmezni, `mod 64` azaz az 1 eltolást és a 65 eltolását.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="4ce2b-129">Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="4ce2b-130">A negatív érték balra vagy jobbra való eltolása negatív szám lehet.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="4ce2b-131">Ez azt jelöli, hogy az egyik lépés balra vagy jobbra való eltolása megegyezik a 2. számú szorzással vagy osztással.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="4ce2b-132">Az egész szám és az Integer modulus ugyanazt a viselkedést követi a negatív számok esetében, mint a C#.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span> <span data-ttu-id="4ce2b-133">Vagyis `a % b` mindig ugyanaz a jel, mint a `a` , és `b * (a / b) + a % b` mindig egyenlő `a` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span> <span data-ttu-id="4ce2b-134">Például:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-134">For example:</span></span>

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| <span data-ttu-id="4ce2b-135">5</span><span class="sxs-lookup"><span data-stu-id="4ce2b-135">5</span></span> | <span data-ttu-id="4ce2b-136">2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-136">2</span></span> | <span data-ttu-id="4ce2b-137">2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-137">2</span></span> | <span data-ttu-id="4ce2b-138">1</span><span class="sxs-lookup"><span data-stu-id="4ce2b-138">1</span></span> |
| <span data-ttu-id="4ce2b-139">5</span><span class="sxs-lookup"><span data-stu-id="4ce2b-139">5</span></span> | <span data-ttu-id="4ce2b-140">-2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-140">-2</span></span> | <span data-ttu-id="4ce2b-141">-2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-141">-2</span></span> | <span data-ttu-id="4ce2b-142">1</span><span class="sxs-lookup"><span data-stu-id="4ce2b-142">1</span></span> |
| <span data-ttu-id="4ce2b-143">-5</span><span class="sxs-lookup"><span data-stu-id="4ce2b-143">-5</span></span> | <span data-ttu-id="4ce2b-144">2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-144">2</span></span> | <span data-ttu-id="4ce2b-145">-2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-145">-2</span></span> | <span data-ttu-id="4ce2b-146">-1</span><span class="sxs-lookup"><span data-stu-id="4ce2b-146">-1</span></span> |
| <span data-ttu-id="4ce2b-147">-5</span><span class="sxs-lookup"><span data-stu-id="4ce2b-147">-5</span></span> | <span data-ttu-id="4ce2b-148">-2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-148">-2</span></span> | <span data-ttu-id="4ce2b-149">2</span><span class="sxs-lookup"><span data-stu-id="4ce2b-149">2</span></span> | <span data-ttu-id="4ce2b-150">-1</span><span class="sxs-lookup"><span data-stu-id="4ce2b-150">-1</span></span> |

<span data-ttu-id="4ce2b-151">A Big Integer osztás és a modulus műveletek ugyanúgy működnek.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="4ce2b-152">A numerikus kifejezéseket megadva egy új kifejezés is létrehozható az `-` unáris operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="4ce2b-153">Az új kifejezés ugyanolyan típusú, mint az összetevő kifejezése.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="4ce2b-154">Egy egész szám vagy egy nagy egész szám kifejezés esetén a `~~~` (bitenkénti komplement) egyoperandusú operátor használatával egy adott típusú új kifejezés is létrehozható.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="4ce2b-155">Logikai kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-155">Boolean Expressions</span></span>

<span data-ttu-id="4ce2b-156">A két `Bool` literális érték a `true` és a `false` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="4ce2b-157">Az azonos primitív típusú két kifejezés miatt a `==` és a `!=` bináris operátor is használható kifejezés létrehozásához `Bool` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="4ce2b-158">A kifejezés értéke igaz, ha a két kifejezés egyenlő és hamis, ha nem.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="4ce2b-159">A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="4ce2b-160">Például a "kicsomagolás" operátor használatával `!` (részletesen lásd [ Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator):),</span><span class="sxs-lookup"><span data-stu-id="4ce2b-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="4ce2b-161">Az értékek egyenlőségének összehasonlítása az `Qubit` identitással egyenlő, azaz azt, hogy a két kifejezés ugyanazt a qubit azonosítja-e.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="4ce2b-162">A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="4ce2b-163">Az értékek egyenlőségének összehasonlítása a `Double` kerekítési hatások miatt félrevezető lehet.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="4ce2b-164">Például: `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="4ce2b-165">A két numerikus kifejezéstől függően a bináris operátorok, a, `>` `<` `>=` és `<=` felhasználhatók egy olyan új logikai kifejezés létrehozására, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, mint a második kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="4ce2b-166">Ha két logikai kifejezés van megadva, a `and` bináris operátor használatával olyan új logikai kifejezést hozhat létre, amely igaz, ha mindkét kifejezés igaz.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="4ce2b-167">Hasonlóképpen, az `or` operátor használatával egy olyan kifejezést hoz létre, amely akkor igaz, ha a két kifejezés egyike igaz.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="4ce2b-168">A logikai kifejezéseket megadva az `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="4ce2b-169">Sztringkifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-169">String expressions</span></span>

<span data-ttu-id="4ce2b-170">Q# lehetővé teszi a karakterláncok használatát az `fail` utasításban (a [vezérlési folyamat](xref:microsoft.quantum.guide.controlflow#fail-statement)ismertetése) és a [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) standard függvényben.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) standard function.</span></span> <span data-ttu-id="4ce2b-171">Az utóbbi adott viselkedése a használt szimulátortól függ, de általában egy üzenetet ír a gazdagép-konzolra, amikor egy program során hívja meg Q# .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="4ce2b-172">A karakterláncok Q# literálok vagy interpolált karakterláncok.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="4ce2b-173">A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterlánc-literálokra: a Unicode-karakterek egy sorozata dupla idézőjelek közé `" "` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="4ce2b-174">Egy karakterláncon belül használja a fordított perjel karaktert `\` egy dupla idézőjeles karakter () elküldéséhez `\"` , vagy egy új vonal ( `\n` ), egy kocsivissza ( `\r` ) vagy egy lap () beszúrásához `\t` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="4ce2b-175">Például:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="4ce2b-176">Interpolált karakterláncok</span><span class="sxs-lookup"><span data-stu-id="4ce2b-176">Interpolated strings</span></span>

<span data-ttu-id="4ce2b-177">A Q# karakterlánc-Interpolációk szintaxisa a C# szintaxis egy részhalmaza.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="4ce2b-178">Az alábbiak a legfontosabb pontok, amelyek a következőkre vonatkoznak Q# :</span><span class="sxs-lookup"><span data-stu-id="4ce2b-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="4ce2b-179">Ha egy szövegkonstans-karakterláncot interpolált karakterláncként szeretne azonosítani, a szimbólummal megadhatja azt `$` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="4ce2b-180">A és a közötti térköz nem lehet üres `$` `"` karakterláncot indít.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="4ce2b-181">A következő példa egy olyan alapszintű példát [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) mutat be, amely egy mérés eredményét írja a konzolra, más Q# kifejezésekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-181">The following is a basic example using the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="4ce2b-182">Bármely érvényes Q# kifejezés interpolált karakterláncban jelenhet meg.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="4ce2b-183">Az interpolált karakterláncban szereplő kifejezések Q# szintaxisát és nem C# szintaxist követik.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="4ce2b-184">A legjelentősebb különbség az, hogy nem Q# támogatja a Verbatim (többsoros) interpolált karakterláncokat.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="4ce2b-185">A C# szintaxissal kapcsolatos további információkért lásd: [*interpolált karakterláncok*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="4ce2b-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="4ce2b-186">Tartomány kifejezései</span><span class="sxs-lookup"><span data-stu-id="4ce2b-186">Range Expressions</span></span>

<span data-ttu-id="4ce2b-187">A (z `Int` `start` `step` ) és a (z `stop` ) kifejezés `start .. step .. stop` egy olyan tartomány kifejezése, amelynek első eleme a `start` második elem, a `start+step` harmadik elem, `start+step+step` és így tovább, amíg át nem halad `stop` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="4ce2b-188">A tartomány lehet üres, ha például `step` pozitív és `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="4ce2b-189">A tartomány mindkét végén szerepel.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="4ce2b-190">Ez azt eredményezi, hogy ha a és a közötti különbség az `start` `stop` egész szám `step` , a tartomány utolsó eleme lesz `stop` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="4ce2b-191">`Int` `start` `stop` A kifejezés `start .. stop` egy olyan tartomány kifejezése, amely egyenlő a két kifejezéssel `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="4ce2b-192">Vegye figyelembe, hogy a vélelmezett `step` érték + 1 `stop` , akkor is, ha kevesebb, mint `start` ; ebben az esetben a tartomány üres.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="4ce2b-193">Néhány példa a tartományokra:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-193">Some example ranges are:</span></span>

- <span data-ttu-id="4ce2b-194">`1..3` az 1., 2. és 3. tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="4ce2b-195">`2..2..5` a 2. és 4. tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="4ce2b-196">`2..2..6` a 2, 4, 6. tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="4ce2b-197">`6..-2..2` a 6, 4, 2 tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="4ce2b-198">`2..1` az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="4ce2b-199">`2..6..7` a 2. tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="4ce2b-200">`2..2..1` az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="4ce2b-201">`1..-1..2` az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="4ce2b-202">Qubit kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-202">Qubit Expressions</span></span>

<span data-ttu-id="4ce2b-203">Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékek vagy tömb elemeihez van kötve `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="4ce2b-204">Nincsenek `Qubit` literálok.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="4ce2b-205">Pauli-kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-205">Pauli Expressions</span></span>

<span data-ttu-id="4ce2b-206">A négy érték:,,, `Pauli` `PauliI` `PauliX` `PauliY` és `PauliZ` , minden érvényes `Pauli` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="4ce2b-207">Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékek vagy tömb elemeihez van kötve `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="4ce2b-208">Eredmény kifejezései</span><span class="sxs-lookup"><span data-stu-id="4ce2b-208">Result Expressions</span></span>

<span data-ttu-id="4ce2b-209">A két `Result` érték ( `One` és `Zero` `Result` ) érvényes kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="4ce2b-210">Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékek vagy tömb elemeihez van kötve `Result` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="4ce2b-211">Különösen fontos megjegyezni, hogy `One` nem ugyanaz, mint az egész szám `1` , és nincs közvetlen konverzió a közöttük.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="4ce2b-212">Ugyanez érvényes a és a esetében is `Zero` `0` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="4ce2b-213">Rekordos kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-213">Tuple Expressions</span></span>

<span data-ttu-id="4ce2b-214">A rekordos konstans a megfelelő típusú elemek sorozata, vesszővel elválasztva, zárójelek közé zárva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="4ce2b-215">Például `(1, One)` egy `(Int, Result)` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="4ce2b-216">A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="4ce2b-217">User-Defined típusú kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="4ce2b-218">A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="4ce2b-219">Ha például `IntPair` egy felhasználó által definiált típus a (z) alapján `(Int, Int)` , akkor `IntPair(2, 3)` az egy adott típusú érvényes literál.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="4ce2b-220">A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="4ce2b-221">Kifejezések kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="4ce2b-221">Unwrap Expressions</span></span>

<span data-ttu-id="4ce2b-222">A-ben Q# a kicsomagolási operátor egy záró felkiáltójel `!` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="4ce2b-223">Ha például `IntPair` egy felhasználó által definiált típus az alapul szolgáló típussal `(Int, Int)` , és `s` egy változó értékkel `IntPair(2, 3)` , akkor `s!` `(2, 3)` a következő:.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="4ce2b-224">Más, felhasználó által definiált típusokban definiált, felhasználó által definiált típusok esetén megismételheti a kicsomagolási operátort.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="4ce2b-225">Például `s!!` a kétszeresen kicsomagolt értéket jelöli `s` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="4ce2b-226">Így ha a `WrappedPair` felhasználó által definiált típus egy alapul szolgáló típusú `IntPair` , és `t` egy változó értékkel `WrappedPair(IntPair(1,2))` , akkor a `t!!` következő: `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="4ce2b-227">Az `!` operátor magasabb prioritású, mint az összes többi operátor `[]` , mint a tömb indexelése és a szeletelése.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="4ce2b-228">`!` és a `[]` kötés elhelyezése; ez a következő `a[i]![3]` `((a[i])!)[3]` : a (z), a (z), a kicsomagolása `i` , majd a nem `a` burkolt érték harmadik elemének beolvasása (tömbnek kell lennie).</span><span class="sxs-lookup"><span data-stu-id="4ce2b-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="4ce2b-229">Az operátor elsőbbsége `!` egy olyan hatással van, amely esetleg nem nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="4ce2b-230">Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="4ce2b-231">Például:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="4ce2b-232">Tömb kifejezései</span><span class="sxs-lookup"><span data-stu-id="4ce2b-232">Array Expressions</span></span>

<span data-ttu-id="4ce2b-233">A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, szögletes zárójelek közé `[]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="4ce2b-234">Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="4ce2b-235">Ha a két tömb azonos típusú, a bináris `+` operátor használatával olyan új tömböt formálhat, amely a két tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="4ce2b-236">Például: `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="4ce2b-237">Tömb létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ce2b-237">Array Creation</span></span>

<span data-ttu-id="4ce2b-238">Adott típus és `Int` kifejezés `new` alapján a kezelővel lefoglalhatja a megadott méretű új tömböt.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="4ce2b-239">Például `new Int[i + 1]` kioszt egy új `Int` tömböt `i + 1` elemekkel.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="4ce2b-240">Az üres tömb literálok (például `[]` ) nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="4ce2b-241">Ehelyett létrehozhat egy nulla hosszúságú tömböt a használatával `new T[0]` , ahol a a `T` megfelelő típusú helyőrző.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="4ce2b-242">Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="4ce2b-243">A legtöbb esetben ez a nulla valamilyen változata.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="4ce2b-244">Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="4ce2b-245">Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely nem használható futásidejű hiba nélkül, hasonlóan a nyelvekhez, mint például a C# vagy a Java.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="4ce2b-246">Az qubits vagy callables tartalmazó tömböket nem alapértelmezett értékekkel kell inicializálni az elemek biztonságos használata előtt.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="4ce2b-247">A megfelelő inicializálási rutinok: <xref:Microsoft.Quantum.Arrays> .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-247">For suitable initialization routines, see <xref:Microsoft.Quantum.Arrays>.</span></span>

<span data-ttu-id="4ce2b-248">Az egyes típusok alapértelmezett értékei a következők:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-248">The default values for each type are:</span></span>

<span data-ttu-id="4ce2b-249">Típus</span><span class="sxs-lookup"><span data-stu-id="4ce2b-249">Type</span></span> | <span data-ttu-id="4ce2b-250">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="4ce2b-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="4ce2b-251">_Érvénytelen qubit_</span><span class="sxs-lookup"><span data-stu-id="4ce2b-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="4ce2b-252">Az üres tartomány, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="4ce2b-253">_Érvénytelen hívható_</span><span class="sxs-lookup"><span data-stu-id="4ce2b-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="4ce2b-254">A rekord típusú típusok inicializálása elemről elemre.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="4ce2b-255">Tömb elemei</span><span class="sxs-lookup"><span data-stu-id="4ce2b-255">Array Elements</span></span>

<span data-ttu-id="4ce2b-256">Egy tömböt megadó kifejezés és egy `Int` kifejezés, amely egy új kifejezést képez a tömb elem operátor használatával `[]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="4ce2b-257">Az új kifejezés ugyanaz, mint a tömb elemének típusa.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="4ce2b-258">Ha például `a` egy típusú tömbhöz van kötve `Double` , akkor `a[4]` egy `Double` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="4ce2b-259">Ha a tömb kifejezése nem egyszerű azonosító, akkor zárójelek közé kell helyeznie egy elem kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="4ce2b-260">Ha például a `a` és `b` mindkét típusú tömb `Int` , az összefűzésből származó elemek a következőképpen jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="4ce2b-261">Az összes tömb Q# nulla-alapú.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="4ce2b-262">Vagyis a tömb első eleme `a` mindig `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="4ce2b-263">Tömb szeletek</span><span class="sxs-lookup"><span data-stu-id="4ce2b-263">Array Slices</span></span>

<span data-ttu-id="4ce2b-264">Egy tömb kifejezése és egy `Range` kifejezés alapján egy új kifejezés is létrehozható a tömb szelet operátor használatával `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="4ce2b-265">Az új kifejezés típusa megegyezik a tömb típusával, és tartalmazza a által a által meghatározott sorrendben indexelt elemeket `Range` `Range` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="4ce2b-266">Ha például `a` egy típusú tömbhöz van kötve `Double` , akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely az első négy elemét tartalmazza, `a` de a fordított sorrendben, ahogy azok megjelennek a ben `a` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="4ce2b-267">Ha az `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="4ce2b-268">A tömbök viszonyítási elemeihez hasonlóan, ha a tömb kifejezése nem egyszerű azonosító, akkor zárójelek közé kell tenni a szeletet.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="4ce2b-269">Ha például a `a` és `b` mindkét típusú tömb `Int` , az összefűzésből származó szelet a következőként van kifejezve:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="4ce2b-270">Következtetett kezdő/záró értékek</span><span class="sxs-lookup"><span data-stu-id="4ce2b-270">Inferred start/end values</span></span>

<span data-ttu-id="4ce2b-271">A 0,8-es [verziótól](xref:microsoft.quantum.relnotes)kezdődően a hatókör-szeletelők környezetfüggő kifejezéseket támogatunk.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="4ce2b-272">Különösen kihagyhatja a tartomány kezdő és záró értékeit egy tartomány-szeletelő kifejezés kontextusában.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="4ce2b-273">Ebben az esetben a fordító a következő szabályok alapján következteti ki a tartományhoz tartozó elhatárolókat:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="4ce2b-274">Ha a tartomány *indítási* értéke kimarad, akkor a késleltetett indítási érték</span><span class="sxs-lookup"><span data-stu-id="4ce2b-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="4ce2b-275">nulla, ha nincs megadva lépés, vagy a megadott lépés pozitív.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="4ce2b-276">a szeletelt tömb hossza mínusz eggyel, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="4ce2b-277">Ha a tartomány *befejezési* értéke kimarad, akkor a következtetett vég értéke</span><span class="sxs-lookup"><span data-stu-id="4ce2b-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="4ce2b-278">a szeletelt tömb hossza mínusz eggyel, ha nincs megadva a lépés, vagy a megadott lépés pozitív.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="4ce2b-279">nulla, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="4ce2b-280">Néhány példa:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="4ce2b-281">Másolás és frissítés kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="4ce2b-282">Mivel Q# az összes típus érték típusú (a qubits valamivel speciális szerepkört vesznek fel), az űrlapos "Copy" (másolás) jön létre, amikor egy érték egy szimbólumhoz van kötve, vagy ha egy szimbólum van kötve.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="4ce2b-283">Ez azt jelenti, hogy a viselkedése Q# ugyanaz, mint ha egy példányt egy hozzárendelési operátor használatával hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="4ce2b-284">Természetesen a gyakorlatban csak az érintett darabok szükségesek újra létrehozva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="4ce2b-285">Ez befolyásolja a tömbök másolásának módját, mert nem lehetséges a tömb elemeinek frissítése.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="4ce2b-286">Egy meglévő tömb módosításához a *copy-Update* mechanizmust kell használnia.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="4ce2b-287">Létrehozhat egy új tömböt egy meglévő tömbből *Másolás és frissítés* kifejezések használatával, amelyek a kezelőket és a-t használják `w/` `<-` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="4ce2b-288">A copy-Update kifejezés az űrlap kifejezése `expression1 w/ expression2 <- expression3` , ahol</span><span class="sxs-lookup"><span data-stu-id="4ce2b-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="4ce2b-289">`expression1` valamilyen típusúnak kell lennie `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="4ce2b-290">`expression2` meghatározza, hogy mely indexeket kell megadni a tömbben a `expression1` módosításhoz.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="4ce2b-291">`expression2` típusnak `Int` vagy típusnak kell lennie `Range` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="4ce2b-292">`expression3` az elemeknek a alkalmazásban való frissítéséhez használt érték (ek) a `expression1` ben megadott indexek alapján `expression2` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="4ce2b-293">Ha `expression2` a típus típusa `Int` , `expression3` típusnak kell lennie `T` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="4ce2b-294">Ha `expression2` a típus típusa `Range` , `expression3` típusnak kell lennie `T[]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="4ce2b-295">A copy-and-Update kifejezés például `arr w/ idx <- value` egy új tömböt hoz létre, amely a megfelelő elemeire van beállítva `arr` , kivéve a által megadott elem (ek) et, `idx` amely a (z) értékre van beállítva `value` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="4ce2b-296">`arr`A megadott tömb tartalmazza `[0,1,2,3]` , majd</span><span class="sxs-lookup"><span data-stu-id="4ce2b-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="4ce2b-297">`arr w/ 0 <- 10` a tömb `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="4ce2b-298">`arr w/ 2 <- 10` a tömb `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="4ce2b-299">`arr w/ 0..2..3 <- [10,12]` a tömb `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="4ce2b-300">Elnevezett elemek másolási és frissítési kifejezései</span><span class="sxs-lookup"><span data-stu-id="4ce2b-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="4ce2b-301">A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="4ce2b-302">Vegyük például a következőt:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="4ce2b-303">Ha `c` a érték tartalmazza a Type értéket `Complex(1., -1.)` , akkor a a `c w/ Re <- 0.` következő típusú kifejezést adja `Complex` vissza: `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="4ce2b-304">Szaggatott tömbök</span><span class="sxs-lookup"><span data-stu-id="4ce2b-304">Jagged Arrays</span></span>

<span data-ttu-id="4ce2b-305">Egy szaggatott tömb, más néven "tömbök tömbje", egy tömb, amelynek elemei tömbök.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="4ce2b-306">A szaggatott tömb elemei eltérő méretűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="4ce2b-307">Az alábbi példa azt szemlélteti, hogyan deklarálható és inicializálható egy többrészes táblát jelképező szaggatott tömb.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="4ce2b-308">Callables tömbök</span><span class="sxs-lookup"><span data-stu-id="4ce2b-308">Arrays of callables</span></span> 

<span data-ttu-id="4ce2b-309">A callables tömbjét is létrehozhatja.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="4ce2b-310">Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="4ce2b-311">A tömb elemének típusa az összes elem által [támogatott összes olyan futtatót](xref:microsoft.quantum.guide.operationsfunctions) támogatja.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="4ce2b-312">Például ha a `Op1` , a `Op2` és `Op3` az mind `Qubit[] => Unit` művelet, de támogatja, `Op1` `Adjoint` `Op2` támogatja `Controlled` és `Op3` támogatja mind a következőket:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="4ce2b-313">`[Op1, Op2]` a a műveletek tömbje `(Qubit[] => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="4ce2b-314">`[Op1, Op3]` a a műveletek tömbje `(Qubit[] => Unit is Adj)` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="4ce2b-315">`[Op2, Op3]` a a műveletek tömbje `(Qubit[] => Unit is Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="4ce2b-316">Azonban bár a műveletek `(Qubit[] => Unit is Adj)` és  `(Qubit[] => Unit is Ctl)` a közös alaptípusa, a `(Qubit[] => Unit)` műveletek *tömbje* nem osztozik közös alaptípuson.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="4ce2b-317">Például `[[Op1], [Op2]]` jelenleg hiba történt, mert megkísérli létrehozni a két nem kompatibilis tömb típusának tömbjét `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="4ce2b-318">A callables kapcsolatos további információkért lásd: [hívható kifejezések](#callable-expressions) ezen az oldalon vagy [műveletek és függvények a Q# -ben ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="4ce2b-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="4ce2b-319">Feltételes kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-319">Conditional Expressions</span></span>

<span data-ttu-id="4ce2b-320">Egy adott típus és egy logikai kifejezés két kifejezése is egy feltételes kifejezést alkot a kérdőjel `?` és a függőleges sáv használatával `|` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="4ce2b-321">A `a==b ? c | d` feltételes kifejezés értéke, `c` Ha `a==b` igaz, és `d` hamis.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="4ce2b-322">Feltételes kifejezések callables</span><span class="sxs-lookup"><span data-stu-id="4ce2b-322">Conditional expressions with callables</span></span>

<span data-ttu-id="4ce2b-323">A feltételes kifejezések kiértékelik azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="4ce2b-324">Ebben az esetben a feltételes kifejezés típusa egy olyan bemenettel és kimenettel rendelkező művelet, amely támogatja a mindkét kifejezés által támogatott összes feltételt.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="4ce2b-325">Például, ha, `Op1` `Op2` és `Op3` mind a `Qubit[]=>Unit` , de támogatja `Op1` `Adjoint` , `Op2` támogatja `Controlled` és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="4ce2b-326">`flag ? Op1 | Op2` egy `(Qubit[] => Unit)` művelet.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="4ce2b-327">`flag ? Op1 | Op3` egy `(Qubit[] => Unit is Adj)` művelet.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="4ce2b-328">`flag ? Op2 | Op3` egy `(Qubit[] => Unit is Ctl)` művelet.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="4ce2b-329">Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor a hívás csak akkor történik meg, ha ez az eredmény a hívás értéke.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="4ce2b-330">`a==b ? C(qs) | D(qs)`Ha például `a==b` igaz, akkor a rendszer `C` meghívja a műveletet, és ha az értéke hamis, akkor csak a `D` művelet meghívására kerül sor.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="4ce2b-331">Ez a megközelítés hasonló a más nyelveken történő *rövid összekapcsoláshoz* .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="4ce2b-332">Hívható kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-332">Callable Expressions</span></span>

<span data-ttu-id="4ce2b-333">A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="4ce2b-334">Például `X` egy olyan műveleti literál, amely a szabványos könyvtári `X` műveletre hivatkozik, és `Message` egy olyan függvény, amely a standard Library `Message` függvényre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="4ce2b-335">Ha egy művelet támogatja az elválasztó műveletet `Adjoint` , akkor `Adjoint op` egy művelet kifejezése.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="4ce2b-336">Hasonlóképpen, ha a művelet támogatja az elválasztó műveletet `Controlled` , akkor `Controlled op` egy művelet kifejezése.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="4ce2b-337">A kifejezések típusaival kapcsolatos további információkért lásd: a [műveleti specializációk meghívása](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="4ce2b-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="4ce2b-338">`Adjoint`A (és `Controlled` ) az összes többi operátorral szorosabban kötődik, kivéve a kicsomagolási operátort és a `!` tömb indexelését `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="4ce2b-339">Így a következők mindegyike érvényes, feltéve, hogy a műveletek támogatják a használt munkafolyamatokat:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="4ce2b-340">Típus – paraméteres hívható kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="4ce2b-341">Használhat egy meghívásos literálot értékként, például hozzárendelheti egy változóhoz, vagy átadhatja egy másik meghívónak.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="4ce2b-342">Ebben az esetben, ha a meghívható [típus paraméterekkel](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)rendelkezik, meg kell adnia a paramétereket a meghívásos érték részeként.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="4ce2b-343">Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="4ce2b-344">Ha például az `Fun` egy függvény az aláírással `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="4ce2b-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="4ce2b-345">Hívható hívási kifejezések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="4ce2b-346">Egy meghívásos kifejezés (művelet vagy függvény) és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos *kifejezéshez* hozzáfűzheti a rekord kifejezését.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="4ce2b-347">A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="4ce2b-348">Ha például az `Op` egy művelet az aláírással, a `((Int, Qubit) => Double)` egy `Op(3, qubit1)` típusú kifejezés `Double` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="4ce2b-349">Hasonlóképpen, ha az `Sin` egy függvény az aláírással `(Double -> Double)` , a egy `Sin(0.1)` típusú kifejezés `Double` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="4ce2b-350">Végül, ha `Builder` az a függvény az aláírással `(Int -> (Int -> Int))` , akkor a `Builder(3)` függvény a- `Int` ből `Int` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="4ce2b-351">Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="4ce2b-352">Így az előző bekezdésből történő hívás eredményének meghívásához `Builder` a helyes szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="4ce2b-353">A [típus-paraméteres](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) metódus meghívásakor megadható, hogy a tényleges Type paraméterek a `< >` meghívásos kifejezés után a szög zárójelben legyenek.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="4ce2b-354">Ez a művelet általában szükségtelen, mert a Q# fordító vezeti a tényleges típusokat.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="4ce2b-355">Azonban szükség *van* a [részleges alkalmazásra](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , ha egy Type-paraméteres argumentum nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="4ce2b-356">Emellett akkor is hasznos, ha a különböző felhasználók által támogatott műveletek továbbítása meghívásos.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="4ce2b-357">Például ha `Func` rendelkezik aláírással, és aláírással rendelkezik, `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` és `Op3` aláírással rendelkezik `(Qubit[] => Unit)` , az `Func` `Op1` első argumentumként, `Op2` a másodikként és `Op3` a harmadikként való meghívásához:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="4ce2b-358">A típus specifikációjának megadása kötelező `Op3` `Op1` , mert különböző típusok vannak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="4ce2b-359">Operátori prioritás</span><span class="sxs-lookup"><span data-stu-id="4ce2b-359">Operator Precedence</span></span>

* <span data-ttu-id="4ce2b-360">Minden bináris operátor megfelelő társítású, kivéve a következőt: `^` .</span><span class="sxs-lookup"><span data-stu-id="4ce2b-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="4ce2b-361">Szögletes zárójelek, `[ ]` a tömb szeletelése és indexelése minden operátor előtt kötést biztosít.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="4ce2b-362">A kikapcsolók `Adjoint` és a `Controlled` kötés a tömb indexelése után, de az összes többi operátor előtt.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="4ce2b-363">A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="4ce2b-364">Q# az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:</span><span class="sxs-lookup"><span data-stu-id="4ce2b-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="4ce2b-365">Operátor</span><span class="sxs-lookup"><span data-stu-id="4ce2b-365">Operator</span></span> | <span data-ttu-id="4ce2b-366">Aritása</span><span class="sxs-lookup"><span data-stu-id="4ce2b-366">Arity</span></span> | <span data-ttu-id="4ce2b-367">Leírás</span><span class="sxs-lookup"><span data-stu-id="4ce2b-367">Description</span></span> | <span data-ttu-id="4ce2b-368">Operandusok típusai</span><span class="sxs-lookup"><span data-stu-id="4ce2b-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="4ce2b-369">záró `!`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-369">trailing `!`</span></span> | <span data-ttu-id="4ce2b-370">Unáris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-370">Unary</span></span> | <span data-ttu-id="4ce2b-371">Kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="4ce2b-371">Unwrap</span></span> | <span data-ttu-id="4ce2b-372">Bármely felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="4ce2b-372">Any user-defined type</span></span>
 <span data-ttu-id="4ce2b-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="4ce2b-374">Unáris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-374">Unary</span></span> | <span data-ttu-id="4ce2b-375">Numerikus negatív, bitenkénti komplement, logikai tagadás</span><span class="sxs-lookup"><span data-stu-id="4ce2b-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="4ce2b-376">`Int`, `BigInt` vagy `Double` esetén `-` a `Int` `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="4ce2b-377">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-377">Binary</span></span> | <span data-ttu-id="4ce2b-378">Egész számú Power</span><span class="sxs-lookup"><span data-stu-id="4ce2b-378">Integer power</span></span> | <span data-ttu-id="4ce2b-379">`Int` vagy az `BigInt` alaphoz `Int` a kitevő esetében</span><span class="sxs-lookup"><span data-stu-id="4ce2b-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="4ce2b-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="4ce2b-381">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-381">Binary</span></span> | <span data-ttu-id="4ce2b-382">Osztás, szorzás, egész szám modulusa</span><span class="sxs-lookup"><span data-stu-id="4ce2b-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="4ce2b-383">`Int`, `BigInt` vagy `Double` `/` `*` `Int` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="4ce2b-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-384">`+`, `-`</span></span> | <span data-ttu-id="4ce2b-385">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-385">Binary</span></span> | <span data-ttu-id="4ce2b-386">Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás</span><span class="sxs-lookup"><span data-stu-id="4ce2b-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="4ce2b-387">`Int``BigInt`vagy `Double` , vagy `String` bármely tömb típusa a következőhöz:`+`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="4ce2b-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="4ce2b-389">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-389">Binary</span></span> | <span data-ttu-id="4ce2b-390">Bal SHIFT, jobb SHIFT</span><span class="sxs-lookup"><span data-stu-id="4ce2b-390">Left shift, right shift</span></span> | <span data-ttu-id="4ce2b-391">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="4ce2b-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="4ce2b-393">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-393">Binary</span></span> | <span data-ttu-id="4ce2b-394">Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="4ce2b-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="4ce2b-395">`Int`, `BigInt` vagy `Double`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="4ce2b-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-396">`==`, `!=`</span></span> | <span data-ttu-id="4ce2b-397">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-397">Binary</span></span> | <span data-ttu-id="4ce2b-398">egyenlő, nem egyenlő összehasonlítások</span><span class="sxs-lookup"><span data-stu-id="4ce2b-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="4ce2b-399">bármely primitív típus</span><span class="sxs-lookup"><span data-stu-id="4ce2b-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="4ce2b-400">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-400">Binary</span></span> | <span data-ttu-id="4ce2b-401">Bitenkénti és</span><span class="sxs-lookup"><span data-stu-id="4ce2b-401">Bitwise AND</span></span> | <span data-ttu-id="4ce2b-402">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="4ce2b-403">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-403">Binary</span></span> | <span data-ttu-id="4ce2b-404">Bitenkénti XOR</span><span class="sxs-lookup"><span data-stu-id="4ce2b-404">Bitwise XOR</span></span> | <span data-ttu-id="4ce2b-405">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="4ce2b-406">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-406">Binary</span></span> | <span data-ttu-id="4ce2b-407">Bitenkénti vagy</span><span class="sxs-lookup"><span data-stu-id="4ce2b-407">Bitwise OR</span></span> | <span data-ttu-id="4ce2b-408">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="4ce2b-409">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-409">Binary</span></span> | <span data-ttu-id="4ce2b-410">Logikai ÉS</span><span class="sxs-lookup"><span data-stu-id="4ce2b-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="4ce2b-411">Bináris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-411">Binary</span></span> | <span data-ttu-id="4ce2b-412">Logikai VAGY</span><span class="sxs-lookup"><span data-stu-id="4ce2b-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="4ce2b-413">Bináris/Ternáris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-413">Binary/Ternary</span></span> | <span data-ttu-id="4ce2b-414">Tartomány operátora</span><span class="sxs-lookup"><span data-stu-id="4ce2b-414">Range operator</span></span> | `Int`
 <span data-ttu-id="4ce2b-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-415">`?` `|`</span></span> | <span data-ttu-id="4ce2b-416">Ternáris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-416">Ternary</span></span> | <span data-ttu-id="4ce2b-417">Feltételes</span><span class="sxs-lookup"><span data-stu-id="4ce2b-417">Conditional</span></span> | <span data-ttu-id="4ce2b-418">`Bool` a bal oldali</span><span class="sxs-lookup"><span data-stu-id="4ce2b-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="4ce2b-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="4ce2b-419">`w/` `<-`</span></span> | <span data-ttu-id="4ce2b-420">Ternáris</span><span class="sxs-lookup"><span data-stu-id="4ce2b-420">Ternary</span></span> | <span data-ttu-id="4ce2b-421">Másolás és frissítés</span><span class="sxs-lookup"><span data-stu-id="4ce2b-421">Copy-and-update</span></span> | <span data-ttu-id="4ce2b-422">Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="4ce2b-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ce2b-423">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="4ce2b-423">Next steps</span></span>

<span data-ttu-id="4ce2b-424">Most, hogy együttműködik a kifejezésekkel a alkalmazásban Q# , lépjen be a [műveletekre Q# és a functions](xref:microsoft.quantum.guide.operationsfunctions) szolgáltatásba, ahol megtudhatja, hogyan határozhat meg és hívhat meg műveleteket és funkciókat.</span><span class="sxs-lookup"><span data-stu-id="4ce2b-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
