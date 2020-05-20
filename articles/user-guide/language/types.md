---
title: Típusok a Q#-ban
description: 'A Q # programozási nyelvben használt különböző típusok megismerése.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609141"
---
# <a name="types-in-q"></a><span data-ttu-id="63e45-103">Típusok a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="63e45-103">Types in Q#</span></span>

<span data-ttu-id="63e45-104">Ez a lap a Q # type modellt mutatja be, és leírja a típusok megadásának és használatának szintaxisát.</span><span class="sxs-lookup"><span data-stu-id="63e45-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="63e45-105">A következő lapon [írja be a kifejezések kifejezést](xref:microsoft.quantum.guide.expressions), és adja meg, hogyan kell létrehozni és használni az ilyen típusú kifejezéseket.</span><span class="sxs-lookup"><span data-stu-id="63e45-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="63e45-106">Fontos megjegyezni, hogy a Q # egy *erősen gépelt* nyelv, így az ilyen típusú alkalmazások körültekintő használata segíthet a fordítónak a q # programokkal kapcsolatos erős garanciák megadásában a fordítási idő alatt.</span><span class="sxs-lookup"><span data-stu-id="63e45-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="63e45-107">Ahhoz, hogy a lehető legerősebb garanciát nyújtson, a Q # típusok közötti konverziónak explicit módon kell megadnia az átalakítást kifejező függvények hívásait.</span><span class="sxs-lookup"><span data-stu-id="63e45-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="63e45-108">Számos ilyen függvény a névtér részeként van megadva <xref:microsoft.quantum.convert> .</span><span class="sxs-lookup"><span data-stu-id="63e45-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="63e45-109">A kompatibilis típusok egymásra való átadása implicit módon történik.</span><span class="sxs-lookup"><span data-stu-id="63e45-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="63e45-110">A Q # egyszerű típusokat biztosít, amelyek közvetlenül is használhatók, és számos különböző módon hozhatók létre más típusú új típusok.</span><span class="sxs-lookup"><span data-stu-id="63e45-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="63e45-111">Ezeket a szakasz további részében ismertetjük.</span><span class="sxs-lookup"><span data-stu-id="63e45-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="63e45-112">Primitív típusok</span><span class="sxs-lookup"><span data-stu-id="63e45-112">Primitive Types</span></span>

<span data-ttu-id="63e45-113">A Q # nyelv számos *primitív típust*biztosít, amelyekből más típusok is létrehozhatók:</span><span class="sxs-lookup"><span data-stu-id="63e45-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="63e45-114">A `Int` típus 64 bites aláírt egész számot jelöl, például: `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="63e45-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="63e45-115">A `BigInt` típus tetszőleges méretű aláírt egész számot jelöl, például:, `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="63e45-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="63e45-116">Ez a típus a .NET-alapú<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="63e45-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="63e45-117">típusa.</span><span class="sxs-lookup"><span data-stu-id="63e45-117">type.</span></span>
- <span data-ttu-id="63e45-118">A `Double` típus egy dupla pontosságú lebegőpontos számot jelöl, például: `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="63e45-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="63e45-119">A `Bool` típus olyan logikai értéket jelöl, amely vagy lehet `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="63e45-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="63e45-120">A `Range` típus egy egész számokból álló sorozatot jelöl, amelyet a (a) jelöl, `start..step..stop` Ha a lépés megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="63e45-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="63e45-121">Ez `start .. stop` megfelel a-nek `start..1..stop` , és például `1..2..7` az \{ 1., 3., 5., 7 $-os sorozatot jelöli \} .</span><span class="sxs-lookup"><span data-stu-id="63e45-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="63e45-122">A `String` típus egy Unicode-karakterből álló sor, amely átlátszatlan a felhasználó számára a létrehozás után.</span><span class="sxs-lookup"><span data-stu-id="63e45-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="63e45-123">Ez a típus egy klasszikus gazdagép üzeneteinek jelentésére szolgál hiba vagy diagnosztikai esemény esetén.</span><span class="sxs-lookup"><span data-stu-id="63e45-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="63e45-124">A `Unit` típus az a típus, amely csak egy értéket engedélyez `()` .</span><span class="sxs-lookup"><span data-stu-id="63e45-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="63e45-125">Ez a típus azt jelzi, hogy a Q # függvény vagy művelet nem ad vissza információt.</span><span class="sxs-lookup"><span data-stu-id="63e45-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="63e45-126">A `Qubit` típus a Quantum bitet vagy a qubit jelöli.</span><span class="sxs-lookup"><span data-stu-id="63e45-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="63e45-127">`Qubit`a (z) a felhasználó számára átlátszatlan; az egyetlen lehetséges művelet, amely nem egy másik műveletnek, hanem az identitás (egyenlőség) tesztelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="63e45-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="63e45-128">Végső soron az s-műveletek `Qubit` megvalósítása a kvantum-processzoron (vagy annak szimulációján) alapuló belső utasítások meghívásával valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="63e45-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="63e45-129">A `Pauli` típus a négy egyqubites Pauli-operátor egyikét jelöli.</span><span class="sxs-lookup"><span data-stu-id="63e45-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="63e45-130">Ez a típus az alapművelet elforgatására, valamint a megfigyelhető mérések megadására szolgál.</span><span class="sxs-lookup"><span data-stu-id="63e45-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="63e45-131">Ez egy enumerált típus, amely négy lehetséges értékkel rendelkezik:,,, `PauliI` `PauliX` `PauliY` és `PauliZ` , amelyek típusú konstansok `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="63e45-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="63e45-132">A `Result` típus a mérték eredményét jelöli.</span><span class="sxs-lookup"><span data-stu-id="63e45-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="63e45-133">Ez egy enumerált típus, amely két lehetséges értékkel rendelkezik: `One` és `Zero` , amelyek típusú konstansok `Result` .</span><span class="sxs-lookup"><span data-stu-id="63e45-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="63e45-134">`Zero`azt jelzi, hogy a + 1 sajátérték mérése megtörténik; `One`az-1 sajátérték jelöli.</span><span class="sxs-lookup"><span data-stu-id="63e45-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="63e45-135">A konstansok,,,,,,, `true` `false` és a `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # összes fenntartott szimbóluma.</span><span class="sxs-lookup"><span data-stu-id="63e45-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="63e45-136">Tömbök típusai</span><span class="sxs-lookup"><span data-stu-id="63e45-136">Array Types</span></span>

<span data-ttu-id="63e45-137">Az érvényes Q # típusnak megfelelő típus `'T` esetén a rendszer egy típusú értékek tömbjét jelöli `'T` .</span><span class="sxs-lookup"><span data-stu-id="63e45-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="63e45-138">Ez a tömb típusa a következő `'T[]` :, például `Qubit[]` vagy `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="63e45-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="63e45-139">Egy egész számokból álló gyűjteményt például a rendszer az `Int[]` értékek tömbök tömbjét jelöli `(Bool, Pauli)` `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="63e45-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="63e45-140">A második példában látható, hogy ez a tömbök potenciálisan szaggatott tömbjét jelöli, nem pedig egy téglalap alakú kétdimenziós tömböt.</span><span class="sxs-lookup"><span data-stu-id="63e45-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="63e45-141">A Q # nem nyújt támogatást a négyszögletes többdimenziós tömbökhöz.</span><span class="sxs-lookup"><span data-stu-id="63e45-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="63e45-142">A tömb értéke Q # forráskódban is megadható, ha szögletes zárójeleket használ egy tömb elemei körül `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="63e45-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="63e45-143">A tömb literál típusát a tömbben lévő összes elem közös alaptípusa határozza meg.</span><span class="sxs-lookup"><span data-stu-id="63e45-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="63e45-144">Egy tömb elemei nem módosíthatók a tömb létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="63e45-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="63e45-145">Módosított tömb létrehozásához a [frissítés és az ismételt hozzárendelés utasítások](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) és/vagy [a másolási és frissítési kifejezések](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) használhatók.</span><span class="sxs-lookup"><span data-stu-id="63e45-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="63e45-146">Azt is megteheti, hogy létrehoz egy tömböt a méretétől a `new` következő kulcsszó használatával:</span><span class="sxs-lookup"><span data-stu-id="63e45-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="63e45-147">Mindkét esetben a tömb kiépítése után az alapfunkció használatával `Length` megszerezhető az elemek száma `Int` .</span><span class="sxs-lookup"><span data-stu-id="63e45-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="63e45-148">A tömbök a szögletes zárójelek használatával, a típus vagy a típus beírásával, a tömb `Int` `Range` elemeinek egy részhalmazát tartalmazó önálló elemek vagy új tömbök beszerzésére is alkalmasak.</span><span class="sxs-lookup"><span data-stu-id="63e45-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="63e45-149">A tömbök alszkriptje nulla-alapú:</span><span class="sxs-lookup"><span data-stu-id="63e45-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="63e45-150">Rekord típusok</span><span class="sxs-lookup"><span data-stu-id="63e45-150">Tuple Types</span></span>

<span data-ttu-id="63e45-151">Megadott nulla vagy több különböző típus `T0` , `T1` ,..., `Tn` egy új *rekord típusát* jelöli `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="63e45-152">Az új bejegyzéstípus létrehozásához használt típusok maguk is rekordok, például: `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="63e45-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="63e45-153">Az ilyen beágyazás mindig véges, azonban a rekord típusú típusok semmilyen körülmények között nem tartalmazhatják magukat.</span><span class="sxs-lookup"><span data-stu-id="63e45-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="63e45-154">Az új rekord típusának értékeit a rekordban lévő egyes típusok értékeinek rekordok alkotják.</span><span class="sxs-lookup"><span data-stu-id="63e45-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="63e45-155">Például `(3, false)` egy olyan rekord, amelynek típusa a rekord típusa `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="63e45-156">A rekordok, a rekordok, a rekordok és az alrekordokok tömbje is létrehozható.</span><span class="sxs-lookup"><span data-stu-id="63e45-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="63e45-157">A Q # 0,3-tól kezdve a (z) `Unit` üres rekord *típusának* neve, `()` amelyet az üres rekord *értékéhez*használ a rendszer.</span><span class="sxs-lookup"><span data-stu-id="63e45-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="63e45-158">A rekordos példányok nem változtathatók meg.</span><span class="sxs-lookup"><span data-stu-id="63e45-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="63e45-159">A Q # nem biztosít olyan mechanizmust, amely a létrehozott rekord tartalmának módosítását végzi.</span><span class="sxs-lookup"><span data-stu-id="63e45-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="63e45-160">A rekordok hatékony koncepciót használ a Q #-ban az értékek egyetlen értékkel való összegyűjtéséhez, így könnyebben átadhatja őket.</span><span class="sxs-lookup"><span data-stu-id="63e45-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="63e45-161">A rekordos jelölések használatával kifejezhető, hogy minden művelet és a hívó pontosan egy bemenetet fogad, és pontosan egy kimenetet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="63e45-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="63e45-162">Egyszeres rekord egyenértékűsége</span><span class="sxs-lookup"><span data-stu-id="63e45-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="63e45-163">Létre lehet hozni egy egyelemes (Single-Element) rekordot, `('T1)` például `(5)` vagy `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="63e45-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="63e45-164">A Q # azonban egy egyszeres rekordot teljesen egyenértékűként kezel a befoglalt típus értékével.</span><span class="sxs-lookup"><span data-stu-id="63e45-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="63e45-165">Ez azt jelentheti, hogy nincs különbség a és a között, illetve a és a között, illetve a és a között `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="63e45-166">Ugyanúgy írható `(5)+3` , mint az írás `5+3` , és mindkét kifejezés kiértékelése a következőre történik: `8` .</span><span class="sxs-lookup"><span data-stu-id="63e45-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="63e45-167">Ez az egyenértékűség minden célra érvényes, beleértve a hozzárendelést és a kifejezéseket is.</span><span class="sxs-lookup"><span data-stu-id="63e45-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="63e45-168">Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="63e45-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="63e45-169">Például `(7)` egy `Int` kifejezés, amely `([1,2,3])` egy tömb típusú kifejezés, `Int` és `((1,2))` egy típusú kifejezés `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="63e45-170">Ez különösen azt jelenti, hogy egy olyan művelet vagy függvény, amelynek bemeneti vagy kimeneti rekordjának típusa egyetlen mező, egyetlen argumentumként vagy egyetlen érték visszaadása esetén lehet.</span><span class="sxs-lookup"><span data-stu-id="63e45-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="63e45-171">Ezt a tulajdonságot egy különálló _rekord egyenértékűségének_nevezzük.</span><span class="sxs-lookup"><span data-stu-id="63e45-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="63e45-172">Felhasználó által definiált típusok</span><span class="sxs-lookup"><span data-stu-id="63e45-172">User-Defined Types</span></span>

<span data-ttu-id="63e45-173">A felhasználó által definiált típusú deklaráció a kulcsszóból áll `newtype` , amelyet a felhasználó által definiált típus, az a `=` , az érvényes típus-specifikáció és a megszakítási pontosvesszővel kell kiegészíteni.</span><span class="sxs-lookup"><span data-stu-id="63e45-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="63e45-174">Például:</span><span class="sxs-lookup"><span data-stu-id="63e45-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="63e45-175">Minden Q # forrásfájl tetszőleges számú felhasználó által definiált típust deklarálhat.</span><span class="sxs-lookup"><span data-stu-id="63e45-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="63e45-176">A típus nevének egyedinek kell lennie a névtéren belül, és előfordulhat, hogy a művelet és a függvények nevei nem ütköznek egymással.</span><span class="sxs-lookup"><span data-stu-id="63e45-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="63e45-177">A felhasználó által definiált típusok akkor is eltérőek, ha az alaptípusok azonosak.</span><span class="sxs-lookup"><span data-stu-id="63e45-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="63e45-178">Különösen, ha az alapul szolgáló típusok azonosak, a felhasználó által definiált típusok értékei között nincs automatikus konverzió.</span><span class="sxs-lookup"><span data-stu-id="63e45-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="63e45-179">Névvel ellátott és névtelen elemek</span><span class="sxs-lookup"><span data-stu-id="63e45-179">Named vs. anonymous items</span></span>

<span data-ttu-id="63e45-180">A Q #-fájlok meghatározhatnak egy olyan új névvel ellátott típust, amely bármely jogi típus egyetlen értékét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="63e45-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="63e45-181">Bármilyen típusú rekord esetében `T` deklarálhat egy új, felhasználó által definiált típust, amely az utasítás altípusa `T` `newtype` .</span><span class="sxs-lookup"><span data-stu-id="63e45-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="63e45-182">A @"microsoft.quantum.math" névtérben például az összetett számok felhasználó által definiált típusként vannak meghatározva:</span><span class="sxs-lookup"><span data-stu-id="63e45-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="63e45-183">Ez az utasítás egy új típust hoz létre két névtelen elem típussal `Double` .</span><span class="sxs-lookup"><span data-stu-id="63e45-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="63e45-184">A névtelen elemektől eltekintve a felhasználó által definiált típusok az *elnevezett elemeket* is támogatják a Q # 0,7-es vagy újabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="63e45-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="63e45-185">Tegyük fel például, hogy elnevezte az elemet a Double elemnek, amely `Re` egy komplex szám valódi részét jelképezi, és `Im` a képzeletbeli részhez:</span><span class="sxs-lookup"><span data-stu-id="63e45-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="63e45-186">Egy felhasználó által definiált típus egyik elemének elnevezése nem jelenti azt, hogy az összes elemet el kell nevezni – a nevesített és a nem nevezett elemek bármely kombinációja támogatott.</span><span class="sxs-lookup"><span data-stu-id="63e45-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="63e45-187">Emellett a belső elemek is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="63e45-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="63e45-188">Az `Nested` alább definiált típus például egy alapul szolgáló típussal rendelkezik `(Double, (Int, String))` , amelyből csak a nevű elem `Int` neve és minden más elem névtelen.</span><span class="sxs-lookup"><span data-stu-id="63e45-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="63e45-189">Az elnevezett elemek előnye, hogy közvetlenül a *hozzáférési operátoron* keresztül érhetők el `::` .</span><span class="sxs-lookup"><span data-stu-id="63e45-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="63e45-190">Amellett, hogy rövid aliasokat biztosít a potenciálisan bonyolult rekordokhoz, az ilyen típusú típusok egyik jelentős előnye, hogy dokumentálni tudja egy adott érték szándékát.</span><span class="sxs-lookup"><span data-stu-id="63e45-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="63e45-191">A példára való visszatéréshez a `Complex` 2D poláris koordinátákat is definiálhatja felhasználó által definiált típusként:</span><span class="sxs-lookup"><span data-stu-id="63e45-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="63e45-192">Bár mindkettő `Complex` és `Polar` mindkettő egy alapul szolgáló típussal rendelkezik `(Double, Double)` , a két típus teljes mértékben inkompatibilis a Q #-ban, ami minimalizálja annak kockázatát, hogy a komplex matematikai függvények véletlenül hívása a Polar koordinátákkal és fordítva.</span><span class="sxs-lookup"><span data-stu-id="63e45-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="63e45-193">Így a felhasználó által definiált típusokhoz hasonló szerepkör tartozik, mint például az F # rekord.</span><span class="sxs-lookup"><span data-stu-id="63e45-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="63e45-194">Névtelen elemek elérése a kicsomagolási operátorral</span><span class="sxs-lookup"><span data-stu-id="63e45-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="63e45-195">A névtelen elemek eléréséhez a beburkolt értéket először a Postfix operátor használatával kell kinyerni `!` .</span><span class="sxs-lookup"><span data-stu-id="63e45-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="63e45-196">A "kicsomagolás" operátor `!` lehetővé teszi, hogy kinyerje a felhasználó által definiált típusban található értéket.</span><span class="sxs-lookup"><span data-stu-id="63e45-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="63e45-197">A "kicsomagolás" kifejezés típusa a felhasználó által definiált típus alapjául szolgáló típus.</span><span class="sxs-lookup"><span data-stu-id="63e45-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="63e45-198">A kicsomagolási operátor kicsomagolja pontosan a burkoló rétegét.</span><span class="sxs-lookup"><span data-stu-id="63e45-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="63e45-199">Több kibontható operátor is használható egy szorzáshoz burkolt érték eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="63e45-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="63e45-200">Ilyenek például a következők:</span><span class="sxs-lookup"><span data-stu-id="63e45-200">For instance:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="63e45-201">A kicsomagolással foglalkozó operátorral kapcsolatos további részletek a [Q # típus kifejezések kifejezésében](xref:microsoft.quantum.guide.expressions)találhatók.</span><span class="sxs-lookup"><span data-stu-id="63e45-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="63e45-202">Felhasználó által definiált típusok értékeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="63e45-202">Creating values of user-defined types</span></span>

<span data-ttu-id="63e45-203">A felhasználó által definiált típus értékeit a megfelelő típusú konstruktor meghívásával lehet létrehozni:</span><span class="sxs-lookup"><span data-stu-id="63e45-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="63e45-204">Másik lehetőségként új értékeket is létrehozhat a meglévő [példányokból másolás és frissítés kifejezések](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)használatával.</span><span class="sxs-lookup"><span data-stu-id="63e45-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="63e45-205">A tömbökhöz hasonlóan az ilyen kifejezések az eredeti kifejezés összes elemét is átmásolják, a megadott megnevezett elemek kivételével.</span><span class="sxs-lookup"><span data-stu-id="63e45-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="63e45-206">Ezeknél az értékek a kifejezés jobb oldalán definiált értékekre vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="63e45-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="63e45-207">Más nyelvi szerkezetek, például az [Update-and-reassign utasítások](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), amelyek a tömb elemei számára elérhetők a felhasználó által definiált típusokban is.</span><span class="sxs-lookup"><span data-stu-id="63e45-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

<span data-ttu-id="63e45-208">A felhasználó által definiált típusok bármely más típus használata esetén használhatók.</span><span class="sxs-lookup"><span data-stu-id="63e45-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="63e45-209">Egy felhasználó által definiált típus tömbjét lehet meghatározni, és egy felhasználó által definiált típust is felvenni egy rekord típusú elemként.</span><span class="sxs-lookup"><span data-stu-id="63e45-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="63e45-210">Megjegyzés: rekurzív típusú struktúrákat nem lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="63e45-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="63e45-211">A felhasználó által definiált típust definiáló típus nem lehet olyan rekord típusú, amely a felhasználó által definiált típus elemét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="63e45-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="63e45-212">A felhasználó által definiált típusok általában nem lehetnek ciklikus függőségek egymással, így a következő típusú definíciók érvénytelenek lesznek:</span><span class="sxs-lookup"><span data-stu-id="63e45-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="63e45-213">Művelet és függvények típusai</span><span class="sxs-lookup"><span data-stu-id="63e45-213">Operation and Function Types</span></span>

<span data-ttu-id="63e45-214">Az összes meghívóhoz tartozó alaptípust a vagy a értékre kell írni `('Tinput => 'Tresult)` `('Tinput -> 'Tresult)` , ahol mindkettő `'Tinput` és `'Tresult` típus szerepel.</span><span class="sxs-lookup"><span data-stu-id="63e45-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="63e45-215">Ezeket a meghívásos *aláírásnak* nevezzük.</span><span class="sxs-lookup"><span data-stu-id="63e45-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="63e45-216">Az összes Q # callables egyetlen értéket vesz fel bemenetként, és egyetlen értéket ad vissza kimenetként.</span><span class="sxs-lookup"><span data-stu-id="63e45-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="63e45-217">A bemeneti és a kimeneti értékek is rekordok.</span><span class="sxs-lookup"><span data-stu-id="63e45-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="63e45-218">Callables, amelyek nem adnak vissza eredményt `Unit` .</span><span class="sxs-lookup"><span data-stu-id="63e45-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="63e45-219">Azok a Callables, amelyek nem rendelkeznek bemenettel, az üres rekordokat is be kell tölteni.</span><span class="sxs-lookup"><span data-stu-id="63e45-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="63e45-220">A rendszer az első űrlapot `=>` használja a műveletekhez, a második pedig a `->` függvényekhez.</span><span class="sxs-lookup"><span data-stu-id="63e45-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="63e45-221">Például `((Qubit, Pauli) => Result)` az egy lehetséges qubit mérési művelet aláírását jelöli.</span><span class="sxs-lookup"><span data-stu-id="63e45-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="63e45-222">A *függvények* típusát az aláírása teljesen megadja.</span><span class="sxs-lookup"><span data-stu-id="63e45-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="63e45-223">Például egy olyan függvény, amely egy szög szinuszát számítja ki, típusnak kellene lennie `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="63e45-224">Az *operations*---, de a függvények nem---vannak olyan további jellemzők, amelyek a Művelettípus részeként vannak kifejezve.</span><span class="sxs-lookup"><span data-stu-id="63e45-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="63e45-225">Ezek *a jellemzők* a művelet által támogatott operációs rendszerekből származó információkat tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="63e45-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="63e45-226">Ha például a művelet végrehajtása más qubits állapotára is felhasználható, akkor támogatnia kell az elválasztó `Controlled` . Ha a művelet inverz, akkor támogatnia kell a következőt: `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="63e45-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="63e45-227">A műveletek és a műveletek a [Q # műveletekben](xref:microsoft.quantum.guide.operationsfunctions)részletesen tárgyalnak, de itt egyszerűen megbeszéljük, hogy ez hogyan változtatja meg a művelet aláírását.</span><span class="sxs-lookup"><span data-stu-id="63e45-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="63e45-228">Ahhoz, hogy egy Művelettípus támogassa a `Controlled` és/vagy az operátort `Adjoint` , hozzá kell adnia egy jegyzetet, amely a megfelelő tulajdonságokat jelzi.</span><span class="sxs-lookup"><span data-stu-id="63e45-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="63e45-229">`is Ctl`A jegyzet (például `(Qubit => Unit is Ctl)` ) azt jelzi, hogy a művelet---, azaz egy másik qubit vagy qubits állapotára vonatkozó végrehajtásra van állítva.</span><span class="sxs-lookup"><span data-stu-id="63e45-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="63e45-230">Hasonlóképpen `is Adj` azt is jelzi, hogy a művelet rendelkezik egy adjoint, vagy egyszerűen "invertálva" lehet, hogy egy művelet egymást követő alkalmazása, majd az állapot adjoint változatlan marad.</span><span class="sxs-lookup"><span data-stu-id="63e45-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="63e45-231">Ha szeretné megkövetelni, hogy egy adott típusú művelet támogassa a és a-kezelőt is, ezt a típust `Adjoint` `Controlled` is kinyilváníthatja `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="63e45-232">A beépített Pauli-művelet például a <xref:microsoft.quantum.intrinsic.x> következőt írja be: `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="63e45-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="63e45-233">Egy olyan Művelettípus, amely nem támogatja az egyiket sem, a bemeneti és a kimeneti típus szerint, külön megjegyzés nélkül adja meg.</span><span class="sxs-lookup"><span data-stu-id="63e45-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="63e45-234">Type-paraméteres függvények és műveletek</span><span class="sxs-lookup"><span data-stu-id="63e45-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="63e45-235">A hívható típusok tartalmazhatnak típusú paramétereket.</span><span class="sxs-lookup"><span data-stu-id="63e45-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="63e45-236">A Type paramétereket egy adott idézőjel által előre meghatározott szimbólum jelöli. például `'A` egy jogi típusparaméter.</span><span class="sxs-lookup"><span data-stu-id="63e45-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="63e45-237">A Type-paraméteres callables definiálásával kapcsolatos részletek a [Q # oldalon található műveletek és függvények esetében](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) találhatók.</span><span class="sxs-lookup"><span data-stu-id="63e45-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="63e45-238">Egy típusparaméter egynél többször is megjelenhet egyetlen aláírásban.</span><span class="sxs-lookup"><span data-stu-id="63e45-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="63e45-239">Például egy függvény, amely egy tömb minden elemére egy másik függvényt alkalmaz, és az összegyűjtött eredményeket az aláírással adja vissza `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="63e45-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="63e45-240">Hasonlóképpen, egy függvény, amely két művelet összetételét adja vissza, aláírással rendelkezhet `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="63e45-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="63e45-241">A típus-paraméteres metódus hívásakor az azonos típusú paraméterrel rendelkező összes argumentumnak azonos típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="63e45-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="63e45-242">A Q # nem biztosít olyan mechanizmust, amely lehetővé teszi a Type paraméterhez helyettesíthető lehetséges típusok korlátozását.</span><span class="sxs-lookup"><span data-stu-id="63e45-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="63e45-243">Vajon mi a következő lépés?</span><span class="sxs-lookup"><span data-stu-id="63e45-243">What's Next?</span></span>
<span data-ttu-id="63e45-244">Most, hogy megismerte a Q # nyelvét alkotó összes típust, [írja be a kifejezéseket a q # szövegbe](xref:microsoft.quantum.guide.expressions) , hogy megtudja, hogyan hozhat létre és kezelhet a különböző típusú kifejezéseket.</span><span class="sxs-lookup"><span data-stu-id="63e45-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


