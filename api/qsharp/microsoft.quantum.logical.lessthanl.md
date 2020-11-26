---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197721"
---
# <a name="lessthanl-function"></a><span data-ttu-id="2f339-102">LessThanL függvény</span><span class="sxs-lookup"><span data-stu-id="2f339-102">LessThanL function</span></span>

<span data-ttu-id="2f339-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2f339-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2f339-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f339-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f339-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="2f339-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2f339-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2f339-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2f339-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2f339-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2f339-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="2f339-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2f339-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2f339-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2f339-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="2f339-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2f339-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f339-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f339-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan kisebb `b` .</span><span class="sxs-lookup"><span data-stu-id="2f339-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f339-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2f339-113">Remarks</span></span>

<span data-ttu-id="2f339-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="2f339-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```