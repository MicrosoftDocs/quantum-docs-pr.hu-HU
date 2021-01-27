---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 9438fc05b4ccb041b087f9cfeb30ac0c8cfcabd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815603"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="ee7e1-102">LessThanOrEqualI függvény</span><span class="sxs-lookup"><span data-stu-id="ee7e1-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="ee7e1-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ee7e1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ee7e1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee7e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee7e1-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="ee7e1-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="ee7e1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ee7e1-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ee7e1-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee7e1-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee7e1-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="ee7e1-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="ee7e1-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee7e1-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee7e1-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="ee7e1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ee7e1-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ee7e1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ee7e1-112">`true` Ha és csak akkor, ha `a` kisebb vagy egyenlő, `b` mint.</span><span class="sxs-lookup"><span data-stu-id="ee7e1-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee7e1-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ee7e1-113">Remarks</span></span>

<span data-ttu-id="ee7e1-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="ee7e1-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```