---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722646"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="d3c5e-102">GreaterThanOrEqualL függvény</span><span class="sxs-lookup"><span data-stu-id="d3c5e-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="d3c5e-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d3c5e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d3c5e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3c5e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3c5e-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="d3c5e-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d3c5e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d3c5e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d3c5e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d3c5e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d3c5e-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="d3c5e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d3c5e-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d3c5e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d3c5e-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="d3c5e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d3c5e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d3c5e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d3c5e-112">`true` Ha és csak akkor, ha `a` nagyobb vagy egyenlő, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="d3c5e-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3c5e-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d3c5e-113">Remarks</span></span>

<span data-ttu-id="d3c5e-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="d3c5e-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```