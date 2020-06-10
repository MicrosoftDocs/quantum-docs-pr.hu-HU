---
title: 'Kifejezések megadása a Q-ban #'
description: 'Megtudhatja, hogyan adhat meg, hivatkozhat és egyesíthet állandókat, változókat, operátorokat, műveleteket és függvényeket kifejezésként a Q #-ban.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629994"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="474d2-103">Kifejezések megadása a Q-ban #</span><span class="sxs-lookup"><span data-stu-id="474d2-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="474d2-104">Numerikus kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-104">Numeric Expressions</span></span>

<span data-ttu-id="474d2-105">A numerikus kifejezések a következő típusú kifejezések:, `Int` `BigInt` vagy `Double` .</span><span class="sxs-lookup"><span data-stu-id="474d2-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="474d2-106">Vagyis egész vagy lebegőpontos számok.</span><span class="sxs-lookup"><span data-stu-id="474d2-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="474d2-107">`Int`a Q # literálok csak számjegyek sorozatából írhatók.</span><span class="sxs-lookup"><span data-stu-id="474d2-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="474d2-108">A hexadecimális és a bináris egész számok a `0x` és a `0b` előtaggal támogatottak.</span><span class="sxs-lookup"><span data-stu-id="474d2-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="474d2-109">`BigInt`a Q # karakteres literálok egy záró `l` vagy `L` utótaggal íródnak.</span><span class="sxs-lookup"><span data-stu-id="474d2-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="474d2-110">A hexadecimális nagy egész számok "0x" előtaggal támogatottak.</span><span class="sxs-lookup"><span data-stu-id="474d2-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="474d2-111">Így az alábbi értékek érvényesek a literálok összes érvényes használatára `BigInt` :</span><span class="sxs-lookup"><span data-stu-id="474d2-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="474d2-112">`Double`a Q # literális lebegőpontos számok, amelyek decimális számjegyek használatával íródnak.</span><span class="sxs-lookup"><span data-stu-id="474d2-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="474d2-113">Ezek írhatók decimális ponttal, `.` és/vagy az "e" vagy "e" karakterrel jelzett exponenciális rész (amely után csak egy lehetséges negatív jel és decimális számjegy érvényes).</span><span class="sxs-lookup"><span data-stu-id="474d2-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="474d2-114">A következő érvényes `Double` literálok: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="474d2-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="474d2-115">Egy adott elemtípus tömb kifejezése miatt a beépített függvénnyel létrehozható egy `Int` kifejezés, [`Length`](xref:microsoft.quantum.core.length) amely zárójelek közé foglalt tömb kifejezéssel `(` és `)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="474d2-116">Ha például `a` egy tömbhöz van kötve, akkor az egy `Length(a)` egész szám kifejezés.</span><span class="sxs-lookup"><span data-stu-id="474d2-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="474d2-117">Ha `b` az egész számokból álló tömbök tömbje, akkor a- `Int[][]` ben az `Length(b)` altömbök száma, a `b` `Length(b[1])` pedig a második altömbben lévő egész számok száma `b` .</span><span class="sxs-lookup"><span data-stu-id="474d2-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="474d2-118">Az adott típus két numerikus kifejezése, a bináris operátorok, a, `+` `-` és az `*` `/` új numerikus kifejezéseket is felhasználhatja.</span><span class="sxs-lookup"><span data-stu-id="474d2-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="474d2-119">Az új kifejezés típusa megegyezik az összetevő-kifejezések típusával.</span><span class="sxs-lookup"><span data-stu-id="474d2-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="474d2-120">A két egész szám kifejezés miatt a bináris operátor `^` (Power) egy új egész kifejezés létrehozásához használható.</span><span class="sxs-lookup"><span data-stu-id="474d2-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="474d2-121">Hasonlóképpen, két kettős kifejezéssel is használható, amelyek `^` új dupla kifejezést alkotnak.</span><span class="sxs-lookup"><span data-stu-id="474d2-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="474d2-122">Végül a `^` bal oldalon egy nagy egész számmal, a jobb oldalon pedig egy egész számmal, egy új Big Integer típusú kifejezés létrehozásához is használható.</span><span class="sxs-lookup"><span data-stu-id="474d2-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="474d2-123">Ebben az esetben a második paraméternek 32 bitesnek kell lennie; Ha nem, a rendszer futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="474d2-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="474d2-124">A két egész vagy nagy egész szám típusú kifejezés esetében egy új egész vagy Big Integer kifejezés is létrehozható a `%` (modulus), `&&&` (bitenkénti és), `|||` (bitenkénti vagy), vagy `^^^` (bitenkénti XOR) operátorok használatával.</span><span class="sxs-lookup"><span data-stu-id="474d2-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="474d2-125">A bal oldali egész szám vagy nagy egész szám kifejezés, a jobb oldalon pedig egy egész szám kifejezés, a `<<<` (aritmetikai bal SHIFT) vagy `>>>` (aritmetikai jobbra váltás) operátorok használhatók a bal oldali kifejezéssel megegyező típusú új kifejezés létrehozására.</span><span class="sxs-lookup"><span data-stu-id="474d2-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="474d2-126">A második paraméternek (a eltolási mennyiségnek) vagy a SHIFT műveletnek nullánál nagyobbnak vagy azzal egyenlőnek kell lennie. a negatív eltolású összegek viselkedése nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="474d2-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="474d2-127">A eltolási művelet eltolási értékének a 32 bit-be is illeszkednie kell. Ha nem, a rendszer futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="474d2-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="474d2-128">Ha az áthelyezhető szám egész szám, akkor a rendszer a eltolási értéket fogja értelmezni, `mod 64` azaz az 1. és a 65-es váltás hatása megegyezik.</span><span class="sxs-lookup"><span data-stu-id="474d2-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="474d2-129">Mind az egész, mind a Big Integer érték esetén a váltások aritmetikai értékek.</span><span class="sxs-lookup"><span data-stu-id="474d2-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="474d2-130">A negatív érték eltolása balra vagy jobbra is negatív számot eredményez.</span><span class="sxs-lookup"><span data-stu-id="474d2-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="474d2-131">Ez azt okozhatja, hogy az egyik lépés balra vagy jobbra való eltolása pontosan ugyanaz, mint a 2. számú szorzás vagy osztás.</span><span class="sxs-lookup"><span data-stu-id="474d2-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="474d2-132">Az egész szám és az Integer modulus ugyanazt a viselkedést követi a negatív számok esetében, mint a C#.</span><span class="sxs-lookup"><span data-stu-id="474d2-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="474d2-133">Ez azt `a % b` eredményezi, hogy mindig ugyanazzal a jellel fog rendelkezni `a` , és `b * (a / b) + a % b` mindig egyenlő lesz `a` .</span><span class="sxs-lookup"><span data-stu-id="474d2-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="474d2-134">Például:</span><span class="sxs-lookup"><span data-stu-id="474d2-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="474d2-135">5</span><span class="sxs-lookup"><span data-stu-id="474d2-135">5</span></span> | <span data-ttu-id="474d2-136">2</span><span class="sxs-lookup"><span data-stu-id="474d2-136">2</span></span> | <span data-ttu-id="474d2-137">2</span><span class="sxs-lookup"><span data-stu-id="474d2-137">2</span></span> | <span data-ttu-id="474d2-138">1</span><span class="sxs-lookup"><span data-stu-id="474d2-138">1</span></span>
 <span data-ttu-id="474d2-139">5</span><span class="sxs-lookup"><span data-stu-id="474d2-139">5</span></span> | <span data-ttu-id="474d2-140">-2</span><span class="sxs-lookup"><span data-stu-id="474d2-140">-2</span></span> | <span data-ttu-id="474d2-141">-2</span><span class="sxs-lookup"><span data-stu-id="474d2-141">-2</span></span> | <span data-ttu-id="474d2-142">1</span><span class="sxs-lookup"><span data-stu-id="474d2-142">1</span></span>
 <span data-ttu-id="474d2-143">-5</span><span class="sxs-lookup"><span data-stu-id="474d2-143">-5</span></span> | <span data-ttu-id="474d2-144">2</span><span class="sxs-lookup"><span data-stu-id="474d2-144">2</span></span> | <span data-ttu-id="474d2-145">-2</span><span class="sxs-lookup"><span data-stu-id="474d2-145">-2</span></span> | <span data-ttu-id="474d2-146">-1</span><span class="sxs-lookup"><span data-stu-id="474d2-146">-1</span></span>
 <span data-ttu-id="474d2-147">-5</span><span class="sxs-lookup"><span data-stu-id="474d2-147">-5</span></span> | <span data-ttu-id="474d2-148">-2</span><span class="sxs-lookup"><span data-stu-id="474d2-148">-2</span></span> | <span data-ttu-id="474d2-149">2</span><span class="sxs-lookup"><span data-stu-id="474d2-149">2</span></span> | <span data-ttu-id="474d2-150">-1</span><span class="sxs-lookup"><span data-stu-id="474d2-150">-1</span></span>

<span data-ttu-id="474d2-151">A Big Integer osztás és a modulus hasonló módon működik.</span><span class="sxs-lookup"><span data-stu-id="474d2-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="474d2-152">A numerikus kifejezéseket megadva egy új kifejezés hozható létre az `-` unáris operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="474d2-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="474d2-153">Az új kifejezés ugyanolyan típusú lesz, mint az összetevő kifejezése.</span><span class="sxs-lookup"><span data-stu-id="474d2-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="474d2-154">Adott egész szám vagy nagy egész szám kifejezés esetén az azonos típusú új kifejezés az `~~~` (bitenkénti komplement) unáris operátor használatával hozható létre.</span><span class="sxs-lookup"><span data-stu-id="474d2-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="474d2-155">Logikai kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-155">Boolean Expressions</span></span>

<span data-ttu-id="474d2-156">A két `Bool` literális érték a `true` és a `false` .</span><span class="sxs-lookup"><span data-stu-id="474d2-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="474d2-157">Az azonos primitív típusú két kifejezés miatt a `==` és a `!=` bináris operátor is használható kifejezés létrehozásához `Bool` .</span><span class="sxs-lookup"><span data-stu-id="474d2-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="474d2-158">A kifejezés akkor igaz, ha a két kifejezés egyenlő, és hamis, ha nem.</span><span class="sxs-lookup"><span data-stu-id="474d2-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="474d2-159">A felhasználó által definiált típusok értéke nem hasonlítható össze, csak a nem burkolt értékeket lehet összehasonlítani.</span><span class="sxs-lookup"><span data-stu-id="474d2-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="474d2-160">Például a "kicsomagolás" operátor használatával `!` (részletes magyarázat a [Q # típusokban](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator))</span><span class="sxs-lookup"><span data-stu-id="474d2-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="474d2-161">Az értékek egyenlőségének összehasonlítása az `Qubit` identitással egyenlő, azaz azt, hogy a két kifejezés ugyanazt a qubit azonosítja-e.</span><span class="sxs-lookup"><span data-stu-id="474d2-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="474d2-162">A két qubits állapota nem hasonlítható össze, nem érhető el, nem mérhető, illetve nem módosult ezzel az összehasonlítással.</span><span class="sxs-lookup"><span data-stu-id="474d2-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="474d2-163">Az értékek egyenlőségének összehasonlítása a `Double` kerekítési hatások miatt félrevezető lehet.</span><span class="sxs-lookup"><span data-stu-id="474d2-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="474d2-164">Például: `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="474d2-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="474d2-165">A két numerikus kifejezéstől függően a bináris operátorok, a, `>` `<` `>=` és `<=` felhasználhatók egy olyan új logikai kifejezés létrehozására, amely igaz, ha az első kifejezés nagyobb, mint, kisebb, mint, nagyobb vagy egyenlő, mint a második kifejezés.</span><span class="sxs-lookup"><span data-stu-id="474d2-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="474d2-166">A két logikai kifejezés miatt a `and` és a `or` bináris operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha a két kifejezés mindkét (vagy mindkét) értéke igaz.</span><span class="sxs-lookup"><span data-stu-id="474d2-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="474d2-167">A logikai kifejezéseket megadva az `not` egyoperandusú operátor felhasználható egy olyan új logikai kifejezés létrehozására, amely igaz, ha az összetevő kifejezése hamis.</span><span class="sxs-lookup"><span data-stu-id="474d2-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="474d2-168">Karakterlánc-kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-168">String Expressions</span></span>

<span data-ttu-id="474d2-169">A Q # lehetővé teszi a karakterláncok használatát az `fail` utasításban (a [vezérlési folyamat](xref:microsoft.quantum.guide.controlflow#fail-statement)ismertetése) és a [`Message`](xref:microsoft.quantum.intrinsic.message) standard függvényben.</span><span class="sxs-lookup"><span data-stu-id="474d2-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="474d2-170">Az utóbbi adott viselkedése a használt szimulátortól függ, de általában egy üzenetet ír a gazdagép-konzolra, amikor a rendszer egy Q # programban hívja meg.</span><span class="sxs-lookup"><span data-stu-id="474d2-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="474d2-171">A Q # sztringek literálok vagy interpolált karakterláncok.</span><span class="sxs-lookup"><span data-stu-id="474d2-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="474d2-172">A karakterlánc-literálok a legtöbb nyelvben hasonlítanak az egyszerű karakterlánc-literálokra: az Unicode-karakterek egy számsorozata idézőjelek közé `"` .</span><span class="sxs-lookup"><span data-stu-id="474d2-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="474d2-173">Egy karakterláncon belül a háttér-perjel karakter `\` felhasználható dupla idézőjelek kiírására, valamint egy új vonal beszúrására, `\n` a kocsivissza karaktert `\r` és a lapot `\t` .</span><span class="sxs-lookup"><span data-stu-id="474d2-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="474d2-174">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="474d2-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="474d2-175">Interpolált karakterláncok</span><span class="sxs-lookup"><span data-stu-id="474d2-175">Interpolated strings</span></span>

<span data-ttu-id="474d2-176">A Q # szintaxis a karakterlánc-Interpolációk esetében a C# szintaxis egy részhalmaza, de itt összefoglaljuk azokat a kulcsfontosságú pontokat, amelyek a Q #-ra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="474d2-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="474d2-177">A legfontosabb különbségeket az alábbiakban tárgyaljuk.</span><span class="sxs-lookup"><span data-stu-id="474d2-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="474d2-178">Ha egy szövegkonstans-karakterláncot interpolált karakterláncként szeretne azonosítani, a szimbólummal megadhatja azt `$` .</span><span class="sxs-lookup"><span data-stu-id="474d2-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="474d2-179">A és a között nem lehet szóköz, `$` `"` amely egy szövegkonstans-karakterláncot indít el.</span><span class="sxs-lookup"><span data-stu-id="474d2-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="474d2-180">A következő példa egy olyan alapszintű példát mutat be, amely a [`Message`](xref:microsoft.quantum.intrinsic.message) mérés eredményét a konzolra írja, más Q # kifejezésekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="474d2-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="474d2-181">Bármely érvényes Q # kifejezés egy interpolált karakterláncban jelenhet meg.</span><span class="sxs-lookup"><span data-stu-id="474d2-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="474d2-182">A C# szintaxissal kapcsolatos további részletek az [*interpolált karakterláncokban*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)találhatók.</span><span class="sxs-lookup"><span data-stu-id="474d2-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="474d2-183">A legfontosabb különbség az, hogy a Q # nem támogatja a Verbatim (többsoros) interpolált karakterláncokat.</span><span class="sxs-lookup"><span data-stu-id="474d2-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="474d2-184">Az interpolált karakterláncban szereplő kifejezések a Q # szintaxist követik, nem a C# szintaxist.</span><span class="sxs-lookup"><span data-stu-id="474d2-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="474d2-185">Tartomány kifejezései</span><span class="sxs-lookup"><span data-stu-id="474d2-185">Range Expressions</span></span>

<span data-ttu-id="474d2-186">`Int`Egy három kifejezés `start` , a `step` és a `stop` `start .. step .. stop` egy olyan tartomány kifejezése, amelynek első eleme a, a `start` második elem `start+step` , a harmadik elem, `start+step+step` stb., amíg `stop` a rendszer át nem adja.</span><span class="sxs-lookup"><span data-stu-id="474d2-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="474d2-187">A tartomány lehet üres, ha például a `step` pozitív és a `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="474d2-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="474d2-188">A tartomány utolsó eleme abban az esetben lesz `stop` , ha a és a közötti különbség a `start` `stop` többszöröse `step` ; vagyis a tartomány mindkét végén szerepel.</span><span class="sxs-lookup"><span data-stu-id="474d2-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="474d2-189">`Int`A két kifejezésnek `start` `stop` megfelelő, és `start .. stop` egy tartománybeli kifejezés, amely egyenlő `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="474d2-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="474d2-190">Vegye figyelembe, hogy a vélelmezett `step` érték + 1 `stop` , akkor is, ha kevesebb, mint `start` ; ebben az esetben a tartomány üres.</span><span class="sxs-lookup"><span data-stu-id="474d2-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="474d2-191">Néhány példa a tartományokra:</span><span class="sxs-lookup"><span data-stu-id="474d2-191">Some example ranges are:</span></span>

- <span data-ttu-id="474d2-192">`1..3`az 1., 2. és 3. tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="474d2-193">`2..2..5`a 2. és 4. tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="474d2-194">`2..2..6`a 2, 4, 6. tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="474d2-195">`6..-2..2`a 6, 4, 2 tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="474d2-196">`2..1`az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="474d2-197">`2..6..7`a 2. tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="474d2-198">`2..2..1`az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="474d2-199">`1..-1..2`az üres tartomány.</span><span class="sxs-lookup"><span data-stu-id="474d2-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="474d2-200">Qubit kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-200">Qubit Expressions</span></span>

<span data-ttu-id="474d2-201">Az egyetlen `Qubit` kifejezés olyan szimbólum, amely `Qubit` értékek vagy tömb elemeihez van kötve `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="474d2-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="474d2-202">Nincsenek `Qubit` literálok.</span><span class="sxs-lookup"><span data-stu-id="474d2-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="474d2-203">Pauli-kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-203">Pauli Expressions</span></span>

<span data-ttu-id="474d2-204">A négy érték:,,, `Pauli` `PauliI` `PauliX` `PauliY` és `PauliZ` , minden érvényes `Pauli` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="474d2-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="474d2-205">Ettől függetlenül az egyetlen `Pauli` kifejezés olyan szimbólum, amely `Pauli` értékek vagy tömb elemeihez van kötve `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="474d2-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="474d2-206">Eredmény kifejezései</span><span class="sxs-lookup"><span data-stu-id="474d2-206">Result Expressions</span></span>

<span data-ttu-id="474d2-207">A két `Result` érték ( `One` és `Zero` `Result` ) érvényes kifejezés.</span><span class="sxs-lookup"><span data-stu-id="474d2-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="474d2-208">Ettől függetlenül az egyetlen `Result` kifejezés olyan szimbólum, amely `Result` értékek vagy tömb elemeihez van kötve `Result` .</span><span class="sxs-lookup"><span data-stu-id="474d2-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="474d2-209">Különösen fontos megjegyezni, hogy `One` nem ugyanaz, mint az egész szám `1` , és nincs közvetlen konverzió a közöttük.</span><span class="sxs-lookup"><span data-stu-id="474d2-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="474d2-210">Ugyanez érvényes a és a esetében is `Zero` `0` .</span><span class="sxs-lookup"><span data-stu-id="474d2-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="474d2-211">Rekordos kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-211">Tuple Expressions</span></span>

<span data-ttu-id="474d2-212">A rekordos literál a megfelelő típusú elemek sorozata, vesszővel elválasztva, a és a közé foglalt módon `(` `)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="474d2-213">Például `(1, One)` egy `(Int, Result)` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="474d2-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="474d2-214">A konstansok kivételével az egyetlen rekord kifejezés olyan szimbólum, amely a rekord értékekhez, a rekordos tömbök tömb elemeihez és a rekordok visszaadó hívható hívásokhoz van kötve.</span><span class="sxs-lookup"><span data-stu-id="474d2-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="474d2-215">Felhasználó által definiált típusú kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="474d2-216">A felhasználó által definiált típus egy literálja a típus nevét, a típus alaprekordjának típusát pedig a rekordból.</span><span class="sxs-lookup"><span data-stu-id="474d2-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="474d2-217">Ha például a `IntPair` felhasználó által definiált típus a (z) alapján `(Int, Int)` , akkor az `IntPair(2, 3)` adott típusú érvényes literál lenne.</span><span class="sxs-lookup"><span data-stu-id="474d2-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="474d2-218">A konstansok kivételével a felhasználó által definiált típusok egyetlen kifejezése az adott típus értékeit, tömb elemeit és a típust visszaadó hívható hívásokat tartalmazó szimbólumok.</span><span class="sxs-lookup"><span data-stu-id="474d2-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="474d2-219">Kifejezések kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="474d2-219">Unwrap Expressions</span></span>

<span data-ttu-id="474d2-220">A Q # értéknél a kicsomagolás operátor egy záró felkiáltójel `!` .</span><span class="sxs-lookup"><span data-stu-id="474d2-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="474d2-221">Például, ha `IntPair` egy felhasználó által definiált típus, amely egy alapul szolgáló típussal rendelkezik `(Int, Int)` , és `s` egy változó értékkel rendelkezik `IntPair(2, 3)` , akkor a következő `s!` lesz: `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="474d2-222">Más, felhasználó által definiált típusokban definiált, felhasználó által definiált típusok esetében előfordulhat, hogy a kicsomagolási operátor megismétlődik; például `s!!` a kétszeresen kicsomagolt értéket jelöli `s` .</span><span class="sxs-lookup"><span data-stu-id="474d2-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="474d2-223">Így ha a `WrappedPair` felhasználó által definiált típus egy alapul szolgáló típusú `IntPair` , és `t` egy változó értékkel `WrappedPair(IntPair(1,2))` , akkor a következő `t!!` lesz: `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="474d2-224">Az `!` operátor magasabb prioritású, mint az összes többi operátor `[]` , mint a tömb indexelése és a szeletelése.</span><span class="sxs-lookup"><span data-stu-id="474d2-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="474d2-225">`!`és a `[]` kötés elhelyezése, azaz a `a[i]![3]` következőképpen kell elolvasni `((a[i])!)[3]` : a `i` "th elemének `a` kicsomagolása, a kicsomagolása, majd a nem burkolt érték harmadik elemének beolvasása (tömbnek kell lennie).</span><span class="sxs-lookup"><span data-stu-id="474d2-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="474d2-226">Az operátor elsőbbsége `!` egy olyan hatással van, amely esetleg nem nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="474d2-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="474d2-227">Ha egy függvény vagy művelet egy értéket ad vissza, amelyet a rendszer kicsomagol, a függvény vagy a művelet hívását zárójelek közé kell foglalni, hogy az argumentum rekordja a kicsomagolás helyett a híváshoz kapcsolódjon.</span><span class="sxs-lookup"><span data-stu-id="474d2-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="474d2-228">Például:</span><span class="sxs-lookup"><span data-stu-id="474d2-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="474d2-229">Tömb kifejezései</span><span class="sxs-lookup"><span data-stu-id="474d2-229">Array Expressions</span></span>

<span data-ttu-id="474d2-230">A tömb literál egy vagy több elem kifejezésének sorozata, vesszővel elválasztva, a és a `[` közé `]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="474d2-231">Minden elemnek kompatibilisnek kell lennie ugyanazzal a típussal.</span><span class="sxs-lookup"><span data-stu-id="474d2-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="474d2-232">Mivel a két tömb azonos típusú, a bináris `+` operátor egy olyan új tömb létrehozásához használható, amely a két tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="474d2-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="474d2-233">Például: `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="474d2-234">Tömb létrehozása</span><span class="sxs-lookup"><span data-stu-id="474d2-234">Array Creation</span></span>

<span data-ttu-id="474d2-235">Adott típus és kifejezés alapján `Int` az `new` operátor felhasználható a megadott méretű új tömb kiosztására.</span><span class="sxs-lookup"><span data-stu-id="474d2-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="474d2-236">Például `new Int[i + 1]` lefoglalhat egy új `Int` tömböt `i + 1` elemekkel.</span><span class="sxs-lookup"><span data-stu-id="474d2-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="474d2-237">Az üres tömb literálok `[]` nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="474d2-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="474d2-238">A használata helyett, `new ★[0]` ahol a `★` egy megfelelő típusú helyőrző, lehetővé teszi a nulla hosszúságú kívánt tömb létrehozását.</span><span class="sxs-lookup"><span data-stu-id="474d2-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="474d2-239">Az új tömb elemei egy típustól függő alapértelmezett értékre vannak inicializálva.</span><span class="sxs-lookup"><span data-stu-id="474d2-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="474d2-240">A legtöbb esetben ez a nulla valamilyen változata.</span><span class="sxs-lookup"><span data-stu-id="474d2-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="474d2-241">Az entitásokra hivatkozó qubits és callables esetében nincs ésszerű alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="474d2-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="474d2-242">Ezért az ilyen típusú típusok esetében az alapértelmezett érték egy érvénytelen hivatkozás, amely futásidejű hiba nélkül nem használható.</span><span class="sxs-lookup"><span data-stu-id="474d2-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="474d2-243">Ez hasonló a más nyelveken (például C# vagy Java) található null hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="474d2-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="474d2-244">A qubits vagy callables tartalmazó tömböket megfelelően kell inicializálni a nem alapértelmezett értékekkel, mielőtt az elemek biztonságosan használhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="474d2-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="474d2-245">A megfelelő inicializálási rutinok a következő címen találhatók: <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="474d2-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="474d2-246">Az egyes típusok alapértelmezett értékei a következők:</span><span class="sxs-lookup"><span data-stu-id="474d2-246">The default values for each type are:</span></span>

<span data-ttu-id="474d2-247">Típus</span><span class="sxs-lookup"><span data-stu-id="474d2-247">Type</span></span> | <span data-ttu-id="474d2-248">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="474d2-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="474d2-249">_Érvénytelen qubit_</span><span class="sxs-lookup"><span data-stu-id="474d2-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="474d2-250">Az üres tartomány,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="474d2-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="474d2-251">_Érvénytelen hívható_</span><span class="sxs-lookup"><span data-stu-id="474d2-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="474d2-252">A rekord típusú típusok inicializálása elem-by-Element.</span><span class="sxs-lookup"><span data-stu-id="474d2-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="474d2-253">Tömb elemei</span><span class="sxs-lookup"><span data-stu-id="474d2-253">Array Elements</span></span>

<span data-ttu-id="474d2-254">Egy tömb kifejezése és egy `Int` kifejezés alapján egy új kifejezés is létrehozható a `[` és a `]` tömb elem operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="474d2-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="474d2-255">Az új kifejezés ugyanolyan típusú lesz, mint a tömb elemének típusa.</span><span class="sxs-lookup"><span data-stu-id="474d2-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="474d2-256">Ha például `a` egy tömbhöz van kötve `Double` , akkor `a[4]` egy `Double` kifejezés.</span><span class="sxs-lookup"><span data-stu-id="474d2-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="474d2-257">Ha a tömb kifejezése nem egyszerű azonosító, zárójelek közé kell tenni, hogy ki lehessen választani egy elemet.</span><span class="sxs-lookup"><span data-stu-id="474d2-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="474d2-258">Ha például a `a` és `b` mindkét tömbje `Int` , az összefűzésből származó elem a következőként lesz kifejezve:</span><span class="sxs-lookup"><span data-stu-id="474d2-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="474d2-259">A Q # összes tömbje nulla-alapú.</span><span class="sxs-lookup"><span data-stu-id="474d2-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="474d2-260">Vagyis a tömb első eleme `a` mindig `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="474d2-261">Tömb szeletek</span><span class="sxs-lookup"><span data-stu-id="474d2-261">Array Slices</span></span>

<span data-ttu-id="474d2-262">Egy tömböt megadó kifejezés és egy `Range` kifejezés alapján egy új kifejezés is létrehozható a `[` és a `]` tömb szelet operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="474d2-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="474d2-263">Az új kifejezés ugyanolyan típusú, mint a tömb, és a () elemei által indexelt tömb elemeket fogja tartalmazni `Range` a által definiált sorrendben `Range` .</span><span class="sxs-lookup"><span data-stu-id="474d2-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="474d2-264">Ha például egy `a` tömbhöz van kötve `Double` , akkor `a[3..-1..0]` egy `Double[]` kifejezés, amely az első négy elemét tartalmazza, `a` de a fordított sorrendben, ahogy azok megjelennek a következőben: `a` .</span><span class="sxs-lookup"><span data-stu-id="474d2-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="474d2-265">Ha az `Range` üres, akkor az eredményül kapott tömb szelete nulla hosszúságú lesz.</span><span class="sxs-lookup"><span data-stu-id="474d2-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="474d2-266">A tömb elemeihez hasonlóan, ha a tömb kifejezése nem egyszerű azonosító, azt zárójelek közé kell tenni a szelethez.</span><span class="sxs-lookup"><span data-stu-id="474d2-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="474d2-267">Ha `a` és `b` mindkét tömbje `Int` , az összefűzésből származó szeletek a következőképpen lesznek kifejezve:</span><span class="sxs-lookup"><span data-stu-id="474d2-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="474d2-268">Következtetett kezdő/záró értékek</span><span class="sxs-lookup"><span data-stu-id="474d2-268">Inferred start/end values</span></span>

<span data-ttu-id="474d2-269">A 0,8-es verziótól kezdődően a hatókör-szeletelők környezetfüggő kifejezéseket támogatunk.</span><span class="sxs-lookup"><span data-stu-id="474d2-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="474d2-270">A tartomány indítási és befejezési értékei a tartomány-szeletelő kifejezés kontextusában is kihagyhatók.</span><span class="sxs-lookup"><span data-stu-id="474d2-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="474d2-271">Ebben az esetben a fordító a következő szabályok alkalmazásával következteti ki a tartományhoz tartozó elhatárolókat.</span><span class="sxs-lookup"><span data-stu-id="474d2-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="474d2-272">Ha például a tartomány indítási értéke kimarad, akkor a késleltetett indítási érték</span><span class="sxs-lookup"><span data-stu-id="474d2-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="474d2-273">nulla, ha nincs megadva lépés, vagy a megadott lépés pozitív, és</span><span class="sxs-lookup"><span data-stu-id="474d2-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="474d2-274">a szeletelt tömb hossza mínusz eggyel, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="474d2-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="474d2-275">Ha a tartomány befejezési értéke kimarad, akkor a következtetett vég értéke</span><span class="sxs-lookup"><span data-stu-id="474d2-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="474d2-276">a szeletelt tömb hossza mínusz eggyel, ha nincs megadva lépés, vagy a megadott lépés pozitív, és</span><span class="sxs-lookup"><span data-stu-id="474d2-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="474d2-277">nulla, ha a megadott lépés negatív.</span><span class="sxs-lookup"><span data-stu-id="474d2-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="474d2-278">Másolás és frissítés kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="474d2-279">Mivel az összes Q # típus érték típusú, és a qubits némileg speciális szerepkört vesznek fel – a "Copy" szó akkor jön létre, amikor egy érték egy szimbólumhoz van kötve, vagy ha egy szimbólum újra van kötve.</span><span class="sxs-lookup"><span data-stu-id="474d2-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="474d2-280">Ez azt jelenti, hogy a Q # viselkedése megegyezik azzal, mintha egy másolat lett létrehozva a hozzárendelésen.</span><span class="sxs-lookup"><span data-stu-id="474d2-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="474d2-281">A gyakorlatban természetesen csak az érintett darabok szükségesek a létrehozásuk során.</span><span class="sxs-lookup"><span data-stu-id="474d2-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="474d2-282">Ez különösen magában foglalja a tömböket is.</span><span class="sxs-lookup"><span data-stu-id="474d2-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="474d2-283">Különösen nem lehetséges a tömb elemeinek frissítése.</span><span class="sxs-lookup"><span data-stu-id="474d2-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="474d2-284">Egy meglévő tömb módosításához a *copy-Update* mechanizmust kell használnia.</span><span class="sxs-lookup"><span data-stu-id="474d2-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="474d2-285">Új tömbök hozhatók létre a meglévő *példányokból másolás és frissítés* kifejezések használatával.</span><span class="sxs-lookup"><span data-stu-id="474d2-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="474d2-286">A copy-Update kifejezés az űrlap kifejezése `expression1 w/ expression2 <- expression3` , amelyben valamilyen típusú típusnak `expression1` kell lennie `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="474d2-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="474d2-287">A második `expression2` meghatározza, hogy az elem (ek) milyen indexeket módosítson a tömbhöz képest, `expression1` és a típusnak vagy típusúnak kell lennie `Int` `Range` .</span><span class="sxs-lookup"><span data-stu-id="474d2-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="474d2-288">Ha a `expression2` típusa típusú `Int` , a `expression3` típusnak kell lennie `T` .</span><span class="sxs-lookup"><span data-stu-id="474d2-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="474d2-289">Ha a `expression2` típusa típusú `Range` , a `expression3` típusnak kell lennie `T[]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="474d2-290">A másolási és frissítési kifejezés `arr w/ idx <- value` egy új tömböt hoz létre, amely a megfelelő elemre van állítva `arr` , kivéve a (z) elem (ek) et, amely a (z) értékre `idx` van beállítva `value` .</span><span class="sxs-lookup"><span data-stu-id="474d2-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="474d2-291">Ha például `arr` egy tömböt tartalmaz `[0,1,2,3]` , akkor</span><span class="sxs-lookup"><span data-stu-id="474d2-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="474d2-292">`arr w/ 0 <- 10`a tömb `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="474d2-293">`arr w/ 2 <- 10`a tömb `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="474d2-294">`arr w/ 0..2..3 <- [10,12]`a tömb `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="474d2-295">Elnevezett elemek másolási és frissítési kifejezései</span><span class="sxs-lookup"><span data-stu-id="474d2-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="474d2-296">A felhasználó által definiált típusokban hasonló kifejezések léteznek a megnevezett elemekhez.</span><span class="sxs-lookup"><span data-stu-id="474d2-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="474d2-297">Vegyük például a típust</span><span class="sxs-lookup"><span data-stu-id="474d2-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="474d2-298">Ha `c` a érték tartalmazza a Type értéket `Complex(1., -1.)` , akkor a a `c w/ Re <- 0.` következő típusú kifejezést adja `Complex` vissza: `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="474d2-299">Szaggatott tömbök</span><span class="sxs-lookup"><span data-stu-id="474d2-299">Jagged Arrays</span></span>

<span data-ttu-id="474d2-300">Egy szaggatott tömb, más néven "tömbök tömbje", egy tömb, amelynek elemei tömbök.</span><span class="sxs-lookup"><span data-stu-id="474d2-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="474d2-301">A szaggatott tömb elemei eltérő méretűek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="474d2-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="474d2-302">Az alábbi példa azt szemlélteti, hogyan deklarálható és inicializálható egy többrészes táblát jelképező szaggatott tömb.</span><span class="sxs-lookup"><span data-stu-id="474d2-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="474d2-303">Callables tömbök</span><span class="sxs-lookup"><span data-stu-id="474d2-303">Arrays of callables</span></span> 

<span data-ttu-id="474d2-304">Vegye figyelembe, hogy a hívható típusokkal kapcsolatos további részletek az alábbiakban láthatók, valamint a következő oldalon a [Q #-ban található műveletek és függvények](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="474d2-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="474d2-305">Ha az általános elemtípus művelet vagy függvény típusú, az összes elemnek azonos bemeneti és kimeneti típussal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="474d2-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="474d2-306">A tömb elemének típusa az összes elem által támogatott összes olyan futtatót támogatni fogja.</span><span class="sxs-lookup"><span data-stu-id="474d2-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="474d2-307">Például, ha, `Op1` `Op2` és `Op3` mind a `Qubit[] => Unit` , de támogatja `Op1` `Adjoint` , `Op2` támogatja `Controlled` és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="474d2-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="474d2-308">`[Op1, Op2]`a a műveletek tömbje `(Qubit[] => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="474d2-309">`[Op1, Op3]`a a műveletek tömbje `(Qubit[] => Unit is Adj)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="474d2-310">`[Op2, Op3]`a a műveletek tömbje `(Qubit[] => Unit is Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="474d2-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="474d2-311">Bár `(Qubit[] => Unit is Adj)` `(Qubit[] => Unit is Ctl)` a és a műveletek közös alaptípussal rendelkeznek `(Qubit[] => Unit)` , vegye figyelembe, hogy ezen *of* operátorok tömbje nem közös alaptípust tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="474d2-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="474d2-312">Például `[[Op1], [Op2]]` jelenleg hiba történt, mivel a nem kompatibilis tömbök tömbjét kísérli meg létrehozni `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="474d2-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="474d2-313">Feltételes kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-313">Conditional Expressions</span></span>

<span data-ttu-id="474d2-314">Egy adott típus és egy logikai kifejezés két másik kifejezése alapján a feltételes kifejezés a kérdőjel `?` és a függőleges sáv használatával hozható létre `|` .</span><span class="sxs-lookup"><span data-stu-id="474d2-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="474d2-315">Például: `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="474d2-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="474d2-316">Ebben a példában a feltételes kifejezés értéke `c` `a==b` true (igaz `d` ) és false (hamis) lesz.</span><span class="sxs-lookup"><span data-stu-id="474d2-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="474d2-317">Feltételes kifejezések callables</span><span class="sxs-lookup"><span data-stu-id="474d2-317">Conditional expressions with callables</span></span>

<span data-ttu-id="474d2-318">A két kifejezés kiértékelheti azokat a műveleteket, amelyek azonos bemenettel és kimenettel rendelkeznek, de támogatják a különböző elhasználókat.</span><span class="sxs-lookup"><span data-stu-id="474d2-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="474d2-319">Ebben az esetben a feltételes kifejezés típusa olyan művelet, amely azokat a bemeneteket és kimeneteket támogatja, amelyek a mindkét kifejezés által támogatott összes feltételt támogatják.</span><span class="sxs-lookup"><span data-stu-id="474d2-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="474d2-320">Például, ha, `Op1` `Op2` és `Op3` mind a `Qubit[]=>Unit` , de támogatja `Op1` `Adjoint` , `Op2` támogatja `Controlled` és `Op3` támogatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="474d2-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="474d2-321">`flag ? Op1 | Op2`egy `(Qubit[] => Unit)` művelet.</span><span class="sxs-lookup"><span data-stu-id="474d2-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="474d2-322">`flag ? Op1 | Op3`egy `(Qubit[] => Unit is Adj)` művelet.</span><span class="sxs-lookup"><span data-stu-id="474d2-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="474d2-323">`flag ? Op2 | Op3`egy `(Qubit[] => Unit is Ctl)` művelet.</span><span class="sxs-lookup"><span data-stu-id="474d2-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="474d2-324">Ha a két lehetséges eredményhalmaz egyike egy függvény vagy művelet hívása, akkor ez a hívás csak akkor kerül sor, ha az eredmény a hívás értéke lesz.</span><span class="sxs-lookup"><span data-stu-id="474d2-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="474d2-325">`a==b ? C(qs) | D(qs)`Ha például `a==b` igaz, akkor a rendszer `C` meghívja a műveletet, és ha hamis, akkor csak a rendszer `D` hívja meg.</span><span class="sxs-lookup"><span data-stu-id="474d2-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="474d2-326">Ez hasonló a más nyelvek rövid összekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="474d2-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="474d2-327">Hívható kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-327">Callable Expressions</span></span>

<span data-ttu-id="474d2-328">A meghívásos literál a fordítási hatókörben definiált művelet vagy függvény neve.</span><span class="sxs-lookup"><span data-stu-id="474d2-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="474d2-329">Például egy olyan `X` műveleti literál, amely a szabványos könyvtári `X` műveletre hivatkozik, és `Message` egy függvény literál, amely a standard Library `Message` függvényre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="474d2-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="474d2-330">Ha egy művelet támogatja az elválasztó műveletet `Adjoint` , akkor `Adjoint op` egy művelet kifejezése.</span><span class="sxs-lookup"><span data-stu-id="474d2-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="474d2-331">Hasonlóképpen, ha a művelet támogatja az elválasztó műveletet `Controlled` , akkor `Controlled op` egy művelet kifejezése.</span><span class="sxs-lookup"><span data-stu-id="474d2-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="474d2-332">Ezeknek a kifejezéseknek a típusa a [Hívási művelet specializációjában](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)van megadva.</span><span class="sxs-lookup"><span data-stu-id="474d2-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="474d2-333">A (z `Adjoint` ) és a (z) (és `Controlled` ) az összes többi operátornál jobban kötődik, kivéve a kicsomagolási operátort és a tömb indexelését a következővel: `!` [].</span><span class="sxs-lookup"><span data-stu-id="474d2-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="474d2-334">Így a következők mindegyike jogi, feltételezve, hogy a műveletek támogatják a használt munkafolyamatokat:</span><span class="sxs-lookup"><span data-stu-id="474d2-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="474d2-335">Típus – paraméteres hívható kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="474d2-336">Egy meghívásos literál is használható értékként, azaz egy változóhoz való hozzárendeléshez, vagy egy másik meghíváshoz való továbbításhoz.</span><span class="sxs-lookup"><span data-stu-id="474d2-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="474d2-337">Ebben az esetben, ha a meghívható [paraméterekkel](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)rendelkezik, azokat a meghívásos érték részeként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="474d2-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="474d2-338">Egy meghívható érték nem rendelkezhet meghatározatlan típusú paraméterekkel.</span><span class="sxs-lookup"><span data-stu-id="474d2-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="474d2-339">Ha például a `Fun` függvény aláírása `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="474d2-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="474d2-340">Hívható hívási kifejezések</span><span class="sxs-lookup"><span data-stu-id="474d2-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="474d2-341">Egy meghívásos (művelet vagy függvény) kifejezés és a meghívásos aláírás bemeneti típusának egy rekord kifejezése miatt a meghívásos kifejezés úgy hozható létre, hogy hozzáfűzi a rekord kifejezését a meghívható kifejezéshez.</span><span class="sxs-lookup"><span data-stu-id="474d2-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="474d2-342">A Meghívási kifejezés típusa a hívható aláírása kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="474d2-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="474d2-343">Ha például `Op` az egy aláírással rendelkező művelet, a egy `((Int, Qubit) => Double)` `Op(3, qubit1)` típusú kifejezés `Double` .</span><span class="sxs-lookup"><span data-stu-id="474d2-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="474d2-344">Hasonlóképpen, ha `Sin` az egy függvény az aláírással `(Double -> Double)` , `Sin(0.1)` egy típusú kifejezés `Double` .</span><span class="sxs-lookup"><span data-stu-id="474d2-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="474d2-345">Végül, ha `Builder` az a függvény az aláírással `(Int -> (Int -> Int))` , akkor `Builder(3)` a függvény a from int értékre.</span><span class="sxs-lookup"><span data-stu-id="474d2-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="474d2-346">Egy hívható értékű kifejezés eredményének meghívásához egy további zárójelre van szükség a meghívásos kifejezés körül.</span><span class="sxs-lookup"><span data-stu-id="474d2-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="474d2-347">Így az előző bekezdésből történő hívás eredményének meghívásához `Builder` a helyes szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="474d2-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="474d2-348">A [típus-paraméteres](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) metódus meghívásakor a tényleges Type paraméterek a szögletes zárójelben `<` és `>` a meghívásos kifejezés után is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="474d2-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="474d2-349">Ez általában szükségtelen, mivel a Q # fordítóprogram a tényleges típusokat fogja kikövetkeztetni.</span><span class="sxs-lookup"><span data-stu-id="474d2-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="474d2-350">Azonban szükség *van* a [részleges alkalmazásra](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , ha egy Type-paraméteres argumentum nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="474d2-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="474d2-351">Időnként hasznos lehet, ha a különböző felállókkal rendelkező műveletek átadása meghívásos támogatással történik.</span><span class="sxs-lookup"><span data-stu-id="474d2-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="474d2-352">Ha például `Func` rendelkezik aláírással, és aláírással rendelkezik, `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` és `Op3` aláírással rendelkezik `(Qubit[] => Unit)` , az `Func` `Op1` első argumentumként, `Op2` a másodikként és `Op3` a harmadikként való meghívásához:</span><span class="sxs-lookup"><span data-stu-id="474d2-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="474d2-353">A típus specifikációjának megadása kötelező `Op3` `Op1` , mert különböző típusok vannak, így a fordító ezt a specifikáció nélkül nem egyértelműként fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="474d2-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="474d2-354">Operátori prioritás</span><span class="sxs-lookup"><span data-stu-id="474d2-354">Operator Precedence</span></span>

<span data-ttu-id="474d2-355">Minden bináris operátor megfelelő társítású, kivéve a következőt: `^` .</span><span class="sxs-lookup"><span data-stu-id="474d2-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="474d2-356">Szögletes zárójelek, `[` valamint `]` a tömb szeleteléséhez és indexeléséhez minden operátor előtt kötést kell kötni.</span><span class="sxs-lookup"><span data-stu-id="474d2-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="474d2-357">A kikapcsolók `Adjoint` és a `Controlled` kötés a tömb indexelése után, de az összes többi operátor előtt.</span><span class="sxs-lookup"><span data-stu-id="474d2-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="474d2-358">A művelethez és a függvényhez tartozó zárójelek az operátorok előtt, de a tömb indexelése és a feldolgozók után is kötésben vannak.</span><span class="sxs-lookup"><span data-stu-id="474d2-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="474d2-359">Az operátorok elsőbbségi sorrendben, a legmagasabbtól a legalacsonyabbig:</span><span class="sxs-lookup"><span data-stu-id="474d2-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="474d2-360">Operátor</span><span class="sxs-lookup"><span data-stu-id="474d2-360">Operator</span></span> | <span data-ttu-id="474d2-361">Aritása</span><span class="sxs-lookup"><span data-stu-id="474d2-361">Arity</span></span> | <span data-ttu-id="474d2-362">Leírás</span><span class="sxs-lookup"><span data-stu-id="474d2-362">Description</span></span> | <span data-ttu-id="474d2-363">Operandusok típusai</span><span class="sxs-lookup"><span data-stu-id="474d2-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="474d2-364">záró`!`</span><span class="sxs-lookup"><span data-stu-id="474d2-364">trailing `!`</span></span> | <span data-ttu-id="474d2-365">Unáris</span><span class="sxs-lookup"><span data-stu-id="474d2-365">Unary</span></span> | <span data-ttu-id="474d2-366">Kicsomagolása</span><span class="sxs-lookup"><span data-stu-id="474d2-366">Unwrap</span></span> | <span data-ttu-id="474d2-367">Bármely felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="474d2-367">Any user-defined type</span></span>
 <span data-ttu-id="474d2-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="474d2-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="474d2-369">Unáris</span><span class="sxs-lookup"><span data-stu-id="474d2-369">Unary</span></span> | <span data-ttu-id="474d2-370">Numerikus negatív, bitenkénti komplement, logikai tagadás</span><span class="sxs-lookup"><span data-stu-id="474d2-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="474d2-371">`Int`, `BigInt` vagy `Double` esetén `-` a `Int` `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="474d2-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="474d2-372">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-372">Binary</span></span> | <span data-ttu-id="474d2-373">Egész számú Power</span><span class="sxs-lookup"><span data-stu-id="474d2-373">Integer power</span></span> | <span data-ttu-id="474d2-374">`Int`vagy az `BigInt` alaphoz `Int` a kitevő esetében</span><span class="sxs-lookup"><span data-stu-id="474d2-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="474d2-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="474d2-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="474d2-376">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-376">Binary</span></span> | <span data-ttu-id="474d2-377">Osztás, szorzás, egész szám modulusa</span><span class="sxs-lookup"><span data-stu-id="474d2-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="474d2-378">`Int`, `BigInt` vagy `Double` `/` `*` `Int` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="474d2-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="474d2-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="474d2-379">`+`, `-`</span></span> | <span data-ttu-id="474d2-380">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-380">Binary</span></span> | <span data-ttu-id="474d2-381">Hozzáadás vagy karakterlánc és tömb összefűzése, kivonás</span><span class="sxs-lookup"><span data-stu-id="474d2-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="474d2-382">`Int``BigInt`vagy `Double` , vagy `String` bármely tömb típusa a következőhöz:`+`</span><span class="sxs-lookup"><span data-stu-id="474d2-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="474d2-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="474d2-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="474d2-384">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-384">Binary</span></span> | <span data-ttu-id="474d2-385">Bal SHIFT, jobb SHIFT</span><span class="sxs-lookup"><span data-stu-id="474d2-385">Left shift, right shift</span></span> | <span data-ttu-id="474d2-386">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="474d2-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="474d2-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="474d2-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="474d2-388">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-388">Binary</span></span> | <span data-ttu-id="474d2-389">Kevesebb mint, kisebb vagy egyenlő, több mint, nagyobb, mint vagy egyenlő összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="474d2-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="474d2-390">`Int`, `BigInt` vagy`Double`</span><span class="sxs-lookup"><span data-stu-id="474d2-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="474d2-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="474d2-391">`==`, `!=`</span></span> | <span data-ttu-id="474d2-392">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-392">Binary</span></span> | <span data-ttu-id="474d2-393">egyenlő, nem egyenlő összehasonlítások</span><span class="sxs-lookup"><span data-stu-id="474d2-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="474d2-394">bármely primitív típus</span><span class="sxs-lookup"><span data-stu-id="474d2-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="474d2-395">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-395">Binary</span></span> | <span data-ttu-id="474d2-396">Bitenkénti és</span><span class="sxs-lookup"><span data-stu-id="474d2-396">Bitwise AND</span></span> | <span data-ttu-id="474d2-397">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="474d2-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="474d2-398">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-398">Binary</span></span> | <span data-ttu-id="474d2-399">Bitenkénti XOR</span><span class="sxs-lookup"><span data-stu-id="474d2-399">Bitwise XOR</span></span> | <span data-ttu-id="474d2-400">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="474d2-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="474d2-401">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-401">Binary</span></span> | <span data-ttu-id="474d2-402">Bitenkénti vagy</span><span class="sxs-lookup"><span data-stu-id="474d2-402">Bitwise OR</span></span> | <span data-ttu-id="474d2-403">`Int` vagy `BigInt`</span><span class="sxs-lookup"><span data-stu-id="474d2-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="474d2-404">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-404">Binary</span></span> | <span data-ttu-id="474d2-405">Logikai ÉS</span><span class="sxs-lookup"><span data-stu-id="474d2-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="474d2-406">Bináris</span><span class="sxs-lookup"><span data-stu-id="474d2-406">Binary</span></span> | <span data-ttu-id="474d2-407">Logikai VAGY</span><span class="sxs-lookup"><span data-stu-id="474d2-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="474d2-408">Bináris/Ternáris</span><span class="sxs-lookup"><span data-stu-id="474d2-408">Binary/Ternary</span></span> | <span data-ttu-id="474d2-409">Tartomány operátora</span><span class="sxs-lookup"><span data-stu-id="474d2-409">Range operator</span></span> | `Int`
 <span data-ttu-id="474d2-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="474d2-410">`?` `|`</span></span> | <span data-ttu-id="474d2-411">Ternáris</span><span class="sxs-lookup"><span data-stu-id="474d2-411">Ternary</span></span> | <span data-ttu-id="474d2-412">Feltételes</span><span class="sxs-lookup"><span data-stu-id="474d2-412">Conditional</span></span> | <span data-ttu-id="474d2-413">`Bool`a bal oldali</span><span class="sxs-lookup"><span data-stu-id="474d2-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="474d2-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="474d2-414">`w/` `<-`</span></span> | <span data-ttu-id="474d2-415">Ternáris</span><span class="sxs-lookup"><span data-stu-id="474d2-415">Ternary</span></span> | <span data-ttu-id="474d2-416">Másolás és frissítés</span><span class="sxs-lookup"><span data-stu-id="474d2-416">Copy-and-update</span></span> | <span data-ttu-id="474d2-417">Lásd: [Másolás és frissítés kifejezések](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="474d2-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="474d2-418">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="474d2-418">Next steps</span></span>

<span data-ttu-id="474d2-419">Most, hogy a Q #-ban kifejezésekkel dolgozhat, a [q # műveletekhez és függvényekhez](xref:microsoft.quantum.guide.operationsfunctions) is megtudhatja, hogyan határozhatja meg és hívhatja meg a műveleteket és a függvényeket.</span><span class="sxs-lookup"><span data-stu-id="474d2-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
