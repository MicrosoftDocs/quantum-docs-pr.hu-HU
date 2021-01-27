---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849200"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="8e2bf-102">GreaterThanL függvény</span><span class="sxs-lookup"><span data-stu-id="8e2bf-102">GreaterThanL function</span></span>

<span data-ttu-id="8e2bf-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8e2bf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8e2bf-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e2bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e2bf-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="8e2bf-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="8e2bf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8e2bf-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="8e2bf-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8e2bf-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8e2bf-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="8e2bf-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="8e2bf-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8e2bf-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8e2bf-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="8e2bf-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8e2bf-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8e2bf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8e2bf-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="8e2bf-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e2bf-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8e2bf-113">Remarks</span></span>

<span data-ttu-id="8e2bf-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="8e2bf-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```