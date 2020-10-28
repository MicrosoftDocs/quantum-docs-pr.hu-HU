---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709945"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="67a09-102">LessThanOrEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="67a09-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="67a09-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="67a09-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="67a09-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67a09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67a09-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="67a09-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="67a09-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="67a09-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="67a09-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67a09-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67a09-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="67a09-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="67a09-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67a09-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67a09-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="67a09-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="67a09-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="67a09-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="67a09-112">`true` Ha és csak akkor, ha `a` kisebb vagy egyenlő, `b` mint.</span><span class="sxs-lookup"><span data-stu-id="67a09-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="67a09-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="67a09-113">Remarks</span></span>

<span data-ttu-id="67a09-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="67a09-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```