---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197755"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="13f47-102">GreaterThanOrEqualL függvény</span><span class="sxs-lookup"><span data-stu-id="13f47-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="13f47-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="13f47-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="13f47-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13f47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13f47-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="13f47-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="13f47-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="13f47-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="13f47-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="13f47-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="13f47-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="13f47-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="13f47-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="13f47-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="13f47-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="13f47-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="13f47-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="13f47-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="13f47-112">`true` Ha és csak akkor, ha `a` nagyobb vagy egyenlő, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="13f47-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="13f47-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="13f47-113">Remarks</span></span>

<span data-ttu-id="13f47-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="13f47-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```