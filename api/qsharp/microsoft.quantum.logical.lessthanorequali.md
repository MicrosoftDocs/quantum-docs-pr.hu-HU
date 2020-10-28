---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709931"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="e58d8-102">LessThanOrEqualI függvény</span><span class="sxs-lookup"><span data-stu-id="e58d8-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="e58d8-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e58d8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e58d8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e58d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e58d8-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="e58d8-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="e58d8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e58d8-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e58d8-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e58d8-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e58d8-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="e58d8-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="e58d8-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e58d8-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e58d8-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="e58d8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e58d8-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e58d8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e58d8-112">`true` Ha és csak akkor, ha `a` kisebb vagy egyenlő, `b` mint.</span><span class="sxs-lookup"><span data-stu-id="e58d8-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e58d8-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e58d8-113">Remarks</span></span>

<span data-ttu-id="e58d8-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="e58d8-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```