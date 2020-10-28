---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709986"
---
# <a name="greaterthani-function"></a><span data-ttu-id="34ba5-102">GreaterThanI függvény</span><span class="sxs-lookup"><span data-stu-id="34ba5-102">GreaterThanI function</span></span>

<span data-ttu-id="34ba5-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="34ba5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="34ba5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34ba5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34ba5-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="34ba5-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="34ba5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="34ba5-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="34ba5-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34ba5-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34ba5-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="34ba5-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="34ba5-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34ba5-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34ba5-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="34ba5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="34ba5-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34ba5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34ba5-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="34ba5-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="34ba5-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="34ba5-113">Remarks</span></span>

<span data-ttu-id="34ba5-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="34ba5-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```