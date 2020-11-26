---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197789"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="0fada-102">GreaterThanOrEqualI függvény</span><span class="sxs-lookup"><span data-stu-id="0fada-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="0fada-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0fada-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0fada-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0fada-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0fada-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="0fada-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="0fada-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0fada-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0fada-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fada-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0fada-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="0fada-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="0fada-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fada-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0fada-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="0fada-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0fada-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0fada-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0fada-112">`true` Ha és csak akkor, ha `a` nagyobb vagy egyenlő, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="0fada-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0fada-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0fada-113">Remarks</span></span>

<span data-ttu-id="0fada-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="0fada-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```