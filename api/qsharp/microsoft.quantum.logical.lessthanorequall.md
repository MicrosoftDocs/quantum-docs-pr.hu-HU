---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197601"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="193f7-102">LessThanOrEqualL függvény</span><span class="sxs-lookup"><span data-stu-id="193f7-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="193f7-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="193f7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="193f7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="193f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="193f7-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="193f7-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="193f7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="193f7-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="193f7-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="193f7-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="193f7-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="193f7-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="193f7-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="193f7-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="193f7-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="193f7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="193f7-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="193f7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="193f7-112">`true` Ha és csak akkor, ha `a` kisebb vagy egyenlő, `b` mint.</span><span class="sxs-lookup"><span data-stu-id="193f7-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="193f7-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="193f7-113">Remarks</span></span>

<span data-ttu-id="193f7-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="193f7-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```