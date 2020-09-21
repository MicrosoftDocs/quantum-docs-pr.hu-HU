---
title: Típusok Q#
description: Ismerje meg a programozási nyelvben használt különböző típusokat Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: c4a3e6563b8cabee87d1db6b9cb1c1f1c1a7131b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835825"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="e7944-103">Típusok Q#</span><span class="sxs-lookup"><span data-stu-id="e7944-103">Types in Q#</span></span>

<span data-ttu-id="e7944-104">Ez a cikk a Q# típus modelljét és a típusok megadásának és használatának szintaxisát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="e7944-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="e7944-105">Az ilyen típusú kifejezések létrehozásával és működésével kapcsolatos részletekért lásd: [kifejezések megadása](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="e7944-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="e7944-106">Fontos megjegyezni, hogy ez Q# egy *erősen gépelt* nyelv, amely az ilyen típusú alkalmazások körültekintő használatát segíti a fordítót, hogy erős garanciát nyújtson a Q# programoknak a fordítás ideje alatt.</span><span class="sxs-lookup"><span data-stu-id="e7944-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="e7944-107">A legerősebb garanciák biztosításához a típusok közötti konverziónak explicit módon kell megadnia a Q# függvényeknek a konverziót kifejező hívásait.</span><span class="sxs-lookup"><span data-stu-id="e7944-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="e7944-108">Q# számos ilyen funkciót biztosít a névtér részeként <xref:microsoft.quantum.convert> .</span><span class="sxs-lookup"><span data-stu-id="e7944-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="e7944-109">A kompatibilis típusokra való kivezetés viszont implicit módon történik.</span><span class="sxs-lookup"><span data-stu-id="e7944-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="e7944-110">Q# a a közvetlen használatú primitív típusokat, valamint számos különböző módszert biztosít a más típusú új típusok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e7944-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="e7944-111">Ezeket a cikk további részében ismertetjük.</span><span class="sxs-lookup"><span data-stu-id="e7944-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="e7944-112">Primitív típusok</span><span class="sxs-lookup"><span data-stu-id="e7944-112">Primitive Types</span></span>

<span data-ttu-id="e7944-113">A Q# nyelv a következő *primitív típusokat*biztosítja, amelyek mindegyike közvetlenül a Q# programokban használható.</span><span class="sxs-lookup"><span data-stu-id="e7944-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="e7944-114">Ezeket a primitív típusokat új típusok létrehozására is használhatja.</span><span class="sxs-lookup"><span data-stu-id="e7944-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="e7944-115">A `Int` típus 64 bites aláírt egész számot jelöl, például:,, `2` `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="e7944-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="e7944-116">A `BigInt` típus tetszőleges méretű aláírt egész számot jelöl, például:,, `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="e7944-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="e7944-117">Ez a típus a .NET-alapú <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="e7944-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="e7944-118">típusa.</span><span class="sxs-lookup"><span data-stu-id="e7944-118">type.</span></span>

- <span data-ttu-id="e7944-119">A `Double` típus egy dupla pontosságú lebegőpontos számot jelöl, például:,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="e7944-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="e7944-120">A `Bool` típus a vagy a logikai értékét jelöli `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="e7944-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="e7944-121">A `Range` típus egy egész számokból álló sorozatot jelöl, amelyet a (a) jelöl, `start..step..stop` Ha a lépés megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="e7944-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="e7944-122">Például a megfelel a következőnek `start .. stop` `start..1..stop` , és `1..2..7` az \{ 1., 3, 5, 7 $ értéket jelöli \} .</span><span class="sxs-lookup"><span data-stu-id="e7944-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="e7944-123">A `String` típus egy Unicode-karakterből álló sor, amely átlátszatlan a felhasználó számára a létrehozás után.</span><span class="sxs-lookup"><span data-stu-id="e7944-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="e7944-124">`string`Hiba vagy diagnosztikai esemény esetén a típus használatával jelentheti az üzeneteket egy klasszikus gazdagépnek.</span><span class="sxs-lookup"><span data-stu-id="e7944-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="e7944-125">A `Unit` típusnak csak egy értéke lehet `()` .</span><span class="sxs-lookup"><span data-stu-id="e7944-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="e7944-126">Ezzel a típussal jelezheti, hogy egy Q# függvény vagy művelet nem ad vissza adatokat.</span><span class="sxs-lookup"><span data-stu-id="e7944-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="e7944-127">A `Qubit` típus a Quantum bitet vagy a qubit jelöli.</span><span class="sxs-lookup"><span data-stu-id="e7944-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="e7944-128">`Qubit`a (z) a felhasználó számára átlátszatlan.</span><span class="sxs-lookup"><span data-stu-id="e7944-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="e7944-129">Az egyetlen lehetséges művelet, amely nem egy másik műveletnek, hanem az identitás (egyenlőség) tesztelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="e7944-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="e7944-130">Végső soron olyan műveleteket hajt végre a s-ben, amelyek `Qubit` belső utasításokat kérnek a kvantum-processzoron (vagy egy kvantum-szimulátoron).</span><span class="sxs-lookup"><span data-stu-id="e7944-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="e7944-131">A `Pauli` típus a négy egyqubites Pauli-operátor egyikét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e7944-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="e7944-132">Ezzel a típussal jelezheti a forgatások alapműveletét, és meghatározhatja a megfigyelhető mérési értéket.</span><span class="sxs-lookup"><span data-stu-id="e7944-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="e7944-133">Ez egy enumerált típus, amely négy lehetséges értéket tartalmaz:,,, `PauliI` `PauliX` `PauliY` és `PauliZ` , amelyek típusú konstansok `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="e7944-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="e7944-134">A `Result` típus a mérték eredményét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e7944-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="e7944-135">Ez egy enumerált típus, amely két lehetséges értékkel rendelkezik: `One` és `Zero` , amelyek típusú konstansok `Result` .</span><span class="sxs-lookup"><span data-stu-id="e7944-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="e7944-136">`Zero` azt jelzi, hogy a + 1 sajátérték mérése megtörténik; `One` azt jelzi, hogy a-1 sajátérték mérték.</span><span class="sxs-lookup"><span data-stu-id="e7944-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="e7944-137">A konstansok,,,,,,, `true` `false` és az `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` összes foglalt szimbólum szerepel a alkalmazásban Q# .</span><span class="sxs-lookup"><span data-stu-id="e7944-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="e7944-138">Tömbök típusai</span><span class="sxs-lookup"><span data-stu-id="e7944-138">Array Types</span></span>

* <span data-ttu-id="e7944-139">Bármely érvényes Q# típus esetében létezik egy típus, amely az adott típusú értékek tömbjét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e7944-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="e7944-140">Például az `Qubit[]` `(Bool, Pauli)[]` értékek és a rekord típusú értékek tömböket jelölik `Qubit` `(Bool, Pauli)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="e7944-141">Tömbök tömbje is érvényes.</span><span class="sxs-lookup"><span data-stu-id="e7944-141">An array of arrays is also valid.</span></span> <span data-ttu-id="e7944-142">Az előző példát kiterjesztve a tömbök tömbjét `(Bool, Pauli)` jelöli `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="e7944-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="e7944-143">Ez a példa `(Bool, Pauli)[][]` a tömbök potenciálisan szaggatott tömbjét jelöli, nem pedig egy téglalap alakú kétdimenziós tömböt.</span><span class="sxs-lookup"><span data-stu-id="e7944-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="e7944-144">Q# a nem támogatja a négyszögletes többdimenziós tömböket.</span><span class="sxs-lookup"><span data-stu-id="e7944-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="e7944-145">A tömb értéke a Q# forráskódban a tömb elemei körül szögletes zárójelek használatával is írható `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="e7944-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="e7944-146">A tömbben lévő összes elem közös alaptípusa határozza meg egy tömb literál típusát.</span><span class="sxs-lookup"><span data-stu-id="e7944-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="e7944-147">Ezért a tömb olyan elemekkel való létrehozása, amelyek nem rendelkeznek közös alaptípussal, hibát jeleznek.</span><span class="sxs-lookup"><span data-stu-id="e7944-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="e7944-148">Példaként tekintse meg a [callables tömböket](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="e7944-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="e7944-149">A létrehozást követően a tömb elemei nem módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="e7944-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="e7944-150">Módosított tömb létrehozásához használja a [Update-and-reassign utasításait](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) vagy a [másolási és frissítési kifejezéseket](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="e7944-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="e7944-151">Azt is megteheti, hogy létrehoz egy tömböt a méretétől a `new` következő kulcsszó használatával:</span><span class="sxs-lookup"><span data-stu-id="e7944-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="e7944-152">A Core függvénnyel `Length` megszerezheti az elemek számát egy tömbből `Int` .</span><span class="sxs-lookup"><span data-stu-id="e7944-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="e7944-153">A tömbök a tömb elemeinek egy részhalmazát tartalmazó önálló elemek vagy új tömbök beszerzéséhez használhatók.</span><span class="sxs-lookup"><span data-stu-id="e7944-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="e7944-154">A tömbök alszkriptje nulla-alapú, és típusnak `Int` vagy típusnak kell lennie `Range` :</span><span class="sxs-lookup"><span data-stu-id="e7944-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="e7944-155">Rekord típusok</span><span class="sxs-lookup"><span data-stu-id="e7944-155">Tuple Types</span></span>

<span data-ttu-id="e7944-156">A rekordok egy hatékony koncepció, amellyel Q# az értékek összegyűjthetők egyetlen értékkel, így könnyebben átadhatók.</span><span class="sxs-lookup"><span data-stu-id="e7944-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="e7944-157">A rekordos jelölések használatával kipróbálhatja, hogy minden művelet és a hívó pontosan egy bemenetet fogadjon, és pontosan egy kimenetet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="e7944-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="e7944-158">Megadott nulla vagy több különböző típus `T0` , `T1` ,..., az `Tn` új  *rekord típusát* jelöli `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="e7944-159">Az új bejegyzéstípus létrehozásához használt típusok maguk is rekordok, például: `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="e7944-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="e7944-160">Az ilyen beágyazás mindig véges, azonban a rekord típusú típusok semmilyen körülmények között nem tartalmazhatják magukat.</span><span class="sxs-lookup"><span data-stu-id="e7944-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="e7944-161">Az új rekordok értékei a rekordban lévő egyes típusok értékeinek sorozatából jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="e7944-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="e7944-162">Például `(3, false)` egy olyan rekord, amelynek típusa a rekord típusa `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="e7944-163">Létrehozhatók rekordok, rekordok, rekordok, alrekordokek és így tovább.</span><span class="sxs-lookup"><span data-stu-id="e7944-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="e7944-164">A 0,3-as és az Q# `Unit` üres rekord *típusának* neve az `()` üres rekord *értékéhez* használatos.</span><span class="sxs-lookup"><span data-stu-id="e7944-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="e7944-165">A rekordos példányok nem változtathatók meg.</span><span class="sxs-lookup"><span data-stu-id="e7944-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="e7944-166">Q# a nem biztosít olyan mechanizmust, amely a létrehozott rekord tartalmát egyszer módosítja.</span><span class="sxs-lookup"><span data-stu-id="e7944-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="e7944-167">Egyszeres rekord egyenértékűsége</span><span class="sxs-lookup"><span data-stu-id="e7944-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="e7944-168">Létrehozhat egy egyelemes (Single-Element) rekordot `('T1)` , például `(5)` vagy `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="e7944-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="e7944-169">Q#Az Egypéldányos rekordokat azonban a befoglalt típus értékével egyenértékűként kezeli.</span><span class="sxs-lookup"><span data-stu-id="e7944-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="e7944-170">Ez azt jelentheti, hogy nincs különbség a és a között, illetve a és a között, illetve a és a között `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="e7944-171">Ugyanúgy írható, mint az írás, és a `(5)+3` `5+3` kifejezések kiértékelése is megtörténik `8` .</span><span class="sxs-lookup"><span data-stu-id="e7944-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="e7944-172">Ez az egyenértékűség minden célra érvényes, beleértve a hozzárendelést és a kifejezéseket is.</span><span class="sxs-lookup"><span data-stu-id="e7944-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="e7944-173">Ha bármilyen kifejezés szerepel, a zárójelek közé zárt kifejezés azonos típusú kifejezés.</span><span class="sxs-lookup"><span data-stu-id="e7944-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="e7944-174">Például `(7)` egy típusú kifejezés, egy típusú kifejezés `Int` `([1,2,3])` `Int[]` , és `((1,2))` egy típusú kifejezés `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="e7944-175">Ez különösen azt jelenti, hogy megtekintheti azt a műveletet vagy függvényt, amelynek bemeneti vagy kimeneti rekordjának típusa egyetlen mező, vagy egyetlen értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="e7944-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="e7944-176">Ezt a tulajdonságot egy különálló _rekord egyenértékűségének_nevezzük.</span><span class="sxs-lookup"><span data-stu-id="e7944-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="e7944-177">Felhasználó által definiált típusok</span><span class="sxs-lookup"><span data-stu-id="e7944-177">User-Defined Types</span></span>

<span data-ttu-id="e7944-178">A felhasználó által definiált típusú deklaráció a kulcsszóból áll `newtype` , amelyet a felhasználó által definiált típus, az a `=` , az érvényes típus-specifikáció és a megszakítási pontosvesszővel kell kiegészíteni.</span><span class="sxs-lookup"><span data-stu-id="e7944-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="e7944-179">Például:</span><span class="sxs-lookup"><span data-stu-id="e7944-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="e7944-180">Q#Előfordulhat, hogy minden forrásfájl tetszőleges számú felhasználó által definiált típust deklarál.</span><span class="sxs-lookup"><span data-stu-id="e7944-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="e7944-181">A típus nevének egyedinek kell lennie a névtéren belül, és előfordulhat, hogy a művelet és a függvények nevei nem ütköznek egymással.</span><span class="sxs-lookup"><span data-stu-id="e7944-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="e7944-182">A felhasználó által definiált típusok egyediek, még akkor is, ha az alaptípusok azonosak.</span><span class="sxs-lookup"><span data-stu-id="e7944-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="e7944-183">Különösen, ha az alapul szolgáló típusok azonosak, a felhasználó által definiált típusok értékei között nincs automatikus konverzió.</span><span class="sxs-lookup"><span data-stu-id="e7944-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="e7944-184">Névvel ellátott és névtelen elemek</span><span class="sxs-lookup"><span data-stu-id="e7944-184">Named vs. anonymous items</span></span>

<span data-ttu-id="e7944-185">Egy Q# fájl meghatározhatja a jogi típusok egyetlen értékét tartalmazó új elnevezett típust.</span><span class="sxs-lookup"><span data-stu-id="e7944-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="e7944-186">Bármilyen típusú rekord esetében `T` deklarálhat egy új, felhasználó által definiált típust, amely az utasítás altípusa `T` `newtype` .</span><span class="sxs-lookup"><span data-stu-id="e7944-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="e7944-187">A @"microsoft.quantum.math" névtérben például az összetett számok felhasználó által definiált típusként vannak meghatározva:</span><span class="sxs-lookup"><span data-stu-id="e7944-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="e7944-188">Ez az utasítás egy új típust hoz létre két névtelen elem típussal `Double` .</span><span class="sxs-lookup"><span data-stu-id="e7944-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="e7944-189">A névtelen elemektől eltekintve a felhasználó által definiált típusok a 0,7-es vagy újabb verzióként is támogatják az *elnevezett elemeket* Q# .</span><span class="sxs-lookup"><span data-stu-id="e7944-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="e7944-190">Megadhatja például, hogy az elemek `Real` egy összetett szám valódi részét jelképező dupla érték legyen, a `Imag` képzeletbeli rész pedig:</span><span class="sxs-lookup"><span data-stu-id="e7944-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="e7944-191">Egy felhasználó által definiált típus egyik elemének elnevezése nem jelenti azt, hogy az összes elemet el kell nevezni – a nevesített és a nem nevezett elemek bármely kombinációja támogatott.</span><span class="sxs-lookup"><span data-stu-id="e7944-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="e7944-192">Emellett a belső elemek is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="e7944-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="e7944-193">Az `Nested` alább megadott típus például egy alapul szolgáló típussal rendelkezik `(Double, (Int, String))` , amelyből csak a `Int` nevű elem neve szerepel, és minden más elem névtelen.</span><span class="sxs-lookup"><span data-stu-id="e7944-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="e7944-194">Az elnevezett elemek előnye, hogy közvetlenül a *hozzáférési operátoron* keresztül érhetők el `::` .</span><span class="sxs-lookup"><span data-stu-id="e7944-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="e7944-195">Amellett, hogy rövid aliasokat biztosít a potenciálisan bonyolult rekordokhoz, az ilyen típusok meghatározásának jelentős előnye, hogy dokumentálni tudja egy adott érték szándékát.</span><span class="sxs-lookup"><span data-stu-id="e7944-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="e7944-196">A következő példára visszatérve egy `Complex` Polar koordináta-represenation is definiálhat felhasználó által definiált típusként:</span><span class="sxs-lookup"><span data-stu-id="e7944-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="e7944-197">Bár mindkettő `Complex` és `ComplexPolar` mindkettő rendelkezik egy alapul szolgáló típussal `(Double, Double)` , a két típus teljesen inkompatibilis a-ben Q# , ami minimalizálja annak kockázatát, hogy véletlenül egy összetett matematikai függvényt hív meg a Polar koordinátákkal, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="e7944-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="e7944-198">Névtelen elemek elérése a kicsomagolási operátorral</span><span class="sxs-lookup"><span data-stu-id="e7944-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="e7944-199">A névtelen elemek eléréséhez először bontsa ki a becsomagolt értéket a Postfix operátor használatával `!` .</span><span class="sxs-lookup"><span data-stu-id="e7944-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="e7944-200">A "kicsomagolás" operátor `!` használatával kinyerheti a felhasználó által definiált típusban található értéket.</span><span class="sxs-lookup"><span data-stu-id="e7944-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="e7944-201">A "kicsomagolás" kifejezés típusa a felhasználó által definiált típus alapjául szolgáló típus.</span><span class="sxs-lookup"><span data-stu-id="e7944-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="e7944-202">Egyetlen kibontott operátor kicsomagolja az egyik réteget.</span><span class="sxs-lookup"><span data-stu-id="e7944-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="e7944-203">Több kibontható operátor használata egy szorzáshoz burkolt érték eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="e7944-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="e7944-204">Például:</span><span class="sxs-lookup"><span data-stu-id="e7944-204">For example:</span></span>

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

<span data-ttu-id="e7944-205">További információ a kicsomagolási operátorról: [kifejezések beírása Q# a alkalmazásban ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="e7944-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="e7944-206">Felhasználó által definiált típusok értékeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="e7944-206">Creating values of user-defined types</span></span>

<span data-ttu-id="e7944-207">Hozzon létre egy felhasználó által definiált típus értékeit a megfelelő típusú konstruktor meghívásával:</span><span class="sxs-lookup"><span data-stu-id="e7944-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="e7944-208">Azt is megteheti, hogy a [Másolás és frissítés kifejezések](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)használatával új értékeket hoz létre a meglévők közül.</span><span class="sxs-lookup"><span data-stu-id="e7944-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="e7944-209">Csakúgy, mint a tömbök esetében, a másolási és frissítési kifejezések az eredeti kifejezés összes elemét átmásolják, kivéve a megadott megnevezett elemeket.</span><span class="sxs-lookup"><span data-stu-id="e7944-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="e7944-210">A kivételek esetében ezek az elemek a kifejezés jobb oldalán megadott értékek.</span><span class="sxs-lookup"><span data-stu-id="e7944-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="e7944-211">A tömb elemeihez rendelkezésre álló más nyelvi szerkezetek, például az [Update-and-reassign utasítások](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)léteznek a felhasználó által definiált típusokban lévő névvel ellátott elemekhez is.</span><span class="sxs-lookup"><span data-stu-id="e7944-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

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

* <span data-ttu-id="e7944-212">A felhasználó által definiált típusokat bárhol használhatja bármilyen más típus használata esetén.</span><span class="sxs-lookup"><span data-stu-id="e7944-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="e7944-213">Egy felhasználó által definiált típus tömbjét lehet meghatározni, és egy felhasználó által definiált típust is felvenni egy rekord típusú elemként.</span><span class="sxs-lookup"><span data-stu-id="e7944-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="e7944-214">Nem lehet rekurzív típusú struktúrákat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="e7944-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="e7944-215">Vagyis a felhasználó által definiált típust definiáló típus nem lehet a felhasználó által definiált típusú elemet tartalmazó rekord típusa.</span><span class="sxs-lookup"><span data-stu-id="e7944-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="e7944-216">A felhasználó által definiált típusok általában nem lehetnek ciklikus függőségek egymástól, így a következő típusú definíciók érvénytelenek:</span><span class="sxs-lookup"><span data-stu-id="e7944-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="e7944-217">Művelet és függvények típusai</span><span class="sxs-lookup"><span data-stu-id="e7944-217">Operation and Function Types</span></span>

<span data-ttu-id="e7944-218">A típusok `'Tinput` és a `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="e7944-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="e7944-219">`('Tinput => 'Tresult)` a *művelet*alapszintű típusa, például: `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="e7944-220">`('Tinput -> 'Tresult)` a *függvény*alapvető típusa, például: `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="e7944-221">Ezeket a meghívásos *aláírásnak* nevezzük.</span><span class="sxs-lookup"><span data-stu-id="e7944-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="e7944-222">Minden Q# callables egyetlen értéket adjon meg bemenetként, és egyetlen értéket ad vissza kimenetként.</span><span class="sxs-lookup"><span data-stu-id="e7944-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="e7944-223">A bemeneti és a kimeneti értékekhez egyaránt használhatja a rekordok.</span><span class="sxs-lookup"><span data-stu-id="e7944-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="e7944-224">Olyan Callables, amelyeknek nincs eredménye, vissza `Unit` .</span><span class="sxs-lookup"><span data-stu-id="e7944-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="e7944-225">Azok a Callables, amelyek nem rendelkeznek bemenettel, az üres rekordokat is be kell tölteni.</span><span class="sxs-lookup"><span data-stu-id="e7944-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="e7944-226">Működők</span><span class="sxs-lookup"><span data-stu-id="e7944-226">Functors</span></span>

<span data-ttu-id="e7944-227">A *függvények* típusát az aláírása teljesen megadja.</span><span class="sxs-lookup"><span data-stu-id="e7944-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="e7944-228">Például egy olyan függvény, amely egy szög szinuszát számítja ki, típusnak kellene lennie `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="e7944-229">A *műveletek* bizonyos további jellemzőkkel rendelkeznek, amelyek a művelet típusának részeként vannak kifejezve.</span><span class="sxs-lookup"><span data-stu-id="e7944-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="e7944-230">Ezek a tulajdonságok olyan információkat tartalmaznak *, amelyek a* művelet által támogatott operációs rendszerek.</span><span class="sxs-lookup"><span data-stu-id="e7944-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="e7944-231">Ha például a művelet egy másik qubits állapotára támaszkodik, akkor az a következőt támogatja:. `Controlled` Ha a műveletnek van inverze, akkor támogatnia kell az elválasztó szolgáltatást `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="e7944-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="e7944-232">Ez a cikk csak azt tárgyalja, hogyan változtatják meg a műveleti aláírást.</span><span class="sxs-lookup"><span data-stu-id="e7944-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="e7944-233">További információ a-feladatokról és a műveletekről: [műveletek és Q# függvények a alkalmazásban ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="e7944-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="e7944-234">Ha a `Controlled` és/vagy az `Adjoint` üzemben lévőt egy művelet típusában szeretné támogatni, hozzá kell adnia egy jegyzetet, amely a megfelelő tulajdonságokat jelzi.</span><span class="sxs-lookup"><span data-stu-id="e7944-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="e7944-235">A jegyzet `is Ctl` (például `(Qubit => Unit is Ctl)` ) azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="e7944-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="e7944-236">Ez a Futtatás egy másik qubit vagy qubits állapotára támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="e7944-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="e7944-237">Hasonlóképpen, a jegyzet `is Adj` azt jelzi, hogy a műveletnek van egy adjoint, azaz "invertált" lehet, például egy művelet egymást követő alkalmazása, majd az állapot adjoint változatlan marad.</span><span class="sxs-lookup"><span data-stu-id="e7944-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="e7944-238">Ha szeretné megkövetelni, hogy egy adott típusú művelet támogassa a és a-kezelőt is, ezt a következő `Adjoint` `Controlled` módon fejezheti ki: `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="e7944-239">A beépített Pauli-művelet például a <xref:microsoft.quantum.intrinsic.x> következőt írja be: `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="e7944-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="e7944-240">Egy olyan Művelettípus, amely nem támogatja az egyiket sem, a bemeneti és a kimeneti típus szerint, külön megjegyzés nélkül adja meg.</span><span class="sxs-lookup"><span data-stu-id="e7944-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="e7944-241">Type-paraméteres függvények és műveletek</span><span class="sxs-lookup"><span data-stu-id="e7944-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="e7944-242">A hívható típusok tartalmazhatnak *típusú paramétereket*.</span><span class="sxs-lookup"><span data-stu-id="e7944-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="e7944-243">Egy idézőjel által előre meghatározott szimbólumot használjon, amely egy type paramétert jelez; például `'A` egy jogi típusparaméter.</span><span class="sxs-lookup"><span data-stu-id="e7944-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="e7944-244">A típus-paraméteres callables definiálásával kapcsolatos további információkért lásd: [műveletek és függvények a alkalmazásban Q# ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="e7944-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="e7944-245">Egy típusparaméter egynél többször is megjelenhet egyetlen aláírásban.</span><span class="sxs-lookup"><span data-stu-id="e7944-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="e7944-246">Például egy olyan függvény, amely egy tömb minden elemére egy másik függvényt alkalmaz, és az összegyűjtött eredményeket az aláírással adja vissza `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="e7944-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="e7944-247">Hasonlóképpen, egy függvény, amely két művelet összeállítását adja vissza, az aláírással rendelkezik `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="e7944-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="e7944-248">Ha egy Type-paraméteres meghívást hív meg, az azonos típusú paraméterrel rendelkező összes argumentumnak azonos típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e7944-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="e7944-249">Q# a nem biztosít olyan mechanizmust, amely lehetővé teszi, hogy a felhasználók egy típusparaméter esetében helyettesíthetik a lehetséges típusokat.</span><span class="sxs-lookup"><span data-stu-id="e7944-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7944-250">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="e7944-250">Next steps</span></span>

<span data-ttu-id="e7944-251">Most, hogy megismerte a nyelvet alkotó összes típust Q# , tekintse meg a [kifejezések Q# beírása](xref:microsoft.quantum.guide.expressions) című témakört, amelyből megtudhatja, hogyan hozhat létre és kezelhet különféle típusú kifejezéseket.</span><span class="sxs-lookup"><span data-stu-id="e7944-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
