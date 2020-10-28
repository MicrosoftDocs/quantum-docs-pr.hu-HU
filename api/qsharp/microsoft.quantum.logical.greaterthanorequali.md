---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723500"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="26a4b-102">GreaterThanOrEqualI függvény</span><span class="sxs-lookup"><span data-stu-id="26a4b-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="26a4b-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="26a4b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="26a4b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26a4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26a4b-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb vagy egyenlő, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="26a4b-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="26a4b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="26a4b-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="26a4b-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26a4b-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26a4b-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="26a4b-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="26a4b-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26a4b-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26a4b-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="26a4b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="26a4b-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26a4b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26a4b-112">`true` Ha és csak akkor, ha `a` nagyobb vagy egyenlő, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="26a4b-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26a4b-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="26a4b-113">Remarks</span></span>

<span data-ttu-id="26a4b-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="26a4b-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```