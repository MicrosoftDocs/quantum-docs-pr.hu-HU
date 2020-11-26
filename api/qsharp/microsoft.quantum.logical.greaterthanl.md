---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197976"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="b934f-102">GreaterThanL függvény</span><span class="sxs-lookup"><span data-stu-id="b934f-102">GreaterThanL function</span></span>

<span data-ttu-id="b934f-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b934f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b934f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b934f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b934f-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="b934f-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b934f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b934f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b934f-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b934f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b934f-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="b934f-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b934f-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b934f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b934f-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="b934f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b934f-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b934f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b934f-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="b934f-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b934f-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b934f-113">Remarks</span></span>

<span data-ttu-id="b934f-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="b934f-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```