---
title: A numerikus függvénytár használata | Microsoft Docs
description: A numerikus könyvtár használata
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ca24ff60cd9ae5077c7f4bae0012fe1180d7e6d4
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821031"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="81d10-103">A numerikus könyvtár használata</span><span class="sxs-lookup"><span data-stu-id="81d10-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="81d10-104">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="81d10-104">Overview</span></span>

<span data-ttu-id="81d10-105">A numerikus könyvtár három összetevőből áll</span><span class="sxs-lookup"><span data-stu-id="81d10-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="81d10-106">**Alapszintű egész aritmetika** egész számokkal és összehasonlító értékekkel</span><span class="sxs-lookup"><span data-stu-id="81d10-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="81d10-107">Az alapszintű funkciókra épülő **magas szintű egész funkciók** ; többek között a szorzás, a osztás, az inverzió stb.  aláírt és aláíratlan egész számok esetén.</span><span class="sxs-lookup"><span data-stu-id="81d10-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="81d10-108">**Rögzített szintű aritmetikai funkciók** rögzített pontú inicializálással, hozzáadással, szorzással, kölcsönös, polinom értékeléssel és méréssel.</span><span class="sxs-lookup"><span data-stu-id="81d10-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="81d10-109">Ezen összetevők mindegyike egyetlen `open` utasítás használatával érhető el:</span><span class="sxs-lookup"><span data-stu-id="81d10-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="81d10-110">Típusok</span><span class="sxs-lookup"><span data-stu-id="81d10-110">Types</span></span>

<span data-ttu-id="81d10-111">A numerikus könyvtár a következő típusokat támogatja</span><span class="sxs-lookup"><span data-stu-id="81d10-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="81d10-112">**`LittleEndian`** : egy qubit tömb `qArr : Qubit[]`, amely egy egész számot jelöl, amelyben `qArr[0]` a legkevésbé jelentős bitet jelzi.</span><span class="sxs-lookup"><span data-stu-id="81d10-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="81d10-113">**`SignedLittleEndian`** : ugyanaz, mint `LittleEndian`, kivéve, hogy a két kiegészítésben tárolt, aláírt egész számot jelöli.</span><span class="sxs-lookup"><span data-stu-id="81d10-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="81d10-114">**`FixedPoint`** : egy qubit tömbből álló valós számot jelöl, `qArr2 : Qubit[]` és egy bináris pont `pos`, amely a bináris pont bal oldalán lévő bináris számjegyek számát számolja.</span><span class="sxs-lookup"><span data-stu-id="81d10-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="81d10-115">a `qArr2` tárolása ugyanúgy történik, mint `SignedLittleEndian`.</span><span class="sxs-lookup"><span data-stu-id="81d10-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="81d10-116">Műveletek</span><span class="sxs-lookup"><span data-stu-id="81d10-116">Operations</span></span>

<span data-ttu-id="81d10-117">A fenti három típus mindegyikéhez számos művelet érhető el:</span><span class="sxs-lookup"><span data-stu-id="81d10-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="81d10-118">Mellett</span><span class="sxs-lookup"><span data-stu-id="81d10-118">Addition</span></span>
    - <span data-ttu-id="81d10-119">Összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="81d10-119">Comparison</span></span>
    - <span data-ttu-id="81d10-120">Szorzás</span><span class="sxs-lookup"><span data-stu-id="81d10-120">Multiplication</span></span>
    - <span data-ttu-id="81d10-121">Négyszögesítése</span><span class="sxs-lookup"><span data-stu-id="81d10-121">Squaring</span></span>
    - <span data-ttu-id="81d10-122">Osztás (a maradéktal)</span><span class="sxs-lookup"><span data-stu-id="81d10-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="81d10-123">Mellett</span><span class="sxs-lookup"><span data-stu-id="81d10-123">Addition</span></span>
    - <span data-ttu-id="81d10-124">Összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="81d10-124">Comparison</span></span>
    - <span data-ttu-id="81d10-125">A többverziós adattárház 2</span><span class="sxs-lookup"><span data-stu-id="81d10-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="81d10-126">Szorzás</span><span class="sxs-lookup"><span data-stu-id="81d10-126">Multiplication</span></span>
    - <span data-ttu-id="81d10-127">Négyszögesítése</span><span class="sxs-lookup"><span data-stu-id="81d10-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="81d10-128">Előkészítés/inicializálás klasszikus értékekre</span><span class="sxs-lookup"><span data-stu-id="81d10-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="81d10-129">Hozzáadás (klasszikus állandó vagy más kvantum rögzített pont)</span><span class="sxs-lookup"><span data-stu-id="81d10-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="81d10-130">Összehasonlítás</span><span class="sxs-lookup"><span data-stu-id="81d10-130">Comparison</span></span>
    - <span data-ttu-id="81d10-131">Szorzás</span><span class="sxs-lookup"><span data-stu-id="81d10-131">Multiplication</span></span>
    - <span data-ttu-id="81d10-132">Négyszögesítése</span><span class="sxs-lookup"><span data-stu-id="81d10-132">Squaring</span></span>
    - <span data-ttu-id="81d10-133">Többfunkciós kiértékelés a páros és páratlan függvények esetében</span><span class="sxs-lookup"><span data-stu-id="81d10-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="81d10-134">Kölcsönös (1/x)</span><span class="sxs-lookup"><span data-stu-id="81d10-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="81d10-135">Mérés (klasszikus dupla)</span><span class="sxs-lookup"><span data-stu-id="81d10-135">Measurement (classical Double)</span></span>

<span data-ttu-id="81d10-136">Az egyes műveletekkel kapcsolatos további információkért és részletes dokumentációért tekintse meg a Q # Library dokumentációs dokumentumait a következő címen: [docs.microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="81d10-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="81d10-137">Minta: egész szám hozzáadása</span><span class="sxs-lookup"><span data-stu-id="81d10-137">Sample: Integer addition</span></span>

<span data-ttu-id="81d10-138">Alapszintű példaként vegye fontolóra a $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ értéket, amely egy n-qubit egész $x $ és egy n-vagy (n + 1) értékű művelet, amely a qubit regisztrálja $y $ bemenetként, amely az utóbbi, amelynek a összege a $ (x + y) $-ra van leképezve.</span><span class="sxs-lookup"><span data-stu-id="81d10-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="81d10-139">Vegye figyelembe, hogy az összeg számítása $2 ^ n $, ha $y $ egy $n $ bites regisztrációban van tárolva.</span><span class="sxs-lookup"><span data-stu-id="81d10-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="81d10-140">A Quantum Development Kit használatával ez a művelet a következőképpen alkalmazható:</span><span class="sxs-lookup"><span data-stu-id="81d10-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="81d10-141">Minta: simított függvények kiértékelése</span><span class="sxs-lookup"><span data-stu-id="81d10-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="81d10-142">Ha olyan simított függvényeket szeretne kiértékelni, mint például a $ \sin (x) $ a kvantum-számítógépen, ahol a $x $ a Quantum `FixedPoint` száma, a Quantum Development Kit numerikus könyvtára biztosítja az operatív `EvaluatePolynomialFxP` és `Evaluate[Even/Odd]PolynomialFxP`.</span><span class="sxs-lookup"><span data-stu-id="81d10-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="81d10-143">Az első, `EvaluatePolynomialFxP`lehetővé teszi, hogy kiértékelje a "$ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, ahol $d $ a *mértéket*.</span><span class="sxs-lookup"><span data-stu-id="81d10-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="81d10-144">Ehhez minden szükséges, hogy a polinom-`[a_0,..., a_d]` (típusú `Double[]`), a bemeneti `x : FixedPoint` és a kimeneti `y : FixedPoint` (kezdetben nulla):</span><span class="sxs-lookup"><span data-stu-id="81d10-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="81d10-145">Az eredmény, $P (x) = 1 + 2x $, `yFxP`lesz tárolva.</span><span class="sxs-lookup"><span data-stu-id="81d10-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="81d10-146">A második, `EvaluateEvenPolynomialFxP`és a harmadik `EvaluateOddPolynomialFxP`a páros és páratlan függvények esetében is specializált.</span><span class="sxs-lookup"><span data-stu-id="81d10-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="81d10-147">Ez a páros/páratlan függvény esetében $f (x) $ és $ $ P_ {even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, a $ $ $f (x) $ megközelítő értéke $P _ {even} (x) $ vagy $P _ {odd} (x): = x\cdot P_ {even} (x) $, ill.</span><span class="sxs-lookup"><span data-stu-id="81d10-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="81d10-148">A Q #-ban ez a két eset a következőképpen kezelhető:</span><span class="sxs-lookup"><span data-stu-id="81d10-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="81d10-149">amely kiértékeli $P _ {even} (x) = 1 + 2x ^ 2 $ értéket, és</span><span class="sxs-lookup"><span data-stu-id="81d10-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="81d10-150">amely kiértékeli $P _ {odd} (x) = x + 2x ^ 3 $ értéket.</span><span class="sxs-lookup"><span data-stu-id="81d10-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="81d10-151">További példák</span><span class="sxs-lookup"><span data-stu-id="81d10-151">More samples</span></span>

<span data-ttu-id="81d10-152">További mintákat a [fő minták tárházában](https://github.com/Microsoft/Quantum)talál.</span><span class="sxs-lookup"><span data-stu-id="81d10-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="81d10-153">Első lépésként klónozott a tárházat, és nyissa meg a `Numerics` almappát:</span><span class="sxs-lookup"><span data-stu-id="81d10-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="81d10-154">Ezután `cd` az egyik minta mappájába, és futtassa a mintát a használatával</span><span class="sxs-lookup"><span data-stu-id="81d10-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
