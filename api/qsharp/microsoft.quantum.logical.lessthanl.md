---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709958"
---
# <a name="lessthanl-function"></a><span data-ttu-id="e5b10-102">LessThanL függvény</span><span class="sxs-lookup"><span data-stu-id="e5b10-102">LessThanL function</span></span>

<span data-ttu-id="e5b10-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e5b10-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e5b10-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5b10-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5b10-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="e5b10-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e5b10-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e5b10-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e5b10-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e5b10-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e5b10-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="e5b10-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e5b10-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e5b10-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e5b10-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="e5b10-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e5b10-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e5b10-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e5b10-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan kisebb `b` .</span><span class="sxs-lookup"><span data-stu-id="e5b10-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5b10-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e5b10-113">Remarks</span></span>

<span data-ttu-id="e5b10-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="e5b10-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```