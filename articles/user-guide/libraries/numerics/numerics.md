---
title: 'A Microsoft Q # numerikus könyvtár használata'
description: Ismerje meg a Microsoft Quantum numerikus könyvtárában elérhető típusokat és műveleteket.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275184"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="cd461-103">A numerikus könyvtár használata</span><span class="sxs-lookup"><span data-stu-id="cd461-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="cd461-104">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cd461-104">Overview</span></span>

<span data-ttu-id="cd461-105">A numerikus könyvtár három összetevőből áll</span><span class="sxs-lookup"><span data-stu-id="cd461-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="cd461-106">**Alapszintű egész aritmetika** egész számokkal és összehasonlító értékekkel</span><span class="sxs-lookup"><span data-stu-id="cd461-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="cd461-107">Az alapszintű funkciókra épülő **magas szintű egész funkciók** ; többek között a szorzás, a osztás, az inverzió stb.  aláírt és aláíratlan egész számok esetén.</span><span class="sxs-lookup"><span data-stu-id="cd461-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="cd461-108">**Rögzített szintű aritmetikai funkciók** rögzített pontú inicializálással, hozzáadással, szorzással, kölcsönös, polinom értékeléssel és méréssel.</span><span class="sxs-lookup"><span data-stu-id="cd461-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="cd461-109">Ezen összetevők mindegyike egyetlen utasítás használatával érhető el `open` :</span><span class="sxs-lookup"><span data-stu-id="cd461-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="cd461-110">Típusok</span><span class="sxs-lookup"><span data-stu-id="cd461-110">Types</span></span>

<span data-ttu-id="cd461-111">A numerikus könyvtár a következő típusokat támogatja</span><span class="sxs-lookup"><span data-stu-id="cd461-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="cd461-112">**`LittleEndian`**: Egy `qArr : Qubit[]` egész számot jelölő qubit tömb, amely `qArr[0]` a legkevésbé jelentős bitet jelöli.</span><span class="sxs-lookup"><span data-stu-id="cd461-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="cd461-113">**`SignedLittleEndian`**: Ugyanaz, mint `LittleEndian` a kivételével, hogy a két kiegészítésben tárolt, aláírt egész számot jelöli.</span><span class="sxs-lookup"><span data-stu-id="cd461-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="cd461-114">**`FixedPoint`**: Egy qubit tömbből `qArr2 : Qubit[]` és egy bináris pont pozícióból álló valós számot képvisel `pos` , amely a bináris pont bal oldalán lévő bináris számjegyek számát számlálja.</span><span class="sxs-lookup"><span data-stu-id="cd461-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="cd461-115">`qArr2`a tárolása ugyanúgy történik, mint a `SignedLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="cd461-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="cd461-116">Üzemeltetés</span><span class="sxs-lookup"><span data-stu-id="cd461-116">Operations</span></span>

<span data-ttu-id="cd461-117">A fenti három típus mindegyikéhez számos művelet érhető el:</span><span class="sxs-lookup"><span data-stu-id="cd461-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="cd461-118">Összeadás</span><span class="sxs-lookup"><span data-stu-id="cd461-118">Addition</span></span>
    - <span data-ttu-id="cd461-119">Összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="cd461-119">Comparison</span></span>
    - <span data-ttu-id="cd461-120">Szorzás</span><span class="sxs-lookup"><span data-stu-id="cd461-120">Multiplication</span></span>
    - <span data-ttu-id="cd461-121">Négyszögesítése</span><span class="sxs-lookup"><span data-stu-id="cd461-121">Squaring</span></span>
    - <span data-ttu-id="cd461-122">Osztás (a maradéktal)</span><span class="sxs-lookup"><span data-stu-id="cd461-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="cd461-123">Összeadás</span><span class="sxs-lookup"><span data-stu-id="cd461-123">Addition</span></span>
    - <span data-ttu-id="cd461-124">Összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="cd461-124">Comparison</span></span>
    - <span data-ttu-id="cd461-125">A többverziós adattárház 2</span><span class="sxs-lookup"><span data-stu-id="cd461-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="cd461-126">Szorzás</span><span class="sxs-lookup"><span data-stu-id="cd461-126">Multiplication</span></span>
    - <span data-ttu-id="cd461-127">Négyszögesítése</span><span class="sxs-lookup"><span data-stu-id="cd461-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="cd461-128">Előkészítés/inicializálás klasszikus értékekre</span><span class="sxs-lookup"><span data-stu-id="cd461-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="cd461-129">Hozzáadás (klasszikus állandó vagy más kvantum rögzített pont)</span><span class="sxs-lookup"><span data-stu-id="cd461-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="cd461-130">Összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="cd461-130">Comparison</span></span>
    - <span data-ttu-id="cd461-131">Szorzás</span><span class="sxs-lookup"><span data-stu-id="cd461-131">Multiplication</span></span>
    - <span data-ttu-id="cd461-132">Négyszögesítése</span><span class="sxs-lookup"><span data-stu-id="cd461-132">Squaring</span></span>
    - <span data-ttu-id="cd461-133">Többfunkciós kiértékelés a páros és páratlan függvények esetében</span><span class="sxs-lookup"><span data-stu-id="cd461-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="cd461-134">Kölcsönös (1/x)</span><span class="sxs-lookup"><span data-stu-id="cd461-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="cd461-135">Mérés (klasszikus dupla)</span><span class="sxs-lookup"><span data-stu-id="cd461-135">Measurement (classical Double)</span></span>

<span data-ttu-id="cd461-136">Az egyes műveletekkel kapcsolatos további információkért és részletes dokumentációért tekintse meg a Q # Library dokumentációs dokumentumait a következő címen: [docs.microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="cd461-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="cd461-137">Minta: egész szám hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cd461-137">Sample: Integer addition</span></span>

<span data-ttu-id="cd461-138">Alapszintű példaként vegye fontolóra a $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ értéket, amely egy n-qubit egész $x $ és egy n-vagy (n + 1) értékű művelet, amely a qubit regisztrálja $y $ bemenetként, amely az utóbbi, amelynek a összege a $ (x + y) $-ra van leképezve.</span><span class="sxs-lookup"><span data-stu-id="cd461-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="cd461-139">Vegye figyelembe, hogy az összeg számítása $2 ^ n $, ha $y $ egy $n $ bites regisztrációban van tárolva.</span><span class="sxs-lookup"><span data-stu-id="cd461-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="cd461-140">A Quantum Development Kit használatával ez a művelet a következőképpen alkalmazható:</span><span class="sxs-lookup"><span data-stu-id="cd461-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="cd461-141">Minta: simított függvények kiértékelése</span><span class="sxs-lookup"><span data-stu-id="cd461-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="cd461-142">Ha olyan simított függvényeket szeretne kiértékelni, mint például a $ \sin (x) $ a kvantum-számítógépen, ahol a $x $ a kvantum `FixedPoint` -szám, a Quantum Development Kit numerikus könyvtár biztosítja a műveleteket `EvaluatePolynomialFxP` és a-t `Evaluate[Even/Odd]PolynomialFxP` .</span><span class="sxs-lookup"><span data-stu-id="cd461-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="cd461-143">Az első `EvaluatePolynomialFxP` lehetővé teszi, hogy kiértékelje a "$ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, ahol a $d $ a *mértékét*.</span><span class="sxs-lookup"><span data-stu-id="cd461-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="cd461-144">Ehhez minden szükséges, hogy a polinom `[a_0,..., a_d]` (típus `Double[]` ), a bemenet `x : FixedPoint` és a kimenet `y : FixedPoint` (kezdetben nulla) a következő:</span><span class="sxs-lookup"><span data-stu-id="cd461-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="cd461-145">Az eredmény, $P (x) = 1 + 2x $, a következő helyen lesz tárolva: `yFxP` .</span><span class="sxs-lookup"><span data-stu-id="cd461-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="cd461-146">A második, `EvaluateEvenPolynomialFxP` és a harmadik, a `EvaluateOddPolynomialFxP` páros és páratlan függvények esetében is specializálódott.</span><span class="sxs-lookup"><span data-stu-id="cd461-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="cd461-147">Ez a páros/páratlan függvény esetében $f (x) $ és $ $ P_ {even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, a $ $ $f (x) $ megközelítő értéke $P _ {even} (x) $ vagy $P _ {odd} (x): = x\cdot P_ {even} (x) $, ill.</span><span class="sxs-lookup"><span data-stu-id="cd461-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="cd461-148">A Q #-ban ez a két eset a következőképpen kezelhető:</span><span class="sxs-lookup"><span data-stu-id="cd461-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="cd461-149">amely kiértékeli $P _ {even} (x) = 1 + 2x ^ 2 $ értéket, és</span><span class="sxs-lookup"><span data-stu-id="cd461-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="cd461-150">amely kiértékeli $P _ {odd} (x) = x + 2x ^ 3 $ értéket.</span><span class="sxs-lookup"><span data-stu-id="cd461-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="cd461-151">További példák</span><span class="sxs-lookup"><span data-stu-id="cd461-151">More samples</span></span>

<span data-ttu-id="cd461-152">További mintákat a [fő minták tárházában](https://github.com/Microsoft/Quantum)talál.</span><span class="sxs-lookup"><span data-stu-id="cd461-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="cd461-153">Első lépésként klónozott a tárházat, és nyissa meg az `Numerics` almappát:</span><span class="sxs-lookup"><span data-stu-id="cd461-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="cd461-154">Ezután az `cd` egyik minta mappájába, és futtassa a mintát a használatával</span><span class="sxs-lookup"><span data-stu-id="cd461-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
