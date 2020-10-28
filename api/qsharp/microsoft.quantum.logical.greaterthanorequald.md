---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711373"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="2fb48-102">GreaterThanOrEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="2fb48-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="2fb48-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2fb48-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2fb48-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fb48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fb48-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="2fb48-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="2fb48-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2fb48-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="2fb48-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fb48-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fb48-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="2fb48-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="2fb48-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fb48-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fb48-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="2fb48-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2fb48-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2fb48-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2fb48-112">`true` Ha és csak akkor, ha `a` nagyobb vagy egyenlő, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="2fb48-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fb48-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2fb48-113">Remarks</span></span>

<span data-ttu-id="2fb48-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="2fb48-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```