---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725222"
---
# <a name="decomposedon-function"></a><span data-ttu-id="4fcb7-102">DecomposedOn függvény</span><span class="sxs-lookup"><span data-stu-id="4fcb7-102">DecomposedOn function</span></span>

<span data-ttu-id="4fcb7-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4fcb7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4fcb7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fcb7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fcb7-105">Egy változó kibontása egy változón</span><span class="sxs-lookup"><span data-stu-id="4fcb7-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="4fcb7-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4fcb7-106">Description</span></span>

<span data-ttu-id="4fcb7-107">Adott egy permutációs $ \pi $ ( `perm` ) és egy index $i $ ( `index` ), ez a módszer három permutációt ad vissza ((\ pi_l, \ pi_r), \pi ') $, hogy a $ \ pi_l $ és a $ \ pi_r $ lemezképek ne változtassák meg a BITS-t a $i $ és a $ \pi ' $ értéknél nem módosítható bit $i $ értékkel az elemekben.</span><span class="sxs-lookup"><span data-stu-id="4fcb7-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="4fcb7-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4fcb7-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="4fcb7-109">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4fcb7-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="4fcb7-110">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fcb7-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="4fcb7-111">Kimenet: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="4fcb7-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

