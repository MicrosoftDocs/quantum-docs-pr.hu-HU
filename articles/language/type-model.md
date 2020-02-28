---
title: 'Q # adattípusok'
description: 'Ismerje meg a Q # programozási nyelvben használt különböző típusokat, beleértve a beépített típusokat, a tömböket, a rekordok, a műveleteket, a függvényeket és a felhasználó által definiált típusokat.'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904655"
---
# <a name="the-type-model"></a><span data-ttu-id="e26ca-103">A típus modellje</span><span class="sxs-lookup"><span data-stu-id="e26ca-103">The Type Model</span></span>

<span data-ttu-id="e26ca-104">Ez a szakasz a Q # type modellt ismerteti, és leírja a típusok megadásának és használatának szintaxisát.</span><span class="sxs-lookup"><span data-stu-id="e26ca-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="e26ca-105">Fontos megjegyezni, hogy a Q # egy *erősen gépelt* nyelv, így az ilyen típusú alkalmazások körültekintő használata segíthet a fordítónak a q # programokkal kapcsolatos erős garanciák megadásában a fordítási idő alatt.</span><span class="sxs-lookup"><span data-stu-id="e26ca-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="e26ca-106">Ahhoz, hogy a lehető legerősebb garanciát nyújtson, a Q # típusok közötti konverziónak explicit módon kell megadnia az átalakítást kifejező függvények hívásait.</span><span class="sxs-lookup"><span data-stu-id="e26ca-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="e26ca-107">Számos ilyen függvényt a <xref:microsoft.quantum.convert> névtér részeként biztosítunk.</span><span class="sxs-lookup"><span data-stu-id="e26ca-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="e26ca-108">A kompatibilis típusok egymásra való átadása implicit módon történik.</span><span class="sxs-lookup"><span data-stu-id="e26ca-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="e26ca-109">A Q # egyszerű típusokat biztosít, amelyek közvetlenül is használhatók, és számos különböző módon hozhatók létre más típusú új típusok.</span><span class="sxs-lookup"><span data-stu-id="e26ca-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="e26ca-110">Ezeket a szakasz további részében ismertetjük.</span><span class="sxs-lookup"><span data-stu-id="e26ca-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="e26ca-111">Primitív típusok</span><span class="sxs-lookup"><span data-stu-id="e26ca-111">Primitive Types</span></span>

<span data-ttu-id="e26ca-112">A Q # nyelv számos *primitív típust*biztosít, amelyekből más típusok is létrehozhatók:</span><span class="sxs-lookup"><span data-stu-id="e26ca-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="e26ca-113">A `Int` típus egy 64 bites előjeles egész számot jelöl, például: `2`, `107`, `-5`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="e26ca-114">A `BigInt` típus tetszőleges méretű aláírt egész számot jelöl, például `2L`, `107L`, `-5L`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="e26ca-115">Ez a típus a .NET-<xref:System.Numerics.BigInteger>on alapul.</span><span class="sxs-lookup"><span data-stu-id="e26ca-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="e26ca-116">típusa.</span><span class="sxs-lookup"><span data-stu-id="e26ca-116">type.</span></span>
- <span data-ttu-id="e26ca-117">A `Double` típus egy kétszeres pontosságú lebegőpontos számot jelöl, például: `0.0`, `-1.3`, `4e-7`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="e26ca-118">A `Bool` típus olyan logikai értéket jelöl, amely lehet `true` vagy `false`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="e26ca-119">A `Qubit` típus a Quantum bitet vagy a qubit jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="e26ca-120">`Qubit`s a felhasználó számára átlátszatlan; az egyetlen lehetséges művelet, amely nem egy másik műveletnek, hanem az identitás (egyenlőség) tesztelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="e26ca-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="e26ca-121">Végső soron a `Qubit`s műveleteit a rendszer belső utasítások meghívásával valósítja meg a kvantum-processzoron (vagy annak szimulációján).</span><span class="sxs-lookup"><span data-stu-id="e26ca-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="e26ca-122">A `Pauli` típus a négy egyqubites Pauli-operátor egyikét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="e26ca-123">Ez a típus az alapművelet elforgatására, valamint a megfigyelhető mérések megadására szolgál.</span><span class="sxs-lookup"><span data-stu-id="e26ca-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="e26ca-124">Ez egy enumerált típus, amely négy lehetséges értékkel rendelkezik: `PauliI`, `PauliX`, `PauliY`és `PauliZ`, amely `Pauli`típusú konstansok.</span><span class="sxs-lookup"><span data-stu-id="e26ca-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="e26ca-125">A `Result` típus a mérték eredményét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="e26ca-126">Ez egy enumerált típus, amely két lehetséges értékkel rendelkezik: `One` és `Zero`, amelyek `Result`típusú konstansok.</span><span class="sxs-lookup"><span data-stu-id="e26ca-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="e26ca-127">`Zero` azt jelzi, hogy a + 1 sajátérték mérése megtörténik; `One` az-1 sajátérték jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="e26ca-128">A `Range` típus az egész számokból álló sorozatot jelöli, amelyet a `start..step..stop`jelöl, amelyben a lépés a következő: beállítások.</span><span class="sxs-lookup"><span data-stu-id="e26ca-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="e26ca-129">Ez `start .. stop` megfelel a `start..1..stop`nak, és például `1..2..7` a $\{1, 3, 5, 7\}$ sorozatot jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="e26ca-130">A `String` típus olyan Unicode-karakterekből álló sor, amely a felhasználó számára a létrehozás után átlátszatlan.</span><span class="sxs-lookup"><span data-stu-id="e26ca-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="e26ca-131">Ez a típus egy klasszikus gazdagép üzeneteinek jelentésére szolgál hiba vagy diagnosztikai esemény esetén.</span><span class="sxs-lookup"><span data-stu-id="e26ca-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="e26ca-132">A `Unit` típus az a típus, amely csak egy értéket engedélyez `()`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="e26ca-133">Ez a típus azt jelzi, hogy a Q # függvény vagy művelet nem ad vissza információt.</span><span class="sxs-lookup"><span data-stu-id="e26ca-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="e26ca-134">Az állandók `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`és `Zero` a Q # összes fenntartott szimbóluma.</span><span class="sxs-lookup"><span data-stu-id="e26ca-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="e26ca-135">Tömbök típusai</span><span class="sxs-lookup"><span data-stu-id="e26ca-135">Array Types</span></span>

<span data-ttu-id="e26ca-136">Bármely érvényes Q # típus `'T`, amely egy `'T`típusú értékek tömbjét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="e26ca-137">Ez a tömb típusa `'T[]`; például `Qubit[]` vagy `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="e26ca-138">Az egész számok gyűjteménye például `Int[]`, a `(Bool, Pauli)` értékek tömbje pedig `(Bool, Pauli)[][]`t jelöl.</span><span class="sxs-lookup"><span data-stu-id="e26ca-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="e26ca-139">A második példában látható, hogy ez a tömbök potenciálisan szaggatott tömbjét jelöli, nem pedig egy téglalap alakú kétdimenziós tömböt.</span><span class="sxs-lookup"><span data-stu-id="e26ca-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="e26ca-140">A Q # nem nyújt támogatást a négyszögletes többdimenziós tömbökhöz.</span><span class="sxs-lookup"><span data-stu-id="e26ca-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="e26ca-141">A tömb értékét Q # forráskódban lehet megírni, ha szögletes zárójeleket használ egy tömb elemei körül, ahogy az `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="e26ca-142">A tömb literál típusát a tömbben lévő összes elem közös alaptípusa határozza meg.</span><span class="sxs-lookup"><span data-stu-id="e26ca-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="e26ca-143">Egy tömb elemei nem módosíthatók a tömb létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="e26ca-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="e26ca-144">Módosított tömb létrehozásához a frissítés és az ismételt hozzárendelés utasítások és/vagy a másolási és frissítési kifejezések használhatók.</span><span class="sxs-lookup"><span data-stu-id="e26ca-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="e26ca-145">Azt is megteheti, hogy létrehoz egy tömböt a méretétől a `new` kulcsszó használatával:</span><span class="sxs-lookup"><span data-stu-id="e26ca-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="e26ca-146">Mindkét esetben a tömb kiépítése után a `Length` fő funkciója használható az elemek számának `Int`ként való beszerzéséhez.</span><span class="sxs-lookup"><span data-stu-id="e26ca-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="e26ca-147">A tömböket szögletes zárójelek használatával lehet előírni, és az alszkriptek `Int` vagy Type `Range`típussal rendelkeznek, hogy a tömb elemeinek egy részhalmazát tartalmazó egyetlen elemet vagy új tömböket szerezzenek be.</span><span class="sxs-lookup"><span data-stu-id="e26ca-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="e26ca-148">A tömbök alszkriptje nulla-alapú:</span><span class="sxs-lookup"><span data-stu-id="e26ca-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="e26ca-149">Rekord típusok</span><span class="sxs-lookup"><span data-stu-id="e26ca-149">Tuple Types</span></span>

<span data-ttu-id="e26ca-150">Megadott nulla vagy több különböző típus `T0`, `T1`,..., `Tn`, egy új *rekord típust* jelölünk `(T0, T1, ..., Tn)`ként.</span><span class="sxs-lookup"><span data-stu-id="e26ca-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="e26ca-151">Az új bejegyzéstípus létrehozásához használt típusok maguk is rekordok, mint a `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="e26ca-152">Az ilyen beágyazás mindig véges, azonban a rekord típusú típusok semmilyen körülmények között nem tartalmazhatják magukat.</span><span class="sxs-lookup"><span data-stu-id="e26ca-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="e26ca-153">Az új rekord típusának értékeit a rekordban lévő egyes típusok értékeinek rekordok alkotják.</span><span class="sxs-lookup"><span data-stu-id="e26ca-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="e26ca-154">A `(3, false)` például egy olyan rekord, amelynek típusa a rekord típusa `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="e26ca-155">A rekordok, a rekordok, a rekordok és az alrekordokok tömbje is létrehozható.</span><span class="sxs-lookup"><span data-stu-id="e26ca-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="e26ca-156">A Q # 0,3 esetében `Unit` az üres rekord *típusának* neve; az üres rekord *értékéhez*`()` van használatban.</span><span class="sxs-lookup"><span data-stu-id="e26ca-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="e26ca-157">A rekordos példányok nem változtathatók meg.</span><span class="sxs-lookup"><span data-stu-id="e26ca-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="e26ca-158">A Q # nem biztosít olyan mechanizmust, amely a létrehozott rekord tartalmának módosítását végzi.</span><span class="sxs-lookup"><span data-stu-id="e26ca-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="e26ca-159">A rekordok hatékony koncepciót használ a Q #-ban az értékek egyetlen értékkel való összegyűjtéséhez, így könnyebben átadhatja őket.</span><span class="sxs-lookup"><span data-stu-id="e26ca-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="e26ca-160">A rekordos jelölések használatával kifejezhető, hogy minden művelet és a hívó pontosan egy bemenetet fogad, és pontosan egy kimenetet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="e26ca-161">Egyszeres rekord egyenértékűsége</span><span class="sxs-lookup"><span data-stu-id="e26ca-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="e26ca-162">Létre lehet hozni egy egyelemes (Single-Element) rekordot, `('T1)`, például `(5)` vagy `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="e26ca-163">A Q # azonban egy egyszeres rekordot teljesen egyenértékűként kezel a befoglalt típus értékével.</span><span class="sxs-lookup"><span data-stu-id="e26ca-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="e26ca-164">Ez nem különbözik a `5` és a `(5)`között, illetve `5` és `(((5)))`között, illetve `(5, (6))` és `(5, 6)`között.</span><span class="sxs-lookup"><span data-stu-id="e26ca-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="e26ca-165">Ez az egyenértékűség minden célra érvényes, beleértve a hozzárendelést és a kifejezéseket is.</span><span class="sxs-lookup"><span data-stu-id="e26ca-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="e26ca-166">Éppen úgy írható, hogy `(5)+3` írni `5+3`, és mindkét kifejezés kiértékelése `8`ra történik.</span><span class="sxs-lookup"><span data-stu-id="e26ca-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="e26ca-167">Ez különösen azt jelenti, hogy egy olyan művelet vagy függvény, amelynek bemeneti vagy kimeneti rekordjának típusa egyetlen mező, egyetlen argumentumként vagy egyetlen érték visszaadása esetén lehet.</span><span class="sxs-lookup"><span data-stu-id="e26ca-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="e26ca-168">Ezt a tulajdonságot egy különálló _rekord egyenértékűségének_nevezzük.</span><span class="sxs-lookup"><span data-stu-id="e26ca-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="e26ca-169">Felhasználó által definiált típusok</span><span class="sxs-lookup"><span data-stu-id="e26ca-169">User-Defined Types</span></span>

<span data-ttu-id="e26ca-170">A Q #-fájlok meghatározhatnak egy olyan új névvel ellátott típust, amely bármely jogi típus egyetlen értékét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="e26ca-171">Bármely rekord típusú `T`deklarálhat egy új, felhasználó által definiált típust, amely az `newtype` utasítással `T` altípusa.</span><span class="sxs-lookup"><span data-stu-id="e26ca-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="e26ca-172">A @"microsoft.quantum.math" névtérben például az összetett számok felhasználó által definiált típusként vannak meghatározva:</span><span class="sxs-lookup"><span data-stu-id="e26ca-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="e26ca-173">Ez az utasítás egy új típust hoz létre, amelyben két, `Double`típusú névtelen elem szerepel.</span><span class="sxs-lookup"><span data-stu-id="e26ca-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="e26ca-174">A névtelen elemektől eltekintve a felhasználó által definiált típusok az elnevezett elemeket is támogatják a Q # 0,7-es vagy újabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="e26ca-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="e26ca-175">Előfordulhat például, hogy elnevezte az `Re` elemet a következőhöz, amely egy összetett szám valódi részét jelöli, és `Im` a képzeletbeli részhez:</span><span class="sxs-lookup"><span data-stu-id="e26ca-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="e26ca-176">Egy felhasználó által definiált típus egyik elemének elnevezése nem jelenti azt, hogy minden elemet el kell nevezni – a nevesített és a névvel ellátott elemek bármely kombinációja támogatott.</span><span class="sxs-lookup"><span data-stu-id="e26ca-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="e26ca-177">Emellett a belső elemek is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="e26ca-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="e26ca-178">Az alább megadott típus `Nested` például egy alapul szolgáló típusú `(Double, (Int, String))`, amelyből csak `Int` típusú elemnek van neve, és minden más elem névtelen.</span><span class="sxs-lookup"><span data-stu-id="e26ca-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="e26ca-179">Az elnevezett elemek előnye, hogy közvetlenül a hozzáférési operátor `::`keresztül érhetők el.</span><span class="sxs-lookup"><span data-stu-id="e26ca-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="e26ca-180">A névtelen elemek egymáshoz való eléréséhez először ki kell kinyerni a becsomagolt értéket a Postfix operátor `!`használatával.</span><span class="sxs-lookup"><span data-stu-id="e26ca-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="e26ca-181">A "kicsomagolás" operátor, `!`, lehetővé teszi a felhasználó által definiált típusban található értékek kinyerését.</span><span class="sxs-lookup"><span data-stu-id="e26ca-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="e26ca-182">A "kicsomagolás" kifejezés típusa a felhasználó által definiált típus alapjául szolgáló típus.</span><span class="sxs-lookup"><span data-stu-id="e26ca-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="e26ca-183">A kicsomagolási operátor kicsomagolja pontosan a burkoló rétegét.</span><span class="sxs-lookup"><span data-stu-id="e26ca-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="e26ca-184">Több kibontható operátor is használható egy szorzáshoz burkolt érték eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="e26ca-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="e26ca-185">Például:</span><span class="sxs-lookup"><span data-stu-id="e26ca-185">For instance:</span></span>

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

<span data-ttu-id="e26ca-186">További részletekért tekintse meg a [kicsomagolási kifejezések](xref:microsoft.quantum.language.expressions#unwrap-expressions) és a [kezelők prioritása](xref:microsoft.quantum.language.expressions#operator-precedence) című szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e26ca-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="e26ca-187">A felhasználó által definiált típus értékeit a megfelelő típusú konstruktor meghívásával lehet létrehozni:</span><span class="sxs-lookup"><span data-stu-id="e26ca-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="e26ca-188">Másik lehetőségként új értékeket is létrehozhat a meglévő [példányokból másolás és frissítés kifejezések](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)használatával.</span><span class="sxs-lookup"><span data-stu-id="e26ca-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="e26ca-189">A tömbökhöz hasonlóan az ilyen kifejezések az eredeti kifejezés összes elemét is átmásolják, a megadott megnevezett elemek kivételével.</span><span class="sxs-lookup"><span data-stu-id="e26ca-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="e26ca-190">Ezeknél az értékek a kifejezés jobb oldalán definiált értékekre vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="e26ca-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="e26ca-191">Más nyelvi szerkezetek, például az [Update-and-reassign utasítások](xref:microsoft.quantum.language.statements#update-and-reassign-statement), amelyek tömb elemek számára elérhetők a felhasználó által definiált típusokban is.</span><span class="sxs-lookup"><span data-stu-id="e26ca-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="e26ca-192">A felhasználó által definiált típusok bármely más típus használata esetén használhatók.</span><span class="sxs-lookup"><span data-stu-id="e26ca-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="e26ca-193">Egy felhasználó által definiált típus tömbjét lehet meghatározni, és egy felhasználó által definiált típust is felvenni egy rekord típusú elemként.</span><span class="sxs-lookup"><span data-stu-id="e26ca-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="e26ca-194">Nem lehet rekurzív típusú struktúrákat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="e26ca-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="e26ca-195">A felhasználó által definiált típust definiáló típus nem lehet olyan rekord típusú, amely a felhasználó által definiált típus elemét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="e26ca-196">A felhasználó által definiált típusok általában nem lehetnek ciklikus függőségek egymással, így a következő típusú definíciók érvénytelenek lesznek:</span><span class="sxs-lookup"><span data-stu-id="e26ca-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="e26ca-197">Amellett, hogy rövid aliasokat biztosít a potenciálisan bonyolult rekordokhoz, az ilyen típusú típusok egyik jelentős előnye, hogy dokumentálni tudja egy adott érték szándékát.</span><span class="sxs-lookup"><span data-stu-id="e26ca-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="e26ca-198">Ha visszatér a `Complex`re, az egyik felhasználó által definiált típusként is meghatározhatja a 2D poláris koordinátákat:</span><span class="sxs-lookup"><span data-stu-id="e26ca-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="e26ca-199">Annak ellenére, hogy mindkét `Complex` és `Polar` egyaránt rendelkezik egy alapul szolgáló típussal `(Double, Double)`, a két típus teljes mértékben inkompatibilis a Q #-ban, ami minimalizálja annak kockázatát, hogy véletlenül egy összetett matematikai függvényt hív meg a Polar koordinátákkal, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="e26ca-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="e26ca-200">Így a felhasználó által definiált típusokhoz hasonló szerepkör tartozik, mint például a F# rekordok.</span><span class="sxs-lookup"><span data-stu-id="e26ca-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="e26ca-201">Művelet és függvények típusai</span><span class="sxs-lookup"><span data-stu-id="e26ca-201">Operation and Function Types</span></span>

<span data-ttu-id="e26ca-202">A Q # _művelet_ egy Quantum alrutin.</span><span class="sxs-lookup"><span data-stu-id="e26ca-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="e26ca-203">Vagyis meghívható rutinok, amelyek kvantumműveleteket tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="e26ca-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="e26ca-204">A Q # _függvény_ egy kvantum-algoritmuson belül használt klasszikus alrutin.</span><span class="sxs-lookup"><span data-stu-id="e26ca-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="e26ca-205">Előfordulhat, hogy klasszikus kódot tartalmaz, de nincs Quantum művelet.</span><span class="sxs-lookup"><span data-stu-id="e26ca-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="e26ca-206">A függvények nem foglalhatnak le vagy nem kölcsönözhetnek qubits, és nem hívhatnak meg műveleteket.</span><span class="sxs-lookup"><span data-stu-id="e26ca-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="e26ca-207">Azonban lehetséges, hogy át kell adni a műveleteket vagy a qubits a feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="e26ca-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="e26ca-208">A functions így teljes mértékben determinisztikus, és ugyanazokkal az argumentumokkal hívja meg ugyanazt az eredményt.</span><span class="sxs-lookup"><span data-stu-id="e26ca-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="e26ca-209">A műveletek és a függvények együttes neve _callables_.</span><span class="sxs-lookup"><span data-stu-id="e26ca-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="e26ca-210">Alább néhány [példát](#examples) láthat.</span><span class="sxs-lookup"><span data-stu-id="e26ca-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="e26ca-211">Az összes Q # callables egyetlen értéket vesz fel bemenetként, és egyetlen értéket ad vissza kimenetként.</span><span class="sxs-lookup"><span data-stu-id="e26ca-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="e26ca-212">A bemeneti és a kimeneti értékek is rekordok.</span><span class="sxs-lookup"><span data-stu-id="e26ca-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="e26ca-213">Olyan Callables, amelyeknek nincs eredmény `Unit`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="e26ca-214">Azok a Callables, amelyek nem rendelkeznek bemenettel, az üres rekordokat is be kell tölteni.</span><span class="sxs-lookup"><span data-stu-id="e26ca-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="e26ca-215">Bármely meghívható alaptípusa `('Tinput => 'Tresult)` vagy `('Tinput -> 'Tresult)`ként van írva, ahol a `'Tinput` és a `'Tresult` típus is.</span><span class="sxs-lookup"><span data-stu-id="e26ca-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="e26ca-216">A műveletekhez az első, `=>`tel rendelkező űrlap használatos. a függvényekhez tartozó második űrlap `->`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="e26ca-217">A `((Qubit, Pauli) => Result)` például a lehetséges qubit mérési művelet aláírását jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="e26ca-218">A függvények típusát az aláírása teljesen megadja.</span><span class="sxs-lookup"><span data-stu-id="e26ca-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="e26ca-219">Egy adott szög szinuszát kiszámító függvénynek például a következő típusúnak kell lennie: `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="e26ca-220">Az Operations – de not functions – tartalmaz bizonyos további _jellemzőket_ , amelyek a művelet típusának részeként vannak kifejezve.</span><span class="sxs-lookup"><span data-stu-id="e26ca-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="e26ca-221">Ezek a jellemzők a művelet által támogatott operációs rendszerekből származó információkat tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="e26ca-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="e26ca-222">A kiindulási műveletek olyan metaadatok, amelyek alapműveletek specializációját eredményezik; lásd [alább a](#functors)következőt:.</span><span class="sxs-lookup"><span data-stu-id="e26ca-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="e26ca-223">A műveleti típusokat a bemeneti típusuk, a kimeneti típusuk és azok jellemzői határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="e26ca-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="e26ca-224">Ahhoz, hogy a `Controlled` és/vagy `Adjoint` a művelet típusának támogatását igényli, hozzá kell adnia egy jegyzetet, amely a megfelelő tulajdonságokat jelzi.</span><span class="sxs-lookup"><span data-stu-id="e26ca-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="e26ca-225">A jegyzet `is Ctl` például azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="e26ca-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="e26ca-226">Ha szeretné megkövetelni, hogy egy adott típusú művelet támogassa a `Adjoint` és a `Controlled`-kezelőt is, ezt `(Qubit => Unit is Adj + Ctl)`ként is kifejezzük.</span><span class="sxs-lookup"><span data-stu-id="e26ca-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="e26ca-227">A használatban lévő működés jellemzői `Adj` és `Ctl` szigorúan beszélő két előre definiált készlet, ahol minden címke egy adott működési jellemzőt jelez, például egy adott felhasználó támogatását.</span><span class="sxs-lookup"><span data-stu-id="e26ca-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="e26ca-228">Ezért a `+` a két készlet Uniójának jelölésére szolgál, és `*` a metszéspontot, azaz a mindkét halmazhoz közös címkéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="e26ca-229">Például a Pauli `X` művelet típusa `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="e26ca-230">Egy olyan Művelettípus, amely nem támogatja az egyiket sem, a bemeneti és a kimeneti típus szerint, külön megjegyzés nélkül adja meg.</span><span class="sxs-lookup"><span data-stu-id="e26ca-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="e26ca-231">Type-paraméteres függvények és műveletek</span><span class="sxs-lookup"><span data-stu-id="e26ca-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="e26ca-232">A hívható típusok tartalmazhatnak típusú paramétereket.</span><span class="sxs-lookup"><span data-stu-id="e26ca-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="e26ca-233">A Type paramétereket egy adott idézőjel által előre meghatározott szimbólum jelöli. a `'A` például egy jogi típusparaméter.</span><span class="sxs-lookup"><span data-stu-id="e26ca-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="e26ca-234">Egy típusparaméter egynél többször is megjelenhet egyetlen aláírásban.</span><span class="sxs-lookup"><span data-stu-id="e26ca-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="e26ca-235">Például egy függvény, amely egy tömb egyes elemein egy másik függvényt alkalmaz, és az összegyűjtött eredményeket az aláírási `(('A[], 'A->'A) -> 'A[])`adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="e26ca-236">Hasonlóképpen, egy függvény, amely két művelet összetételét adja vissza, lehet, hogy van aláírás `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="e26ca-237">A típus-paraméteres metódus hívásakor az azonos típusú paraméterrel rendelkező összes argumentumnak azonos típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e26ca-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="e26ca-238">A Q # nem biztosít olyan mechanizmust, amely lehetővé teszi a Type paraméterhez helyettesíthető lehetséges típusok korlátozását.</span><span class="sxs-lookup"><span data-stu-id="e26ca-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="e26ca-239">Típus kompatibilitása</span><span class="sxs-lookup"><span data-stu-id="e26ca-239">Type Compatibility</span></span>

<span data-ttu-id="e26ca-240">Egy olyan művelet, amelynél további felhasználók támogatottak, a rendszer bárhol használható egy kevesebb ellátott művelettel, de ugyanez az aláírás várható.</span><span class="sxs-lookup"><span data-stu-id="e26ca-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="e26ca-241">Előfordulhat például, hogy egy `(Qubit => Unit is Adj)` típusú művelet is használható, `(Qubit => Unit)` típusú művelettel.</span><span class="sxs-lookup"><span data-stu-id="e26ca-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="e26ca-242">A Q # a hívható visszatérési típusok tekintetében: egy olyan meghívót, amely egy típust ad vissza, `'A` kompatibilis ugyanazzal a bemeneti típussal és olyan eredmény típussal, amelyet a `'A` kompatibilis.</span><span class="sxs-lookup"><span data-stu-id="e26ca-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="e26ca-243">A Q # contravariant típusparamétert a bemeneti típusok tekintetében: egy meghívható, amely egy típust `'A` a bemenetnek, és kompatibilis egy ugyanazzal az eredménnyel, és egy olyan bemeneti típussal, amely kompatibilis a `'A`val.</span><span class="sxs-lookup"><span data-stu-id="e26ca-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="e26ca-244">Ez a következő definíciók miatt:</span><span class="sxs-lookup"><span data-stu-id="e26ca-244">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="e26ca-245">a következők teljesülnek:</span><span class="sxs-lookup"><span data-stu-id="e26ca-245">the following are true:</span></span>

- <span data-ttu-id="e26ca-246">A `ConjugateInvertWith` függvény a `Invert` vagy `ApplyUnitary``inner` argumentumával hívható meg.</span><span class="sxs-lookup"><span data-stu-id="e26ca-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="e26ca-247">A `ConjugateUnitaryWith` függvény a `ApplyUnitary``inner` argumentumával hívható meg, de nem `Invert`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="e26ca-248">`(Qubit[] => Unit is Adj + Ctl)` típusú érték adható vissza `ConjugateInvertWith`ból.</span><span class="sxs-lookup"><span data-stu-id="e26ca-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e26ca-249">A Q # 0,3 jelentős eltérést mutat be a felhasználó által definiált típusok viselkedésében.</span><span class="sxs-lookup"><span data-stu-id="e26ca-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="e26ca-250">A felhasználó által definiált típusokat az alapul szolgáló típus burkolt verziójaként, nem pedig altípusként kezeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e26ca-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="e26ca-251">Ez azt jelenti, hogy a felhasználó által definiált típus értéke nem használható, ha a rendszer az alapul szolgáló típus értékét várta.</span><span class="sxs-lookup"><span data-stu-id="e26ca-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="e26ca-252">Működők</span><span class="sxs-lookup"><span data-stu-id="e26ca-252">Functors</span></span>

<span data-ttu-id="e26ca-253">A Q # egy olyan gyár, amely új műveletet határoz meg egy másik műveletből.</span><span class="sxs-lookup"><span data-stu-id="e26ca-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="e26ca-254">Az új művelet megvalósításának meghatározásakor az üzemben lévők az alapművelet megvalósításához férnek hozzá.</span><span class="sxs-lookup"><span data-stu-id="e26ca-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="e26ca-255">Így a fellépők összetettebb funkciókkal rendelkezhetnek, mint a hagyományos magasabb szintű függvények.</span><span class="sxs-lookup"><span data-stu-id="e26ca-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="e26ca-256">A Q # Type rendszer nem rendelkezik képviselettel a következőben:.</span><span class="sxs-lookup"><span data-stu-id="e26ca-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="e26ca-257">Ezért jelenleg nem lehet őket egy változóhoz kötni, vagy argumentumként átadni őket.</span><span class="sxs-lookup"><span data-stu-id="e26ca-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="e26ca-258">A rendszer egy, a műveletre való alkalmazásával egy új műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="e26ca-259">Például az `Adjoint`t futtató műveletnek a `Y` művelethez való alkalmazásának eredményét `Adjoint Y`ként kell írni.</span><span class="sxs-lookup"><span data-stu-id="e26ca-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="e26ca-260">Előfordulhat, hogy az új művelet a többi művelethez hasonlóan hívható meg.</span><span class="sxs-lookup"><span data-stu-id="e26ca-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="e26ca-261">Így a `Adjoint Y(q1)` alkalmazza a Adjoint-futtatót a `Y` műveletre új művelet létrehozásához, és az új műveletet `q1`re alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="e26ca-262">Hasonlóképpen, a `Controlled X(controls, target)` a `X` műveletre alkalmazza az ellenőrzött munkafolyamatot egy új művelet létrehozásához, és az új műveletet `controls` és `target`re alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="e26ca-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="e26ca-263">A Q # két standard szintű el`Adjoint` és `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="e26ca-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="e26ca-264">Adjoint</span></span>

<span data-ttu-id="e26ca-265">A Quantum Computing szolgáltatásban a művelet adjoint a művelet összetett konjugált átültetése.</span><span class="sxs-lookup"><span data-stu-id="e26ca-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="e26ca-266">Az egységes operátort megvalósító műveletek esetében a adjoint a művelet inverze.</span><span class="sxs-lookup"><span data-stu-id="e26ca-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="e26ca-267">Egy olyan egyszerű művelet esetében, amely csak a többi önálló művelet egy sorozatát hívja meg egy qubits, a adjoint kiszámítható úgy, hogy az Alműveletek adjoints alkalmazza ugyanazon a qubits, a fordított sorrendben.</span><span class="sxs-lookup"><span data-stu-id="e26ca-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="e26ca-268">A művelet kifejezése miatt új műveleti kifejezés is létrehozható a `Adjoint`-felhasználó használatával.</span><span class="sxs-lookup"><span data-stu-id="e26ca-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="e26ca-269">A `Adjoint QFT` például a `QFT` művelet adjoint jelöli.</span><span class="sxs-lookup"><span data-stu-id="e26ca-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="e26ca-270">Az új művelet ugyanazzal az aláírással és típussal rendelkezik, mint az alapművelet.</span><span class="sxs-lookup"><span data-stu-id="e26ca-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="e26ca-271">Az új művelet azt is lehetővé teszi, hogy `Adjoint`, és csak akkor engedélyezze a `Controlled`, ha az alapművelet volt.</span><span class="sxs-lookup"><span data-stu-id="e26ca-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="e26ca-272">A Adjoint-tulajdonos a saját inverze. Ez a `Adjoint Adjoint Op` mindig ugyanaz, mint `Op`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="e26ca-273">Ellenőrzött</span><span class="sxs-lookup"><span data-stu-id="e26ca-273">Controlled</span></span>

<span data-ttu-id="e26ca-274">Egy művelet ellenőrzött verziója olyan új művelet, amely hatékonyan alkalmazza az alapműveletet, ha az összes vezérlő qubits megadott állapotban van.</span><span class="sxs-lookup"><span data-stu-id="e26ca-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="e26ca-275">Ha a vezérlő qubits van, akkor az alapszintű műveletet a rendszer következetesen alkalmazza a Felfekvés megfelelő részére.</span><span class="sxs-lookup"><span data-stu-id="e26ca-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="e26ca-276">Így a rendszer gyakran használja az ellenőrzött műveleteket a felakadás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e26ca-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="e26ca-277">A Q # esetében az ellenőrzött verziók mindig a vezérlési qubits egy tömbjét foglalják magukban, és a megadott állapot mindig az összes vezérlési qubits a számítási (`PauliZ`) `One` állapot, a $ \ket{1}$ értéknél.</span><span class="sxs-lookup"><span data-stu-id="e26ca-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="e26ca-278">A más állapotokon alapuló vezérlést úgy érheti el, ha a megfelelő egységes műveletet alkalmazza a vezérlő qubits az ellenőrzött művelet előtt, majd az egységes művelet inverzét alkalmazza az ellenőrzött művelet után.</span><span class="sxs-lookup"><span data-stu-id="e26ca-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="e26ca-279">Ha például egy `X` műveletet egy vezérelt művelet előtt és után qubit egy vezérlőre, akkor a művelet az adott qubit `Zero` állapotának ($ \ket{0}$) vezérlését eredményezi. egy `H` művelet alkalmazása előtt és után a `PauliX` `One` állapotot fogja vezérelni, amely-1 sajátérték a Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ helyett `PauliZ` `One` állapotban.</span><span class="sxs-lookup"><span data-stu-id="e26ca-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="e26ca-280">A művelet kifejezése miatt új műveleti kifejezés is létrehozható a `Controlled`-felhasználó használatával.</span><span class="sxs-lookup"><span data-stu-id="e26ca-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="e26ca-281">Az új művelet aláírása az eredeti művelet aláírásán alapul.</span><span class="sxs-lookup"><span data-stu-id="e26ca-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="e26ca-282">Az eredmény típusa azonos, de a bemeneti típus egy kétrekordos qubit tömb, amely a vezérlő qubit (ka) t az első elemként, az eredeti művelet argumentumait pedig második elemként tárolja.</span><span class="sxs-lookup"><span data-stu-id="e26ca-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="e26ca-283">Az új művelet támogatja a `Controlled`t, és csak akkor támogatja a `Adjoint`, ha az eredeti művelet végrehajtása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="e26ca-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="e26ca-284">Ha az eredeti művelet csak egyetlen argumentumot vett igénybe, akkor a rendszer az önálló rekordos egyenértékűséget fogja itt lejátszani.</span><span class="sxs-lookup"><span data-stu-id="e26ca-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="e26ca-285">`Controlled X` például a `X` művelet ellenőrzött verziója.</span><span class="sxs-lookup"><span data-stu-id="e26ca-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="e26ca-286">a `X` típusa `(Qubit => Unit is Adj + Ctl)`, ezért `Controlled X` típusa `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; az egyszeres rekordos egyenértékűség miatt ez ugyanaz, mint a `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="e26ca-287">Ha az alapművelet több argumentumot is vett igénybe, ne felejtse el zárójelek közé helyezni a művelet ellenőrzött verziójának megfelelő argumentumait, hogy azok egy rekordba legyenek konvertálva.</span><span class="sxs-lookup"><span data-stu-id="e26ca-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="e26ca-288">`Controlled Rz` például a `Rz` művelet ellenőrzött verziója.</span><span class="sxs-lookup"><span data-stu-id="e26ca-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="e26ca-289">a `Rz` típusa `((Double, Qubit) => Unit is Adj + Ctl)`, ezért `Controlled Rz` típusa `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="e26ca-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="e26ca-290">Így `Controlled Rz(controls, (0.1, target))` a `Controlled Rz` érvényes meghívása lenne (jegyezze fel a `0.1, target`zárójeleit).</span><span class="sxs-lookup"><span data-stu-id="e26ca-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="e26ca-291">Egy másik példa, `CNOT(control, target)` `Controlled X([control], target)`ként is megvalósítható.</span><span class="sxs-lookup"><span data-stu-id="e26ca-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="e26ca-292">Ha egy célt 2 vezérlő qubits (CCNOT) kell vezérelni, a `Controlled X([control1, control2], target)` utasítást is használhatjuk.</span><span class="sxs-lookup"><span data-stu-id="e26ca-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="e26ca-293">Példák</span><span class="sxs-lookup"><span data-stu-id="e26ca-293">Examples</span></span>

<span data-ttu-id="e26ca-294">Ez a példa a Q # műveletre a [mérési](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) mintából származik.</span><span class="sxs-lookup"><span data-stu-id="e26ca-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="e26ca-295">A műveleteken belül lefoglalhatjuk a qubits, és használhatjuk azokat a qubits, mint például a `H` és a `X`:</span><span class="sxs-lookup"><span data-stu-id="e26ca-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="e26ca-296">A függvényhez tartozó példa a [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) mintából származik.</span><span class="sxs-lookup"><span data-stu-id="e26ca-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="e26ca-297">Tisztán klasszikus kódot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e26ca-297">It contains purely classical code.</span></span> <span data-ttu-id="e26ca-298">Láthatja, hogy a fenti példától eltérően a rendszer nem foglal le qubits, és nem használ Quantum műveletet.</span><span class="sxs-lookup"><span data-stu-id="e26ca-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="e26ca-299">Azt is megteheti, hogy a függvény átadja a qubits a feldolgozáshoz, ahogy az a [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) -minta példája.</span><span class="sxs-lookup"><span data-stu-id="e26ca-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="e26ca-300">A rendszer átadja a qubits a függvénynek, és feldolgozásra használja, de a qubit-állapotok nem is módosulnak.</span><span class="sxs-lookup"><span data-stu-id="e26ca-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
