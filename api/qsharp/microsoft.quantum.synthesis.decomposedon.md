---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855527"
---
# <a name="decomposedon-function"></a><span data-ttu-id="a4e9e-102">DecomposedOn függvény</span><span class="sxs-lookup"><span data-stu-id="a4e9e-102">DecomposedOn function</span></span>

<span data-ttu-id="a4e9e-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a4e9e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a4e9e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4e9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4e9e-105">Egy változó kibontása egy változón</span><span class="sxs-lookup"><span data-stu-id="a4e9e-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="a4e9e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a4e9e-106">Description</span></span>

<span data-ttu-id="a4e9e-107">Adott egy permutációs $ \pi $ ( `perm` ) és egy index $i $ ( `index` ), ez a módszer három permutációt ad vissza ((\ pi_l, \ pi_r), \pi ') $, hogy a $ \ pi_l $ és a $ \ pi_r $ lemezképek ne változtassák meg a BITS-t a $i $ és a $ \pi ' $ értéknél nem módosítható bit $i $ értékkel az elemekben.</span><span class="sxs-lookup"><span data-stu-id="a4e9e-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="a4e9e-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a4e9e-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="a4e9e-109">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a4e9e-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="a4e9e-110">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4e9e-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="a4e9e-111">Kimenet: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="a4e9e-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="a4e9e-112">Példa</span><span class="sxs-lookup"><span data-stu-id="a4e9e-112">Example</span></span>

<span data-ttu-id="a4e9e-113">Tegyük fel, hogy a bemenet a következők egyike: perm = [0, 2, 3, 5, 7, 1, 4, 6] és index = 0, ez a függvény három permutációt számít ki az alábbi táblázat alapján, amely felsorolja az a `perm` csoport és a D csoport képein belüli bináris jelölésű permutációt.  Az oszlopok felsorolják a bit indexeket.</span><span class="sxs-lookup"><span data-stu-id="a4e9e-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="a4e9e-114">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="a4e9e-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="a4e9e-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-115">2 1 0</span></span> | <span data-ttu-id="a4e9e-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-116">2 1 0</span></span> | <span data-ttu-id="a4e9e-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-117">2 1 0</span></span> | <span data-ttu-id="a4e9e-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="a4e9e-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-119">0 0 0</span></span> |       |       | <span data-ttu-id="a4e9e-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-120">0 0 0</span></span> | <span data-ttu-id="a4e9e-121">0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-121">0</span></span>
| <span data-ttu-id="a4e9e-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-122">0 0 1</span></span> |       |       | <span data-ttu-id="a4e9e-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-123">0 1 0</span></span> | <span data-ttu-id="a4e9e-124">2</span><span class="sxs-lookup"><span data-stu-id="a4e9e-124">2</span></span>
| <span data-ttu-id="a4e9e-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-125">0 1 0</span></span> |       |       | <span data-ttu-id="a4e9e-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-126">0 1 1</span></span> | <span data-ttu-id="a4e9e-127">3</span><span class="sxs-lookup"><span data-stu-id="a4e9e-127">3</span></span>
| <span data-ttu-id="a4e9e-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-128">0 1 1</span></span> |       |       | <span data-ttu-id="a4e9e-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-129">1 0 1</span></span> | <span data-ttu-id="a4e9e-130">5</span><span class="sxs-lookup"><span data-stu-id="a4e9e-130">5</span></span>
| <span data-ttu-id="a4e9e-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-131">1 0 0</span></span> |       |       | <span data-ttu-id="a4e9e-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-132">1 1 1</span></span> | <span data-ttu-id="a4e9e-133">7</span><span class="sxs-lookup"><span data-stu-id="a4e9e-133">7</span></span>
| <span data-ttu-id="a4e9e-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-134">1 0 1</span></span> |       |       | <span data-ttu-id="a4e9e-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-135">0 0 1</span></span> | <span data-ttu-id="a4e9e-136">1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-136">1</span></span>
| <span data-ttu-id="a4e9e-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-137">1 1 0</span></span> |       |       | <span data-ttu-id="a4e9e-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-138">1 0 0</span></span> | <span data-ttu-id="a4e9e-139">4</span><span class="sxs-lookup"><span data-stu-id="a4e9e-139">4</span></span>
| <span data-ttu-id="a4e9e-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-140">1 1 1</span></span> |       |       | <span data-ttu-id="a4e9e-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-141">1 1 0</span></span> | <span data-ttu-id="a4e9e-142">6</span><span class="sxs-lookup"><span data-stu-id="a4e9e-142">6</span></span>

<span data-ttu-id="a4e9e-143">Az indexek összes olyan értéke, amely nem egyenlő a 0 értékkel (= index), az A-tól B-ig és D és C között lesz átmásolva.</span><span class="sxs-lookup"><span data-stu-id="a4e9e-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="a4e9e-144">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="a4e9e-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="a4e9e-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-145">2 1 0</span></span> | <span data-ttu-id="a4e9e-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-146">2 1 0</span></span> | <span data-ttu-id="a4e9e-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-147">2 1 0</span></span> | <span data-ttu-id="a4e9e-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="a4e9e-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-149">0 0 0</span></span> | <span data-ttu-id="a4e9e-150">0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-150">0 0</span></span>   | <span data-ttu-id="a4e9e-151">0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-151">0 0</span></span>   | <span data-ttu-id="a4e9e-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-152">0 0 0</span></span> |
| <span data-ttu-id="a4e9e-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-153">0 0 1</span></span> | <span data-ttu-id="a4e9e-154">0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-154">0 0</span></span>   | <span data-ttu-id="a4e9e-155">0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-155">0 1</span></span>   | <span data-ttu-id="a4e9e-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-156">0 1 0</span></span> |
| <span data-ttu-id="a4e9e-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-157">0 1 0</span></span> | <span data-ttu-id="a4e9e-158">0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-158">0 1</span></span>   | <span data-ttu-id="a4e9e-159">0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-159">0 1</span></span>   | <span data-ttu-id="a4e9e-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-160">0 1 1</span></span> |
| <span data-ttu-id="a4e9e-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-161">0 1 1</span></span> | <span data-ttu-id="a4e9e-162">0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-162">0 1</span></span>   | <span data-ttu-id="a4e9e-163">1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-163">1 0</span></span>   | <span data-ttu-id="a4e9e-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-164">1 0 1</span></span> |
| <span data-ttu-id="a4e9e-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-165">1 0 0</span></span> | <span data-ttu-id="a4e9e-166">1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-166">1 0</span></span>   | <span data-ttu-id="a4e9e-167">1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-167">1 1</span></span>   | <span data-ttu-id="a4e9e-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-168">1 1 1</span></span> |
| <span data-ttu-id="a4e9e-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-169">1 0 1</span></span> | <span data-ttu-id="a4e9e-170">1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-170">1 0</span></span>   | <span data-ttu-id="a4e9e-171">0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-171">0 0</span></span>   | <span data-ttu-id="a4e9e-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-172">0 0 1</span></span> |
| <span data-ttu-id="a4e9e-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-173">1 1 0</span></span> | <span data-ttu-id="a4e9e-174">1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-174">1 1</span></span>   | <span data-ttu-id="a4e9e-175">1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-175">1 0</span></span>   | <span data-ttu-id="a4e9e-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-176">1 0 0</span></span> |
| <span data-ttu-id="a4e9e-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-177">1 1 1</span></span> | <span data-ttu-id="a4e9e-178">1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-178">1 1</span></span>   | <span data-ttu-id="a4e9e-179">1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-179">1 1</span></span>   | <span data-ttu-id="a4e9e-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-180">1 1 0</span></span> |

<span data-ttu-id="a4e9e-181">A következő a 0 értéket helyezi el az első elemhez, amely üres indexszel rendelkezik a B blokkban található 0. oszlopban, majd egy 1 kerül a B helyére, ahol az előtag megegyezik (az első esetben a másik sor az indexekkel 0 0).</span><span class="sxs-lookup"><span data-stu-id="a4e9e-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="a4e9e-182">Ezt követően a rendszer egy 1 értéket ad hozzá a C blokkban található ugyanabban a sorban, majd a C blokkban található megfelelő előtaghoz a 0 értéket.  Ez a folyamat ismétlődik, amíg az összes index be nem került a 0. oszlopba a B és C tömbben.</span><span class="sxs-lookup"><span data-stu-id="a4e9e-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="a4e9e-183">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="a4e9e-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="a4e9e-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-184">2 1 0</span></span> | <span data-ttu-id="a4e9e-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-185">2 1 0</span></span> | <span data-ttu-id="a4e9e-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-186">2 1 0</span></span> | <span data-ttu-id="a4e9e-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="a4e9e-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-188">0 0 0</span></span> | <span data-ttu-id="a4e9e-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-189">0 0 0</span></span> | <span data-ttu-id="a4e9e-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-190">0 0 0</span></span> | <span data-ttu-id="a4e9e-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-191">0 0 0</span></span> |
| <span data-ttu-id="a4e9e-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-192">0 0 1</span></span> | <span data-ttu-id="a4e9e-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-193">0 0 1</span></span> | <span data-ttu-id="a4e9e-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-194">0 1 1</span></span> | <span data-ttu-id="a4e9e-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-195">0 1 0</span></span> |
| <span data-ttu-id="a4e9e-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-196">0 1 0</span></span> | <span data-ttu-id="a4e9e-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-197">0 1 0</span></span> | <span data-ttu-id="a4e9e-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-198">0 1 0</span></span> | <span data-ttu-id="a4e9e-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-199">0 1 1</span></span> |
| <span data-ttu-id="a4e9e-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-200">0 1 1</span></span> | <span data-ttu-id="a4e9e-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-201">0 1 1</span></span> | <span data-ttu-id="a4e9e-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-202">1 0 1</span></span> | <span data-ttu-id="a4e9e-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-203">1 0 1</span></span> |
| <span data-ttu-id="a4e9e-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-204">1 0 0</span></span> | <span data-ttu-id="a4e9e-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-205">1 0 0</span></span> | <span data-ttu-id="a4e9e-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-206">1 1 0</span></span> | <span data-ttu-id="a4e9e-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-207">1 1 1</span></span> |
| <span data-ttu-id="a4e9e-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-208">1 0 1</span></span> | <span data-ttu-id="a4e9e-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-209">1 0 1</span></span> | <span data-ttu-id="a4e9e-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-210">0 0 1</span></span> | <span data-ttu-id="a4e9e-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-211">0 0 1</span></span> |
| <span data-ttu-id="a4e9e-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-212">1 1 0</span></span> | <span data-ttu-id="a4e9e-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-213">1 1 0</span></span> | <span data-ttu-id="a4e9e-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-214">1 0 0</span></span> | <span data-ttu-id="a4e9e-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-215">1 0 0</span></span> |
| <span data-ttu-id="a4e9e-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-216">1 1 1</span></span> | <span data-ttu-id="a4e9e-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-217">1 1 1</span></span> | <span data-ttu-id="a4e9e-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="a4e9e-218">1 1 1</span></span> | <span data-ttu-id="a4e9e-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="a4e9e-219">1 1 0</span></span> |

<span data-ttu-id="a4e9e-220">A táblázatból három új permutációt is olvashat:</span><span class="sxs-lookup"><span data-stu-id="a4e9e-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="a4e9e-221">$ \ pi_l $, a "B" kép elemeivel (bal)</span><span class="sxs-lookup"><span data-stu-id="a4e9e-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="a4e9e-222">$ \ pi_r $, elemek: D, C (jobb) kép</span><span class="sxs-lookup"><span data-stu-id="a4e9e-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="a4e9e-223">$ \pi ' $ a B elemekkel, C-ban található képek (hátralévő)</span><span class="sxs-lookup"><span data-stu-id="a4e9e-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="a4e9e-224">Vegye figyelembe, hogy a tervezési bites értékek nem változnak a $ \ pi_l $ és a $ \ pi_r $ értékben az 1. és a 2. indexek esetében, és a 0 értéknél a (z) $ \ pi_ $ értéke nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="a4e9e-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="a4e9e-225">Azt is vegye figyelembe, hogy a $ \ pi_l $ és $ \ pi_r $ értéknek saját-inverznek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a4e9e-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="a4e9e-226">A származtatott és visszaadott permutációk a következők: Left = [0, 1, 2, 3, 4, 5, 6, 7] jobb = [0, 1, 3, 2, 4, 5, 7, 6] fennmaradó = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="a4e9e-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>